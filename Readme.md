# Issue
> Issue filed here https://github.com/OpenAPITools/openapi-generator/issues/15598

The `typescript-axios` generator is not respecting the `useSingleRequestParameter` additional-properties option, specified [here](https://github.com/OpenAPITools/openapi-generator/blob/master/docs/generators/typescript-axios.md).

This repo uses `@openapitools/openapi-generator-cli@^2.6.0` with `openapi-generator@v6.6.0` and the example PetStore schema provided by the openapi-generator repository.

The generator is generating with `useSingleRequestParameter` as true, no matter the setting.

# Reproduce

The code in the repo at HEAD is based on the configuration that is also checked in. 

To reproduce the behavior:

* Install the deps with `npm install`
* Edit the `openapitools.json` file
* Set `useSingleRequestParameter: false`
* Run the generator script `npm run generate` which runs the generator cli with only the generate option
* Observe that there is no diff, the generated source did not change 

## Notes

The PR that added the option to the generator is [here](https://github.com/OpenAPITools/openapi-generator/pull/6288)
