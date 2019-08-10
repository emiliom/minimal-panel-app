# Emilio's notes (8/9/2019)

I forked this repo from https://github.com/ericmjl/minimal-panel-app. The author posted instructions at https://ericmjl.github.io/blog/2019/7/26/pyviz-panel-apps/. The only thing I changed was https://github.com/emiliom/minimal-panel-app/blob/master/Procfile, to rename the Heroku app to a new unique subdomain: https://panel-app-sample1.herokuapp.com. Everything below is from the original README.md.


# minimal-panel-app

A pedagogical implementation of panel apps served up on a remote machine.

See the full app [here](http://minimal-panel-app.herokuapp.com/minimal-panel).

## why this project exists

I spent a day figuring out how to make this happen at work,
and decided to spend an evening consolidating my knowledge.

## "how to use"


## anything else interesting?

### iPad development

The first version of the app was coded up entirely on an iPad,
using a combination of [blink](http://blink.sh)
[Juno](jhttp://juno.sh),
and `nano` on my home remote server
(which is nothing more than a converted gaming tower).

Web app development in Python is now doable
and we can use modern tablets as a thin client!

### memory usage

Deploying the HIV drug resistance model to Heroku was challenging
because I had to watch out for memory and storage usage.
There are 8 models to make predictions on,
and loading all of them together causes memory overload
on Heroku's free tier.

I got around this by pickling the models individually,
and only loading them when needed.
I also minimized disk usage by using gzip
when pickling the files.
