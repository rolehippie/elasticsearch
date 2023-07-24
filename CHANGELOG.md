# Changelog

## [1.2.0](https://github.com/rolehippie/elasticsearch/compare/v1.1.0...v1.2.0) (2023-07-24)


### Features

* **deps:** update dependency prometheus-community/elasticsearch_exporter to v1.6.0 ([1119973](https://github.com/rolehippie/elasticsearch/commit/11199737ff4e5d197fe20de0bae59648c9da7205))

## [1.1.0](https://github.com/rolehippie/elasticsearch/compare/v1.0.0...v1.1.0) (2023-04-17)


### Features

* use unified path for repo key and drop legacy key ([c749aed](https://github.com/rolehippie/elasticsearch/commit/c749aed8e76fa58f4dff050d11688086d6ccfefd))

## 1.0.0 (2023-01-05)


### Features

* better handling for repo version ([d2d441a](https://github.com/rolehippie/elasticsearch/commit/d2d441a2419ae1a897caa1b482a29538eb01b99d))
* integrate defaults to install plugins ([a34dbd9](https://github.com/rolehippie/elasticsearch/commit/a34dbd9f0235a4e59da5f7df94d217d30ebea832))
* restructure workflows and enable automated releases ([707a6f4](https://github.com/rolehippie/elasticsearch/commit/707a6f44e2602e481ea889f1214728b171d7e82e))
* simplify apt repo definition and java home ([c3b635e](https://github.com/rolehippie/elasticsearch/commit/c3b635e485647a8838a1329638772ddaba974e5c))


### Bugfixes

* make it possible to install 5.1 on ubuntu 16.04 ([a2ebf36](https://github.com/rolehippie/elasticsearch/commit/a2ebf36b791ea4723f696c3fc773c266182dc62c))
* make sure man dir exists and java certs get installed ([494a185](https://github.com/rolehippie/elasticsearch/commit/494a185dc3f8c026e0f95c6160167430a0666057))
* no recursive owner change for data and logs ([b239fba](https://github.com/rolehippie/elasticsearch/commit/b239fba3aa41db43409125c3c3bcbdba4b3d4430))
* resolve issue about undefine ES_PATH_CONF variable ([f5f4b7e](https://github.com/rolehippie/elasticsearch/commit/f5f4b7e8ba2a8cfe6e6a9f7efbf619b36c3ed2fb))
* stdout and stderr for exporter version check ([26bd1f6](https://github.com/rolehippie/elasticsearch/commit/26bd1f6d25561b81801ec7e91a637ac6b1d97d08))
* use include_tasks instead of include ([f3f094a](https://github.com/rolehippie/elasticsearch/commit/f3f094ae0d74f71dd80b686c05445cd212763108))
