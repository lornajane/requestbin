# We have discontinued the publicly hosted version of RequestBin due to ongoing abuse that made it very difficult to keep the site up reliably. Please see instructions below for setting up your own self-hosted instance.

Originally Created by [Jeff Lindsay](http://progrium.com)

Upgraded to python3 by Scott Rogers <scottrogers@newrelic.com>


License
-------
MIT


Looking to self-host?
=====================

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

## Deploy your own instance using Heroku
Create a Heroku account if you haven't, then grab the RequestBin source using git:

`$ git clone git://github.com/Runscope/requestbin.git`

From the project directory, create a Heroku application:

```
$ cd requestbin
$ heroku create
```

This step will have several lines of output.  You care about these two:  
```
Creating app... done, ⬢ clueless-leader-37188
https://clueless-leader-37188.herokuapp.com/ | https://git.heroku.com/clueless-leader-37188.git
```
You need to pluck the application name in this example
*clueless-leader-37188*.  You will need the actual app name in several cases below.


Save the .git link above for a step below.

Add Heroku's redis addon.  Note: you will have to have a credit card on file with Heroku:

`$ heroku addons:add heroku-redis -a clueless-leader-37188`

Set an environment variable to indicate production:

`$ heroku config:set REALM=prod -a clueless-leader-37188`

Now just deploy via git:

`$ git push https://git.heroku.com/clueless-leader-37188.git master`

It will push to Heroku and give you a URL that your own private RequestBin will be running.


## Deploy your own instance using Docker

On the server/machine you want to host this, you'll first need a machine with
docker and docker-compose installed, then grab the RequestBin source using git:

`$ git clone git://github.com/Runscope/requestbin.git`

Go into the project directory and then build and start the containers

```
$ sudo docker-compose build
$ sudo docker-compose up -d
```

Your own private RequestBin will be running on this server.

`http://localhost:8000`

Contributors
------------
 * Barry Carlyon <barry@barrycarlyon.co.uk>
 * Jeff Lindsay <progrium@gmail.com>
