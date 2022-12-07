# Magento and Adobe Commerce Dev Containers

A straightforward way to run a Magento demo project locally with vscode and docker. Goal is to make it Github Codespces compatible too!

## Configuration

```json
...
	"containerEnv": {
		"AUTO_MAGENTO_EDITION": "community",
		"AUTO_MAGENTO_VERSION": "2.4.5-p1",
		"AUTO_COMPOSER_REQUIRE": "facebook/facebook-for-magento2",
		"AUTO_MAGENTO_SAMPLEDATA": "true"
	},
...
```

## TODO

* Multiarch support for running in codespaces https://github.blog/changelog/2020-09-17-github-container-registry-support-for-multi-arch-images/
