---
title: fighting with zalgo spam
thumbnail: /img/zalgo.png
date: 2020-10-20 23:56:34
comments: true
categories:
- [webdev, ui]
tags:
- unicode
- ui
---

In short,

zalgo text: https://stackoverflow.com/questions/6579844/how-does-zalgo-text-work
extra: http://archives.miloush.net/michkap/archive/2010/04/28/10002896.html

the problem: is in the thumbnail

there might be many solution, but none of them really works all the time. just removing diacritics or combine characters won't solve the problem. and striping or Modifying user submitted text should have strong reasons. this is not one of them. imagine if Stack overflow sanitized the content of that question, OP would have to submit a screenshot to describe the **thing**

solution:

```css
p, span, .whatever {
    display: block; // overflow: hidden won't work otherwise
    overflow: hidden;
}
```

set line-height as needed, as much you want to be visible

and also you may want to set overflow: visible on :hover

now, let pips do whatever they want.. like using username/handle: ส็็็็็็็็็็็็็็็็็็็audacioustuxส
