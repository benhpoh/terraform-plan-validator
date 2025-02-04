![passing](https://github.com/bradmccoydev/terraform-plan-validator/actions/workflows/ci.yml/badge.svg) [![Go Report Card](https://goreportcard.com/badge/github.com/bradmccoydev/terraform-plan-validator)](https://goreportcard.com/report/github.com/bradmccoydev/terraform-plan-validator) ![GitHub](https://img.shields.io/github/license/bradmccoydev/terraform-plan-validator) ![GitHub release (latest by date)](https://img.shields.io/github/v/release/bradmccoydev/terraform-plan-validator)

# Terraform Plan Validator
This tool validates Terraform Plans it has been developed in golang as a wrapper around TFSEC and OPA to provide guardrails when deploying in CI/CD pipelines.

### Command Description

| Command | Parameters |
| --- | --- |
| check | Check if the plan passes Policy |
| opascore | Gets the OPA score report |
| tfsec | Outputs TfSec vulnerability report |
| sendreport | Sends Terraform validation Report to slack |

### Commands Parameters

| Command | Parameters |
| --- | --- |
| check | --planFileName "delete-rg-test.json" --cloudProvider "azure" |
| opascore | --planFileName "delete-rg-test.json" --cloudProvider "azure" |
| tfsec | --planFileName "delete-rg-test.json" --cloudProvider "azure" |
| sendreport | --planFileName "delete-rg-test.json" --cloudProvider "azure" |

### Docker
``` 
docker pull bradmccoydev/terraform-plan-validator:latest
```

```
docker run -p 80:80 bradmccoydev/terraform-plan-validator:latest check --planFileName "delete-rg-test.json" --cloudProvider "azure"
```

### Variables

For variables we are using viper. You can set the following environment variables to change the defaults.

| Variable | Value |
| --- | --- |
| OPA_GCP_POLICY | opa-gcp-policy.rego |
| OPA_AZURE_POLICY | opa-azure-policy.rego |
| OPA_AWS_POLICY | opa-aws-policy.rego |
| OPA_REGO_QUERY | data.terraform.analysis.authz |
| TFSEC_MAX_SEVERITY | ["LOW", "MEDIUM", "CRITICAL"] |

### Maintainers:
* Brad McCoy ([@bradmccoydev](https://github.com/bradmccoydev)), Moula
* Ben Poh ([@benhpoh](https://github.com/benhpoh)), Moula
* Aman Tur ([@amantur](https://github.com/amantur)), Moula

## Thanks to all the contributors ❤️
<a href = "https://github.com/bradmccoydev/terraform-plan-validator/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo=bradmccoydev/terraform-plan-validator"/>
</a>

### License

Terraform Plan Validator is released under the Apache 2.0 license. See [LICENSE.txt](https://github.com/bradmccoydev/terraform-plan-validator/blob/main/LICENSE)
