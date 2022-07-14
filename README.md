# GitHub Action: `babbel/generate-github-access-tokens`

Generates a GitHub access token using a custom API endpoint (with SigV4 authentication) and assigns the GitHub access token to an environment variable.

## Usage

```
    steps:
      - uses: aws-actions/configure-aws-credentials@v1
        with:
          role-to-assume: ${{ secrets.AWS_IAM_ROLE_ARN }}
          aws-region: ${{ secrets.AWS_REGION }}
      - uses: babbel/generate-github-access-tokens@v1
        with:
          invoke-url: ${{ secrets.ACCESS_TOKEN_GENERATOR_INVOKE_URL }}
          region: ${{ secrets.ACCESS_TOKEN_GENERATOR_REGION }}
          configuration-name: EXAMPLE_TOKEN
```

This will assign GitHub access token to the `EXAMPLE_TOKEN` environment variable.
