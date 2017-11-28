# Slide Markup Language (SlideML)

Until today, Slides are the #1 tool to create presentations. People create slides to do presentations, business showcase, VC pitches etc. However, using tool like Powerpoint/Keynote is still a pain.

* Slides are difficult to keep consistent design across the team.
* When creating a slide, it's hard for the author to create content as well as make good looking.
* There are thousands of slide teamplates over the internet, however it's hard to use especially apply to your own brand style.
* Difficult to collaborate. (Well, you can by using Office 365 / Keynote with iCloud but that's not how people normally work)
* Impossible to track changes or versional control as they are all binary format.

There are some solutions on the market. Like [S5](https://meyerweb.com/eric/tools/s5/), [Prezi](https://prezi.com/), [REVEAL.JS](https://revealjs.com/), [impress.js](http://impress.github.io/impress.js/), they provide HTML based solutions. Each of them focusing part of the problems but they missing the key features like master layout, theme support etc. Thus it's difficult to create unique beautiful slides, or create mediocre slides if you give up customization using css.

Here comes SlideML.

## Design Goals

The goal of this project is to create standard markup language for slides. It comes with following goals:

* It should be plain text. So that it can be version tracked by version control software.
* It  should separate layout, theme and slides. Then there is a chance for designers, marketers and content authors focus their own part.
* It should be tooling friendly. By using either a simple text editing tool like Atom/Sublimtext, or another home made Wysiwyg design tool.
* It should leverage the existing open standards like html, css.
* It should be easy to learn.


## Spec

[Read Spec →](slideml-spec.md)

## Contribution Welcome

Currently, there is no reference implementation. Ideas around this will be:

* A command line tool to validate, convert SlideML to PDF. (or HTML, PPT, ODF etc)
* An online community can download the master files.
* An IDE to edit the SlideML.

You are more than welcome to create one. Drop me a line if you create one or want to create on under `github.com/slideml`.

You can also contribute to this repository. Simply fork it and send a PR.

