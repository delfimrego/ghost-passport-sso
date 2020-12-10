# Ghost Passport Single Sign-on

This [Ghost](https://ghost.org/) adapter allows you to use [Passport](http://www.passportjs.org/) authentication strategies to provide Single Sign-On (SSO) capabilities.

NOTE: development in progress. Do not use it!

## Instalation

You need to enter the following commands in the directory in which ghost is installed. For example, if you followed the [Ghost setup guide](https://docs.ghost.org/docs/install), it'll be in `/var/www/ghost`.

```shell
npm install ghost-passport-sso
mkdir -p content/adapters/sso
cp -r node_modules/ghost-passport-sso content/adapters/sso/ghost-passport-sso
```

## Configuration

Create new azure storage account, and get the connection string (can be found in the preview portal)

Add `sso` block to file `config.js` in each environment as below:

```json
  "adapters": {
      "sso": {
        "active": "ghost-passport-sso",
        "ghost-passport-sso": [
            {
                "id": "google", 
                "name": "Google",
                "strategy": "passport-google-oauth20",
                "options": {
                    "clientID": "YourClientIdStringHere",
                    "clientSecret": "YourClientSecretStringHere",
                    "scope": ["profile", "email"]
                }
            },
            {
                "id": "github", 
                "name": "GitHub",
                "strategy": "passport-github2",
                "options": {
                    "clientID": "YourClientIdStringHere",
                    "clientSecret": "YourClientIdStringHere",
                    "scope": ["user:email"]
                }
            }
        ]
      }
  },
```



### Examples


## License

Released under the [MIT license](https://github.com/muzix/ghost-s3/blob/master/LICENSE).