# REGEX MASTER

### 8kyu

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

### 7kyu

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
