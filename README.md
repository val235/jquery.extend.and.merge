##jQuery Extended Extend and Union/Merge

###Original Author: val 

###Modified by: Lingliang Zhang

- Slight modification to the jQuery.extend function.

- Has same syntax and similar behavior to the original jQuery
  extend. Documentation [here](http://api.jquery.com/jQuery.extend/).

- Alternate versions allow for either performing `$.merge`,
  or `\_.union` (from Underscore.js) on the conflicting
  arrays.

- Union version is recommended for unique keys, Merge version
  for when multiples of the same object are desired.

- For both functions, when given two objects, attempts to
  merge them together into the first object, giving the
  second object priority to overwrite keys.  When arrays are
  encountered, either a merge (concatinating them together)
  or a union (taking the set of unique keys from both) will
  occur, depending on which version you chose.

- Merge version requires only jQuery. Union version requires jQuery and Underscore.js.

- Code copied directly out of 1.7.1 and slightly modified.

- Everything essentially stayed the same with one important difference, arrays in your objects are now concatenated/union'd instead of having elements replaced.

###Original:

	$.extend(true, {}, {myObject:{myArray:[1,2,3]}}, {myObject:{myArray:[a,b]}} === produced ===> {myObject:{myArray:[a,b,3]}  

	
###New way with merge:

	$.extendAndMerge(true, {}, {myObject:{myArray:[1,2,3]}}, {myObject:{myArray:[a,b,2,3]}} === produces ===> {myObject:{myArray:[1,2,3,a,b,2,3]}  

###New way with union:

	$.extendAndMerge(true, {}, {myObject:{myArray:[1,2,3]}}, {myObject:{myArray:[a,b,2,3]}} === produces ===> {myObject:{myArray:[1,2,3,a,b]}  

