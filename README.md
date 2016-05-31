﻿
# Ghost Azure

This module allows you to store media file at Azure instead of storing at local machine.

## Installation

#### *nix

* `npm install ghost-azurestorage` (note the absence of `--save`)
* `mkdir content/storage` (make the storage folder if it doesn't exist yet)
* `cp -vR node_modules/ghost-azurestorage content/storage/ghost-azurestorage` (copy the module into the right location)

#### powershell
* `npm install ghost-azurestorage` (note the absence of `--save`)
* `mkdir content/storage` (make the storage folder if it doesn't exist yet)
* `cp -Recurse node_modules/ghost-azurestorage content/storage/ghost-azurestorage` (copy the module into the right location)

## Create storage module

Create index.js file with folder path 'content/storage/ghost-azurestorage/index.js' (manually create folder if not exist)

    'use strict';
    module.exports = require('ghost-azure-storage');

## Configuration

Create new azure storage account, and get the connection string (can be found in the preview portal)

Add `storage` block to file `config.js` in each environment as below:
```
     storage: {
			active: 'ghost-azurestorage',
			'ghost-azurestorage': {
				connectionString: 'YourConnectionStringHere',
				container: 'YourOptionalContainerName',
				cdnUrl: "YourCDNEndpointDomain",
				useHttps : "UseHttpsInEndpoint" //Optional: CDN protocol. Defaults to http if omitted. Set to "true", to enable.
			}
		},

```

## Environment Variables

You can set your connection string as the Environment Variable `AZURE_STORAGE_CONNECTION_STRING`

Released under the [MIT license](https://github.com/muzix/ghost-s3/blob/master/LICENSE).
