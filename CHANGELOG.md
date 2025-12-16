# Changelog
All notable changes to this project will be documented in this file.

## opentele-py313 Fork

### [v1.15.2](https://pypi.org/project/opentele-py313/1.15.2/) - 2025-12-16

**Python 3.13 Compatibility Fork**

- Add Python 3.13 compatibility by ignoring `__firstlineno__` and `__static_attributes__` attributes in `extend_class` decorator.
- Forked from original opentele v1.15.1 by thedemons.
- Package renamed to `opentele-py313` to avoid conflicts with the original library.
- All original functionality preserved.

## Original opentele Releases

## [v1.15](https://pypi.org/project/opentele/1.15/) - 2022-01-27

- Massive performance upgrade, UseCurrentSession is now 200x faster than before.
- `TDesktop` now has `PerformanceMode` which is enabled by default. It will now load and save tdata 200x faster.
- Huge performance boost when converting `TelegramClient` to `TDesktop`.
- Replace `inspect.stack()` with `inspect.currentframe()` in `OpenTeleException`. Using `inspect.stack()` is a stupid move, it's really slow.

## [v1.14](https://pypi.org/project/opentele/1.14/) - 2022-01-26

- `TelegramClient` will now use `TelegramDesktop` api by default.
- Fix a bug when saving tdata.

## [v1.13](https://pypi.org/project/opentele/1.13/) - 2022-01-21

- Fix `unique_id` not generated correctly in `API.Generate()`
- Added DC mismatched handling when authorizing a new client.

## [First Stable Release](https://pypi.org/project/opentele/1.13/) - 2022-01-20

- First stable release of opentele.