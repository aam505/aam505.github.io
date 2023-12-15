---
title: "Markdown tutorial"
weight: 6
date: 2019-12-23T20:56:42+06:00
type: portfolio
image: "images/projects/project-thumb-four.jpg"
category: ["Interaction Design"]
project_images: []
pygmentsUseClasses: false               # Use CSS instead of inline styling
pygmentsStyle: monokai                  # Inline style to use
pygmentsCodefencesGuessSyntax: true     # Guess language if not provided
pygmentsUseClassic: false               # Use pygments instead of chroma
pygmentsOptions: "linenos=true"         # Parameters to pass to pygments
---

H2
---

* This is a list element
+ This is also a list element
- This is also a list element
 - This is a sublist element
 + Also a sublist element
     + Sublist level 2
     1. Numbered sublist
     2. Next item
        3. Next indent level

1. Numbered sublist
2. Next item
     1. Next indent level
        * Sublist non numbered
3. Back

Horizontal Lines:
------------------------------------
***********************************
***
---

> Block Quote



#Just a hash tag
Also a # tag.
# Alternate H1
## Alternate H2


###### H6

Text formatting
=============



### Italics h3
*Italics*

#### Italics h4
_Italics_

#### Bold h5
__Bold__


##### Bold+italics h6
___Bold+Italics___

this_is_not_emphasis

~~Strikethough~~

Content with a -- (dash) and a --- (long dash).

[link](http://link/path/to/target)

[link](http://link/path/to/target "TITLE ON LINK")

[Shared Links with footnotes][target 1]

[Second shared link][target 1]

[target 1]

[target 1]: http://footnote.com

Sample inline code `a++` can be specified here.

![Alt Text](/images/projects/ff/car-banner-ff.png "Optional Tooltip")




The “Seamless Watch” watch has all the features that users expect in a digital watch, and some unusual features.

# using HTML in markdown 
HTML Escaped characters:

Copyright: &copy;

Registered: &reg;

Trademark: &trade;

Less Than: &lt;

Greater Than: &gt;

Ampersand: &amp;

Smiley: &#x1F604;

Embedded HTML: x<sup>2</sup>
<img src="/favicon.png">

Floating image via HTML: <img src='favicon.png'> Follow up text after the image. This honors the floats and wraps around the image, automatically going into the next line.


# tables
Table:

   Name | Job
--------|------
   Alex | Web Developer
    Bob | Sys Admin
   Gabby| Technical Writer

Alternate Table:

|  Name | Mantra |
|  ---  |   ---  |
| Alex  | There must be a better way. |
| Bob   | Play it safe. |
| Gabby | Try everything, but do what you like. |

Acme Website task list
- [x] Get the home page up
- [x] Update Privacy Policy and Terms of Use
- [ ] Add the about page
- [ ] Start the blog
- [ ] Enable contact us

```js
var x= 10;
x++;
console.log(x);
```

# others
## Direct Emojis
Smile please :smile:

I :heart: Hugo

Wink :wink:


## Fractions

1/2

100/999

Not a Number/5

A link to [Fractions](#fractions)


## Definition Lists

Alex
: Hippy Web Developer
: Technophile

Bob
: Classic SysAdmin
: Conservative

Gabby
: Cool Content Master
: Cautious