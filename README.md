# Ng13YarnPnp

This is a minimal test for [using Yarn PnP with Angular 13](https://github.com/angular/angular-cli/issues/16980).

Created via:
1.
```
mkdir ng13-yarn-pnp
cd ng13-yarn-pnp
yarn set version berry
mv .\package.json _package.json # Needed so that the yarn pnp package.json isn't in the way
yarn dlx --package @angular/cli ng new ng13-yarn-pnp --directory=. --packageManager=yarn --create-application=false --minimal
```

2. Then, move the contents of `_package.json` to `package.json`, and delete `_package.json`.

3. Update .gitignore per: https://yarnpkg.com/getting-started/qa#which-files-should-be-gitignored
(I used the non-zero-install .gitignore)

4. Add a library
```
yarn ng g library mylib
```

5. Try building the library
```
❯ yarn ng build mylib
Building Angular Package
Cannot find package '@angular/compiler-cli' imported from C:\src\github\johncrim\ng13-yarn-pnp\.yarn\__virtual__\ng-packagr-virtual-fa520e598e\0\cache\ng-packagr-npm-13.1.2-a4236d0e43-5c40f95760.zip\node_modules\ng-packagr\lib\utils\ng-compiler-cli.js
Did you mean to import @angular-compiler-cli-virtual-759efba812/0/cache/@angular-compiler-cli-npm-13.1.1-a3378c32eb-2c9f958b04.zip/node_modules/@angular/compiler-cli/bundles/index.js?
```
