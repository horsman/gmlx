# gmlx
*Game Maker Language Extensions* brings more strutured programming support to Game Maker: Studio, including support for defining multiple functions per file and new datatypes. GMLX accomplishes this task by translating .gmlx files you code in an external text editor into standard .gml files and updating your Game Maker project file. Game Maker will automatically reload your scripts resulting in a seemless coding experience.

## Example
sample.gmlx
```
# define a new datatype called Food and give default values.
# gmlx structs need to give default values.
# you can also put any other code for initialization in there you want.
struct Food{
  give_food = 22;
  name = "coffee";
  effects = "stimulant";
  
}

# define a new function. It can be called from any script just like normal .gml scripts
function decrease_nutrition(amount){
  self.give_food = self.give_food - amount;
}

# this function demonstrates creating a new Food struct and
# calling a function on it with an argument. Use this style 
# to simulate object oriented programming
function test(){
  var coffee = new Food();
  with(coffee){
    decrease_nutrition(10);
  }
}
```

## Version History
* 0.1a [2014-5-11]: first release. 
