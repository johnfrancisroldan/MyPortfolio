Here’s a markdown cheatsheet for Regular Expressions in Python:

```markdown
# Python Regular Expressions (Regex) Cheatsheet

## Importing `re` module

```python
import re
```

---

## Common Regex Patterns

| Pattern   | Description                                           | Example                       |
|-----------|-------------------------------------------------------|-------------------------------|
| `.`       | Matches any character except a newline                | `a.b` matches "acb", "a3b"    |
| `^`       | Matches the start of a string                         | `^Hello` matches "Hello World"|
| `$`       | Matches the end of a string                           | `world$` matches "Hello world"|
| `*`       | 0 or more repetitions of the preceding pattern        | `ab*` matches "a", "ab", "abb"|
| `+`       | 1 or more repetitions of the preceding pattern        | `ab+` matches "ab", "abb"     |
| `?`       | 0 or 1 repetition of the preceding pattern            | `ab?` matches "a", "ab"       |
| `{n}`     | Exactly `n` repetitions                               | `a{3}` matches "aaa"          |
| `{n,m}`   | Between `n` and `m` repetitions                       | `a{2,3}` matches "aa", "aaa"  |
| `[]`      | Matches any single character in brackets              | `[aeiou]` matches "a", "e", etc. |
| `|`       | Matches either of the patterns on each side           | `cat|dog` matches "cat" or "dog" |
| `()`      | Groups multiple patterns together                     | `(ab)+` matches "abab"        |
| `\`       | Escapes special characters or denotes special sequences | `\.` matches "."              |

---

## Special Sequences

| Sequence  | Description                                           | Example                        |
|-----------|-------------------------------------------------------|--------------------------------|
| `\d`      | Matches any digit (0-9)                               | `\d` matches "1", "5"          |
| `\D`      | Matches any non-digit                                 | `\D` matches "a", "!"          |
| `\w`      | Matches any alphanumeric character (letters, digits, underscore) | `\w` matches "a", "3", "_"   |
| `\W`      | Matches any non-alphanumeric character                | `\W` matches "!", " "          |
| `\s`      | Matches any whitespace (space, tab, newline)          | `\s` matches " "               |
| `\S`      | Matches any non-whitespace                            | `\S` matches "a", "1"          |
| `\b`      | Matches the empty string at the beginning or end of a word | `\bword\b` matches "word"      |
| `\B`      | Matches the empty string not at the beginning or end of a word | `\Bword\B` matches "swordplay"|

---

## Example Patterns

| Pattern              | Description                                           | Example                              |
|----------------------|-------------------------------------------------------|--------------------------------------|
| `^\d{3}-\d{2}-\d{4}$`| Matches a Social Security Number format               | `123-45-6789`                        |
| `\b[A-Za-z]{4,}\b`   | Matches words with 4 or more letters                  | "This is a test" -> Matches "This"   |
| `(\d{3})-(\d{3})-(\d{4})` | Matches a phone number and groups the sections     | `123-456-7890` -> Groups "123", "456", "7890" |

---

## Useful Functions

### `re.match()`
- Checks for a match only at the beginning of the string.

```python
result = re.match(r'\d+', '123abc')
print(result.group())  # Output: 123
```

### `re.search()`
- Searches the string for a match and returns the first occurrence.

```python
result = re.search(r'\d+', 'abc123xyz')
print(result.group())  # Output: 123
```

### `re.findall()`
- Returns a list of all matches in the string.

```python
result = re.findall(r'\d+', 'abc123xyz456')
print(result)  # Output: ['123', '456']
```

### `re.sub()`
- Replaces one or many matches with a string.

```python
result = re.sub(r'\d+', 'NUMBER', 'abc123xyz')
print(result)  # Output: abcNUMBERxyz
```

### `re.split()`
- Splits the string at each match.

```python
result = re.split(r'\d+', 'abc123xyz456')
print(result)  # Output: ['abc', 'xyz', '']
```

---

## Flags for Modifiers

| Flag     | Description                                           | Example                             |
|----------|-------------------------------------------------------|-------------------------------------|
| `re.IGNORECASE` or `re.I` | Ignores case (case-insensitive matching) | `re.search(r'hello', 'HELLO', re.I)`|
| `re.DOTALL` or `re.S`     | Makes the `.` match all characters, including newlines | `re.search(r'.+', 'a\nb', re.S)`|
| `re.MULTILINE` or `re.M`  | Makes `^` and `$` match the start and end of each line | `re.search(r'^abc', 'abc\ndef', re.M)`|

---

## Escaping Special Characters

To use a special character like `.`, `*`, `+`, etc., as a literal character, you must escape it with a backslash (`\`).

```python
result = re.search(r'\.', '3.14')
print(result.group())  # Output: .
```

---

This cheatsheet provides a quick reference for common regular expression patterns and methods in Python. With these basics, you can start using regex to perform powerful pattern matching and string manipulation!
```

This markdown file offers a concise overview of regex in Python, including syntax, functions, and examples, all formatted for easy reference.