---
title: Adventures in Syntax Highlighting  - 
date: 2016-10-31
tags: middleman-syntax, rouge, middleman-rouge, css
---

### ... And other fun sources of creative cursing ;-)

*Disclaimer: I am not a front-end web developer.*

# Happy Halloween!

![via http://forums.realgm.com/boards/viewtopic.php?t=953774](/images/deathstar_pumpkin.jpg)


So, I thought I would give it a go tonight to try to fix the syntax highlighting for the blog. I had done a basic setup of ```middleman-syntax``` but it was not working correctly - no color-based highlighting on language, no styling, etc.

So, off to the Github README for ```middleman-syntax``` - should be easy enough to follow, yes?

Wrong.

It turns out, if you are referring to the basic instructions and you happen to have this setup in Middleman:

+ Middleman 4.0
+ Ruby 2.3.0

You'll get an error message after making the change in the attempt to start Middleman server.

I had to do quite a bit of digging, but it looks like this configuration worked well for me to get going:

_config.rb:_

```ruby
set :markdown_engine, :redcarpet
set :markdown, :fenced_code_blocks => true, :smartypants => true
activate :syntax, line_numbers: true, css_class: 'codehilite'
```

_$your_file.css:_ Include all the style for Rouge theme you need

Additionally, style as follows:

```css
.rouge-table { 
	background-color: #e6f3f7;
	max-width: 300px;
	font-size: 16px;
}

.rouge-code {
	width: 40%;
}

code {
	background-color: #e6f3f7;
	font-size: 18px;
	color: purple;
}
```

Things that did not work out well:  Attempting to use ```middleman-rouge``` instead of ```middleman-syntax``` for syntax highlighting. I changed the setup via the Github project instructions only to get an error that lends that it's inherantly incompatible with the version of Ruby I'm using. Looks like the gem hasn't been maintained in awhile either.

#### Bugs to sort out:

1. The code blocks do not allow for any wrapping. I have no idea how to fix this. You can see above that I attempted to set a ```max-width```, hoping that this might force wrapping, but alas - no dice. I also looked at some css that would provide wrapping, but they didn't work either.
1. If I set ```line_numbers: false``` either in ```config.rb``` or the in-line markdown blog files, the line numbers are unset (good) but all other styling is lost (watthecrap).


Front-end development work requires a ton of patience. I think this is good for me. Let's see where this takes me.

