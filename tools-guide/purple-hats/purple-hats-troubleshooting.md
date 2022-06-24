# Troubleshooting


For any technical issues in using Purple HATS, raise a service request under [Purple HATS - Accessibility Testing](https://jira.ship.gov.sg/servicedesk/customer/portal/11/create/212).

## Troubleshooting
Please refer to the information below to exist in debugging. Most errors below are due to the switching between Node.js versions.

### Incompatible Node.js versions
**Issue**: When your Node.js version is incompatible, you may face the following syntax error.
**Solution**: Install Node.js versions > v15.10.0, i.e. Node.js v16 and above.
```shell
const URL_NO_COMMAS_REGEX = RegExp('https?://(www\\.)?[\\p{L}0-9][-\\p{L}0-9@:%._\\+~#=]{0,254}[\\p{L}0-9]\\.[a-z]{2,63}(:\\d{1,5})?(/[-\\p{L}0-9@:%_\\+.~#?&//=\\(\\)]*)?', 'giu'); // eslint-disable-line
                            ^
SyntaxError: Invalid regular expression: /https?://(www\.)?[\p{L}0-9][-\p{L}0-9@:%\._\+~#=]{0,254}[\p{L}0-9]\.[a-z]{2,63}(:\d{1,5})?(/[-\p{L}0-9@:%_\+.~#?&//=\(\)]*)?/: Invalid escape
```

### Compiled against a different Node.js version
**Issue**: When you switch between different versions of Node.js in your environment, you may face the following error.
```shell
<user_path>/purple-hats/node_modules/bindings/bindings.js:91
        throw e
        ^

Error: The module '<module_file_path>'
was compiled against a different Node.js version using
NODE_MODULE_VERSION 57. This version of Node.js requires
NODE_MODULE_VERSION 88. Please try re-compiling or re-installing
the module (for instance, using `npm rebuild` or `npm install`).
```
**Solution**: As recommended in the error message, run `npm rebuild` or `npm install`

### dyld Error
**Issue**: Not able to run Purple HATS due to the following error shown below
```shell
dyld: lazy symbol binding failed: Symbol not found: __ZN2v87Isolate37AdjustAmountOfExternalAllocatedMemoryEx
  Referenced from: <user_path>/purple-hats/node_modules/libxmljs/build/Release/xmljs.node
  Expected in: flat namespace

dyld: Symbol not found: __ZN2v87Isolate37AdjustAmountOfExternalAllocatedMemoryEx
  Referenced from: <user_path>/PURPLE_HATS/purple-hats/node_modules/libxmljs/build/Release/xmljs.node
  Expected in: flat namespace

zsh: abort      node index.js
```
**Solutions**:
1. Delete existing `node_modules` folder and re-install the NPM packages with `npm install`.
3. Refer to this [GitHub issue](https://github.com/fsevents/fsevents/issues/313) for more alternative solutions

## How do I limit number of pages scanned?
If you find a scan takes too long to complete due to large website, or there are too many pages in a sitemap to scan, you may choose to limit number of pages scanned.  

To do this, open `constants\constants.js` with a text editor.  Change the value `exports.maxRequestsPerCrawl` to a smaller number, e.g. `exports.maxRequestsPerCrawl = 10;` and save the file.  Start a new purple-hats scan.
