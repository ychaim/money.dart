# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/) 
and this project adheres to [Semantic Versioning](http://semver.org/).

## Unreleased
### Added
- Dependency on `meta ^1.1.7`.
- Annotations `@immutable` and `@sealed` to `Money`, `Currency`, `MoneyData`.

## 1.0.0-alpha.1 - 2019-04-09
> **This release was made from scratch and provides API incompatible with `0.2.1`.**

### Added
- `Currency` value-type.
- The interface `Currencies` for representation of currency directories.
- Implementation of currencies which can be initialized by any `Iterable<Currency>`
(see the factory `Currencies.from(Iterable<Currency>)`).
- Aggregating `Currencies` implementation (see the factory
`Currencies.aggregating(Iterable<Currencies>)`).
- Adds `Money` value-type:
    - amount predicates: `.isZero`, `.isPositive`, `.isNegative`;
    - currency predicates `.isInCurrency(Currency)`, `.isInSameCurrencyAs(Money)`;
    - comparison operators: `==`, `<`, `<=`, `>`, `>=`;
    - conformance to `Comparable<Money>`;
    - arithmetic operators (`+(Money)`, `-(Money)`, `*(num)`, `/(num)`);
    - allocation according to ratios with `.allocationAccordingTo(List<int>)`;
    - allocation to _N_ targets with `.allocationTo(int)`;
    - `.encodedBy(MoneyDecoder)`;
    - `Money.decoding(MoneyEncoder)`.
- Interface `MoneyEncoder`.
- Interface `MoneyDecoder`.
- `MoneyData` — DTO for encoding/decoding.

## 0.2.1 - 2018-08-21
### Fixed
- Fixes comparison of `0` and `-0` amount in a browser.

## 0.2.0 - 2018-08-17
### Changed
- Code was migrated to Dart 2.0. No API changes.

## 0.1.6 - 2017-02-24
### Fixed
- Fixed wrong parsing from string when integer part of amount is `0`.

## 0.1.5 - 2016-07-06
### Changed
- Class `Currency` is not abstract from now on.

### Fixed
- `Money.hashCode` now relates on `amount` and `currency` (Issue #1).


## 0.1.4 - 2016-06-03
### Changed
- [BC] `Money.==()` now receives `Object` instead of `Money` and checks runtime
  type of the argument, closes [#4](https://github.com/LitGroup/money.dart/issues/4).


## 0.1.3+2 - 2016-05-10
### Fixed
- Fixed invalid rounding of amount in `Money.toString()`, closes
  [#3](https://github.com/LitGroup/money.dart/issues/3).


## 0.1.3 - 2015-05-05
### Added
- Added `Money.fromDouble()` constructor.


## 0.1.2 - 2015-05-05
### Added
- Added getter `Money.amountAsString`.


## 0.1.1 - 2015-05-04
### Added
- Added `Money.fromString()` constructor.
- Added relational operators (`<`, `<=`, `>`, `>=`).


## 0.1.0+1 - 2015-05-01
### Fixed
- Fixes `README.md`.


## [0.1.0] - 2015-05-01
Initial version.
