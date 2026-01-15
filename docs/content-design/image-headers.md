---
title: Header Examples
layout: xanthan
date: 2024-10-24
header-image: /assets/images/backgrounds/pano-1.jpg 
---

# Image Header Examples
This page shows various ways you can use header images on your pages. The blue code boxes show what code you can copy and paste on to your page, and the result shows up just underneath it. 


## Page header
It's common to include a large image at the top of the page. In the YML header at the top of the page, include something like `header-image: images/image_name.jpg`. The YML header for this page is:

```
---
title: Image Examples
layout: xanthan
date: 2025-09-13
header-image: /assets/images/backgrounds/pano-1.jpg 
---
```

Optionally, you can also include `header-height` and/or `header-position` to better control your image. 
`header-height`: controls the height in whatever units you specify
`header-position`: controls what part of the image is visible

`header-position` is useful if you have a large image but only the middle part is what you want to see in the header. 


```
---
title: Image Examples
layout: xanthan
date: 2025-09-13
header-image: /assets/images/backgrounds/pano-1.jpg
header-height: 50vh
header-position: 200px
---
```



## Section Header Images
The [images page](images) shows how to create jumbotron images on your page that span the whole browser window. You can also use jumbotrons as a section divider. Optionally, you can add a title, subtitle, and control the background position.

**Available parameters:**
- `height`: controls the height (default: 40vh)
- `image-path`: path to your image
- `title`: optional heading text
- `subtitle`: optional subtitle text
- `background-position`: controls what part of the image is visible (e.g., "center", "top", "200px", "50% 80%")

```
{% raw %}
{% include images/jumbotron.html
  height="30vh"
  image-path="/assets/images/backgrounds/pano-1.jpg"
  title="Section Heading"
  subtitle="Your subtitle goes here"
  background-position="center"
%}
{% endraw %}
```


{% include images/jumbotron.html
  height="30vh"
  image-path="/assets/images/backgrounds/pano-1.jpg"
  title="Section Heading"
  subtitle="Your subtitle goes here"
%}


##  Peekaboo Headers
You can see that the section header above is basically embedded on the scrolling page. This means it keeps its relative position to the text and scrolls up and down with everything else. We can create the effect of the header revealing parts of a larger image behind it as the page scrolls up. This is what's happening as you scroll now:

```
{% raw %}
{% include scrollybox/bg.html
  height="40vh"
  image-path="/assets/images/backgrounds/pano-1.jpg"
%}
{% endraw %}
```

{% include scrollybox/bg.html
  height="40vh"
  image-path="/assets/images/backgrounds/pano-1.jpg"
%}



## That's a wrap 
That's all for basic headers. 
