Experiments in decoding OpenTRV frame formats. More detailed notes in the [wiki](https://github.com/opentrv/OTWiki/wiki/Adventures-in-SDR)
- ```*.grc``` files can be opened with the [GNU Radio Companion](https://wiki.gnuradio.org/index.php/Main_Page).
    - File Source and File Sink filepaths will need to be changed.
- Example decoded OOK packets in decoded_ook.dat. Recommend viewing with xxd or a hex editor.
- Raw I/Q files are stored in SDR.tar.xz
    - Captured from a REV10 programmed to Tx ```aaaaaaaa{1234567890}``` several times a second. Sketch [here](https://github.com/opentrv/OpenTRV-Arduino-V0p2/blob/master/Arduino/hardware/REV10/REV10RadioTest/REV10RadioTest.ino).
    - Filename in form ```<encoding>_example_<centre_freq>_<sample_rate>_fc.raw```
    - Can be replayed with Gqrx or read by GNU-Radio as a file source.
