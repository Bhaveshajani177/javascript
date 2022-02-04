**1. Naming Convention for Variables:**
  - JavaScript variable names are case-sensitive. Lowercase and uppercase letters are distinct.
  - Example:
    ```js
    var DogName = 'Scooby-Doo';
    var dogName = 'Droopy';
    var DOGNAME = 'Odie';
    console.log(DogName); // "Scooby-Doo"
    console.log(dogName); // "Droopy"
    console.log(DOGNAME); // "Odie"
    ```
  - However, the most recommended way to declare JavaScript variables is with camel case variable names.
  - You can use the camel case naming convention for all types of variables in JavaScript, and it will ensure that there aren’t multiple variables with the same name.
    ```js
    // bad
    var dogname = 'Droopy'; 
    // bad
    var dog_name = 'Droopy'; 
    // bad
    var DOGNAME = ‘Droopy’; 
    // bad
    var DOG_NAME = 'Droopy'; 
    // good
    var dogName = 'Droopy';
    ```
  
**2. Naming Convention for Booleans:**
  - When it comes to Boolean variables, we should use is or has as prefixes. 
  - For example, if you need a Boolean variable to check if a dog has an owner, you should use hasOwner as the variable name.
    ```js
    // bad
    var bark = false;
    // good
    var isBark = false;

    // bad
    var owner = true;
    // good
    var hasOwner = true;
    ```
  
**3. Naming Convention for Functions:**
  - JavaScript function names are also case-sensitive. So, similar to variables, the camel case approach is the recommended way to declare function names.
  - In addition to that, you should use descriptive nouns and verbs as prefixes.
  - For example:
    ```js
    // bad
    function name(dogName, ownerName) { 
      return '${dogName} ${ownerName}';
    }

    // good
    function getName(dogName, ownerName) { 
      return '${dogName} ${ownerName}';
    }
    ```
