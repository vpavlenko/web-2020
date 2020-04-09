Backend framework [Django]
---
Django? Express.js?
(Alternatives - async Flask equivalent is FastAPI)

Again, I love admin panel, Django ORM, migrations, dbshell, Jupyter dbshell. So Django.

Django boilerplate - cookiecutter?
- https://github.com/pydanny/cookiecutter-django
- https://github.com/agconti/cookiecutter-django-rest
- https://github.com/wsvincent/awesome-django#boilerplate

What to look at:
- https://django-extensions.readthedocs.io/
- https://github.com/jazzband/django-debug-toolbar/
- https://github.com/arteria/django-hijack
- https://github.com/wsvincent/awesome-django#models
- https://github.com/joke2k/django-environ

Open-source Django projects:
- https://github.com/zulip/zulip/
- https://github.com/taigaio/taiga-back
- https://github.com/wagtail/wagtail/
- https://github.com/edx/edx-platform
- https://github.com/django/djangoproject.com

Alternatively, you can assmeble a stack around Express.js. Although I recommend go the RDBMS way, which leads to using sequelize as an ORM. And sequelize itself isn't as smooth as Django ORM - it requires more manual actions and verbose configuration. It was also hard to interact with using REPL due to async nature - maybe it's still hard.

- https://vsupalov.com/django/
- https://vsupalov.com/quick-django-refresher-crash-course/
- https://vsupalov.com/django-custom-user-model/
- https://medium.com/3yourmind/keeping-django-database-migrations-backward-compatible-727820260dbb



Frontend framework [React]
---
React? Vue?

Why switching from React if Vue has similar metrics and less ecosystem. For instance, no mainstream Monaco wrapper. Also, React Native is fun.

What to look at:
- https://github.com/welldone-software/why-did-you-render



Language flavor/safety [TypeScript, Mypy]
---
Flow? Typescript? Typed Python?

https://blogs.dropbox.com/tech/2019/09/our-journey-to-type-checking-4-million-lines-of-python/

Mypy is worth a try - the code should be clearer. Once I start doing Mypy - follow this guide: https://realpython.com/python-type-checking/

Django-stubs is Django with types: https://sobolevn.me/2019/08/typechecking-django-and-drf

Looks like Flow is on par with TypeScript and it's better with React - both are maintained by Facebook. One may also migrate from Flow to TypeScript later on: https://medium.com/inato/migrating-from-flow-to-typescript-why-how-worth-it-5b7703d12089

Flow is often blamed to have bad VSCode support and random bugs. Yarn and Jest migrated from Flow to TypeScript. Same for React Native's Expo.

No need to use TSLint anymore: https://medium.com/palantir/tslint-in-2019-1a144c2317a9

Looks like CRA doesn't have ES2016 support, let alone ES2020. What exactly are we missing: https://github.com/tc39/proposals/blob/master/finished-proposals.md It might make sense to enable it using customize-cra: https://2muchcoffee.com/blog/es7-decorators-how-to-use-the-decorator-syntax-in-react/

Looks like Pyright (Microsoft) and Pyre (Facebook) are both maintained tools that do Mypy-like type checking, but faster.

Have a look at:
- Tons of learning resources: https://github.com/dzharii/awesome-typescript
- https://github.com/typescript-cheatsheets/react-typescript-cheatsheet
- https://github.com/jeffijoe/typesync



Linters and formatters [Prettier, Black, flake8, isort, Husky, ShellCheck for .sh, hadolint for Dockerfile]
---

ESLint/Prettier with typescript-eslint. Also Black. Pre-commit hooks running necessary tools with Husky.

JS stuff:
- https://prettier.io/docs/en/integrating-with-linters.html
- https://github.com/alexgorbatchev/eslint-import-resolver-typescript
- https://www.robertcooper.me/using-eslint-and-prettier-in-a-typescript-project

Python stuff:
- https://github.com/vintasoftware/python-linters-and-code-analysis (also watch out for Django-specific linters)
- https://github.com/DmytroLitvinov/awesome-flake8-extensions
- https://github.com/vinta/awesome-python#code-analysis
- https://wemake-python-stylegui.de/en/latest/pages/usage/integrations/auto-formatters.html
- http://www.locallyoptimal.com/blog/2019/08/23/why-you-should-use-black-for-your-python-style-linting/
- https://github.com/psf/black/issues/333#issuecomment-516088368
- https://dmerej.info/blog/post/bye-bye-pylint/
- https://github.com/pilat/vscode-importmagic

Other stuff:
- https://github.com/koalaman/shellcheck
- https://github.com/hadolint/hadolint

What's suspicious about https://github.com/wemake-services/wemake-django-template ?
- poetry isn't as mature as pipenv - eg. [pipenv is working in VSCode with zero configuration](https://code.visualstudio.com/docs/python/environments)
- same for Caddy vs. nginx - it's not worth risking with this layer of infrastructure
- Gitlab CI - not a default Github CI
- wemake-python-styleguide is against black, and I love auto-formatters

A sample project with Black, flake8, mypy and isort are configured to work together and with Django/DRF: https://github.com/vpavlenko/drf-tutorial



Package managers [Yarn 1.22 or npm, npx, Pipenv]
---
Yarn 2 can fail to work with react-app-rewired, so sticking to a Yarn 1.* like 1.22 is a safe option for now.s

Pipenv is a modern replacement for pip/virtualenv, although it itself isn't being actively supported since Oct 2018.

It looks like npm is being actively developed and is on par with Yarn these days, whereas Yarn has almost no big changes throughout 2019.

- https://gioele.io/pyenv-pipenv
- https://xkcd.com/1987/
- https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b



API design [Django REST Framework]
---

Should we use REST or GraphQL?

Django has a very mature REST framework - Django REST framework (DRF), used by 108k projects according to Github stats.
It's been actively maintained since 2011 and very well documented.

GraphQL is a new technology that gives the following benefits:
- typed API requests: auto checking, no need to do Swagger/Postman knowledge sharing between frontend and backend teams
- no overfetching/underfetching

While the technology itself is cool, it's way more supported in the Node.js world, where the express-graphql library
has same 109k users. It's support in the Django world is young and limited: graphene_django has 3k users, it's poorly documented, not very actively maintained and has performance issues.

So for now, Django should be used with DRF. If GraphQL is a must, one should entirely switch to the Node.js stack.

On GraphQL:
- https://github.com/Shopify/graphql-design-tutorial/blob/master/TUTORIAL.md
- https://www.howtographql.com/

On current GraphQL support for Django:
- https://news.ycombinator.com/item?id=20200203
- https://yeti.co/blog/migrating-from-rest-to-graphql-in-django/

On DRF: 
- https://www.valentinog.com/blog/drf/
- https://github.com/wsvincent/awesome-django#django-rest-framework



Database [Postgres]
---
Postgres? (ok, at least here there's no alternative)

Reasoning: I want an RDBMS because why disentangle denormalized Mongo crap if you only have one life? Postgres is top-1 RDBMS.



Authentication [django-allauth, django-rest-auth]
---
Cognito? Auth0? python-social-auth?

Looks like Passport.js is huge and popular.

Can do plain django.contrib.auth with native pages (i.e. no React wrappers around, just redirects) - for prototyping

Django_allauth and django-rest-auth. The latter isn't supported anymore, but it's required to wire with DRF. Also it's maybe not that painful because it's a tiny layer. No critial Issues found at their bug tracker.

Google One-Tap (Google YOLO) is a great experience, but it's still not public.



Bundler config and boilerplate [Create React App]
---
Webpack? Parcel? Create React App? Next.js? Gatsby?

Nano React App: https://hackernoon.com/create-react-app-is-way-too-bloated-5db07c3511

If project can't benefit from server-side rendering or SEO or static generation, then it's not worth going the Next.js or Gatsby way - less popular meaning less support, more traps. Sticking with CRA / ejected CRA.

Parcel may be good, but I don't know if it's easy to wire Parcel and Monaco, as well as any other dependencies. Sticking with CRA.



CSS-in-JS library [styled-components]
---
Anything competing with styled-components? CSS Modules? Not worth it. 

Also, look at https://styled-system.com/

https://styled-components.com/docs/tooling#babel-macro



Components library [Ant]
---
Bootstrap? Material UI? Ant?

https://ant.design/docs/react/use-in-typescript

Ant has better TypeScript support and is being very actively developed

To use:
- https://github.com/fi3ework/vscode-antd-rush
- https://marketplace.visualstudio.com/items?itemName=bang.antd-snippets
- For inspiration: http://antd-admin.zuiidea.com/
- And in general: https://github.com/websemantics/awesome-ant-design

For forms it makes sense to look into both Formik and Yup:
- https://blog.bitsrc.io/creating-forms-in-react-with-formik-and-yup-698d09363a22
- https://github.com/jannikbuschke/formik-antd



Frontend state management [Storeon + React Hooks]
---

Redux? Storeon? React Hooks?

Will replace Storeon with Redux once Storeon isn't good enough. Also have a look at 
- https://nikgraf.github.io/react-hooks/
- https://github.com/enaqx/awesome-react#react-hooks



Code editor as a component [Monaco]
---
https://habr.com/ru/company/Voximplant/blog/445390/

Monaco is compatible with pre-eject CRA: https://github.com/react-monaco-editor/react-monaco-editor/issues/263
See [cra-monaco/](cra-monaco). Although this isn't maintained: https://medium.com/@kitze/configure-create-react-app-without-ejecting-d8450e96196a



Router [Reach Router]
---
@reach/router vs. React Router

Let's start with @reach/router and see how cool React Router v6 is once it's out.

- https://reacttraining.com/blog/reach-react-router-future/
- https://github.com/reach/router/blob/master/website/src/markdown/pages/typescript.md



Frontend deployment [Zeit Now]
---
Netlify? Now? Github Pages?

Try Zeit Now and Netlify, in this order.

Github Pages might be a weaker option because it's not a core business for the company => less convenient.

On marrying frontend and backend:
- https://fractalideas.com/blog/making-react-and-django-play-well-together/



Backend deployment [DigitalOcean Docker (+Portainer) + Managed Postgres + CloudFlare]
---
Amazon/GCP/Azure? Heroku? VPS/Docker/Lambda? RDS?

Heroku isn't great - need to learn + tricky pricing.

DigitalOcean VPS may be good, although there's no autoscaling and Postgres-specific backups.

Dev db, dev env?

No Lambda - hard to reason about it given my experience with VPS and the whole Django entirety.

Let's try Docker.

uWSGI / gunicorn - both aren't well supported, but gunicorn had more patches over the last years.

DigitalOcean has its own RDS competitor: https://www.digitalocean.com/products/managed-databases/
[Loss in latency (100ms)](https://levelup.gitconnected.com/performance-aws-rds-postgres-vs-digital-ocean-postgres-8c2500197f1c), better documentation. (DigitalOcean also has its own S3)

Kubernetes / Docker Swarm is probably an overkill because one instance with Docker Compose should be enough.

So, DigitalOcean, Django app living in a docker, ability to add a load balancer and more dockers, 
and a Managed Database (Postgres) with backups.

[Horizontal scaling for the Django part is better than vertical](https://coderbook.com/@marcus/how-scalable-are-websites-built-in-django-framework/)

Why doesn't googling "django pgbouncer" yield a lot of results? https://stackoverflow.com/questions/40248970/django-settings-when-using-pgbouncer

CloudFlare from the start: for hiding the real server API, maybe caching something, DNS configuration, protecting from malicious 
DDoS (they happen even at a small scale!).

Monitoring: Sentry, Datadog?

- https://vsupalov.com/same-docker-container-django-postgresql/ and all other articles on vsupalov.com
- https://vsupalov.com/tools/portainer/
- https://vsupalov.com/speed-up-python-docker-image-build/
- https://vsupalov.com/deploying-like-a-startup/



Mobile development
---

React Native, Code Push, Fastlane
