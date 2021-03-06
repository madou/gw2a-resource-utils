# [gw2-resource-utils](https://github.com/madou/gw2-resource-utils)

[![NPM version](http://img.shields.io/npm/v/gw2-resource-utils.svg?style=flat-square)](https://www.npmjs.com/package/gw2-resource-utils)
[![NPM downloads](http://img.shields.io/npm/dm/gw2-resource-utils.svg?style=flat-square)](https://www.npmjs.com/package/gw2-resource-utils)
[![Build Status](http://img.shields.io/travis/madou/gw2-resource-utils/master.svg?style=flat-square)](https://travis-ci.org/madou/gw2-resource-utils)
[![codecov](https://codecov.io/gh/madou/gw2-resource-utils/branch/master/graph/badge.svg)](https://codecov.io/gh/madou/gw2-resource-utils)
[![Dependency Status](http://img.shields.io/david/madou/gw2-resource-utils.svg?style=flat-square)](https://david-dm.org/madou/gw2-resource-utils)

Creates maps of gw2 resources with associated helper utilities.

## Installation

```sh
npm install gw2-resource-utils
```

## Api

### `build (resourceName: string) => Promise<ResourceMap>`

```javascript
import { build } from 'gw2-resource-utils';

const nameToIdMap = await build('items');
// { "MONSTER ONLY Moa Unarmed Pet":1 ... }
```

#### `ResourceMap`

```json
{
 "Item Name": 10
}
```

### `exact (map: ResourceMap, itemName: string) => ?number`

```javascript
import { exact } from 'gw2-resource-utils';

const itemId = exact(nameToIdMap, 'MONSTER ONLY Moa Unarmed Pet');
// 1
```

### `fuzzy (map: ResourceMap, itemName: string) => ?number`

```javascript
import { fuzzy } from 'gw2-resource-utils';

const items = fuzzy(nameToIdMap, 'monster');
// { "Legendary Kudu's Monster Loot Box": 65497, ... }
```

### Testing

```bash
npm test
```
