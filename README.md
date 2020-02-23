# Web Service for Solving Mixed-Integer Programs
This program is a web service that provides online solution for Linear Programming problems, using [Open Solver Interface](https://github.com/coin-or/Osi) API.
All you have to do is to run the service with *npm*, and then upload an LP-File, and then the result is shown on the page.
This app is based on Node.js and Express.js, and the OSI framework is integrated as a plugin using [Native Abstractions for Node.js (NAN)](https://github.com/nodejs/nan).
This project is currently supported on Linux.
## How to Install
At first, install the latest version of Node.js; for example, if you want to install version 13.x, enter this command in terminal: 
```bash
curl -sL https://deb.nodesource.com/setup_13.x | sudo -E bash -
sudo apt-get install -y nodejs
```
For installing the dependencies for OSI, we need an installer tool named [CoinBrew](https://coin-or.github.io/coinbrew/). Download its script from [here](https://raw.githubusercontent.com/coin-or/coinbrew/master/coinbrew).
And then, run these commands: (`/path/to/coinbrew` should be swapped with the path to the downloaded script. e.g. If it is in your current directory, the path would be `./coinbrew`)
```bash
chmod 777 /path/to/coinbrew
/path/to/coinbrew fetch --main-proj=Osi
sudo /path/to/coinbrew build --main-proj=Osi --prefix=/usr/local
sudo /path/to/coinbrew install --main-proj=Osi
```
Also, we use the [Clp](https://www.github.com/coin-or/Clp) solver with our interface. To install it, again we use Coinbrew. (You may need to install gfortran or liblapack.)
```bash
sudo apt install gfortran
sudo apt install liblapack-dev
/path/to/coinbrew fetch Clp
sudo /path/to/coinbrew build Clp --prefix=/usr/local
sudo /path/to/coinbrew install Clp
```
Finally, you could `cd` into the main directory of the project and run these commands to install the node dependencies and run the web server:
```bash
npm install
npm start
```
The web server would run on http://localhost:3000. You should upload a .lp file on the form, and then you will get the linear optimization result
## Dependencies
This project's dependencies are listed below:
- [Node.js](https://github.com/nodejs/node)
- [npm](https://github.com/npm/cli)
- [nan](https://github.com/nodejs/nan)
- [Express](https://github.com/expressjs/express)
- [pug](https://github.com/pugjs/pug)
- [multer](https://github.com/expressjs/multer)
- bindings
- cookie-parser
- debug
- http-errors
- morgan
The last 4 dependencies are required by the Express framework.
##Issues
If you have had any problems about running the project or any other issues, feel free to mention it in the GitHub issues.