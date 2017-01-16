# sample-eme
A sample web player using Encrypted Media Extensions

## Generate MP4 DASH contents protected by Common Encryption with Clear Key

Generate a fragmented MP4 file with a key and a kid for Clear Key specified by MP4ENCRYPT.

```
mp4encrypt --method MPEG-CENC --key 1:00112233445566778899aabbccddeeff:6770616363656E6364726D746F6F6C31 --property 1:KID:000102030405060708090a0b0c0d0e0f  --pssh-v1 1077efecc0b24d02ace33c1e52e2fb4b: 240pf.mp4 encrypted_240pf.mp4
```

Generate a MPEG-DASH stream by mp4-dash.

```
path-to-Bento4-SDK/utils/mp4-dash.py --profile=urn:mpeg:dash:profile:isoff-live:2011 --use-segment-timeline encrypted_240pf.mp4
```

### Reference

1. [https://www.bento4.com/documentation/mp4encrypt/](https://www.bento4.com/documentation/mp4encrypt/)


## Create a WebM file protected by Common Encryption with Clear Key

Encrypt a WebM file by 

```
./webm_crypt -o crypt.webm -i ./big-buck-bunny_trailer.webm -video true -audio true -video_options content_id=0123456789012345,base_file=bear1.key -audio_options content_id=0123456789012345,base_file=bear1.key
```

### Reference

1. [https://docs.google.com/document/d/17d6_KX5jX0gY1ygYbjqOEdVzuUGkPO53wL8t40dMGeQ/edit](https://docs.google.com/document/d/17d6_KX5jX0gY1ygYbjqOEdVzuUGkPO53wL8t40dMGeQ/edit)
2. [https://github.com/webmproject/webm-tools/tree/master/webm_crypt](https://github.com/webmproject/webm-tools/tree/master/webm_crypt)
