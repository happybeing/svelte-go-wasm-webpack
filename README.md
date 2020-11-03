# Go WASM Template in Svelte
A quick start template to compile a Golang to WebAssembly for use with a Svelte front end. It is presented as a simple web app which shows how it all fits together.

This uses a fork of the golang-wasm-async-loader webpack plugin in order to work with Golang v1.13.

## Current Status

Relies on a local copy of forked plugin so follow the setup carefully.

## Setup

### Pre-requisites
Tested using `node` v14.14 and `yarn` v1.22. You could use `npm` for linking but I use yarn for this as it seems more reliable.

### Clone the plugin and this template

Note: the directories need to be adjacent in order to work as is. If not you will have to modify the path to `gobridge` in your `main.go` import. I'm not sure why this is needed but maybe the plugin wasn't finalised.

If you have `node` and `yarn`, on Linux you should be able to just copy the following and paste it into your terminal.
``` bash
mkdir -p ~/src/wasm_test
cd ~/src/wasm_test
git clone https://github.com/happybeing/webpack-golang-wasm-async-loader
cd webpack-golang-wasm-async-loader
npm install && npm run build
yarn link

git clone https://github.com/happybeing/svelte-go-wasm-webpack svelte-go-app
cd  svelte-go-app
yarn link golang-wasm-async-loader
yarn && yarn build
yarn dev
```
Note that the plugin directory and its package name are different, so you need to use the `yarn link` command as shown.

## LICENSE

Everything is GPL3.0 unless otherwise stated. Any contributions are accepted on the condition they conform to this license.

See also ./LICENSE