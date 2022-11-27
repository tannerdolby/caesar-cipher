# Caesar Cipher 🗝️
A lightweight utility for performing ceasar ciphers. The cipher shifts characters in a given string by a specified amount to provide a small layer of encryption. Supports shifting in english alphabet (a-zA-Z) and the human-readable ASCII characters between decimal value [33-126].

Default rotation is 13 (ROT13). A custom array of rotations matching the length of the input string can also be provided to create more customized transformations. Random rotations can be generated.

Use cases:
- perform basic, custom, and randomized caesar ciphers
- generate a cool username / social media handle

## Installation
Install the plugin from [npm](https://www.npmjs.com/package/rotation-cipher):

```shell
npm install rotation-cipher
```

Create ciphers on the fly:

```js
const { caesarCipher } = require('rotation-cipher')

console.log(caesarCipher('tanner', 21))
// oviizm
```

### Example usage

#### Basic Cipher
Rotate each character by the default 13 characters:
```js
console.log(caesarCipher('tanner'))
// gnaare
```

#### User defined uniform rotation
Rotate each character by a uniform rotation:
```js
console.log(caesarCipher('tanner', 17))
// kreevi
```

#### User defined uniform rotation (with ASCII)
Rotate each character by a uniform rotation including ASCII:
```js
console.log(caesarCipher('tanner', 17, null, true))
// @Xee\>
```

#### Custom rotation array
Rotate each character by a specific rotation:
```js
console.log(caesarCipher('tanner', null, [3, 5, 1, 2, 7, 8]))
// wfoplz
```

#### Random rotation
Rotate each character by a random rotation:
```js
console.log(caesarCipher('tanner', null, randomRotation(input)))
// jiwogv
```

#### Store ciphers
Write generated ciphers to an output file. Each file will have a timestamp included after the filename to ensure all records can be maintained.

```js
const { writeCiphers } = require('rotation-cipher')

const res = writeCiphers({
    input: 'tanner',
    folder: './shh',
    filename: 'ciphers.txt',
    customRotations: [
        [15, 2, 8, 19, 12, 21],
        [3, 13, 11, 17, 10, 25],
    ],
    useAscii: false,
    randomRotations: 250
})

// Use .then method or use await within an async function
res.then(data => {
    console.log(data.filePath)
    // ./shh/ciphers-2022-11-27T03:52:39.937Z.txt

    console.log(res.fileContent)
})

/* 
---------- Uniform Rotations ----------
input: tanner
name   | rotation
---------------------------------------
uboofs | 1
vcppgt | 2
wdqqhu | 3
xerriv | 4
...
szmmdq | 25
tanner | 26
---------- Custom Rotations ----------
mwwcoo | [19,22,9,15,10,23]
arzytm | [7,17,12,11,15,21]
---------- Random Rotations ----------
tmcrgc | [26,12,15,4,2,11]
ottpvl | [21,19,6,2,17,20]
juekeu | [16,20,17,23,26,3]
...
*/
```

### Resources
- https://en.wikipedia.org/wiki/Caesar_cipher