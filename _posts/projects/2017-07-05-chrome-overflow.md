---
layout: post
title: "ChromeOverflow"
excerpt: "How we built a Google Chrome DevTools extension in 24 hours."
categories: projects
tags: [tech, project]
image:
    feature: chrome-overflow.png
share: true
---

[ChromeOverflow](https://github.com/risamaki/ChromeOverflow) is a Google Chrome DevTools extension that queries StackOverflow for all errors that come up while debugging a web page. Without ever having to conduct a search or even leave DevTools, developers can read StackOverflow posts and continue debugging. 

![](https://raw.githubusercontent.com/risamaki/ChromeOverflow/master/resources/images/2017-03-19%2012_20_19-Create%20a%20new%20fiddle%20-%20JSFiddle.png)

![](https://raw.githubusercontent.com/risamaki/ChromeOverflow/master/resources/images/2017-03-19%2012_20_49-Create%20a%20new%20fiddle%20-%20JSFiddle.png)

![](https://raw.githubusercontent.com/risamaki/ChromeOverflow/master/resources/images/2017-03-19%2012_21_37-Create%20a%20new%20fiddle%20-%20JSFiddle.png)

You can download the Chrome extension [here](https://github.com/risamaki/ChromeOverflow/raw/master/ChromeOverflow.crx). Follow [these instructions](https://stackoverflow.com/a/11879334/5759077) to get set up.

## Development
The extension was conceived and developed in its entirety in the span of 24 hours during **[nwHacks 2017](https://www.nwhacks.io/)** with four other developers. It was my first ever hackathon and I was very happy with what we built!

As far as tech goes, it was very vanilla. Bootstrap + jQuery, as well as [Showdown](https://github.com/showdownjs/showdown), a Markdown-to-HTML converter plugin.

## How the extension works
The extension injects an error listener which notifies the extension in DevTools when a window error occurs. Notifying is done via [Message Passing](https://developer.chrome.com/extensions/messaging). The error is displayed in the extension window.

Then, a search to StackOverflow with the error text is performed using jQuery AJAX. The results are passed to a render function that puts the results in a Bootstrap nested accordian to be interacted with by the user.

## Next Steps
If I pick this project up again and work on it further, there are three immediate priorities I would focus on:

* Implementing OAuth and remove the necessity of having to have an API key. Right now it's in plain text.
* Improving the algorithm to perform better searches using the terms provided in the browser errors. 
* Write tests and get a high code coverage

I believe that after accomplishing those three tasks, the extension would be good enough for end-user use and I'd publish it on the Chrome Extensions store. 