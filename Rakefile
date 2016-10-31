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

task :TravisTest do
  ENV["environment"] = 'headless'
  puts "Environment used in the run: "+ENV["environment"]
  puts "\nBuilding project in Travis-CI..."
  try "middleman server &>/dev/null &"
  # try "cucumber"
end

task :after_success do
  puts "\nRunning Travis Deployment"
  puts "\nSetting up Git access"
  try "git clone git@github.com:brennx0r/brennx0r.github.io.git"
  try "git config user.name ${GH_USER}"
  try "git config user.email ${GH_EMAIL}"
  try "middleman deploy"
end


## Helper so we fail as soon as a command fails.
def try(command)
  system command
  if $? != 0 then
    raise "Command: `#{command}` exited with code #{$?.exitstatus}"
  end
end