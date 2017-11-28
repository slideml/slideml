# Slide Markup Language Specification

_Draft_. updated at 2017.11.28

## 1. General Design

SlideML is a HTML-like file. One SlideML file is a slide file. Here is the structure:

* `slideml` Root node
  * `layout` master slides
  * `theme` (s)css style
  * `slides` slide list

A SlideML file normally like below. You can refer the [sample](sample.slideml) for an idea.

```xml
<slideml version="Draft">
  <layout aspectratio="16x9">
    <master id="title" name="" slidenumber="hide">
      <h1><placeholder type="text" id="title">Title</placeholder></h1>
    </master>
    <!-- More master slide definitions -->
  </layout>

  <theme type="scss">
    $branding-color: #ff00ff;
    master {
      background-color: $branding-color;
      h1 {
        color: $branding-color;
      }
    }
    <!-- More (s)css rules-->
  </theme>

  <slides>
    <slide master="title">
      <fill placeholder="title">An introduction to SlideML</fill>
      <fill placeholder="subtitle">by Michael Chen, 2017</fill>
    </slide>

    <!-- More slides-->

  </slides>

</slideml>
```

Note: a SlideML file contains everyting. Layout, theme and slides. This design to encourge that people share the whole file out without worry about extracting a *template* like Powerpoint. Future SlideML files can **inherit** from the layout and theme by using `inherit`.

## 2. Terms

### Master slide

This is exactly the term of Keynote/Powerpoint. In SlideML, slides don't decorate themselves, master does. a master slide defined in `master`, can have multiple `placeholder` for the `slide` to fill in.

You may imagine `placeholder` like holes on a paper. The master defines where to put content with what style, and the slide will put the concret content in. By using this way, we seperate the design and content. And there is a possibility of upgrading design without break content and vice-versa.

`layout` can also be referenced outside like this:

```xml
<layout inherit="branding-template.slideml">
  <!-- master slides in the branding-template.slideml will be inherited -->
  <!-- You can also override or write more master slide here -->
</layout>
```

By using this way, you can re-use the existing master slide without copy and paste PPT/Keynote file again and again.

Each master will have markups and `placeholder`s. Placeholder can be `text`, `image`, or `iterator`.

### Theme

`theme` is simply css, or scss. `theme` can be also inherited like this:

```xml
<theme inherit="brand-template.slideml">
  <!-- Only the theme part will be inherited here. -->
  <!-- You can also write more, override existing css rules -->
</theme>
```

### Slides

Slides are full of `fill`s and other standard HTML tags if needed.

```xml
<slides>
  <!--refer the master slide defined in layout-->
  <slide master="title">
    <fill placeholder="title">An introduction to SlideML</fill>
    <fill placeholder="subtitle">by Michael Chen, 2017</fill>
  </slide>
</slides>
```

Thinking about the holes of the paper again. slide is basically fill in the holes defined in `master`.

### 3. Supported HTML Tags

All visiable tags are supported. Form/input tags are not supported. `style` not supported.

List of supported tags:

* `h1` to `h6`
* `p`, `br`, `hr`
* abbr, address, strong, blockquote, cite, code, del, i, ins, kdb, mark, meter, pre, progress, q, s, small, sub, sup, time, u
* img, figure, figcaption
* audio, source, track, video
* a, link, nav
* ul, ol, li, dl, dt, dd, menu, menuitem
* table, caption, th, tr, td, tbody, thead, tfoot, col, colgroup
* div, span, header, footer, main, section, article, aside


