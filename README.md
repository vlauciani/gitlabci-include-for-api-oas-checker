# OpenApi Spec 'include', for `.gitlab-ci.yml`
OpenApi Spec 'include', for `.gitlab-ci.yml`

## Usage

This snippet can be included in GitLab CI to check DockerHub rate limit.

In your `.gitlab-ci.yml` file, remeber to set 
- `INCLUDE_DOCKERHUB_REGISTRY_USER` 
- `INCLUDE_DOCKERHUB_REGISTRY_PSW`

Using GitLab CI/CD varaibles approach (https://gitlab.rm.ingv.it/help/ci/variables/index).

This `stage` returns:
```
ratelimit-limit: 200;w=21600
ratelimit-remaining: 176;w=21600
```

### Example

```yml
# .gitlab-ci.yml
include:
  - remote: 'https://raw.githubusercontent.com/vlauciani/gitlabci-include-for-api-oas-checker/main/api-oas-checker.yml'

variables:
  INCLUDE_OPENAPI_DIR: "/home/user/myapp/public
  INCLUDE_OPENAPI_FILENAME: "openapi.yml"
    
stages:
  - . . .
  - api-oas-checker_stage
  - . . .
  
api-oas-checker:
    stage: api-oas-checker_stage  
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
