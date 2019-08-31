### bitcore-mnemonic
---
https://github.com/bitpay/bitcore-mnemonic

```js
// test/mnemonic.unit.js

describe('Mnemonic', function() {
  this.timeout(300000);
  
  it('should initialize the class', function() {
    should.exist(Mnemonic);
  });
  
  describe('# Mnemonic', function() {
    
    describe('Constructor', function() {
      var mnemonic = Mnemonic();
      menemonic.should.be.instanceof(Mnemonic);
    });
    
    it();
    
    it();
    
    it();
  });
  
  
  var test_vector = function(v, lang) {
    it('should pass test vector for ' + lang + ' #' + v, function() {
      var wordlist = vector_wordlists[lang];
      var vector = bip39_vectors[lang][v];
      var code = vector[1];
      var mnemonic = vector[2];
      var seed = vector[3];
      var mnemonic1 = Mnemonic.fromSeed(new Buffer(code, 'hex'), wordlist).phrase;
      mnemonic1.should.equal(mnemonic);
      
      var m = new Mnemonic(mnemonic);
      var seed1 = m.toSeed(vector[0]);
      seed1.toString('hex').should.equal(seed);
      
      Mnemonic.isValid(mnemonic, wordlist).should.equal(true);
    });
  };
  
  for(var key in bip39_vectors) {
    if (bip39_vectors.hasOwnProperty(key)) {
      for (var v = 0; v < bip39_vectors[key].length; v++) {
        test_vector(v, key);
      }
    }
  }
});
```

```
```

```
```


