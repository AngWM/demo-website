# Autoauth demo website

This repository contains a demo website built with Node.js, Express and MongoDB. It has both the ability to create accounts using a username and password, as well as with Autoauth.

## Table of contents

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Docker](#docker)
- [Project Structure](#project-structure)

## Prerequisites

- [MongoDB](https://www.mongodb.org/downloads)
- [Node.js 8.0+](http://nodejs.org)

## Getting started

The easiest way to get started is to clone the repository:

```bash
# Get the latest snapshot
git clone https://github.com/cs3235-autoauth/demo-website.git myproject

# Change directory
cd myproject

# Install NPM dependencies
npm install

# Then simply start your app
node app.js
```

**Note:** I highly recommend installing [Nodemon](https://github.com/remy/nodemon).
It watches for any changes in your  node.js app and automatically restarts the
server. Once installed, instead of `node app.js` use `nodemon app.js`. It will
save you a lot of time in the long run, because you won't need to manually
restart the server each time you make a small change in code. To install, run
`sudo npm install -g nodemon`.

## Docker

You will need docker and docker-compose installed to build the application. 

- [Docker installation](https://docs.docker.com/engine/installation/)

- [Common problems setting up docker](https://docs.docker.com/toolbox/faqs/troubleshoot/)

After installing docker, start the application with the following commands : 

```
# To build the project for the first time or when you add dependencies
docker-compose build web  

# To start the application (or to restart after making changes to the source code)
docker-compose up web

```

To view the app, find your docker ip address + port 8080 ( this will typically be http://localhost:8080/ ).  To use a port other than 8080, you would need to modify the port in app.js, Dockerfile and docker-compose.yml.

## Project Structure

| Name                               | Description                                                    |
| ---------------------------------- | ---------------------------------------------------------------|
| **config**/passport.js             | Passport Local and Autoauth strategies, plus login middleware. |
| **controllers**/contact.js         | Controller for contact form.                                   |
| **controllers**/home.js            | Controller for home page (index).                              |
| **controllers**/user.js            | Controller for user account management.                        |
| **models**/User.js                 | Mongoose schema and model for User.                            |
| **public**/                        | Static assets (fonts, css, js, img).                           |
| **public**/**js**/application.js   | Specify client-side JavaScript dependencies.                   |
| **public**/**js**/main.js          | Place your client-side JavaScript here.                        |
| **public**/**css**/main.scss       | Main stylesheet for your app.                                  |
| **public/css/themes**/default.scss | Some Bootstrap overrides to make it look prettier.             |
| **views/account**/                 | Templates for *login, password reset, signup, profile*.        |
| **views/partials**/flash.pug       | Error, info and success flash notifications.                   |
| **views/partials**/header.pug      | Navbar partial template.                                       |
| **views/partials**/footer.pug      | Footer partial template.                                       |
| **views**/layout.pug               | Base template.                                                 |
| **views**/home.pug                 | Home page template.                                            |
| .dockerignore                      | Folder and files ignored by docker usage.                      |
| .env.example                       | Your API keys, tokens, passwords and database URI.             |
| .eslintrc                          | Rules for eslint linter.                                       |
| .gitignore                         | Folder and files ignored by git.                               |
| .travis.yml                        | Configuration files for continue integration.                  |
| app.js                             | The main application file.                                     |
| docker-compose.yml                 | Docker compose configuration file.                             |
| Dockerfile                         | Docker configuration file.                                     |
| package.json                       | NPM dependencies.                                              |
| package-lock.json                  | Contains exact versions of NPM dependencies in package.json.   |

## Credits

This demo website was based on [sahat/hackathon-starter](https://github.com/sahat/hackathon-starter).