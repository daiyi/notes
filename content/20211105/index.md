---
title: "Joining the dark [mode] side"
date: 2021-11-05T18:05:53-07:00
tags:
  - web dev
  - computer stuff
---

I pretty much dismissed dark mode until enough apps and sites starting supporting it such that the chaotic thrashing between dark themes and white themes is disturbing the peace of quiet nighttime reading. Today I join the dark [mode] side by seeing how fast I could hack together a dark support for my [blorg](https://daiyi.co/blog/) \o/

## home page

<div class="album">
<div class="photos">
{{< figure src="home-light.jpeg" alt="blog home page: light" imgclass="border" >}}
{{< figure src="home-dark.jpeg" alt="blog home page: dark" >}}
</div>
</div>

## blog post

<div class="album">
<div class="photos">
{{< figure src="post-light.jpeg" alt="blog post page: light" imgclass="border" >}}
{{< figure src="post-dark.jpeg" alt="blog post page: dark" >}}
</div>
</div>

## yay media queries

I think it looks pretty good! and only took like an hour or so to refactor the colours into variables, not as painful as I thought it would be. Something like:

```css
:root {
  --background: #fff;
  --text: #222;
}

@media (prefers-color-scheme: dark) {
  :root {
    --background: #222;
    --text: #ddd;
  }
}

body {
  background: var(--background);
  color: var(--text);
}
```

And I found a nice lil button in the dev tools to force toggle light and dark 👀

{{< figure src="devtools.jpg" alt="toggle dark/light in devtools" imgclass="border" >}}
