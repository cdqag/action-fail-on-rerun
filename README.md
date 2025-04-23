# action-fail-on-rerun

Simple GitHub Action to fail a job if it has been retried.
GitHub does not give possibility to hide a Re-run job from the UI. So a workaround is to fail the job if it has been retried.

## Inputs

* `error-title`

    The error title. Default is `Job Re-run Not Allowed`.

* `error-message`

    The error message. Default is `Owner of this workflow disabled possibility to Re-run this job`.

## Example usage

```yaml
name: Release

on:
  workflow_dispatch:

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
    - uses: cdqag/action-fail-on-rerun@v1 # Must be a first step to work as a guard

    # Rest of your job steps

```

## License

This project is licensed under the Apache-2.0 License. See the [LICENSE](LICENSE) file for details.
