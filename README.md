# REGEX MASTER

### 8kyu

- [Regex count lowercase letters
  ](https://www.codewars.com/kata/regex-count-lowercase-letters/javascript)

> count the total number of lowercase letters in a string.

        function lowercaseCount(str) {
          return (str.match(/[a-z]/g) || []).length
        }

        function lowercaseCount(str) {
          return str.replace(/[^a-z]/g, '').length
        }

- [Simple validation of a username with regex](https://www.codewars.com/kata/simple-validation-of-a-username-with-regex/javascript)

> Write a simple regex to validate a username. Allowed characters are: `lowercase letters` or `numbers` or `underscore`. Length should be between 4 and 16 characters

        function validateUsr(username) {
          return /^[0-9a-z_]{4,16}$/.test(username)
        }

### 7kyu

- [Remove consecutive duplicate words](https://www.codewars.com/kata/remove-consecutive-duplicate-words/javascript)

  <!-- HELP: -->

  > Remove all consecutive duplicate words from string, leaving only first words entries.

        function removeConsecutiveDuplicates(str) {
          return str.replace(/\b(\w+)(?: \1)+\b/g, '$1')
        }

- [Regex validate PIN code](https://www.codewars.com/kata/regex-validate-pin-code/javascript)

> ATM machines allow 4 or 6 digit PIN codes and PIN codes cannot contain anything but exactly 4 digits or exactly 6 digits.

        function validatePIN(pin) {
          return /^(\d{4}|\d{6})$/.test(pin)
        }
