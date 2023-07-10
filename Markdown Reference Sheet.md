## Create web links
You can create an inline link by wrapping link text in brackets [ ], and then wrapping the URL in parentheses ( ). You can optionally add a title for the link. This will appear as a tooltip when you hover over the link.

Syntax: 
`[link text](http://url "Title")`

Example:
`[Google](https://www.google.com "Google Home")`

## Create Headers

Headers are created by using the hash (#) symbol before your header text. The number of hashes indicates the level of the header. There are six levels of headers that you can use.

Syntax: 
`# H1`
`## H2`
`### H3`
`#### H4`
`##### H5`
`###### H6`

## Bold and Italic Text

You can make text bold or italic.

Syntax for bold: 
`**bold text**`

Syntax for italic: 
`*italicized text*`

## Insert Images

You can insert images using similar syntax to inserting links. 

Syntax:
`![Alt Text](url)`

Example:
`![Markdown Logo](https://markdown-here.com/img/icon256.png)`

## Create Lists

You can create two types of lists in markdown - ordered and unordered.

For an unordered list, prefix each line with either *, -, or +.
```
* Item 1
* Item 2
* Item 3
```

For an ordered list, prefix each line with a number.
```
1. Item 1
2. Item 2
3. Item 3
```

## BlockQuotes

If you need to call special attention to a quote from another source, or design a pull quote for a magazine article, then Markdown’s blockquote syntax will be useful. 

Syntax:
>`This is a blockquote.`

## Inline Code & Code Blocks

If you want to share code snippets, Markdown makes it easy with inline code blocks.

Single backticks ` are used for inline code blocks.

Triple backticks ``` are used for multiline code blocks.

Example:
\```python
def hello_world():
    print("Hello World!")
\```