https://user-images.githubusercontent.com/6392321/160298183-799a26ad-8435-4a9c-8171-e7b711cf4e47.mp4




browser extension for bionic reading

# How to install

1. git clone https://github.com/casey-barr/chrome-fastread.git
2. Follow https://developer.chrome.com/docs/extensions/mv3/getstarted/#unpacked

# Algorithm Specification
Algorithm is customizable using a string similar to this:
```
- 0 1 1 2 0.4
```
The first character can be either `-` or `+`. If it is `-`, we don't highlight common english words (for example 'a', 'and', etc.) if it is '+' we highlight all words.
 
```
- 0 1 1 2 0.4
  ^
```
This specifies the number of highlighted characters for words with length 1. For example 'a' and 'I'. Here we have specified that we don't want to highlight these characters.
```
- 0 1 1 2 0.4
    ^
```
This specifies the number of highlighted characters for words with length 2. For example 'an' and 'or'. Here we have specified that we highlight the first character of these words.
```
- 0 1 1 2 0.4
      ^
```
Highlight the first character of 3 letter words.
```
- 0 1 1 2 0.4
        ^
```
Highlight the first two character of 4 letter words.
```
- 0 1 1 2 0.4
           ^
```
Unlike the previews entries, the last entry is a fractional value between 0 and 1 which specified which fraction of words that are not specified by previous rules must be highlighted.
For example, here we highlight the first 40% characters of words with 5 or more characters.
