<p>Markdown codes are known with .md or .markdown formats.</p>
Remember to use 'bierner.markdown-preview-github-styles' extension to see a live preview of this markdown file.

<!-- heading -->
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
<h2><i>HTML</i> syntaxes work here as well</h2>

<!-- italic -->
*this text is italic*
<br>
_this text is italic_

<!-- bold -->
**this text is bold**

__this text is bold__

<!-- emphasis -->
this text ***is very important***, so it's both italic and bold.

<!-- Block quotes -->
> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.  
> This will be a new line since I used two spaces after the previous line and THEN hit the 'enter' of my keyboard. 
> In this line, however, i just used 'enter' key without two or more spaces at the end of the previous line. so you can see the difference.  
> So, this is how we create break lines in MarkDown!


<!-- link -->
Visit the following website to learn more about markdown language
[Website](https://www.markdownguide.org/basic-syntax/#blockquotes-1, 'markdownguide')

Also, checkout this 
[Tutorial](https://www.mongard.ir/one_part/145/python-markdown/, 'Mongard')
to learn how to work with markdown files in python and convert them into HTML.

<!-- unordered lists  -->
<!-- (characterized by *, -, + characters. using tabs, we can create nested lists.) -->
+ first
  + one
  * two
  * three
+ second
- third
* fourth

<br>
<br>

<!-- ordered lists -->
<!-- (characterized by numbers. using tabs, we can create nested lists.) -->
1. first
   1. one
   2. two
2. second
3. third

<!-- code snippets -->
```python
    pint('hello world')
    pint('hello world')
    pint('hello world')
```

```html
<h1> hello world <h1>
<p> this is my lorem ispum </p>
```

Use double dollar signs for mathematical expressions. e.g.:
$$
1 = 2 * 3
$$

You can use keyboard shortcuts to insert some special snippets in your markdown file.
For instance, using ctrl+b creates a **bold** snippet or ctrl+I creates a *italic* one.
You can browse for more of these shortcuts by searching the following command in VSCode's 
command palette (ctrl+shift+p):
`Snippets: insert snippet`