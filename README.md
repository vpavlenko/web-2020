Backend framework [Django]
---
Django? Express.js?
(Alternatives - async Flask equivalent is FastAPI)

Again, I love admin panel, Django ORM, migrations, dbshell, Jupyter dbshell. So Django.

Frontend framework [React]
---
React? Vue?

Why switching from React if Vue has similar metrics and less ecosystem. For instance, no mainstream Monaco wrapper.

Language flavor/safety [TypeScript, Mypy]
---
Flow? Typescript? Typed Python?

https://blogs.dropbox.com/tech/2019/09/our-journey-to-type-checking-4-million-lines-of-python/

Mypy is worth a try - the code should be clearer.

Once I start doing Mypy - follow this guide: https://realpython.com/python-type-checking/

Looks like Flow is on par with TypeScript and it's better with React - both are maintained by Facebook.

May migrate from Flow to TypeScript later on: https://medium.com/inato/migrating-from-flow-to-typescript-why-how-worth-it-5b7703d12089

Flow is often blamed to have bad VSCode support and random bugs.

Yarn and Jest migrated from Flow to TypeScript. Same for React Native's Expo.

https://medium.com/palantir/tslint-in-2019-1a144c2317a9

Linters and formatters [Prettier, Black, Husky]
---

ESLint/Prettier and Black, lucky we

pre-commit Black hook with Husky

TSLint?


API design [DRF]
---
REST? GraphQL?

Looks like it's easy to plug in graphene_django at any time. Benefits: typed API requests, no overfetching/underfetching. Worth a try once we get to writing actual API queries.

What about DRF instead? DRF has 30 times more projects using it.

To read: https://github.com/Shopify/graphql-design-tutorial/blob/master/TUTORIAL.md
https://www.howtographql.com/

GraphQL seems to be cool, Graphene probably sucks: https://news.ycombinator.com/item?id=20200203

https://www.valentinog.com/blog/drf/

Database [Postgres]
---
Postgres? (ok, at least here there's no alternative)

Authentication [Django_allauth, django-rest-auth]
---
Cognito? Auth0? python-social-auth?

Looks like Passport.js is huge and popular.

Can do plain django.contrib.auth with native pages (i.e. no React wrappers around, just redirects) - for prototyping

Django_allauth and django-rest-auth. The latter isn't supported anymore, but it's required to wire with DRF.

Bundler config and boilerplate [Create React App]
---
Webpack? Parcel? Create React App? Next.js? Gatsby?

**Nano React App**: https://hackernoon.com/create-react-app-is-way-too-bloated-5db07c3511

If project can't benefit from server-side rendering or SEO or static generation, then it's not worth going the Next.js or Gatsby way - less popular meaning less support, more traps. Sticking with CRA / ejected CRA.

Parcel may be good, but I don't know if it's easy to wire Parcel and Monaco, as well as any other dependencies. Sticking with CRA.

Frontend deployment
---
Netlify? Now? Github Pages?

Backend deployment
---
Amazon? Heroku? docker? RDS?




CSS-in-JS library [styled-components]
---
Anything competing with styled-components? CSS Modules?

Components library [Ant]
---
Bootstrap? Material UI? Ant?

https://ant.design/docs/react/use-in-typescript

Ant has better TypeScript support and is being very actively developed

Frontend state management [Storeon + React Hooks]
---

Redux? Storeon? React Hooks?

Will replace Storeon with Redux once Storeon isn't good enough.

Code editor as a component [Monaco]
---
https://habr.com/ru/company/Voximplant/blog/445390/

Monaco is compatible with pre-eject CRA: https://github.com/react-monaco-editor/react-monaco-editor/issues/263
See [cra-monaco/](cra-monaco)
