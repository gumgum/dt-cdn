# DigiTrust

The DigiTrust code base relies on Node.js, Grunt and Browserify among other libraries.

### Local Development

To initialize your local repository for development, clone this repository and run:

    #install dependencies
    npm install
    # build only
    grunt --env local (build script)
    # build & watch script
    grunt watch --env local
    # deploy to cdn
    grunt --env prod && grunt --env prod deploy
    # generate new key pair
    grunt generateKey --keyversion N

    # to run fileserving with CORS *; may need to sudo
    npm install connect
    npm install serve-static
    node node-server.js

Available environments: local, dev, prod

Before committing, you can run the following to validate your code

    npm run test
    npm run validate

They will be automatically run on push to ensure that only clean code makes it into the repository.

### Production Releases

1. Update `digitrustVersion` in `Gruntfile.js`
2. Update `digitrustHostPath`, `digitrustRedirect`, and `digitrustIframe` in the `prod` section of `src/config/general.json`
3. `grunt --env prod && grunt --env prod deploy`
