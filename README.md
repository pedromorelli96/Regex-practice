# 🔰 Regular Expressions (REGEX)

### `.test()` Method

```js
let sentence = "The dog chased the cat.";
let regex = /the/;

let myString = "Hello, World!";
let myRegex = /Hello/;
let result = myRegex.test(myString);

console.log(result); // true
```

### Match Literal Strings

```js
let waldoIsHiding = "Somewhere Waldo is hiding in this text.";
let waldoRegex = /Waldo/; // Case Sensitive
let result = waldoRegex.test(waldoIsHiding);

console.log(result); // true
```

### Match a Literal String with Different Possibilities

```js
let petString = "James has a pet cat.";
let petRegex = /dog|cat|bird|fish/; // | is the "or" operator
let result = petRegex.test(petString);

console.log(result); // true
```

### Ignore Case while Matching

```js
let myString = "freeCodeCamp";
let fccRegex = /freecodecamp/i; // i flag ignores case
let result = fccRegex.test(myString);

console.log(result); // true
```

### Extract Matches with the `.match()` method

```js
let extractStr = "Extract the word 'coding' from this string.";
let codingRegex = /coding/;
let result = extractStr.match(codingRegex);

console.log(result); // ["coding"]
```

### Find More Than the First Match

```js
let testStr = "Repeat, Repeat, Repeat";
let ourRegex = /Repeat/g;
testStr.match(ourRegex);

let twinkleStar = "Twinkle, twinkle, little star";
let starRegex = /twinkle/gi; // g flag matches every single occurrence
let result = twinkleStar.match(starRegex);

console.log(result); // ["Twinkle", "twinkle"]
```

### Match Anything with Wildcard Period `.`

```js
let humStr = "I'll hum a song";
let hugStr = "Bear hug";
let huRegex = /hu./;
humStr.match(huRegex); // Returns ["hum"]
hugStr.match(huRegex); // Returns ["hug"]

let exampleStr = "Let's have fun with regular expressions!";
let unRegex = /.un/; // . is the wildcard character
let result = unRegex.test(exampleStr);

console.log(result); // true
```

### Match Single Character with Multiple Possibilities `[]`

```js
let bgRegex = /b[aiu]g/; // matches bag, big or bug

let quoteSample =
    "Beware of bugs in the above code; I have only proved it correct, not tried it.";
let vowelRegex = /[aeiou]/gi; // matches every vowel
let result = quoteSample.match(vowelRegex);

console.log(result);
// ["e", "a", "e", "o", "u", "i", "e", "a", "o", "e", "o", "e", "I", ...]
```

### Match Letters of the Alphabet `-`

```js
let quoteSample = "The quick brown fox jumps over the lazy dog.";
let alphabetRegex = /[a-z]/gi; // matches a range of letters
let result = quoteSample.match(alphabetRegex);

console.log(result);
// ["T", "h", "e", "q", "u", "i", "c", "k", "b", "r", "o", "w", ...]
```

### Match Numbers and Letters of the Alphabet

```js
let quoteSample = "Blueberry 3.141592653s are delicious.";
let myRegex = /[2-6h-s]/gi;
// matches numbers from 2 to 6 and letters from h to s
let result = quoteSample.match(myRegex);

console.log(result);
// ["l", "r", "r", "3", "4", "5", "2", "6", "5", "3", "s", "r", "l", "i", "i", "o", "s"]
```

### Select Characters that you Do Not Want to Match `^`

```js
let quoteSample = "3 blind mice.";
let myRegex = /[^0-9aeiou]/gi; // ^ is the caret operator
// matches everything except all numbers and all vowels
let result = quoteSample.match(myRegex);

console.log(result); // [" ", "b", "l", "n", "d", " ", "m", "c", "."]
// it includes spaces and punctuation
```

### Match Characters that Occur One or More Times `+`

```js
let difficultSpelling = "Mississipspi";
let myRegex = /s+/g; // + is the plus operator
let result = difficultSpelling.match(myRegex);

console.log(result); // ["ss", "ss", "s"]
```

### Match Characters that Occur Zero or More Times `*`

```js
let soccerWord = "gooooooooal!";
let gPhrase = "gut feeling";
let oPhrase = "over the moon";
let goRegex = /go*/; // character 'o' might happen zero or more times
soccerWord.match(goRegex); // Returns ["goooooooo"]
gPhrase.match(goRegex); // Returns ["g"]
oPhrase.match(goRegex); // Returns null

let chewieQuote = "Aaaaaaaaaaaaaaaarrrgh!";
let chewieRegex = /Aa*/; // * is the star operator
let result = chewieQuote.match(chewieRegex);

console.log(result); // ["Aaaaaaaaaaaaaaaa"]
```

### Find Characters with Lazy Matching `?`

```js
let string = "titanic";
let regex = /t[a-z]*?i/; // <-- returns 'ti' (lazy)
// let regex = /t[a-z]*i/; <-- returns 'titani' (greedy)
string.match(regex);

let text = "<h1>Winter is coming</h1>";
//let myRegex = /<.*>/; // <-- returns ["<h1>Winter is coming</h1>"]
let myRegex = /<.*?>/;
let result = text.match(myRegex);

console.log(result); // ["<h1>"]
```

_Note_: RegEx defaults to `greedy`.

### Find One or More Criminals in a Hunt

```js
let crowd = "P1P2P3P4P5P6CCCP7P8P9";
let reCriminals = /C+/; // finds one or more 'C'
let matchedCriminals = crowd.match(reCriminals);

console.log(matchedCriminals); // ["CCC"]
```

### Match Beginning String Patterns `^`

```js
let rickyAndCal = "Cal and Ricky both like racing.";
// let rickyAndCal = "and Ricky both Cal like racing."; // returns false
let calRegex = /^Cal/; // ^ caret operator matches string beginning only
let result = calRegex.test(rickyAndCal);

console.log(result); // true
```

### Match Ending String Patterns `$`

```js
let caboose = "The last car on a train is the caboose";
// let caboose = "The last car on a train is caboose the "; // returns false
let lastRegex = /caboose$/; // $ dolar sign operator matches string ending only
let result = lastRegex.test(caboose);

console.log(result); // true
```

### Match All Letters and Numbers `\w`

#### `\w` matches:

-   Capital `A-Z`
-   Lowercase `a-z`
-   Digits `0-9`
-   Underscore `_`

```js
let quoteSample = "The five boxing wizards jump quickly.";
let alphabetRegexV2 = /\w/g; // \w shorthand class (lowercase)
let result = quoteSample.match(alphabetRegexV2).length;

console.log(result); // 31 (excluding spaces and punctuation)
```

### Match Everything But Letters and Numbers `\W`

```js
let quoteSample = "The five boxing wizards jump quickly.";
let nonAlphabetRegex = /\W/g; // \W shorthand class (uppercase)
let result = quoteSample.match(nonAlphabetRegex).length;

console.log(result); // 6
```

### Match All Numbers `\d`

```js
let numString = "Your sandwich will be $5.00";
let numRegex = /\d/g; // \d shorthand class (lowercase)
let result = numString.match(numRegex).length;

console.log(result); // 3
```

### Match All Non-Numbers `\D`

```js
let numString = "Your sandwich will be $5.00";
let noNumRegex = /\D/g; // \D shorthand class (uppercase)
let result = numString.match(noNumRegex).length;

console.log(result); // 24
```

### Restrict Possible Usernames `{}`

#### `{X,Y}`

-   X = the **minimum** number of matches
-   Y = the **maximum** number of matches

```js
/*
1) If there are numbers, they must be at the end.
2) Letters can be lowercase and uppercase.
3) At least two characters long. Two-letter names can't have numbers.
*/

let username = "JackOfAllTrades";
let userCheck = /^[A-Za-z]{2,}\d*$/;
/*
1) \d*$ = zero or more numbers, at the end
2) ^[A-Za-z] = all uppercase and lowercase letters, at the beginning
3) {2,} = between 2 (minimum) and infinite characters
*/
let result = userCheck.test(username);

console.log(result); // true
```

### Match Whitespace `\s`

#### `\s` matches:

-   Space `" "`
-   Tab `\t`
-   Newline `\n`
-   Vertical Tab `\v`
-   Carriage return `\r`
-   Form feed `\f`

```js
let sample = "Whitespace is important in separating words";
let countWhiteSpace = /\s/g; // \s shorthand class (lowercase)
let result = sample.match(countWhiteSpace);

console.log(result); // [" ", " ", " ", " ", " "]
```

### Match Non-Whitespace Characters `\S`

```js
let sample = "Whitespace is important in separating words";
let countWhiteSpace = /\S/g; // \S shorthand class (uppercase)
let result = sample.match(countWhiteSpace);

console.log(result);
// ["W", "h", "i", "t", "e", "s", "p", "a", "c", "e", "i", "s", ...]
```

### Specify Upper and Lower Number of Matches `{X,Y}`

```js
let ohStr = "Ohhh no";
let ohRegex = /Oh{3,6} no/; // {} is the quantity specifier
let result = ohRegex.test(ohStr);

console.log(result); // true
```

### Specify Only the Lower Number of Matches `{X,}`

```js
let haStr = "Hazzzzah";
let haRegex = /z{4,}/; // at least 4 'z' characters or more
let result = haRegex.test(haStr);

console.log(result); // true
```

### Specify Exact Number of Matches `{X}`

```js
let timStr = "Timmmmber";
let timRegex = /Tim{4}ber/; // exactly 4 'm' characters
let result = timRegex.test(timStr);

console.log(result); // true
```

### Check for All or None `?`

```js
let favWord = "favorite";
let favRegex = /favou?rite/; // 'u' character is optional
let result = favRegex.test(favWord);

console.log(result); // true
```

### Positive and Negative Lookahead `(?=) (?!)`

-   #### Positive Lookahead: `(?=)`

-   #### Negative Lookahead: `(?!)`

They _lookahead_ to make sure there either **is** or is **not**
a match later in the string, but the match is **not** returned.

```js
let quit = "qu";
let noquit = "qt";
let quRegex = /q(?=u)/;
let qRegex = /q(?!u)/;
quit.match(quRegex); // Returns ["q"]
noquit.match(qRegex); // Returns ["q"]

let sampleWord = "astronaut";
let pwRegex = /(?=\w{5})(?=\D*\d{2})/;
/*
1) (?=\w{5}) = matches for atleast 5 characters
2) (?=\D*\d{2}) = any number of characters that are not digits and two or more digits
*/
let result = pwRegex.test(sampleWord);

console.log(result); // true
```

### Reuse Patterns Using Capture Groups `()`

```js
let repeatStr = "regex regex";
let repeatRegex = /(\w+)\s\1/;
repeatRegex.test(repeatStr); // Returns true
repeatStr.match(repeatRegex); // Returns ["regex regex", "regex"]

let repeatNum = "42 42 42";
let reRegex = /^(\d+)\s\1\s\1$/; // () is the capture group
/*
1) (\d+) = any number of digits
2) (\d+)\s\1\s\1 = repeated two more times
3) ^(\d+)\s\1\s\1$ = exactly this match, nothing less or more
*/

let result = reRegex.test(repeatNum);
```

### Use Capture Groups to Search and Replace `()`

```js
let wrongText = "The sky is silver.";
let silverRegex = /silver/;
wrongText.replace(silverRegex, "blue"); // Returns "The sky is blue."

"Code Camp".replace(/(\w+)\s(\w+)/, "$2 $1"); // Returns "Camp Code"
/*
$2 = second capture group
$1 = first capture group
*/

let huhText = "This sandwich is good.";
let fixRegex = /good/;
let replaceText = "okey-dokey";
let result = huhText.replace(fixRegex, replaceText);

console.log(result); // "This sandwich is okey-dokey"
```

### Remove Whitespace from Start and End

```js
let hello = "   Hello, World!  ";
let wsRegex = /^\s+|\s+$/g;
let result = hello.replace(wsRegex, "");

console.log(result); // Hello, World!
```
