## Research afternoon

- important to understand how the server and client relate to each other, and the roles that they'll play in your application the **Architecting** section explores some of those ideas. 
- Node also comes with its own features and approaches that will be unfamiliar if you've only written client-side code before the **Engineering** section examines a few of the key ones. 

- One of the best things about Node is the ease with which you can incorporate other developers' code into your own projects, by using node modules

- you can't just open your back-end code in a browser – you have to deploy it somewhere. The **Deploying** section looks at some of the places you might deploy your code, and some of the things you'll need to bear in mind if your code's going to run in different environments.


### Topic 1: Architecting

- *Separation of concerns*: 
  - What kind of tasks are normally handled in the back end
  - which are more usually handled in the front end? 
  - Why?

- *Client side vs server side*: 
  - Some tasks – such as **templating** and **validation** – can be implemented on either the client or the server. 
  - What are the pros and cons of running code on the client, rather than the server, or the other way around?

- *Alternative back-end technologies*: 
  - Which other technologies (programming languages and servers) might be used instead of Node on the back end? 
  - What are some of the pros and cons of using Node in your stack, rather than one of those alternatives?

- *Writing for different environments*: 
  - Why might you have to write JavaScript differently if it's going to run in the browser, rather than in Node?
  - How can we check if Javascript functions are ES5 or ES6? How can we find out what browsers will run them
  - What tools can help make it so you don't have to do that - what is **babel** and why would you use it?


### Topic 2: Engineering

- *Modules*: 
  - Why should you **modularise** your code? 
  - What are `require` and `module.exports`? 
  - Why can't you use them in the browser? 
  - How might you modularise client-side code - what does **webpack** do?

- *Asyncronous functions*: 
  - Why should you use asyncronous forms of functions wherever possible in Node? 
  - What are error-first callbacks, and why is it important to follow that pattern in your own code? 
  - Why should you avoid using `throw` in callbacks? 
  - When might you use the syncronous form of a function instead?

- *Input/output (the `fs` and `path` modules)*: 
  - What kind of tasks does the `fs` module enable you to perform that you wouldn't be able to in the browser? 
  - What are some of the issues of working with paths when accessing a file system? 
  - How does the `path` module help, and why should you use it instead of manually writing file paths as strings?

- *Working with URLs (the `url` and `querystring` modules)*: 
  - What is a `urlObject` and how is it structured?
  - Why is it important to be able to turn JavaScript objects into querystrings and back again?
  - Why is it a bad idea to build a query string manually from other strings (think about URL encoding and escape characters)?


### Topic 3: Deploying and NPM

- *Cloud platforms*: 
  - What is PaaS? 
  - Why is it useful to be able to deploy your code to a cloud platform, rather than running it locally? 
  - What services are there that can provide you with a platform for your code? [Heroku](http://www.heroku.com) is a good start, but try to find some others. 
  - Deploy a simple server to Heroku as a demo.

- *Environment variables*:
  - Why might some variables in your code need to change for different environments?
  - Why is it a bad idea to include those variables in a public repository?
  - What modules might you use to help manage environment variables? (Look at [env2](https://github.com/dwyl/env2) from our neighbours at DWYL.) If you can, write some sample code to show how it works.
  
 - *NPM*
   - What are some common scripts to have in your `package.json`
   - What is the difference between `package.json` and `package-lock.json`
   - What npm scripts to cloud platforms like heroku use?
 
