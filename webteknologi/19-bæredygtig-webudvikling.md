# Bæredygtig webudvikling, Recap og prøve eksamen



## New links

- https://codecarbon.io/
- https://github.com/social-impact/focus-areas/environmental-sustainability/climate-action-plan-for-developers
- 



## Overview

- Read slides. These notes are just notes to the slides!



## Leveraging tools to assess performance and impact

- [https://www.webpagetest.org/](https://www.webpagetest.org/)
- [https://pagespeed.web.dev/](https://pagespeed.web.dev/)
- [https://www.webpagetest.org/carbon-control/](https://www.webpagetest.org/carbon-control/)
- [https://www.websitecarbon.com/](https://www.websitecarbon.com/)



## Concrete tips

- Collaborating with the community for web sustainability

- - [ClimateAction.tech](https://climateaction.tech/) is a community of tech workers working together to seed climate action  in companies, organizations and industries. It's a great place to have  conversations with like-minded people and get inspired to take action.
  - The [Sustainable Web Design Community Group](https://www.w3.org/community/sustyweb/) is working to define a set of guidelines for building sustainable websites. Join the group, or contribute via [Github](https://github.com/w3c/sustyweb/).



From here: [https://developer.mozilla.org/en-US/blog/introduction-to-web-sustainability/](https://developer.mozilla.org/en-US/blog/introduction-to-web-sustainability/)



## Introduction - why even care

- How much energy do the web use
- Terms
  - Sustainability
  - Carbon footprint



## Measuring impact - Where are we now?



## Design

- Simplify user experience
- Lightweight imagery
  - Cutting down image size: [https://tinypng.com/](https://tinypng.com/)
- Avoid large images, self playing
- Avoid gifs, use webp format instead - *source: Sustainable Web Design*
- Efficient web typography
  - Limiting the number of web fonts we use
  - Consider using a [variable font](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide) if multiple weights and styles of a particular typeface are needed
  - [Self-hosting your fonts](https://sia.codes/posts/making-google-fonts-faster/#self-host-your-web-fonts-for-full-control) will save on network requests and give you more control.
- Making greener design choices
  - A greener design might involve using less energy-intensive colors. Blue colors use more energy than red or green do, and on Organic  Light-Emitting Diode (OLED) screens, a dark color scheme can save energy because black pixels are "off".
  - Websites can be designed to minimize the use of video and large images,  especially by avoiding autoplaying videos or by using SVGs instead of  photos where possible.
  - The user journey also plays an important part: How much time are users spending clicking around on your site, loading more resources than they need because they can't find what they're looking for?



## Accessibility



## Hosting

- Choosing a green web host

  - Ensuring that our web hosts use renewable energy is an important step  towards reducing our sites' carbon emissions. Unfortunately, it's not  always easy to distinguish genuine green credentials from greenwashing  and marketing claims. The [Green Web Foundation's hosting directory](https://www.thegreenwebfoundation.org/directory/) lists companies that provide proof of their "green" credentials.

  - [https://aremythirdpartiesgreen.com/](https://aremythirdpartiesgreen.com/)



## Sustainable web development

- Choosing efficient programming language - *source: Sustainable Web Design*
- Static web pages - *source: Sustainable Web Design*

- Handling third-party embeds

  - Third-party code such as chat widgets, analytics scripts, and social media embeds are often the worst offenders when it comes to page weight and data transfer
  - Consider using the import-on-interaction pattern, where loading is deferred until a user interacts with the widget.
  - Trackers

- Reducing JavaScript usage

  - Do you have to use js? [http://youmightnotneedjs.com/](http://youmightnotneedjs.com/)
  - [https://bundlephobia.com/](https://bundlephobia.com/)

- [Dynamic imports](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/import#description) can help reduce the upfront JavaScript bundle size and prevent users  from downloading code that won't be needed until much later.

- Block the Bots - *source: Sustainable Web Design*

- General optimization

  - Minifying, compressing, and [tree-shaking](https://developer.mozilla.org/en-US/docs/Glossary/Tree_shaking) your code, in addition to compressing images, will all contribute to reducing data transfer.
  - Image, video, font, html, css and javascript - *Source: https://sustainablewww.gumroad.com/l/sustainable-web-design-in-20-lessons*

- Cache - Additionally, we can make sure we cache as much as possible. Harry Roberts provides a great guide to [cache-control for civilians](https://csswizardry.com/2019/03/cache-control-for-civilians/)

- Optimizing energy use with carbon-aware computing

  - The [Green Software Foundation](https://learn.greensoftware.foundation/carbon-awareness) offers some great resources on this topic.

  - We can reduce our reliance on electricity generated from fossil fuels by looking at where and when we run energy-intensive processes:

    - By utilizing servers in locations where a higher proportion of electricity comes from renewable sources (spatial shifting).
    - By running processes at times of the day when demand on the  electrical grid is low, or when more electricity is being produced by  intermittent solar or wind power (temporal shifting).
    - https://solar.lowtechmagazine.com/

    ![alt_text](https://learn.greensoftware.foundation/assets/images/07_variability_CI-7435d76aabeeecd5e276367c2003f018.png)

- CDN's



## Links

- [https://greensoftware.foundation/](https://greensoftware.foundation/)



## Books

- https://abookapart.com/products/responsible-javascript
- https://abookapart.com/products/sustainable-web-design.html



## Sources used:

- [https://sustainablewww.gumroad.com/l/sustainable-web-design-in-20-lessons](https://sustainablewww.gumroad.com/l/sustainable-web-design-in-20-lessons)
- [https://developer.mozilla.org/en-US/blog/introduction-to-web-sustainability/](https://developer.mozilla.org/en-US/blog/introduction-to-web-sustainability/)
-  Tom Greenwood - Sustainable Web Design - På KEA biblioteket



## Opgaver

