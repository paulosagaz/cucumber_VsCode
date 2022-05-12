# Contributing

Thank you for contributing! Please follow these steps to manually test your changes locally.

Most of the logic in this extension is implemented in two other libraries:

* https://github.com/cucumber/language-service
* https://github.com/cucumber/language-server

If your work involves modifying any of these, here is how you can manually test it in VSCode:

```
pushd language-service
npm install
npm link
npm run build
popd

pushd language-server
npm install
npm link @cucumber/language-service
npm link
npm run build
popd

pushd vscode
npm install
npm link @cucumber/language-server

code .
# Make sure you've disabled the Cucumber extension if you installed it from the marketplace
# Chose `Run -> Run without debugging` to open a 2nd editor where you can manually test
```