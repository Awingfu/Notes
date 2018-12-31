# Express in NodeJS

[Official Express Documentation](https://expressjs.com/)

## First Steps - Hello World

1. Make a new project directory with ```mkdir <project name>``` and ```cd``` into it
2. Initialize NPM with ```npm init (-y)```
3. Install Express with ```npm install --save express```
4. Touch an app.js file with ```touch app.js```
5. Paste the following 
```javascript
const express = require("express")

const app = express();

app.get("/", (req,res) => {
    res.send("Hello World");
});

app.listen(3000, () => {
    console.log("Server started on port 3000");
});
```
6. Make a script in package.json or run ```npm app.js```
7. Visit ```http://localhost:3000/```

To kill the instance, press `control` + `C` in the terminal where "npm app.js" is running.
If the shell is gone, but node is still running, run ```lsof -Pi | grep LISTEN``` and ```kill -9 <process id>```