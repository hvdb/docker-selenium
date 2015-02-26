# Selenium Grid Node - Chrome

Selenium Node configured to run Google Chrome.
This one has 10 instances of chrome and 10 sessions are allowed.

## Dockerfile

[`selenium/node-chrome` Dockerfile](https://github.com/SeleniumHQ/docker-selenium/blob/master/NodeChrome/Dockerfile)

## How to use this image

First, you will need a Selenium Grid Hub that the Node will connect to.
You need to set the max session to the number you want.
The default is only 5.
This means that only 5 webdriver session can be started == 5 tests.
So if you are running a big test set (or use this chrome node) you need to increase this number.

```
$ docker run -d -P --name selenium-hub -e  hvdb/docker-selenium-hub -
```

Once the hub is up and running will want to launch nodes that can run tests. You can run as many nodes as you wish.

```
$ docker run -d --link selenium-hub:hub hvdb/docker-node-chrome-10
```

## What is Selenium?
_Selenium automates browsers._ That's it! What you do with that power is entirely up to you. Primarily, it is for automating web applications for testing purposes, but is certainly not limited to just that. Boring web-based administration tasks can (and should!) also be automated as well.

Selenium has the support of some of the largest browser vendors who have taken (or are taking) steps to make Selenium a native part of their browser. It is also the core technology in countless other browser automation tools, APIs and frameworks.

See the Selenium [site](http://docs.seleniumhq.org/) for documation on usage within your test code.

## License

View [license information](https://code.google.com/p/selenium/source/browse/COPYING) for the software contained in this image.

