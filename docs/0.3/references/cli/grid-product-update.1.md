% GRID-PRODUCT-UPDATE(1) Cargill, Incorporated | Grid Commands
<!--
  Copyright 2018-2020 Cargill Incorporated
  Licensed under Creative Commons Attribution 4.0 International License
  https://creativecommons.org/licenses/by/4.0/
-->

NAME
====

**grid-product-update** — Updates existing products

SYNOPSIS
========

**grid product update** \[**FLAGS**\] \[**OPTIONS**\]

DESCRIPTION
===========

Updates existing products. This command requires the `--path` option
to specify the path to a YAML file containing a list of products.

FLAGS
=====

`-h`, `--help`
: Prints help information

`-k`, `--key`
: Base name for private key file

`-q`, `--quiet`
: Do not display output

`--service-id`
: The ID of the service the payload should be sent to; required if running on
  Splinter. Format <circuit-id>::<service-id>

`-V`, `--version`
: Prints version information

`-v`
: Increases verbosity (the opposite of `-q`). Specify multiple times for more
  output

`--url`
: URL for the REST API

`--wait`
: How long to wait for transaction to be committed

OPTIONS
=======

`--path`
: Path to a YAML file containing a list of products

EXAMPLES
========

Products can be updated by using the `update` command

```
$ grid product update \
    --path products.yaml
```

Sample YAML file describing products.

```
- product_namespace: "GS1"
  product_id: "762111177704"
  owner: "314156"
  properties:
    - name: "length"
      data_type: "NUMBER"
      number_value: 8
    - name: "width"
      data_type: "NUMBER"
      number_value: 12
    - name: "height"
      data_type: "NUMBER"
      number_value: 4
- product_namespace: "GS1"
  product_id: "881334009880"
  owner: "314156"
  properties:
    - name: "length"
      data_type: "NUMBER"
      number_value: 8
    - name: "width"
      data_type: "NUMBER"
      number_value: 12
    - name: "height"
      data_type: "NUMBER"
      number_value: 12
```

ENVIRONMENT VARIABLES
=====================

**`GRID_DAEMON_ENDPOINT`**
: Specifies the endpoint for the grid daemon (`gridd`)
  if `-U` or `--url` is not used.

**`GRID_DAEMON_KEY`**
: Specifies key used to sign transactions if `k` or `--key`
  is not used.

**`GRID_SERVICE_ID`**
: Specifies service ID if `--service-id` is not used

SEE ALSO
========
| `grid-product-create(1)`
| `grid-product-update(1)`
| `grid-product-delete(1)`
| `grid-product-show(1)`
| `grid-product-list(1)`
|
| Grid documentation: https://grid.hyperledger.org/docs/0.3/
