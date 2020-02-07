backend framework
---
Django? Express.js?
(Alternatives - async Flask equivalen is FastAPI)

Again, I love admin, Django ORM, dbshell, Jupyter dbshell.

frontend framework
---
React? Vue?

Why switching from React if Vue has similar metrics and less ecosystem. For instance, no mainstream Monaco wrapper.

language flavor/safety
---
flow? custom babel preset?

bundler config and boilerplate
---
Webpack? Parcel? Create React App? Next.js? Gatsby?

**Nano React App**: https://hackernoon.com/create-react-app-is-way-too-bloated-5db07c3511

If project can't benefit from server-side rendering or SEO or static generation, then it's not worth going the Next.js or Gatsby way - less popular meaning less support, more traps. Sticking with CRA / ejected CRA.

Parcel may be good, but I don't know if it's easy to wire Parcel and Monaco, as well as any other dependencies. Sticking with CRA.

frontend deployment
---
Netlify? Now?

backend deployment
---
Amazon? Heroku? docker? RDS?

database
---
Postgres? (ok, at least here there's no alternative)

authentication
---
Cognito? Auth0? python-social-auth?

Looks like Passport.js is huge and popular.

CSS-in-JS library
---
anything competing with styled-components?

components library
---
Bootstrap? Material UI? Ant?

linters and formatters
---

ESLint/Prettier and Black, lucky we

pre-commit Black hook with Husky

frontend state management
---

Redux? Storeon? React Hooks?

Code editor as a component
---
**Monaco**: https://habr.com/ru/company/Voximplant/blog/445390/

Monaco is compatible with pre-eject CRA: https://github.com/react-monaco-editor/react-monaco-editor/issues/263
See [cra-monaco/](cra-monaco)
