# Mongoid Monkey

### Monkey Patches for Mongoid

Mongoid Monkey is a collection of monkey patches for Mongoid 3, 4, 5, including feature
backports, fixes, and forward compatibility.

#### Warning #1

In your Gemfile, require this gem **after** requiring `mongoid`.

#### Warning #2

The patches in this gem will change/override the behavior of Mongoid. While effort has been
made to be as backward compatible as possible, use at your own risk.

### Version Requirement

* Works with Mongoid 3, 4, 5
* Due to the `list_collections` patch, this gem requires **at least MongoDB 3.0.** Other patches will work on older MongoDB versions.

### Patch List

Installing this gem will apply all monkey patches for the Mongoid version you are using.
If you would only like some of the patches, please copy and paste the code to your app directly
(e.g. `/config/initializers` if using Rails.)

| File | Description | 3 | 4 | 5 |
| `atomic.rb` | Backport syntax change of atomic query methods. | O | - | - |
| `big_decimal.rb` | Fixes buggy BigDecimal behavior. | O | O | O |
| `instrument.rb` | Backport instrumentation change to Moped 1. | O | - | - |
| `list_collections.rb` | Fetch collections via `listCollections` command; required for WiredTiger. | O | O | - |
| `reorder.rb` | Backport `Criteria#reorder` method. | O | - | - |

### License

* This project is licensed under the MIT License.
* Some code in this repo is adapted from the fantastic work of Durran Jordan, et. al. on Mongoid.
* (c) Copyright 2016 Johnny Shields.