# current-time-using-dayjs
Repository for current-time-using-dayjs, a lightweight JavaScript project that displays the current time and date using the Day.js library. </br>
Steps that i took to run this project successfully :- </br>
1 - run ```npm init -y``` to quickly get the default project package.json values. </br>
2 - create the files required for the first steps of the project, index.html, index.js. </br>
3 - next to be able to use the require command in the index.js file, i need to install a webpack which is a module bundler, that enables the use of commands like require() which is not identified by the browser. ```npm install webpack webpack-cli save-dev```, this installs the webpack bundler, and saves it as a dev dependency, references in the package.json file. </br>
4 - Once the webpack and webpack-cli is installed, the next step is to use the webpack-cli from the command line, ```./node_modules/.bin/webpack ./index.js --mode-development```, what this basically does is that it uses the webpack installed in the node_modules folder on the index.js file, and finds all the require statements in the code, and replaces them with the appropriate code to run them into a single or multiple files, usually it is the dist/main.js file. The ```--mode=development``` is to keep the javascript readable for developers.</br>
5 - The next step is to actually replace the script tags previously that included the location of the index.js file and dayjs module in the node_modules directory with the new location of the main.js file which is, ```dist/main.js```. Every time the command ```./node_modules/.bin/webpack ./index.js --mode=development``` is run it restructures the main.js file accordingly." </br>
6 - To run the command ```./node_modules/.bin/webpack ./index.js --mode=development``` every single time, can turn out to be a lot tedious, this can get more complex as the you try to implement more complex features with the webpack bundler. The solution is as follows:- One thing you need to know that webpack can read options from a config file named "webpack.config.js", which if it exists naturally can look like,  </br>
```
module.exports = {
    mode: "development",
    entry: "./index.js",
    output: {
        filename: "main.js",
        publicPath: "dist"
    }
}
```
</br> Now each time you change index.js, you can run webpack with the command, ./node_modules/.bin/webpack, the reason for not including the rest of the code is, because webpack can now fetch all the necessary information from the config file.</br>
7 - Having evertyhing setip, the website can now use dayjs to print the current time to the screen/display. </br>


