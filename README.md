# gmlx
*Game Maker Language Extensions* brings more structured programming support to Game Maker: Studio, including support for defining multiple functions per file and new datatypes. GMLX accomplishes this task by translating .gmlx files you code in an external text editor into standard .gml files and updating your Game Maker project file. Game Maker will automatically reload your scripts resulting in a seemless coding experience.

## Example
sample.gmlx
```javascript
// define a new datatype called Food and give default values.
// gmlx structs need to give default values.
// you can also put any other code for initialization in there you want.
struct Food{
  give_food = 22;
  name = "coffee";
  effects = "stimulant";
}

// define a new function. It can be called from any script just like normal .gml scripts
function decrease_nutrition(amount){
  self.give_food = self.give_food - amount;
}

// this function demonstrates creating a new Food struct and
// calling a function on it with an argument. Use this style 
// to simulate object oriented programming
function test(){
  var coffee = new Food();
  with(coffee){
    decrease_nutrition(10);
  }
}
```
The above example gets parsed and turned into three normal Game Maker script files and your project file gets updated accordingly. Warning: this can and will overwrite script files with the same name as the functions here. Always back up your project before starting with GMLX, since it is still in alpha and might break things!


## Getting Started
1.  Download Sublime Text 2 or Sublime Text 3.
2.  Download [this git repo zip](https://github.com/horsman/gmlx/archive/master.zip).
3.  Unzip the repo
4.  Copy the GMLX folder inside to %APPDATA%\Sublime Text 2\Packages\ (usually C:\Users\USERNAME\AppData\Roaming\Sublime Text 2\Packages)
5.  In your Game Maker Project Folder (.GMK) make a directory called GMLX 
6.  Create HelloWorld.gmlx in that folder with Sublime Text and put the following code:

        function test_gmlx(){
          show_message("Hello World")
        }
7.  From the Sublime Text Tools menu choose Build System > GMLX
8.  Build HelloWorld.gmlx with Ctrl-B when it is open in Sublime Text
9.  Open or switch to your Game Maker Project to see if test_gmlx shows up in your scripts
10.  Call text_gmlx as you would any other script to test



## Version History
* 0.1a [2014-5-11]: first release. 

## Roadmap
* 0.1b: member function convenience syntax, dictionary and list literals ( {a:1 b:2} and [a, b, c] ), better struct syntax.
