# Caesar Cipher 🗝️
A lightweight utility for performing ceasar ciphers. The cipher shifts characters in a given string by a specified amount to provide a small layer of encryption. Supports shifting in english alphabet (a-zA-Z) and the human-readable ASCII characters between decimal value [33-126].

Default rotation is 13 (ROT13). A custom array of rotations matching the length of the input string can also be provided to create more customized transformations. Random rotations can be generated.

Use cases:
- perform basic, custom, and randomized caesar ciphers
- generate a cool username / social media handle

## Installation
Install the plugin from npm:

```shell
npm install rotation-cipher
```

### Example usage

### Basic Cipher
Rotate each character by the default 13 characters:
```js
const s = caesarCipher('tanner')
console.log(s)
// gnaare
```

### User defined uniform rotation
Rotate each character by a uniform rotation:
```js
const s = caesarCipher('tanner', 17)
console.log(s)
// kreevi
```

### Custom rotation array
Rotate each character by a specific rotation:
```js
const s = caesarCipher('tanner', null, [3, 5, 1, 2, 7, 8])
console.log(s)
// wfoplz
```

### Random rotation

```js
const input = 'tanner'
const s  = caesarCipher(input, null, randomRotation(input))
console.log(s)
// jiwogv
```

### Store ciphers
Write generated ciphers to an output file.

```js
const out = writeCiphers({
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

console.log(out.fileContent)
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

Each file will have a timestamp included after the filename to ensure all records can be maintained.

### Functions
<ul>
    <li>
        <a href='https://github.com/tannerdolby/rotation-cipher/blob/master/index.js/#L4'>caesarCipher</a>
    </li>
    <li>
        <a href='https://github.com/tannerdolby/rotation-cipher/blob/master/index.js/#L28'>decrypt</a>
    </li>
    <li>
        <a href='https://github.com/tannerdolby/rotation-cipher/blob/master/index.js/#L77'>writeCiphers</a>
    </li>
    <li>
        <a href='https://github.com/tannerdolby/rotation-cipher/blob/master/index.js/#L142'>createDir</a>
    </li>
    <li>
        <a href='https://github.com/tannerdolby/rotation-cipher/blob/master/index.js/#L151'>writeFile</a>
    </li>
    <li>
        <a href='https://github.com/tannerdolby/rotation-cipher/blob/master/index.js/#L32'>rotate</a>
    </li>
    <li>
        <a href='https://github.com/tannerdolby/rotation-cipher/blob/master/index.js/#L119'>getUniformCiphers</a>
    </li>
    <li>
        <a href='https://github.com/tannerdolby/rotation-cipher/blob/master/index.js/#L127'>getCustomCiphers</a>
    </li>
    <li>
        <a href='https://github.com/tannerdolby/rotation-cipher/blob/master/index.js/#L135'>getRandomCiphers</a>
    </li>
    <li>
        <a href='https://github.com/tannerdolby/rotation-cipher/blob/master/index.js/#L69'>getUniqueRotations</a>
    </li>
    <li>
        <a href='https://github.com/tannerdolby/rotation-cipher/blob/master/index.js/#L62'>randomRotation</a>
    </li>
</ul>

### Resources
- https://en.wikipedia.org/wiki/Caesar_cipher