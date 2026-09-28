# Countess-Variant-Caller

This is a variant caller which makes HGVS variant strings from DNA sequences.
It it part of the [CountESS Project](https://github.com/CountESS-Project/)
but may be used separately.

It is intended to be fast and efficient when finding a small variation from a 
known sequence, as is common in mutational scanning experiments.

Typical usage calling DNA changes:

```
>>> from countess_variant_caller import find_variant_string

>>> find_variant_string("g.", "GATTACA", "GTTTACA")
'g.2A>T'

>>> find_variant_string("g.", "GATTACA", "GTTCAGA")
'g.[2A>T;4T>C;6C>G]'
```

It also does protein variant calling:

```
>>> from countess_variant_caller import find_variant_string

>>> find_variant_string("p.", "ATGGTTGGTTCA", "ATGGTTGGTGGTTCA")
'p.Gly3dup'

>>> find_variant_string("p.", "ATGGTTGGTTCA", "ATGGCTGCTTCA")
'p.Val2_Gly3delinsAlaAla'
```

## Contributors

* Nick Moore `nick@zoic.org`.

## License

Copyright (C) 2022- CountESS Developers under BSD 3-Clause license,
see `LICENSE.txt`.
