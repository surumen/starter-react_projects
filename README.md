<p align="center">
  <h2 align="center">React Redux JWT Auth Projects Starter</h2>
  <p align="center">
    <a href="https://travis-ci.org/me-io/angular-2-starter">
      <img src="https://img.shields.io/travis/me-io/angular-2-starter/master.svg?style=flat-square" alt="Travis Status">
    </a>
    <a href="LICENSE.md">
      <img src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square" alt="Software License">
    </a>
    <a href="https://david-dm.org/me-io/angular-2-starter">
      <img src="https://img.shields.io/david/me-io/angular-2-starter.svg?style=flat-square" alt="Dependencies">
    </a> 
    <a href="https://david-dm.org/me-io/angular-2-starter?type=dev">
      <img src="https://img.shields.io/david/dev/me-io/angular-2-starter.svg?style=flat-square" alt="devDependencies">
    </a> 
  </p>
</p>



Changelog
---------
Changes and version updates will be posted here



## Usage

[Create an auth0 account](https://manage.auth0.com/). Then run the following commands. Make sure your `src/utils/config.js` file has the correct values from your auth0 account.

```bash
# Install dependencies
npm install

# Copy configuration and replace with your own
cp src/utils/config.example.js src/utils/config.js

# Run
npm start
```


## Features

### Auth0

Auth0 helps to:

* Add authentication with [multiple authentication sources](https://docs.auth0.com/identityproviders), either social like **Google, Facebook, Microsoft Account, LinkedIn, GitHub, Twitter, Box, Salesforce, among others**, or enterprise identity systems like **Windows Azure AD, Google Apps, Active Directory, ADFS or any SAML Identity Provider**.
* Add authentication through more traditional **[username/password databases](https://docs.auth0.com/mysql-connection-tutorial)**.
* Add support for **[linking different user accounts](https://docs.auth0.com/link-accounts)** with the same user.
* Support for generating signed [Json Web Tokens](https://docs.auth0.com/jwt) to call your APIs and **flow the user identity** securely.
* Analytics of how, when and where users are logging in.
* Pull data from other sources and add it to the user profile, through [JavaScript rules](https://docs.auth0.com/rules).

### AuthService

The library `auth0-lock` provides the user authentication, and I also have a `src/utils/AuthService.js` module to wrap this Lock Widget usage and manage the localStorage items.

I'm using the latest Auth0 Lock 10 version in [popup mode](https://auth0.com/docs/libraries/lock/v11/authentication-modes#popup-mode), which means here's the flow:

* ->Login widget shows login panel
* ->Redirect to auth0 to check login creds (done in hidden iframe)
* ->Redirect back to localhost:3000/callback (done in hidden iframe)
* ->AuthService waits for 'authenticated' event to fire
* ->Redirects back to homepage

### Libraries

This starter kit is minimal, only the strict necessary is added.

| Library                                                                   | Description                                                      |
| ------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| [react](https://github.com/facebook/react)                                | Facebook's library for building user interfaces                  |
| [redux](https://github.com/rackt/redux)                                   | State container for JavaScript apps                              |
| [react-router](https://github.com/rackt/react-router)                     | Declarative routing for React apps using navigational components |
| [create-react-app](https://github.com/facebookincubator/create-react-app) | All tooling needed for react apps                                |

The starter kit includes a working example app that puts all of the above to use.

## Development

`create-react-app` takes care of tooling, development server, live reload, building, testing.

HMR is unfortunately not enabled during development, because `create-react-app` doesn't support it.

If you wish to directly use Webpack instead of `create-react-app`, you can eject any time by running `npm run eject`. Read [here](https://github.com/facebookincubator/create-react-app#converting-to-a-custom-setup) for more information about ejecting.

## Testing

`npm run lint` to check linting errors. This projects follows [`eslint-config-react-app`](https://github.com/facebookincubator/create-react-app/tree/master/packages/eslint-config-react-app) style.

`npm test` to run all tests. This project uses jest to run tests, and [enzyme](https://github.com/airbnb/enzyme) for unit testing React components.

## Deployment

Out of the box, this starter kit is deployable by serving the `~/build` folder generated by `npm run build`.

## License

MIT.

## To do

* [ ] Add a side effects library (`redux-saga`, `redux-observable`) to manage side effects. It makes the code more redux-compliant, however it goes against minimalism.
* [ ] Any other ideas are welcome! Just post an issue.

