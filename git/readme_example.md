# Basic writing and formatting syntax of the README.md

See link [Basic writing and formatting syntax](https://help.github.com/articles/basic-writing-and-formatting-syntax/).
Or see that one - [Markdown: Syntax](https://daringfireball.net/projects/markdown/syntax#backslash).

__________________________________________________________________________________________

## Ignoring Markdown formatting

You can tell GitHub to ignore (or escape) Markdown formatting by using \ before the Markdown character.

__________________________________________________________________________________________


## Headings

To create a heading, add one to six # symbols before your heading text. The number of # you use will determine the size of the heading. 

\### Heading 
### Heading 
__________________________________________________________________________________________

## Styling text

You can indicate emphasis with bold, italic, or strikethrough text:

bold \**some text\** or \_\_some text\_\_ - **some text**

italic \*some text\* or \_some text\_ - *some text*

strikethrough \~\~some text\~\~ - ~~some text~~
__________________________________________________________________________________________

## Quoting text

You can quote text with a >.

\> Pardon my French

> Pardon my French
__________________________________________________________________________________________

## Images

Format: \!\[ Alt Text \] \(url\)

![GitHub Logo](https://assets-cdn.github.com/images/modules/logos_page/GitHub-Mark.png)
__________________________________________________________________________________________

## Inline code

I think you should use an
`<addr>` element here instead.

I think you should use an
\` \< addr \> \` element here instead.
__________________________________________________________________________________________

## Quoting code

You can call out code or a command within a sentence with single backticks. The text within the backticks will not be formatted.

\```

git status

git add

git commit

\```
```
git status
git add
git commit
```
__________________________________________________________________________________________

## Links

You can create an inline link by wrapping link text in brackets [ ], and then wrapping the URL in parentheses ( ).

This site was built using \[ GitHub Pages \] \( https://pages.github.com/ \).

This site was built using [GitHub Pages](https://pages.github.com/).

…you can use a relative link:

\[a relative link\]\(other_file.md\)

[a relative link](other_file.md)
__________________________________________________________________________________________

## Lists

You can make an unordered list by preceding one or more lines of text with - or *.

- George Washington
- John Adams
- Thomas Jefferson


### Nested Lists

You can create a nested list by indenting one or more list items below another item.

To create a nested list using the web editor on GitHub or a text editor that uses a monospaced font, like Atom, you can align your list visually. Type space characters in front of your nested list item, until the list marker character (- or *) lies directly below the first character of the text in the item above it.
__________________________________________________________________________________________

## Task lists

To create a task list, preface list items with [ ]. To mark a task as complete, use [x].

- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request
__________________________________________________________________________________________

## Using emoji

You can add emoji to your writing by typing :EMOJICODE:.

\: +1 \: This PR looks great - it's ready to merge! \: shipit \:

:+1: This PR looks great - it's ready to merge! :shipit:

Rendered emoji

Typing : will bring up a list of suggested emoji. The list will filter as you type, so once you find the emoji you're looking for, press Tab or Enter to complete the highlighted result.
__________________________________________________________________________________________


## Tables

You can create tables by assembling a list of words and dividing them with hyphens - (for the first row), and then separating each column with a pipe |:

First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column







