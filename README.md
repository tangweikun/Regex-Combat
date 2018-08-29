# REGEX COMBAT

## Instruction

Learning Regular Expressions to solve problems, there are some problems you can solve by regex.

## Recommend

⌛ [Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)

🎊 [learn-regex](https://github.com/zeeshanu/learn-regex)

✂️ [Regex 对象](http://javascript.ruanyifeng.com/stdlib/regexp.html)

## Combat

### 👶 8kyu

- [Regex count lowercase letters
  ](https://www.codewars.com/kata/regex-count-lowercase-letters/javascript)

> count the total number of lowercase letters in a string.

```js
function lowercaseCount(str) {
  return (str.match(/[a-z]/g) || []).length
}

function lowercaseCount(str) {
  return str.replace(/[^a-z]/g, '').length
}
```

- [Simple validation of a username with regex](https://www.codewars.com/kata/simple-validation-of-a-username-with-regex/javascript)

> Write a simple regex to validate a username. Allowed characters are: `lowercase letters` or `numbers` or `underscore`. Length should be between 4 and 16 characters

```js
function validateUsr(username) {
  return /^[0-9a-z_]{4,16}$/.test(username)
}
```

### 👦 7kyu

- [Remove consecutive duplicate words](https://www.codewars.com/kata/remove-consecutive-duplicate-words/javascript)

<!-- HELP: -->

> Remove all consecutive duplicate words from string, leaving only first words entries.

```js
function removeConsecutiveDuplicates(str) {
  return str.replace(/\b(\w+)(?: \1)+\b/g, '$1')
}
```

- [Regex validate PIN code](https://www.codewars.com/kata/regex-validate-pin-code/javascript)

> ATM machines allow 4 or 6 digit PIN codes and PIN codes cannot contain anything but exactly 4 digits or exactly 6 digits.

```js
function validatePIN(pin) {
  return /^(\d{4}|\d{6})$/.test(pin)
}
```

- [Hide password from jdbc url](https://www.codewars.com/kata/hide-password-from-jdbc-url/javascript)

> Create a function that receives a connection string with password included and you have to mask the password i.e. change password by asterisks.(`password=` will occur only once)

```js
function hidePasswordFromConnection(urlString) {
  return urlString.replace(/(?<=password\=)([^&]*)/, match =>
    '*'.repeat(match.length),
  )
}
```

- [Start with a Vowel](https://www.codewars.com/kata/start-with-a-vowel/javascript)

> Create a function that takes any sentence and redistributes the spaces (and adds additional spaces if needed) so that each word starts with a vowel. The letters should all be in the same order but every vowel in the sentence should be the start of a new word. The first word in the new sentence may start without a vowel. It should return a string in all lowercase with no punctuation (only alphanumeric characters).

```js
function vowelStart(str) {
  return str
    .toLowerCase()
    .replace(/[^a-z\d]/g, '')
    .replace(/[aeiou]/g, ' $&')
    .trim()
}

function vowelStart(str) {
  return str
    .toLowerCase()
    .replace(/\W/g, '')
    .split(/(?=[aeiou])/)
    .join(' ')
}
```

- [Manipulate URL Parameters](https://www.codewars.com/kata/manipulate-url-parameters)

<!-- HELP: -->

> You need to write a function ( addOrChangeUrlParameter(url, keyValueParameter) ) that can manipulate URL parameters.It should be able to `add a parameter to an existing URL` and `change a parameter if it already exists`

```js
function addOrChangeUrlParameter(url, param) {
  const foo = url.replace(new RegExp(param.split('=')[0] + '=[^&]*'), param)

  return foo.includes(param)
    ? foo
    : foo + (foo.includes('?') ? '&' : '?') + param
}
```

- [Remove all exclamation marks from the end of words](https://www.codewars.com/kata/exclamation-marks-series-number-5-remove-all-exclamation-marks-from-the-end-of-words)

> Remove all exclamation marks from the end of words. Words are separated by spaces in the sentence.

```js
function remove(s) {
  return s.replace(/\b!+/g, '')
}

function remove(s) {
  return s.replace(/(\w)!+/g, '$1')
}
```

- [Authenticate a list of usernames](https://www.codewars.com/kata/authenticate-a-list-of-usernames/javascript)

<!-- HELP: -->

> Given an usernames, return true only if usernames comply with your company's guidelines. Return false otherwise.

- it is between 6-10 characters long;
- contains at least 1 lowercase letter;
- contains at least 1 number;
- contains only numbers and lowercase letters.

```js
function authList(x) {
  return /^(?=.*\d+)(?=.*[a-z])[a-z\d]{6,10}$/.test(x)
}
```

- [Anchorize me](https://www.codewars.com/kata/anchorize-me/train/javascript)

> Parse the text and replace Globally url with corresponding html syntax.Supported protocols: `http`,`https`,`ftp`,`ftps`,`file`,`smb`

        Example:
          Input: `hello http://world.com !`
          Output: `hello <a href="http://world.com">http://world.com</a> !`

```js
function anchorize(text) {
  var urlRegex = /((https?|ftps?|file|smb):[^\s]+)/gi
  return text.replace(urlRegex, `<a href="$1">$1</a>`)
}
```

- [Fruit string calculator](https://www.codewars.com/kata/fruit-string-calculator/javascript)

<!-- HELP: -->

        Example:
            "Panda has 48 apples and loses 4" returns 44
            "Jerry has 34 apples and gains 6" returns 40
            "loses" and "gains" are the only two words describing operators.

```js
function calculate(str) {
  return eval(
    str
      .match(/\d+|lose|gain/g)
      .join('')
      .replace('lose', '-')
      .replace('gain', '+'),
  )
}

function calculate(str) {
  const [op1, op2] = str.match(/\d+/gm)
  return /loses/.test(str) ? +op1 - +op2 : +op1 + +op2
}
```

- [Create sequence containing all allowed characters](https://www.codewars.com/kata/create-sequence-containing-all-allowed-characters/javascript)

<!-- HELP: -->

> Define createSequence(regex) function that returns a string of all characters (in ASCII order) matching specified regular expression one-character criterion.

```js
const createSequence = regex => {
  let seq = ''
  for (let i = 0; i < 256; i++) {
    if (regex.test(String.fromCharCode(i))) {
      seq += String.fromCharCode(i)
    }
  }
  return seq
}
```

- [Simple template](https://www.codewars.com/kata/simple-template/javascript)

<!-- HELP: -->

> Implement function createTemplate which takes string with tags wrapped in {{brackets}} as input and returns closure, which can fill string with data (flat object, where keys are tag names).

        Example
            let personTmpl = createTemplate("{{name}} likes {{animalType}}");
            personTmpl({ name: "John", animalType: "dogs" }); // John likes dogs

```js
function createTemplate(template) {
  return values => template.replace(/{{(\w+)}}/g, (_, foo) => values[foo] || '')
}
```

- [Are there doubles](https://www.codewars.com/kata/are-there-doubles/javascript)

<!-- HELP: -->

> Determines whether or not there are double characters in a string (including whitespace characters)

```js
function doubleCheck(str) {
  return /(.)\1/i.test(str)
}
```

- [Where's Wally](https://www.codewars.com/kata/wheres-wally)

> Write a function that returns the index of the first occurence of the word "Wally". "Wally" must not be part of another word, but it can be directly followed by a punctuation mark. If no such "Wally" exists, return -1.

```js
function wheresWally(str) {
  return (' ' + str).search(/ Wally\b/)
}
```

- [heggeleggleggo](https://www.codewars.com/kata/heggeleggleggo/javascript)

> Insert an "egg" after each consonant

```js
function heggeleggleggo(word) {
  return word.replace(/([^aeiou\s])/gi, '$1egg')
}
```

- [The old switcheroo](https://www.codewars.com/kata/the-old-switcheroo/javascript)

> Takes in a string and replaces all the vowels [a,e,i,o,u] with their respective positions within that string

```js
function vowel2index(str) {
  return str.replace(/[aeiou]/gi, (_, i) => i + 1)
}
```

## 👨 6kyu

- [Number Format](https://www.codewars.com/kata/number-format/train/javascript)

> Format any integer provided into a string with "," (commas) in the correct places.

<!-- HELP: -->

```js
function numberFormat(number) {
  return number.toLocaleString()
}

const numberFormat = number =>
  String(number).replace(/\d(?=(?:\d{3})+$)/g, '$&,')

const numberFormat = number =>
  String(number).replace(/(\d)(?=(\d{3})+$)/g, '$1,')

const numberFormat = number => String(number).replace(/\B(?=(\d{3})+$)/g, ',')
```

- [Braces status](https://www.codewars.com/kata/braces-status/train/javascript)

> Write a function that checks the braces status in a string, and return True if all braces are properly closed, or False otherwise. Available types of brackets: (), [], {}.

```js
const bracesStatus = s => {
  s = s.replace(/[^\(\)\[\]\{\}]/g, '')
  while (/\(\)|\[\]|\{\}/.test(s)) s = s.replace(/\(\)|\[\]|\{\}/g, '')
  return s.length < 1
}
```

- [extract file name](https://www.codewars.com/kata/extract-file-name/javascript)

```js
class FileNameExtractor {
  static extractFileName(s) {
    return s.replace(/^\d*_(.*)\..*$/, '$1')
  }
}

class FileNameExtractor {
  static extractFileName(s) {
    return s.match(/^\d+_([^.]+\.[^.]+)/)[1]
  }
}
```

- [Strip Url Params](https://www.codewars.com/kata/strip-url-params/javascript)

<!-- HELP: -->

> Removes any duplicate query string parameters from the url

> Removes any query string parameters specified within the 2nd argument (optional array)

```js
function stripUrlParams(url, paramsToStrip) {
  return url.replace(/&?([^?=]+)=.+?/g, function(m, p1, qPos) {
    return url.indexOf(p1 + '=') < qPos ||
      (paramsToStrip || []).indexOf(p1) > -1
      ? ''
      : m
  })
}
```

- [Creating a string for an array of objects from a set of words](https://www.codewars.com/kata/creating-a-string-for-an-array-of-objects-from-a-set-of-words/javascript)

```js
function wordsToObject(str) {
  return (
    '[' +
    str.replace(/(\S+) (\S+)/g, "{name : '$1', id : '$2'},").slice(0, -1) +
    ']'
  )
}
```

- [Validate my Password](https://www.codewars.com/kata/validate-my-password/train/javascript)

```js
function validPass(password) {
  return /^(?=.+[a-z])(?=.+\d)[a-z\d]{3,20}$/i.test(password)
    ? 'VALID'
    : 'INVALID'
}
```

### 👨‍🏫 5kyu

### 👨‍🌾 4kyu

### 👨‍🎓 3kyu
