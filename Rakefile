task default: %w[test]

# For now, just make sure that Middleman at a base level can build the project
# Cucumber tests and support to be added soon.

task :test do
  ENV["environment"] = 'firefox'
  puts "Environment used in the run: "+ENV["environment"]
  puts "\nBuilding project..."
  try "middleman server &>/dev/null &"
  # try "cucumber"
end

# task :TravisTest do
#   ENV["environment"] = 'headless'
#   puts "Environment used in the run: "+ENV["environment"]
#   puts "\nBuilding project in Travis-CI..."
#   try "middleman server &>/dev/null &"
#   try "cucumber"
# end

task :deploy do
  puts "\nDeploying to GitHub Pages"
  try "middleman deploy"
end

namespace :travis do
  task :script do
    Rake::Task["TravisTest"].invoke
  end

  task :after_success do
    puts "\nRunning Travis Deployment"
    puts "\nSetting up Git access"
    try "echo ${GH_TOKEN} > ./.git/credentials"
    try "git config --global user.name ${GH_USER}"
    try "git config --global user.email ${GH_EMAIL}"
    try "git remote set-url origin \"https://${GH_TOKEN}@github.com/${GH_USER/brennx0r\.github\.io\""

    Rake::Task["deploy"].invoke
  end
end

## Helper so we fail as soon as a command fails.
def try(command)
  system command
  if $? != 0 then
    raise "Command: `#{command}` exited with code #{$?.exitstatus}"
  end
end