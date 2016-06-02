# Drush progress bar API

## Usage

Given that:
 *  you have ```$total``` which is the total number of items to process;
 *  and ```$done``` is the item count processed so far;

you may do:

```php

$total = some_count();

$bar = \DrushProgressBar::create();
$bar->start();

$done = 0;
foreach ($items as $item) {
  process_item($item);

  // Note that here, you could also change the total (yes you can).
  $bar->setProgress($total, ++$done);
}

$bar->end();

```
