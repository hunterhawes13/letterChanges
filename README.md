## Synopsis

####JavaScript Challenge 

Using the JavaScript language, have the function LetterChanges(str) take the str parameter being passed and modify it using the following algorithm. Replace every letter in the string with the letter following it in the alphabet (ie. c becomes d, z becomes a). Then capitalize every vowel in this new string (a, e, i, o, u) and finally return this modified string. 

1. The replace() method returns a new string with some or all matches of a pattern replaced by a replacement. The pattern can be a string or a RegExp, and the replacement can be a string or a function to be called for each match.

```
str.replace(regexp|substr, newSubStr|function)
```

•regexp (pattern)
A RegExp object or literal. The match or matches are replaced with newSubStr or the value returned by the specified function.

•newSubStr (replacement)
The String that replaces the substring specified by the specified regexp or substr parameter. A number of special replacement patterns are supported; see the "Specifying a string as a parameter" section below.

•function (replacement)
A function to be invoked to create the new substring to be used to replace the matches to the given regexp or substr. The arguments supplied to this function are described in the "Specifying a function as a parameter" section below.

2. return (char === 'z' || char === 'Z') which is char strict equals the string lowercase z or char strict equals the string uppercase z. then an if statement which basically adds one to whatever the charcode # is. The start of this first line only comes into play if the letter is z working its way through to add one to the char number.

•The conditional (ternary) operator is the only JavaScript operator that takes three operands. This operator is frequently used as a shortcut for the if statement.

3. Then we capitalize the vowels by again using the replace method with a regex and function, this time the function just returns .toUpperCase()

4. finally we return the final string. Voilà... yes this one hurt my head too.

## Code Example

```
function LetterChanges(str) { 

  // we will replace every letter in the string with the letter following it
  // by first getting the charCode number of the letter, adding 1 to it, then 
  // converting this new charCode number to a letter using the fromCharCode function
  // we also check to see if the character is z and if so we simply convert the z to an a
  var converted = str.replace(/[a-z]/gi, function(char) { 
    return (char === 'z' || char === 'Z') ? 'a' : String.fromCharCode(char.charCodeAt() + 1);
  });

  // we have now successfully converted each letter to the letter following it
  // in the alphabet, and all we need to do now is capitalize the vowels
  var capitalized = converted.replace(/a|e|i|o|u/gi, function(vowel) { 
    return vowel.toUpperCase();
  });

  // return the final string
  return capitalized;
         
}
   
LetterChanges("fun times!");           
```

## Motivation

stay sharp

## Contributors

Hunter Hawes
github: hunterhawes13
twitter: @tikishackfun

## License

This project is licensed under the terms of the MIT license.

## Warning

This should not be used in production. It is for demonstration purposes only.
