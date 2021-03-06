# PHPAnalyseDog

## Description
PHP code analyse on pull request and review comment via reviewdog.

## Inputs
name | description | required | default
---|---|---|---
github_token|GITHUB_TOKEN|true|-
level|Report level for reviewdog [info, warning, error]|false|'error'
reporter|Reporter of the rebiewdog command [github-pr-check, github-pr-review]|false|'github-pr-review'
filter_mode|Filtering mode for the reviewdog command [added, diff_context, file, nofilter]|false|'added'
fail_on_error|Exit code for reviewdog when errors are found [true, false]|false|'true'
reviewdog_args|Additional reviewdog options|false|''
phpcs|Enable PHP_CodeSniffer [true, false]|false|true
phpmd|Enable PHPMD [true, false]|false|false
phinder|Enable Phinder [true, false]|false|false
phpcs_args|PHP_CodeSniffer command args|false|'. --standard=/phpcs.xml'
phpmd_args|PHPMD command args|false|'. json cleancode,codesize,controversial,design,naming,unusedcode'
phinder_args|Phinder command args|false|'find -f "json" .'
workdir|The directory from which to look for and run commands|false|'.'
update_dependency|Update dependencies if you have "composer.json" in workdir|false|false
debug|Output debug messages|false|false

## Usage on Github Actions
```
uses: MiddleFieldInc/PHPAnalyseDog@master
with:
  github_token: ${{ secrets.GITHUB_TOKEN }}
```
