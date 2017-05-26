# count-min-sketch

A Count-Min Sketch implementation in C.

Count-Min Sketch is a probabilistic data-structure that takes sub linear space
to store the probable count of occurrences of elements added into the
data-structure. Due to the structure and strategy of storing elements, it is
possible that elements are over counted.

## License:
MIT 2017

## Main Features:
* Ability to add and remove elements from the Count-Min Sketch
* Ability to lookup elements in the data-structure
* Multiple lookup types:
    * Minimum
    * Mean (good for when removes and negatives are possible, but increases
        the false count upwards)

## Future Enhancements
* update tests to be more in-depth
* document the .h file
* add export/import (?)
* add width and depth calculators (?) - https://cs.stackexchange.com/q/44803

## Usage:
``` c
#include <stdio.h>
#include "count_min_sketch.h"

CountMinSketch cms;
cms_init(&cms, 10000, 7);

int i, res;
for (i = 0; i < 10; i++) {
    res = cms_add(&cms, "this is a test");
}

res = cms_check(&cms, "this is a test");
if (res != 10) {
    printf("Error with lookup: %d\n", res);
}
cms_destroy(&cms);
```
