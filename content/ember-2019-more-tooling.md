---
title: Ember 2019 - More Tooling 🔧 🔨
image: /images/tooling.jpg
imageMeta:
  attribution: "Todd Quackenbush"
  attributionLink: "https://unsplash.com/@toddquackenbush"
featured: true
authors:
  - alon
date: Sat Jun 15 2019 15:00:16 GMT+0300 (Jerusalem Daylight Time)
tags:
  - roadmap
---

Ember.js is one of the most mature web frameworks in this day and age. The Ember Ecosystem has reached a stage where it must take more responsibility for the way that Ember developers author their applications. The way to do this is with _better tooling and more of it._

## Motivation

I have been working on an [Ember](https://emberjs.com/) application at my _"first real developer job ™"_ for three years. In that time I have been to an EmberFest (Berlin), became part of [The Ember Times Newsletter](https://blog.emberjs.com/tags/newsletter.html), written an RFC or two, [adopted some addons](https://github.com/adopted-ember-addons/program-guidelines) and more. To sum it up, I have fallen in love with the Ember community as a whole. With the second [#EmberJS2019](https://twitter.com/search?q=emberjs2019) [call for blog posts](https://blog.emberjs.com/2019/05/20/ember-2019-roadmap-call-for-posts.html) underway I want to make my voice heard regarding the direction that, I think, Ember should take during the next Roadmap.

## More Tooling 🔧 🔨

Ember, albeit being a somewhat niche framework compared to React/Angular/Vue/etc, has some amazing tooling built around it. We pioneered the CLI experience, our scaffolding and blueprint generators are top notch, and our build pipeline is strong and robust. We also have a great [Ember Inspector](https://guides.emberjs.com/release/ember-inspector/) browser extension that I couldn't live without. Given that, I am going to talk about the other side of the tooling regarding the authoring experience of actually writing the code.

We currently have many IDE/Editor extensions that improve how we write code. There are extensions for [VSCode](https://github.com/Alonski/ember-vscode-extensions), [JetBrains IDEs](https://plugins.jetbrains.com/plugin/8049-ember-js) and more. I myself use VSCode for all of my Ember needs. I still feel as if Ember doesn't have the appropriate tools for all jobs.

### Ember Language Server 🐹 🗣 🖥

The [Ember Language Server](https://github.com/emberwatch/ember-language-server) is an implementation of the Language Server Protocol for Ember projects.

> "ELS enables editors to provide features like auto complete, goto definition and diagnostics. To get these features, you have to install the plugin for your editor."

It is possible to use this in VSCode using the [VSCode Ember Extension](https://github.com/emberwatch/vscode-ember) and in Atom using the [Atom IDE Ember Extension](https://github.com/josa42/atom-ide-ember).
The initial work that was done is amazing but we need to keep iterating on top of this work. [@lifeart](https://github.com/lifeart) has been experimenting with an [Unstable Ember Language Server](https://github.com/lifeart/vscode-ember) and his work should be supported and pushed so that everyone can benefit from it. We are slowly moving the Ember framework and templating language to a place where it is easier to statically analyze it. Let's keep going in this direction and more.

### Formatting Templates 📝

One area that I feel needs improvement is Handlebars/Glimmer support. Currently in VSCode it is possible to setup the editor to [autoformat templates](https://medium.com/@alonbukai/how-to-format-handlebars-in-vscode-26144e9feec8). Taking this a step further would be to use something like Prettier, which I love, and being able to apply it to Ember templates in a simple and ergonomic way. Currently Prettier allows formatting templates but the support is 90% of the way there. We need to finish the journey so that any new, or existing app, can adopt this and reap the benefits of a consistent template style across all templates.

Some further reading:

- [Handlebars Formatter](https://github.com/mfeckie/handlebars-formatter)
- [Support Handlebars](https://github.com/prettier/prettier/issues/5340#issuecomment-474603873)
- [What would it take to make Glimmer support a bit more official](https://github.com/prettier/prettier/issues/4908)
- [Prettier Glimmer Playground](https://prettier.io/playground/#N4Igxg9gdgLgprEAuEACdqA8AbAlqgEwEMYiBaeAZxjICc4jLoA+AHSgw2GAGJcAzVEwC2cAHQwAFrigBzAL7z2nTvwi1U3EeNzxhi5RlYxucbJTgGOK9JkoAHIhzDZGlALysQcYfZgBPLzZrG3QycLJDG0wAegcnYJtuGIErTli8ZhAAGhAIP1xoSmRQIlpaCAB3AAUyhGKUIgA3CFwCHJAAI1oiMABrOBgAZUcwGVlkGFoAVzhcyRhhbAB1aSpRuCH63Vwm3X9kcEpi3JkLWhhqntlhImR+InM5kAArSgAPACEe-sGholEABkZHB7o8LLk3u8huNsHAAIrTCDwMFPXKOWjnQ6yPDCUS0Dr2WgyGDLNpSZAADgADOiKhZlj17IciXBzk1Qbl6ABHaa4ehXIg3O5IB5okAWYS4SYzZ6UWEIpEo0Xg56kTpkggUpAAJlyUyIuDwcgAwhA8SKQFBoJyQNMLAAVIidBpiiyKIA)

### More codemods, lint rules, quick fix shortcuts 💻 📏 🍰

We have an amazing [codemod](https://github.com/ember-codemods) community, an awesome [ESLint plugin](https://github.com/ember-cli/eslint-plugin-ember) and [Template Lint ecosystem](https://github.com/ember-template-lint) and many more of these tools are coming out on a monthly basis. Alas, I feel that we need to focus on these tools more and more as well as develop more tools that will help out the newbie and the pro at the same time.

For example, a few ESLint rules today such as [Order in Components](https://github.com/ember-cli/eslint-plugin-ember/blob/master/docs/rules/order-in-components.md) don't work in Native Class syntax. We need to make sure that this plugin is kept updated as well as the others. Another feature that I would like from `template-lint` is to have the ability to autofix errors. Also, with Octane gearing up to be released soon many current extensions aren't "aware" of it. Many of the snippet extensions for VSCode are outdated and none of them provide `<AngleBracket>` syntax snippets yet.

Another tool that I feel we need and don't yet have is an IDE/editor extension for `Ember Quick Fixes`. I think of this akin to using a codemod on a specific file or section of code. An example of this today is the VSCode [Convert to async function](https://code.visualstudio.com/updates/v1_28#_convert-to-async-function). This could allow us to do so many things and really improve developer productivity. There is a codemod today to [migrate Ember Objects to Native Classes](https://github.com/ember-codemods/ember-es6-class-codemod), wouldn't it be cool if we could apply this on a file by file basis?

Another area where this could be really useful is inside of templates. An idea that I have been thinking about for a while now is an `export template section to component` feature. This would allow extracting parts of a template into a newly generated component. It would know which arguments it needs to pass in and how to use them inside of the component. This alone could save small teams hours every week.

## Suggestions 🏁

My suggestion for the future is to create a new [Tooling Strike Team](https://emberjs.com/team/). This team would take the interests of the community and try to steer the tooling in that direction. The team wouldn't necessarily need to build everything by themselves but they would be _the place_ to go to find out what needs to be built and what is currently available. A `#dev-ember-tooling` channel in [Discord](https://discord.gg/emberjs) is needed as not all chat is relevant to `#topic-editors`.

In addition, there should be a [dedicated tooling section](https://github.com/ember-learn/ember-website/issues/294) in the guides. This would allow developers to learn and make informed decisions about which IDE/editor they should use and the best ways to use them.

## Conclusion 🐹

_We need to take tooling more seriously!_ Our community, while small, is so strong. I am already proud of what we have but we can definitely do better with a more targeted and managed approach. Today most of these tooling efforts are done, on the side as a fun side project or built slowly over time without much direction. We have the knowledge and community power to do this. We can do this. 🐹

## Summary

<table>
  <tr>
    <th>The tldr;</th>
    <th>Just read this table if you don't have much time</th>
  </tr>
  <tr>
    <td>Alon Bukai</td>
    <td>Ember Times Editor, Addon maintainer, Lover of Ember Community</td>
  </tr>
  <tr>
    <td>Suggestions</td>
    <td>Lets create a <a href="https://emberjs.com/team/">Tooling Strike Team</a>.</td>
  </tr>
  <tr>
    <td></td>
    <td>A `#dev-ember-tooling` channel in Discord.</td>
  </tr>
  <tr>
    <td></td>
    <td>A <a href="https://github.com/ember-learn/ember-website/issues/294">dedicated tooling section</a> in the guides.</td>
  </tr>
  <tr>
    <td>More Tooling</td>
    <td>We have good tools around CLI, scaffolding and generators.</td>
  </tr>
  <tr>
    <td></td>
    <td>We need better IDE/Editor tools</td>
  </tr>
  <tr>
    <td>Editor Extensions</td>
    <td><a href="https://github.com/Alonski/ember-vscode-extensions">VSCode</a></td>
  </tr>
  <tr>
    <td></td>
    <td><a href="https://plugins.jetbrains.com/plugin/8049-ember-js">JetBrains IDEs</a></td>
  </tr>
  <tr>
    <td>Ember Language Server</td>
    <td>Needs more support and love. Lets make this official and supported.</td>
  </tr>
  <tr>
    <td></td>
    <td><a href="https://github.com/emberwatch/ember-language-server">Ember Language Server</a></td>
  </tr>
  <tr>
    <td></td>
    <td><a href="https://github.com/lifeart/vscode-ember">Unstable Ember Language Server</a></td>
  </tr>
  <tr>
    <td>Formatting Templates</td>
    <td>Lets get Glimmer support for Prettier working correctly</td>
  </tr>
  <tr>
    <td></td>
    <td><a href="https://github.com/mfeckie/handlebars-formatter">Handlebars Formatter</a></td>
  </tr>
  <tr>
    <td></td>
    <td><a href="https://github.com/prettier/prettier/issues/5340#issuecomment-474603873">Support Handlebars</a></td>
  </tr>
  <tr>
    <td></td>
    <td><a href="https://github.com/prettier/prettier/issues/4908">What would it take to make Glimmer support a bit more official</a></td>
  </tr>
  <tr>
    <td></td>
    <td><a href="https://prettier.io/playground/#N4Igxg9gdgLgprEAuEACdqA8AbAlqgEwEMYiBaeAZxjICc4jLoA+AHSgw2GAGJcAzVEwC2cAHQwAFrigBzAL7z2nTvwi1U3EeNzxhi5RlYxucbJTgGOK9JkoAHIhzDZGlALysQcYfZgBPLzZrG3QycLJDG0wAegcnYJtuGIErTli8ZhAAGhAIP1xoSmRQIlpaCAB3AAUyhGKUIgA3CFwCHJAAI1oiMABrOBgAZUcwGVlkGFoAVzhcyRhhbAB1aSpRuCH63Vwm3X9kcEpi3JkLWhhqntlhImR+InM5kAArSgAPACEe-sGholEABkZHB7o8LLk3u8huNsHAAIrTCDwMFPXKOWjnQ6yPDCUS0Dr2WgyGDLNpSZAADgADOiKhZlj17IciXBzk1Qbl6ABHaa4ehXIg3O5IB5okAWYS4SYzZ6UWEIpEo0Xg56kTpkggUpAAJlyUyIuDwcgAwhA8SKQFBoJyQNMLAAVIidBpiiyKIA">Prettier Glimmer Playground</a></td>
  </tr>
  <tr>
    <td>Codemods, Linting, Quick Fixes</td>
    <td>Lets up our game regarding these important tools.</td>
  </tr>
    <tr>
    <td></td>
    <td>We have so much more that can be built.</td>
  </tr>
  <tr>
    <td></td>
    <td><a href="https://github.com/ember-codemods">Codemods</a></td>
  </tr>
  <tr>
    <td></td>
    <td><a href="https://github.com/ember-cli/eslint-plugin-ember">ESLint plugin</a></td>
  </tr>
  <tr>
    <td></td>
    <td><a href="https://github.com/ember-template-lint">Template Lint ecosystem</a></td>
  </tr>
  <tr>
    <td></td>
    <td><a href="https://code.visualstudio.com/updates/v1_28#_convert-to-async-function">Convert to async function</a></td>
  </tr>
  <tr>
    <td></td>
    <td><code>Extract template section to component` refactor</code></td>
  </tr>
</table>
