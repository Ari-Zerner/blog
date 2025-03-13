---
title: "Adding Sidenotes"
date: 2024-10-07
draft: false
---

Inspired by some other blogs I like, I decided I wanted to add hovering previews to the footnotes on my own site[^1]. This turned out to be surprisingly complex! First, I asked ChatGPT for a simple plug-and-play solution. When it didn't have one and the code it suggested didn't work, I turned to [Manicode](https://jamesgrugett.com/p/announcing-manicode-v0). Sadly for me, Manicode also struggled; despite several iterations of prompting and troubleshooting, Manicode couldn't find a solution that worked. I was going to have to dive into the issue myself.

I wasn't the first to run into this problem. A quick Google search turned up this [Hugo forum post](https://discourse.gohugo.io/t/how-to-add-title-tooltip-with-footnote-content-to-footnote-link/25498), which in turn linked to this [Github discussion](https://github.com/gohugoio/hugo/issues/7291#issuecomment-630621888). As I understood it, Hugo uses a rendering engine called Goldmark, which has the capability to display footnote previews. However, enabling that functionality would necessitate bringing in heavy rendering features that would impact performance, so the Hugo team decided to exclude it. At this point, the most promising approach seemed to be writing custom Javascript to implement the functionality. I was a little nervous about that, because LLMs had already failed at that, and I didn't have much JS experience to draw on beyond theirs, but the best way to learn is by doing!

To get oriented, I inspected an existing footnote. It looked like this:
```html
<sup id="fnref:1">
    <a href="#fn:1" class="footnote-ref" role="doc-noteref">1</a>
</sup>
```
One somewhat hacky option at this stage would have been to use JS to populate a title attribute with the footnote content. However, I didn't want to put my efforts into that until I ruled out solutions that would look better. More Googling was required.

My Googling found an alternative that I hadn't thought of: sidenotes. Instead of giving footnote references hoverable previews, I could rework the way they appear to begin with. {{< sidenote "Sidenotes look like this." >}}Instead of displaying at the bottom of the page, sidenotes display in the margin of the text where they appear. On mobile devices and other small screens, there is no margin, so tapping expands/collapses a sidenote.{{< /sidenote >}} The main downside, as I saw it, would be clunkier syntax when writing posts, but following the principle of "write once, read many", I decided that was a fine cost if it improved the reading experience for my audience. For the implementation of sidenotes, I drew heavily from this [blog post](https://0xda.de/blog/2024/07/hugo-sidenotes-shortcode/). I ran into a hitch when adding the SCSS from the post that controls the appearance of sidenotes: it overrode existing styles, and the website looked horrible. To solve that, I converted the SCSS to CSS and followed the standard workflow of calling it `assets/css/extended/custom.css`. With the implementation working, I changed the sidenote highlight color to my liking. After that, I just had to change the footnotes in [Manifesting a Trading Career]({{< ref "/posts/manifest-trading-bootcamp" >}}) to sidenotes, and the changes were ready to go, no custom JS required!

[^1]: For example, this one. As you'll see, I decided on a different approach, so this footnote has no preview.