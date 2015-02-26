# Selenium Grid Hub

The Hub receives a test to be executed along with information on which browser and 'platform' where the test should be run. The hub will use this information and delegate to a node that can service those needs.
Changed the timeout to 300000 (5minutes)
Changed sessions to 100.
## Dockerfile

[`selenium/hub` Dockerfile](https://github.com/SeleniumHQ/docker-selenium/blob/master/Hub/Dockerfile)

## How to use this image

```
$ docker run -d -P --name selenium-hub hvdb/docker-selenium-hub
```

Note: You can optionally override default configuration settings using environment variables.
See the [Hub's Dockerfile](Dockerfile) to view the list of variables and their default values.

```
$ docker run -d -P --name selenium-hub  hvdb/docker-selenium-hub
```


Once the hub is up and running will want to launch nodes that can run tests. You can run as many nodes as you wish.

```
$ docker run -d --link selenium-hub:hub hvdb/docker-node-chrome-10
$ docker run -d --link selenium-hub:hub hvdb/docker-node-firefox-10
```

## What is Selenium?
_Selenium automates browsers._ That's it! What you do with that power is entirely up to you. Primarily, it is for automating web applications for testing purposes, but is certainly not limited to just that. Boring web-based administration tasks can (and should!) also be automated as well.

Selenium has the support of some of the largest browser vendors who have taken (or are taking) steps to make Selenium a native part of their browser. It is also the core technology in countless other browser automation tools, APIs and frameworks.

See the Selenium [site](http://docs.seleniumhq.org/) for documation on usage within your test code.

## License

View [license information](https://code.google.com/p/selenium/source/browse/COPYING) for the software contained in this image.
