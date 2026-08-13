---
publish: true
title: ukranian guitars
description: guitarras en dorian#4
socialDescription: guitarras en dorian#4
created: 2025-08-29
modified: 2026-08-02
published: 2026-08-02
Author: liminal-garden
tags:
- audio
- strudel
---

[Strudel REPL](https://strudel.cc/#c2FtcGxlcygnZ2l0aHViOmxpbWluYWxnYXJkZW4xNTgvYnJlYWtzJykKCnNldGNwcyg3MC82MC80KQoKJDogY2hvcmQoIjxDbTcgRDcgRWJNNyBENz4iKS52b2ljaW5nKCkKLnN0cnVjdCgiW1stIHhdIFstIHhdIC0geCAtIHhdKjIiKQoucygiZ21fYWNvdXN0aWNfZ3VpdGFyX3N0ZWVsIikKLmRlYygwLjgpCi5nYWluKDIpCgokOiBuKGlyYW5kKDE2KS5zZWcoMTYpKS5zY2FsZSgnYzQgZG9yaWFuICM0JykKLnN0cnVjdChyYW5kLm11bCgiMS4yIikucm91bmQoKS5zZWcoMjQpKQouZGVsYXkoMi41KS5kZWxheXRpbWUocmFuZC5yb3VuZCgpLnNlZygyNCkpCi5wYW4oc2luZS5zbG93KDIpKQouZ2FpbigyKQoucygiZ21fYWNvdXN0aWNfZ3VpdGFyX3N0ZWVsIikKCiQ6IHMoImJyZWFrczozLzIiKS5maXQoKS5nYWluKDEuNSkKLnNjcnViKGlyYW5kKDE2KS5kaXYoMTYpLnNlZygyNCkpCi5ocGYoNTAwKQouY29hcnNlKDIpCgokOiBzKCJiZCg3LDEyKSIpCgokOiBzKGBbLSBbLSBzZF0gLSBbc2RdIFstIHNkXSAtXQpbWy0gc2RdIHNkIC0gWy0gc2RdIC0gc2RdCmApLm4oNikuZ2FpbigxLjMpCgokOiBzKCJyaW06MSIpLnN0cnVjdChyYW5kLm11bCgxLjQpLnJvdW5kKCkuc2VnKDI0KSkuZ2FpbigxLjIpCgokOiBzKCJ3aGl0ZSExMiIpLmRlYyh0cmkucmFuZ2UoMC4wOCwwLjEzKSkK)

<iframe src="https://strudel.cc/#c2FtcGxlcygnZ2l0aHViOmxpbWluYWxnYXJkZW4xNTgvYnJlYWtzJykKCnNldGNwcyg3MC82MC80KQoKJDogY2hvcmQoIjxDbTcgRDcgRWJNNyBENz4iKS52b2ljaW5nKCkKLnN0cnVjdCgiW1stIHhdIFstIHhdIC0geCAtIHhdKjIiKQoucygiZ21fYWNvdXN0aWNfZ3VpdGFyX3N0ZWVsIikKLmRlYygwLjgpCi5nYWluKDIpCgokOiBuKGlyYW5kKDE2KS5zZWcoMTYpKS5zY2FsZSgnYzQgZG9yaWFuICM0JykKLnN0cnVjdChyYW5kLm11bCgiMS4yIikucm91bmQoKS5zZWcoMjQpKQouZGVsYXkoMi41KS5kZWxheXRpbWUocmFuZC5yb3VuZCgpLnNlZygyNCkpCi5wYW4oc2luZS5zbG93KDIpKQouZ2FpbigyKQoucygiZ21fYWNvdXN0aWNfZ3VpdGFyX3N0ZWVsIikKCiQ6IHMoImJyZWFrczozLzIiKS5maXQoKS5nYWluKDEuNSkKLnNjcnViKGlyYW5kKDE2KS5kaXYoMTYpLnNlZygyNCkpCi5ocGYoNTAwKQouY29hcnNlKDIpCgokOiBzKCJiZCg3LDEyKSIpCgokOiBzKGBbLSBbLSBzZF0gLSBbc2RdIFstIHNkXSAtXQpbWy0gc2RdIHNkIC0gWy0gc2RdIC0gc2RdCmApLm4oNikuZ2FpbigxLjMpCgokOiBzKCJyaW06MSIpLnN0cnVjdChyYW5kLm11bCgxLjQpLnJvdW5kKCkuc2VnKDI0KSkuZ2FpbigxLjIpCgokOiBzKCJ3aGl0ZSExMiIpLmRlYyh0cmkucmFuZ2UoMC4wOCwwLjEzKSkK" width="600" height="400"></iframe>

```javascript title:"sketch.js"
samples('github:liminalgarden158/breaks')

setcps(70/60/4)

$: chord("<Cm7 D7 EbM7 D7>").voicing()
.struct("[[- x] [- x] - x - x]*2")
.s("gm_acoustic_guitar_steel")
.dec(0.8)
.gain(2)

$: n(irand(16).seg(16)).scale('c4 dorian #4')
.struct(rand.mul("1.2").round().seg(24))
.delay(2.5).delaytime(rand.round().seg(24))
.pan(sine.slow(2))
.gain(2)
.s("gm_acoustic_guitar_steel")

$: s("breaks:3/2").fit().gain(1.5)
.scrub(irand(16).div(16).seg(24))
.hpf(500)
.coarse(2)

$: s("bd(7,12)")

$: s(`[- [- sd] - [sd] [- sd] -]
[[- sd] sd - [- sd] - sd]
`).n(6).gain(1.3)

$: s("rim:1").struct(rand.mul(1.4).round().seg(24)).gain(1.2)

$: s("white!12").dec(tri.range(0.08,0.13))

```
