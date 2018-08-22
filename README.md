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
