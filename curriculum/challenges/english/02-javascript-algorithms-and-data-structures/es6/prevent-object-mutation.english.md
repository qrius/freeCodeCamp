---
id: 598f48a36c8c40764b4e52b3
title: Prevent Object Mutation
challengeType: 1
---

## Description
<section id='description'>
As seen in the previous challenge, <code>const</code> declaration alone doesn't really protect your data from mutation. To ensure your data doesn't change, JavaScript provides a function <code>Object.freeze</code> to prevent data mutation.
Once the object is frozen, you can no longer add, update, or delete properties from it. Any attempt at changing the object will be rejected without an error.
<blockquote>let obj = {<br>&nbsp;&nbsp;name:"FreeCodeCamp",<br>&nbsp;&nbsp;review:"Awesome"<br>};<br>Object.freeze(obj);<br>obj.review = "bad"; //will be ignored. Mutation not allowed<br>obj.newProp = "Test"; // will be ignored. Mutation not allowed<br>console.log(obj); <br>// { name: "FreeCodeCamp", review:"Awesome"}</blockquote>
</section>

## Instructions
<section id='instructions'>
In this challenge you are going to use <code>Object.freeze</code> to prevent mathematical constants from changing. You need to freeze the <code>MATH_CONSTANTS</code> object so that no one is able alter the value of <code>PI</code>, add, or delete properties .
</section>

## Tests
<section id='tests'>

```yml
tests:
  - text: Do not replace <code>const</code> keyword.
    testString: 'getUserInput => assert(getUserInput("index").match(/const/g), "Do not replace <code>const</code> keyword.");'
  - text: <code>MATH_CONSTANTS</code> should be a constant variable (by using <code>const</code>).
    testString: 'getUserInput => assert(getUserInput("index").match(/const\s+MATH_CONSTANTS/g), "<code>MATH_CONSTANTS</code> should be a constant variable (by using <code>const</code>).");'
  - text: Do not change original <code>MATH_CONSTANTS</code>.
    testString: 'getUserInput => assert(getUserInput("index").match(/const\s+MATH_CONSTANTS\s+=\s+{\s+PI:\s+3.14\s+};/g), "Do not change original <code>MATH_CONSTANTS</code>.");'
  - text: <code>PI</code> equals <code>3.14</code>.
    testString: 'assert(PI === 3.14, "<code>PI</code> equals <code>3.14</code>.");'

```

</section>

## Challenge Seed
<section id='challengeSeed'>

<div id='js-seed'>

```js
function freezeObj() {
  'use strict';
  const MATH_CONSTANTS = {
    PI: 3.14
  };
  // change code below this line


  // change code above this line
  try {
    MATH_CONSTANTS.PI = 99;
  } catch( ex ) {
    console.log(ex);
  }
  return MATH_CONSTANTS.PI;
}
const PI = freezeObj();
```

</div>



</section>

## Solution
<section id='solution'>

```js
function freezeObj() {
  'use strict';
  const MATH_CONSTANTS = {
    PI: 3.14
  };
  // change code below this line
  Object.freeze(MATH_CONSTANTS);

  // change code above this line
  try {
    MATH_CONSTANTS.PI = 99;
  } catch( ex ) {
    console.log(ex);
  }
  return MATH_CONSTANTS.PI;
}
const PI = freezeObj();
```
</section>
