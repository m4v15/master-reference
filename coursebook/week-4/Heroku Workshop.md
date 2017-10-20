# Deploying Node.js Apps on Heroku
***This Workshop assumes that you have a free Heroku account, and that you have Node.js and npm installed locally.***
****
## What is Heroku?
Heroku is a cloud platform as a service (PaaS) supporting several programming languages that is used as a web application deployment model. Heroku supports Ruby, Java, Node.js, Scala, Clojure, Python and PHP programming languages.
## Why is it better to use Heroku for deploying your app?
* #### **Service type: Pure PaaS**.

* #### **Ease of use:**  You can be up and running with an app continuously deployed from Github, for free, within minutes. Beautiful interface pared down to the bare essentials.

* #### **Performance and Value: Pretty good compared to the other PaaS solutions, but still far off from IaaS.**

* #### **Scalabilility: It really does not get easier than this. Adjust a slider (or have it scaled automatically) and handle all of the load balancing for you.**

---

### 1. Set up
In this step, you will install the Heroku Command Line Interface (CLI), formerly known as the Heroku Toolbelt.

**If you have Debian/Ubuntu -Run this from your terminal:**

```
1. sudo add-apt-repository "deb https://cli-assets.heroku.com/branches/stable/apt ./"
```
```
2. curl -L https://cli-assets.heroku.com/apt/release.key | sudo apt-key add -
```
```
3. sudo apt-get update
```
```
4. sudo apt-get install Heroku
```
**If you have Mac, Download This File [Heroku CLI for Mac OS X](https://devcenter.heroku.com/articles/heroku-cli#macos)**
**Authenticating is required to allow both the Heroku and git commands to operate.**

Before you continue, check that you have the prerequisites installed properly.
Type each command below and make sure it displays the version you have installed. (Your versions might be different from the example.)
```
$ node -v
>
v5.9.1
```
npm is installed with Node, so check that it’s there. If you don’t have it, install a more recent version of Node:
```
$ npm -v
>
3.7.3
```
Now check that you have git installed. If not, install it and test again.
```
$ git --version
>
git version 2.2.1
```
****
### 2. Prepare the app
You should have been cloned the [Node-girls-Workshop](https://github.com/node-girls/node-workshop) and followed the steps to make your own Node.js app.
```
cd workshop-cms
```
If not - clone the repo and follow the steps to make the app.
****
### 3. Deploy the app
In this step, you will deploy the app to Heroku.
Create an app on Heroku, which prepares Heroku to receive your source code.
```
$ heroku create
```
Now deploy your code:
```
$ git push heroku master
```


The application now should be deployed.
****

### 4. Declare app dependencies
Heroku recognizes an app as Node.js by the existence of a package.js file in the root directory. For your own apps, you can create one by running `npm init --yes`.
Run this command in your local directory to install the dependencies, preparing your system for running the app locally:
```
$ npm install
```

Once dependencies are installed, you will be ready to run your app locally.
****
### 5. Run the app locally
Now start your application locally using the Heroku local command, which was installed as part of the Heroku CLI:
```
$ heroku local web
```
To stop the app from running locally, in the CLI, press Ctrl+C to exit.
****
### 6.Push local changes

Now deploy. Almost every deploy to Heroku follows this same pattern. First, add the modified files to the local git repository:
```
$ git add .
```
Now commit the changes to the repository:

```$ git commit -m "Demo" ```
Now deploy, just as you did previously:
```
$ git push Heroku (name of the branch)
```