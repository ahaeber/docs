---
title: PHP API Tutorial
name: PHP API
alias:
  - php
languages:
  - PHP
thirdParty: false
image: /media/platforms/php.png
tags:
  - quickstart
snippets:
  dependencies: server-apis/php/dependencies
  setup: server-apis/php/setup
  use: server-apis/php/use
---

## PHP API Tutorial

<%= include('../_includes/package', {
  pkgRepo: 'auth0-PHP',
  pkgBranch: 'master',
  pkgPath: 'examples/basic-api',
  pkgFilePath: null,
  pkgType: 'server' + account.clientParam
}) %>

**Otherwise, Please follow the steps below to configure your existing PHP app to use it with Auth0.**

### 1. Add the needed dependencies

We need 2 dependencies to make this work:

* **php-jwt**: this will take care of checking the JWT
* **router**: we'll use this for creating simple routes

${snippet(meta.snippets.dependencies)}

>>>>>>> Extracted snippets from tutorials
> This sample uses **[Composer](https://getcomposer.org/doc/00-intro.md)**, a tool for dependency management in PHP. It allows you to declare the dependent libraries your project needs and it will install them in your project for you.

### 2. Create the JWT Validation filter

Now, you need to validate the [JWT](/jwt). For that, we'll create a filter that will run in the routes we need.

${snippet(meta.snippets.setup)}

### 3. Create a /secured route that will use this filter

Now, you can just create routes under /secured route which will check the JWT

${snippet(meta.snippets.use)}

### 4. You're done!

Now you have both your FrontEnd and Backend configured to use Auth0. Congrats, you're awesome!

### Options Steps
#### Configure CORS

You can configure CORS, by just adding [this lines](https://github.com/auth0/auth0-PHP/blob/master/examples/basic-api/index.php#L45-L54) to your `index.php`

#### Define `apache_request_headers` if not available

If the function is not available, just [copy this lines](https://github.com/auth0/auth0-PHP/blob/master/examples/basic-api/index.php#L8-L29) to your `index.php`
