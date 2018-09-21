minih264
==========

[![Build Status](https://travis-ci.org/lieff/minih264.svg)](https://travis-ci.org/lieff/minih264)

Small, but yet reasonable fast H264/SVC encoder single-header library with SSE/NEON optimizations.
Decoder can be popped up in future.

Disclamer: code highly experemental.

## Comparison with [x264](https://www.videolan.org/developers/x264.html)

Rough comparision with x264 on an i7-6700K:

`x264 -I 30 --profile baseline --preset veryfast --tune zerolatency -b 0 -r 1 --qp 33 --ipratio 1.0 --qcomp 1.0 -o x264.264 --fps 30 vectors/foreman.cif --input-res 352x288 --slices 1 --threads 1`

vs

`./h264enc_x86 vectors/foreman.cif`

| x264         | minih264 |
| ------------ | -------- |
| source: ~4.6mb | 409kb |
| binary: 1.2mb | 100kb |
| time: 0,282s | 0,503s |
| out size: 320kb | 391kb  |

PSNR:
```
x264:     PSNR y:32.774824 u:38.874450 v:39.926132 average:34.084281 min:31.842667 max:36.630286
minih264: PSNR y:33.321686 u:38.858879 v:39.955914 average:34.574459 min:32.389171 max:37.174073
```

## Usage

TBD

## Interesting links

 * https://www.videolan.org/developers/x264.html
 * https://www.openh264.org/
 * https://github.com/cisco/openh264
 * http://iphome.hhi.de/suehring/tml/
 * https://github.com/oneam/h264bsd
 * https://github.com/fhunleth/hollowcore-h264
 * https://github.com/digetx/h264_decoder
 * https://github.com/lspbeyond/p264decoder
 * https://github.com/jcasal-homer/HomerHEVC
 * https://github.com/neocoretechs/h264j
 * https://github.com/jcodec/jcodec