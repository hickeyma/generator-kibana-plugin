# Kibana Plugin Yeoman Generator

This project is a Yeoman generator for bootstrapping a Kibana Plugin. It creates a basic hello world Kibana plugin with all the elements in place so you can easily get started with creating your first Kibana plugin.

## Getting Started

1. Install Yeoman and the Kibana plugin generator

  ```sh
  npm install -g yo generator-kibana-plugin
  ```

1. Setup your [Kibana development enviroment](https://github.com/elastic/kibana/blob/master/CONTRIBUTING.md#development-environment-setup)

1. Create a directory for your plugin that is right next to your Kibana directory.

  - The Kibana directory must be named `kibana`
  - `kibana` and your plugin directory must be siblings

    ```sh
    ls ~/wherever/you/store/your/code
      kibana # <- where you store the Kibana development environment
      my-new-plugin # <- your plugin directory
    ```

1. Double check that you have the right node.js version installed

  ```sh
  node --version # should output the version found in Kibana's .node-version file
  ```

1. Run the generator inside your plugin directory

  ```sh
  cd my-new-plugin
  yo kibana-plugin
  ```

1. Get the URL for your Elasticsearch installation (most commonly `http://localhost:9200`)

1. Start Kibana in development mode with your new plugin included

  ```sh
  npm start -- --elasticsearch.url 'http://localhost:9200'

  # passing the elasticsearch.url here is to demonstrate how arguments can
  # be passed to kibana with `npm start` but is not actually necessary if
  # you are running elasticsearch locally
  ```

1. Visit [http://localhost:5601](http://localhost:5601)

## options

If you start the generator with the `--minimal` flag it will not generate any sample, code only
the bare folder structure.

If you start the generator with the `--advanced` flag you can choose what sample
components it should generate for you.

## development tasks

  - `npm start`

    Start kibana and have it include this plugin

  - `npm start -- --config kibana.yml`

    You can pass any argument that you would normally send to `bin/kibana` by putting them after `--` when running `npm start`

  - `npm run build`

    Build a distributable archive

  - `npm run test:browser`

    Run the browser tests in a real web browser

  - `npm run test:server`

    Run the server tests using mocha

For more information about any of these commands run `npm run ${task} -- --help`.
