---
title: Blog Setup Using Middleman  - 
date: 2016-10-29
tags: middleman, first post, SVG, CSS
---

### Hello!
Welcome to the first post of my new blog! I am very excited to be entering the blogosphere again after a hiatus of many years (shoutout to LiveJournal and Blogspot!). I hope that you enjoy my writing.

If you stumbled onto this site and not sure who I am, let me introduce myself! My name is Brenna, and I am a Senior Build & Delivery Engineer by day, surly knitter/spinner/runner by night. I live in Seattle, WA with my partner Jeremy and our two pets - a long-haired chihuahua and a tabby cat.

I created this site using Middleman. Given that my work is mainly focused on Jenkins, configuration management tools (like Chef or Puppet), containerization and cloud deployment, so getting my feet wet with site generation was a fun, interesting, and challenging distraction.

Even though there are tons of blogs that explain how to get started using Middleman, I thought that I would share some of the details of what I did to get up and running. Please keep in mind that I know next to nothing about CSS or professional front-end development work in general. I am sure that you will find my tinkering with basic CSS to be amusing and not at all ground-breaking. ;-)

### In a Nutshell

#### Local Development

1. Install Middleman: <https://middlemanapp.com/basics/install/>
1. Install the middleman-blog gem
1. Create your new project:  `middleman init MY_BLOG_PROJECT_NAME --template=blog`
1. Look at some sites on "theme templates" and despair; decide to do simple CSS rather than a bunch of copy-pasta or bloated theme download.
1. Research some basic CSS and add some SVG
  * [Adding pretty Google fonts](https://knowledge.hubspot.com/articles/kcs_article/cos-general/how-do-i-add-google-fonts-to-my-new-landing-pages)
  * [Using SVG](https://css-tricks.com/using-svg/)
  * [About CSS floats](https://css-tricks.com/all-about-floats/)
1. Do all the development!
  * When doing local changes, make sure that Middleman live-reload is active (seems to be with 4.0 without additional modification for me so ¯\\_(ツ)_/¯)
  * Before doing the brunt of development work, bring up Middleman locally and make/see small, iterative changes for fast feedback:  `middleman server`
  * Middleman configuration settings are always available to you via  `http://127.0.0.1:4567/__middleman/config` as an added troubleshooting resource.


#### Deployment

Gotchas - If you are using Middleman 4.0, you will need to use 
 
``` ruby
'middleman-deploy', '~> 2.0.0.pre.alpha'
```

Otherwise, if you attempt to run middleman you'll get an error like the following:

```
Ilmatar:brendo-blog brennx0r$ middleman server
/Users/brennx0r/.rvm/gems/ruby-2.2.3/gems/middleman-core-4.1.10/lib/middleman-core/extensions.rb:96:in `load': Tried to activate old-style extension: deploy. They are no longer supported. (RuntimeError)
```

1. Create a CNAME in the root of the project
1. [Github Pages Considerations](https://pages.github.com/)
  * <https://help.github.com/articles/using-a-custom-domain-with-github-pages/>

  	 






