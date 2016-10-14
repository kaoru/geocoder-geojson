[![Build Status](https://travis-ci.org/DenisCarriere/geocoder-geojson.svg?branch=master)](https://travis-ci.org/DenisCarriere/geocoder-geojson)
[![Coverage Status](https://coveralls.io/repos/github/DenisCarriere/geocoder-geojson/badge.svg?branch=master)](https://coveralls.io/github/DenisCarriere/geocoder-geojson?branch=master)
[![npm version](https://badge.fury.io/js/geocoder-geojson.svg)](https://badge.fury.io/js/geocoder-geojson)

# [Geocoder GeoJSON](https://www.npmjs.com/package/geocoder-geojson)

Geocoding results in standard GeoJSON geographic data structures.

## Install

```bash
$ npm install --save geocoder-geojson
```

## Quickstart

```javascript
import * as geocoder from 'geocoder-geojson'

geocoder.google('New York City')
  .then(geojson => console.log(geojson))
```

## Providers

| Providers       | Coverage    | Restrictions |
|-----------------|:------------|:-------------|
| Google          | Global      | API Key      |
# google

Google Provider

**Parameters**

-   `address` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Location for your search
-   `short` **\[[boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)]** Google address components have long or short results (optional, default `true`)

**Examples**

```javascript
geocoder.google('Ottawa')
  .then(data => data.results)
```

Returns **GoogleResults** JSON Object

# confidenceScore

Generates a confidence score from 1 (worst) to 10 (best) from a given BBox

**Parameters**

-   `bbox` **BBox** extent in [minX, minY, maxX, maxY] order

**Examples**

```javascript
confidenceScore([-75.1, 45.1, -75, 45])
//=4
confidenceScore([-75.001, 45.001, -75, 45])
//=10
```

Returns **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** confidence score

# replaceStreetSuffix

Replaces Street Suffix with a complete word

**Parameters**

-   `name` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** street name

**Examples**

```javascript
replaceStreetSuffix('Foo Bar St')
//='Foo Bar Street'
replaceStreetSuffix('Foo Bar Dr.')
//='Foo Bar Drive'
```

Returns **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** name replace street suffix

# Changelog

## 1.0.0 - 2016-10-14

First Stable release was created

Features:

- `google` provider
- `confidenceScore`
- `replaceStreetSuffix`
