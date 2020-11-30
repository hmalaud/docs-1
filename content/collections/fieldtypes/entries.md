---
title: Entries
meta_title: 'Entries Fieldtype'
description: 'Create relationships with other entries.'
intro: |
  Create relationships with other entries in one or more collections. It's not very much like online dating because you can create and link the entries on the fly without leaving the page.
screenshot: fieldtypes/entries.png
video: https://youtu.be/WWbsM5u9afc
options:
  -
    name: collection
    type: array
    description: |
      Configure which collections you want to allow relationships with.

  -
    name: max_items
    type: integer
    description: >
      The maximum number of items that may be selected. Setting this to `1` will change the UI to a dropdown.
stage: 4
id: acee879a-c832-449d-a714-c57ea5862717
---
## Overview

Use this fieldtype to create a one-way relationship with entries of any collection in your site. It's delightfully simple.

## Data Structure

This fieldtype will store an array of ids to the selected entries. They will be augmented in your Antlers templates to give you access to each entry's data.

``` yaml
related_entries:
  - 12f9be1f-a12e-4680-b769-639d2d1f1d14
  - ea48926d-bf67-4d45-9420-9627a31c37fb
  ```

## Templating

Loop through the entries and do anything you want with the data.

```
<ul>
  {{ related_entries }}
    <li><a href="{{ url }}">{{ title }}</a></li>
  {{ /related_entries }}
</ul>
```

``` output
<ul>
  <li><a href="/look-at-this">Look at This!</a></li>
  <li><a href="/look-at-that">Wait, Look at That!</a></li>
</ul>
```

## Config Options