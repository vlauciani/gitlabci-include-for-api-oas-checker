[![License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://github.com/vlauciani/gitlabci-include-for-api-oas-checker/blob/main/LICENSE)

# OpenApi Spec 'include', for `.gitlab-ci.yml`
*Open-Api-Specification* `include:` directive, for `.gitlab-ci.yml`

## Usage

This snippet can be included in GitLab CI to check *Open-Api-Specification*.

In your `.gitlab-ci.yml` file, remeber to set varaibles:
- `OAS_BASEDIR` 
- `OAS_FILENAME`

### Example

```yml
# .gitlab-ci.yml
include:
  - remote: 'https://raw.githubusercontent.com/vlauciani/gitlabci-include-for-api-oas-checker/main/api-oas-checker.yml'

variables:
  OAS_DIR: "/home/user/myapp/public"
  OAS_FILENAME: "openapi.yml"
    
stages:
  - . . .
  - api-oas-checker_stage
  - . . .
  
api-oas-checker:
    stage: api-oas-checker_stage
    variables:
      INCLUDE_OAS_BASEDIR: ${OAS_DIR}
      INCLUDE_OAS_FILENAME: ${OAS_FILENAME}
```

## Contribute
Thanks to your contributions!

Here is a list of users who already contributed to this repository:
<a href="https://github.com/vlauciani/gitlabci-include-for-api-oas-checker/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=vlauciani/gitlabci-include-for-api-oas-checker" />
</a>

## References
- https://github.com/italia/api-oas-checker
- https://medium.com/@imalik8088/tired-of-repeated-gitlab-ci-files-includes-to-the-rescue-17225532812a
- https://gitlab.com/imalik8088/gitlab-ci-include-test/-/blob/master/.gitlab-ci.yml

## Author
(c) 2021 Valentino Lauciani vlauciani[at]gmail.com
