Experiments in decoding OpenTRV frame formats. More detailed notes in the [wiki](https://github.com/opentrv/OTWiki/wiki/Adventures-in-SDR)
- Example GNU-Radio Companion files are *.grc
- Example decoded OOK packets in decoded_ook.dat. Recommend viewing with xxd or a hex editor.
- Raw I/Q files are stored in SDR.tar.xz
    - Captured from a REV10 programmed to Tx ```aaaaaaaa{1234567890}``` several times a second.
    - Filename in form ```<encoding>_example_<centre_freq>_<sample_rate>_fc.raw```
    - Can be replayed with Gqrx or read by GNU-Radio as a file source.
