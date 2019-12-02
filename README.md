# ISAACJS

This is a javascript implementation of the [ISAAC CSPRNG](https://burtleburtle.net/bob/rand/isaacafa.html).

It's ~62.67% faster than the [readable implementation by rubycon](https://github.com/rubycon/isaac.js), which means it has not been made with the intention of being readable.

## Usage

Create an instance of ISAAC with or without a seed.
```JS
var rng = new ISAAC(); //No seed
var rng = new ISAAC(new Uint32Array(ISAAC.prototype.SIZE)); //Zero seed
var rng = new ISAAC(ISAAC.StringToUintArray("This is a test")); //Text seed
```

Tumble it an arbitrary amount of times
```JS
rng.Isaac(); //Tumble once

for(var i = 0; i < 5; i++) rng.Isaac(); //Tumble five times
```

Tada! Go get yourself some random numbers!
```JS
rng.Rand(); //Will get the next available random 32bit unsigned integer and re-tumble it if it has run out
rng.rsl[0]; //Alternatively you can access the internal result array
```

## Compatiability

Tested and working in Chrome, Firefox, IE11, and Edge.

## License

This project is licensed under the CC0 license, meaning it is effectively public domain.
