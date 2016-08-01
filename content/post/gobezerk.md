+++
date = "2016-08-01T15:35:28-04:00"
draft = false
title = "gobezerk"

+++

A Slack Bot that tells you if an intruder is at your computer using a leap motion device

  Uses *github.com/hybridgroup/gobot/platforms/leap* and *github.com/nlopes/slack* to send a slack bot message to a channel when someone is at your computer.  

  Code can be found on my github https://github.com/rafael-azevedo/goberzerk  

**General Setup**

This guide assumes you have Go language environment setup and you have a [leap motion](https://www.leapmotion.com/) device and software one your computer . If you do not please refer to this guide [here](https://golang.org/doc/install)

To setup a quick IDE for Go development use the guide [here](https://www.wolfe.id.au/2015/03/05/using-sublime-text-for-go-development/)
 
You will then need to get a slack api key you can create your own channel and have up to 10 bots per channel 

*  **Create a Slack Channel and Get an API key**
	* Go to Slack.com. Fill out an email and hit *Create New Team*
  	![New Slack](/images/newSlack.png)
	* Once in your slack account hit the drop down next to your user and select *Apps & Integration*
	![New Slack](/images/appIntegration.png)
	* Search and select *Bots*
	![New Slack](/images/newBot.png)
	* Hit *Add Configuration* and give your bot a unique name
	![New Slack](/images/addConfiguration.png)
	* Click *Add bot integration* to finish adding the integration and View settings to get its API key
	![New Slack](/images/botIntegration.png)  

* **Add the bot to a channel**

	Once you have an api key and bot created go to the channel you wish to notify with the bot and add it to the channel using the following command

	`/invite @<your_bot_name>`

*  **Configure Code**
	*  Clone repo to a directory  
	`git clone https://github.com/rafael-azevedo/goberzerk`
	*  Insert your api key for the slack bot in the following line  
	`api := slack.New("SLACK API KEY")`
	* Use the listchannels.go code to print out the channel IDs of the chat rooms. You will need the channel ID of the room you would like to send messages to  
	`go build -i listchannels.go` and run the binary 
	* Use the id in the goberzerk.go channel you want to message
	![New Slack](/images/listChannels.png)


* **Run Code**
	* Once you have placed the api key and channel id in goberzerk.go you can build and run the code 
	* Build the Code  
	`go build -i goberzerk.go`  
	`./goberzerk.go`
	![New Slack](/images/goberzerk.png)
	![New Slack](/images/slackUpdate.png)
