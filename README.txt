Benchmark CSS without and without Metamorphs
============================================

Testing methodology:

- Use Latest Chrome (21.0.1180.89) on Mac OSX Mountain Lion.
- Machine is a 3.53 Ghz Intel Core i7 with 32GB of RAM (3770k Hackintosh)


1) Load index.html fresh
2) Turn on profiling in chrome
3) Click the appropriate button
4) Record the value for Recalculate Style only (not concerned with DOM insertion speeds, just CSS)


Loop count = 1000:

  Without Metamorphs (1013 DOM elements):
  avg = 5ms

  With Metamorphs (3012 DOM elements):
  avg = 40ms

Loop count = 10000:

  Without Metamorphs (10012 DOM elements)
  avg = 647ms

  With Metamorphs: (30012 DOM elements)
  avg = 3930ms

Conclusion:

- It seems having the extra script tags in the DOM do slow down CSS rendering quite a bit.
- On a DOM with 1000 metamorphs, the slowdown is 8x
- On a DOM with 10000 metamorphs, the slowdown is 6x

