% Pandoc Test Suite
% John MacFarlane; Anonymous
% July 17, 2006

This is a set of tests for pandoc.  Most of them are adapted from
John Gruber's markdown test suite.

-----

# Headers

## Level 2 with an [embedded link](/url)

### Level 3 with another [embedded link](/url)

#### Level 4

##### Level 5

Level 1
=======

Level 2 with *emphasis*
-----------------------

### Level 3
with no blank line

Level 2
-------
with no blank line

# Paragraphs

Here's a regular paragraph.

In Markdown 1.0.0 and earlier. Version
8. This line turns into a list item.
Because a "hard-wrapped line in the"
middle of a paragraph looked like a
list item.

Here's one with a bullet.
* criminey.

There should be a hard line break\
here.

# Block Quotes

E-mail style:

> This is a block quote.
> It is pretty short.

> Code in a block quote:
>
>     sub status {
>         print "working";
>     }
>
> A list:
>
> 1. item one
> 2. item two
>
> Nested block quotes:
>
> > nested
>

This should 'not' be a block quote: 2
> 1.

And a following paragraph.

# Code Blocks

Code:

    ---- (should be four hyphens)

    sub status {
        print "working";
    }

	this code block is indented by one tab

And:

		this code block is indented by two tabs

    These should not be escaped:  \$ \\ \> \[ \{

___________

# Lists

## Unordered

-	Minus 1
-	Minus 2
-	Minus 3

## Ordered

Tight:

1.	First
2.	Second
3.	Third

and:

1. One
2. Two
3. Three

Multiple paragraphs:

1.	Item 1, graf one.

	Item 1. graf two. The quick brown fox jumped over the lazy dog's
	back.

2.	Item 2.

3.	Item 3.

## Nested

*	Tab
	*	Tab
		*	Tab

Here's another:

1. First
2. Second:
	* Fee
	* Fie
	* Foe
3. Third

Same thing but with paragraphs:

1. First

2. Second:

	* Fee
	* Fie
	* Foe

3. Third

## Tabs and spaces

+	this is a list item
	indented with tabs

+   this is a list item
    indented with spaces

	+	this is an example list item
		indented with tabs

	+   this is an example list item
	    indented with spaces

## Fancy list markers

(2) begins with 2
(3) and now 3

    with a continuation

    iv. sublist with roman numerals,
        starting with 4
    v.  more items
        (A)  a subsublist
        (B)  a subsublist

Nesting:

A.  Upper Alpha
    I.  Upper Roman.
        (6) Decimal start with 6
            c)  Lower alpha with paren

Autonumbering:

#. Autonumber.
#. More.
   #. Nested.

Should not be a list item:

M.A. 2007

B. Williams

----

# Definition Lists

Tight using spaces:

apple
:   red fruit

orange
:   orange fruit

banana
:   yellow fruit

Tight using tabs:

apple
:	red fruit

orange
:	orange fruit

banana
:	yellow fruit

Multiple blocks with italics:

*apple*

:   red fruit

    contains seeds,
    crisp, pleasant to taste

*orange*

:   orange fruit

        { orange code block }

    > orange block quote

Multiple definitions, tight:

apple
:   red fruit
:   computer

orange
:   orange fruit
:   bank

Multiple definitions, loose:

apple

:   red fruit

:   computer

orange

:   orange fruit

:   bank

Blank line after term, indented marker, alternate markers:

apple

  ~ red fruit

  ~ computer

orange

  ~ orange fruit

    1. sublist
    2. sublist

# Inline Markup

This is *emphasized*, and so _is this_.

This is **strong**, and so __is this__.

An *[emphasized link](/url)*.

***This is strong and em.***

So is ***this*** word.

___This is strong and em.___

So is ___this___ word.

This is code: `>`, `$`, `\`, `\$`, `<html>`.

~~This is *strikeout*.~~

Superscripts:  a^bc^d a^*hello*^ a^hello\ there^.

Subscripts: H~2~O, H~23~O, H~many\ of\ them~O.

These should not be superscripts or subscripts,
because of the unescaped spaces:  a^b c^d, a~b c~d.

-----

# Smart quotes, ellipses, dashes

"Hello," said the spider.  "'Shelob' is my name."

'A', 'B', and 'C' are letters.

'Oak,' 'elm,' and 'beech' are names of trees.
So is 'pine.'

'He said, "I want to go."'  Were you alive in the
70's?

Here is some quoted '`code`' and a "[quoted link][1]".

Some dashes:  one---two --- three---four --- five.

Dashes between numbers: 5--7, 255--66, 1987--1999.

Ellipses...and...and....

-----

# LaTeX

- $2+2=4$

These shouldn't be math:

- To get the famous equation, write `$e = mc^2$`.
- $22,000 is a *lot* of money.  So is $34,000.
  (It worked if "lot" is emphasized.)
- Shoes ($20) and socks ($5).
- Escaped `$`:  $73 *this should be emphasized* 23\$.

* * * * *

# Special Characters

Here is some unicode:

- I hat: Î
- o umlaut: ö
- section: §
- set membership: ∈
- copyright: ©

AT&T has an ampersand in their name.

AT&amp;T is another way to write it.

This & that.

4 < 5.

6 > 5.

- - - - - - - - - - - - -

# Links

## Explicit

Just a [URL](/url/).

[URL and title](/url/ "title").

[Email link](mailto:nobody@nowhere.net)

[Empty]().

## Reference

Foo [bar][a].

[a]: /url/

With [embedded [brackets]][b].

[b] by itself should be a link.

Indented [once][].

This should [not][] be a link.

[once]: /url

[b]: /url/

Foo [bar][].

Foo [biz](/url/ "Title with "quote" inside").

  [bar]: /url/ "Title with "quotes" inside"

## With ampersands

Here's a [link with an ampersand in the URL][1].

Here's a link with an amersand in the link text: [AT&T][2].

Here's an [inline link](/script?foo=1&bar=2).

Here's an [inline link in pointy braces](</script?foo=1&bar=2>).

[1]: http://example.com/?foo=1&bar=2
[2]: http://att.com/  "AT&T"

## Autolinks

With an ampersand: <http://example.com/?foo=1&bar=2>

* In a list?
* <http://example.com/>
* It should.

An e-mail address:  <nobody@nowhere.net>

> Blockquoted: <http://example.com/>

Auto-links should not occur here: `<http://example.com/>`

    or here: <http://example.com/>

----

# Images

From "Voyage dans la Lune" by Georges Melies (1902):

![The famous moon still from Georges Méliès's Le Voyage dans la Lune][lalune]

[lalune]: lalune.jpg "Voyage dans la Lune"

Here is a movie ![icon of a movie](movie.jpg) icon.

----

# Footnotes

Here is a footnote reference,[^1] and another.[^longnote]
This should *not* be a footnote reference, because it
contains a space.[^my note]  Here is an inline note.^[This
is *easier* to type.  Inline notes may contain
[links](http://google.com) and `]` verbatim characters,
as well as [bracketed text].]

> Notes can go in quotes.^[In quote.]

1.  And in list items.^[In list.]

[^longnote]: Here's the long note.  This one contains multiple
blocks.

    Subsequent blocks are indented to show that they belong to the
    footnote (as with list items).

        def code():
            some_code

    If you want, you can indent every line, but you can also be
    lazy and just indent the first line of each block.

This paragraph should not be part of the note, as it is not indented.

  [^1]: Here is the footnote.  It can go anywhere after the footnote
  reference.  It need not be placed at the end of the document.
