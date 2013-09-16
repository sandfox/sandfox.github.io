---
layout: post
title: "NodeJS + Uubntu 5 Mins, GO!"
---


Lets assume you have a fresh install of ubuntu and all you have done is logged in (as a non-root user!)

	sudo apt-get update
	sudo apt-get install python-software-properties
	sudo add-apt-repository ppa:chris-lea/node.js
	sudo apt-get update
	sudo apt-get install nodejs npm nodejs-dev

This should be enough to install anything you want from [npm](http://npmjs.org/) (including c/c++ modules) and get any nodejs code written in running by simply typing `node myAwesomeCode.js`

A production system should probably have a bit more work and care applied than this!
