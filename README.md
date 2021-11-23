### Have you been Cloop'd?

Create a skeletal angular mono-repo project, named `cloopd`, comprising of three applications: `savings`, `lettings` and `trades`.

The three applications should share the following:

1. The same set of development and production environment files
2. A shared library called `ClooperCore`, to be located in `projects/clooper/core` of your projects directory. The library should comprise of the following services, http interceptor, and route guard: `AuthService`, `UserService`, `PropertyService`, `DealsService`, `UrlInterceptor`, `AuthGuard`
    1. In `AuthService` implement a `signin` method to take email and password, POST to /auth
    2. In `UserService` implement a `create` method to create a new user account by POST to /users; required fields are: email, password, first_name, last_name, accepts_terms (default to true)
    3. In `PropertyService` implement a `fetch` method to GET list of properties from /properties
    4. In `DealService` implement a `fetch` method to GET list of deals from /deals
    5. In the `UrlInterceptor`, implement the `intercept` method to prepend the `API_ENDPOINT` in environments to the request URL, if the request URL does not begin with http:// or https://.
    6. In the `AuthGaurd` implement the `canActivate` method to redirect to /login page if the user is not logged in. Hint: put a method in `AuthService` to help you check whether a user is logged in or not.
3. A shared library called `ClooperCommon`, to be located in `projects/clooper/common` of your projects directory. The library should comprise of the following components, directives and pipes:
    * a `pagination` component (wraps pagination in Bootstrap 5)
    * a `button` component (wraps buttons in Bootstrap 5)
    * an `accordion` component  (wraps accordion/collapsible in Bootstrap 5)
    * a `toggle password visibility` directive to show or hide the value in inputs of type password
    * a `full name` pipe (that combines a user’s first_name and last_name together)

### Assumptions:

All three applications share the same `API_ENDPOINT` endpoint https://clooper-api.ap76f32dc77r0.eu-west-2.cs.amazonlightsail.com/api/v2

### Restrictions:

1. Use Angular v12
2. Use `yarn` instead of `npm`
3. Use `eslint` in place of `tslint` for linting
4. Use basic Bootstrap 5 for the layout and styling
5. Do not use any `ngx-*` or `angular-material` module

### Expectations

All three applications should launch on different ports, as follows

`yarn run savings` should launch the Savings app on port 4311
`yarn run lettings` should launch the Lettings app on port 4322
`yarn run trades` should launch the Trades app on port 4333

The apps do not necessarily need to do anything, but they must run and lint.

`yarn run lint` should just work!

