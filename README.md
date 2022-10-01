# hacked-server
For maintaining the MariaDB server in localhost for professional work
Tutorial Server

Hi everyone! You can use this repository for the hacktober-fest 2022.
Just make a fork of this project and start working on it, if you get an issue just make it and resolve and make the pull request there.
I wil merge the request if possible, immediately.

You can use it to run the tutorial locally and translate it into your language.

Windows, Unix systems and macOS are supported. For Windows, you'll need to call scripts with ".cmd" extension, that are present in the code alongside with Unix versions.

Installation
Install Git and Node.js.

These are required to update and run the project. For Windows just download and install, otherwise use standard OS install tools (packages or whatever convenient).

Please use Node.js 10+.

(Maybe later, optional) If you're going to change images, please install ImageMagick, use packages for Linux or homebrew/macports for MacOS.

Install global Node modules:

npm install -g bunyan gulp@4
Create the root folder.

Create a folder /js for the project.

You can also use another directory as the root, then change the paths below: replace /js with your root.

Clone the tutorial server into it:

cd /js
git clone https://github.com/javascript-tutorial/server
git clone https://github.com/javascript-tutorial/engine server/modules/engine
Please note, there are two clone commands. That's not a typo: modules/engine is cloned from another repository.

And please don't forget when pulling an updated server code: modules/engine needs to be pulled too.

Clone the tutorial text into it.

The repository starts with the language code, e.g for the French version fr.javascript.info, for Russian – ru.javascript.info, for Chinese zh.javascript.info etc.

The English version is en.javascript.info.

The tutorial text repository should go into the repo subfolder, like this:

cd /js/server/repo
git clone https://github.com/javascript-tutorial/en.javascript.info
Run the site

Install local NPM modules:

cd /js/server
npm install
Run the site with the ./edit command with the language argument. Above we cloned en tutorial, so:

./edit en
This will import the tutorial from /js/server/repo/en.javascript.info and start the server.

Wait a bit while it reads the tutorial from the disk and builds static assets.

Then access the site at http://127.0.0.1:3000.

To change the port, set the PORT environment variable:

# Runs the server at http://127.0.0.1:8080
PORT=8080 ./edit en
For Windows, read the note about environment variables below.

Edit the tutorial

As you edit text files in the tutorial text repository (cloned at step 5), the webpage will reload automatically.

Windows: Environment variables
For Windows, to pass environment variables, such as PORT, you can install npm i -g cross-env and prepend calls with cross-env, like this:

cd /js/server
cross-env PORT=8080 ./edit en
In the examples below, the commands are without cross-env, prepend it please, if you're on Windows.

Alternatively, you can use other Windows-specific ways to set environment variables, such as a separate set PORT=8080 command.

Change server language
The server uses English by default for navigation and design.

You can set another language it with the second argument of edit.

E.g. if you cloned ru tutorial, it makes sense to use ru locale for the server as well:

cd /js/server
./edit ru ru
Please note, the server must support that language. There must be corresponding locale files for that language in the code of the server, otherwise it exists with an error. As of now, ru, en, zh, tr, ko and ja are fully supported.
