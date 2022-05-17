# Questions

### What is the best way to handle strings in Move?

It's a bit hard to find in the documentation, but strings are handled as vectors that are defined inline and can be constructed via hexadecimal literal or bytestring literal of type `vector<u8>`:

```move
// These are both "hello world" strings

let hexStr = x"68656c6c6f20776f726c64";

let byteStr = b"hello world";
```

In either case they are of type `vector<u8>`

More info here:
(https://move-book.com/advanced-topics/managing-collections-with-vectors.html#hex-and-bytestring-literal-for-inline-vector-definitions)

### What is the best way to handle time in Move?

Answer provided by Sam Blackshear:

> For now, we only have a coarse notion of time available via epoch numbers. A new epoch begins every 24 hours.
>
> The current epoch number can be read in Move via [SuiSystem::epoch:](https://github.com/MystenLabs/sui/blob/main/sui_programmability/framework/sources/Governance/SuiSystem.move#L262), but we are working on making the epoch number readable from TxContext, which will be more convenient ([https://github.com/MystenLabs/sui/issues/1980](https://github.com/MystenLabs/sui/issues/1980)).
>
> A finer-grained notion of time is coming, but will take a bit longer--follow [https://github.com/MystenLabs/sui/issues/1696](https://github.com/MystenLabs/sui/issues/1696) for updates.

### Can you generate a random number in Move?

In Move, like other smart contract languages, the contract needs to be deterministic (produce the same output for the same input every time). If you had a random value generated within the contract it would produce a different ouput for each input you provided and would not be deterministic. In order to use random values you need to provide them from outside the contract via parameters (i.e. pass in the random value).
