# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [v4.0.1] - 2022-04-11
- Add the become user root directive for required tasks

## [v4.0.0] - 2022-04-07
- Added 19c October 2021 RU and created unified patching tasks

## [v3.3.0] - 2021-12-17
- Add 19c July 2021 RU

## [v3.2.0] - 2021-02-12
- Remove hard coded S3 bucket.  This allows Ansible to setup instances in the disaster recovery environment.

## [v3.1.1] - 2021-01-27
- Fix debug error if `oneoff_patches` is not defined

## [v3.1.0] - 2020-08-25
- Add 19c July 2020 RU (SI ASM)
- Add this changelog

## [v3.0.0] - 2020-05-19
- Added support for one-off patches

## [v2.0.0] - 2019-10-21
- 19c RU Patching Support
- Re-write of how patch variables are defined.

[Unreleased]: https://github.com/CruGlobal/ansible-oracle-psu/compare/v4.0.1...master

[v4.0.1]: https://github.com/CruGlobal/ansible-oracle-psu/compare/v4.4.0...v4.0.1
[v4.0.0]: https://github.com/CruGlobal/ansible-oracle-psu/compare/v3.3.0...v4.0.0
[v3.3.0]: https://github.com/CruGlobal/ansible-oracle-psu/compare/v3.2.0...v3.3.0
[v3.2.0]: https://github.com/CruGlobal/ansible-oracle-psu/compare/v3.1.1...v3.2.0
[v3.1.1]: https://github.com/CruGlobal/ansible-oracle-psu/compare/v3.1.0...v3.1.1
[v3.1.0]: https://github.com/CruGlobal/ansible-oracle-psu/compare/v3.0.0...v3.1.0
[v3.0.0]: https://github.com/CruGlobal/ansible-oracle-psu/compare/v2.0.0...v3.0.0
[v2.0.0]: https://github.com/CruGlobal/ansible-oracle-psu/releases/tag/v2.0.0
