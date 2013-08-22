author: val
Modified by: Lingliang Zhang

-slight modification to the jQuery.extend function

-Alternate versions allow for either performing `$.merge`, or
`\_.union` (from Underscore.js) on the conflicting arrays.

-In the union version, when given two objects, attempts to merge them together
into the first object, giving the second object priority to overwrite keys.
When arrays are encountered, a union of the arrays will occur. 

-Merge version requires only jQuery. Union version requires jQuery and Underscore.js


-code copied directly out of 1.7.1 and slightly modified

-everything essentially stayed the same with one important difference, arrays in your objects are now concatenated instead of having elements replaced 

original:

	$.extend(true, {}, {myObject:{myArray:[1,2,3]}}, {myObject:{myArray:[a,b]}} === produced ===> {myObject:{myArray:[a,b,3]}  

	
new way:

	$.extendAndMerge(true, {}, {myObject:{myArray:[1,2,3]}}, {myObject:{myArray:[a,b]}} === produces ===> {myObject:{myArray:[a,b,c,1,2,3]}  
