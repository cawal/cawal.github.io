---
layout: post
title:  "Timeline in Markdown"
date:   2017-10-13 00:22:00 -0300
categories: markdown
---

I've adapted the [CodeMyUI's pure CSS timeline](https://gist.github.com/CodeMyUI/d5a6a6d98251de21b934c7c577cce147) for creating timelines in Jekyll-based blog posts (kramdown, essentially). The new CSS allows the user to create the timeline by defining a markdown table.

To create timelines (assuming the user uses the default configurations for SASS in jekyll), the user must copy the [timeline SCSS file](https://github.com/cawal/cawal.github.io/blob/master/_sass/_timeline.scss) to the `_sass`folder of his Jekyll blog. Then, the user must add this file in the `@import` declaration in the `css/main.scss` file, also adding the following variable declarations to the `css/main.scss` file PRIOR to the `@import` declaration.

```sass
$timeline-background-color: $background-color;
$timeline-rule-color: $grey-color;
$timeline-font-family: $base-font-family;

$timeline-event-background-color: $timeline-background-color;
$timeline-event-border-color: $grey-color-dark;
$timeline-big-event-background-color: $timeline-event-background-color;

$timeline-entry-title-color: $grey-color-dark;
$timeline-entry-body-color: $grey-color;
```

Note I'm reusing some variables existing in the default Jekyll theme. Fell free to change them.

With the CSS set, the user must create a markdown table in some page. In this table, the first cell of each line will be the title of the timeline entry, while the second cell of each row will be the body of the entry. Finally, the user must add the CSS class `.timeline-md` to the table using the `{: .timeline-md}` syntax. This will allow to create a table similar to this one...

```markdown
| 11,988 |  Hari Seldon and Cleon I are born on Helicon and Trantor, respectively. |
| 12,020 | Hari Seldon arrives on Trantor to deliver his paper outlining his theory of psychohistory, a method of predicting the future along mass social change in humanity. (Events of Prelude to Foundation) |
| 12,067 | Hari Seldon goes on trial by the Commission of Public Safety, and the Encyclopedia Galactica Foundation is exiled to/established on Terminus (Events of "The Psychohistorians" in Foundation) |
| 12,069 | Hary Seldon dies. |
{: .timeline-md}
```

... and to obtain a timeline similar to this one...

| 11,988 |  Hari Seldon and Cleon I are born on Helicon and Trantor, respectively. |
| 12,020 | Hari Seldon arrives on Trantor to deliver his paper outlining his theory of psychohistory, a method of predicting the future along mass social change in humanity. (Events of Prelude to Foundation) |
| 12,067 | Hari Seldon goes on trial by the Commission of Public Safety, and the Encyclopedia Galactica Foundation is exiled to/established on Terminus (Events of "The Psychohistorians" in Foundation) |
| 12,069 | Hary Seldon dies. |
{: .timeline-md}

No ordering or other features are provided.

(Table data based in the [Wikipedia article for the Foundation Series](https://en.wikipedia.org/wiki/Foundation_series))
