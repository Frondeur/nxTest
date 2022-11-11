# products

This library was generated with [Nx](https://nx.dev).

## Building

Run `nx build products` to build the library.

## Running unit tests

Run `nx test products` to execute the unit tests via [Jest](https://jestjs.io).

## Targets in project.json explained

imagine having this:
```json
{
  "name": "common-ui",
  "$schema": "../../node_modules/nx/schemas/project-schema.json",
  "sourceRoot": "libs/common-ui/src",
  "projectType": "library",
  "tags": [],
  "targets": {
    "lint": {
      "executor": "@nrwl/linter:eslint",
      "outputs": ["{options.outputFile}"],
      "options": {
        "lintFilePatterns": ["libs/common-ui/**/*.{ts,tsx,js,jsx}"]
      }
    },
    "test": {
      "executor": "@nrwl/jest:jest",
      "outputs": ["{workspaceRoot}/coverage/libs/common-ui"],
      "options": {
      "jestConfig": "libs/common-ui/jest.config.ts",
        "passWithNoTests": true
      }
    }
  }
}
```
there are two targets:  **lint** and **test**

`"executor"` which Nx executor to run. The syntax here is: `<plugin name>`:`<executor name>`

`"outputs"` this is an array of files that would be created by running this target

`"options"` this is an object defining which executor options to use for the given target. Every Nx executor allows for options as a way to parameterize its functionality

### Running tasks (each target) of a package

`npx nx test common-ui` - runs `test` task for the project `common-ui`

`npx nx lint common-ui` - runs `lint` task for the project `common-ui`
