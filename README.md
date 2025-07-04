## GOAL
Release workflow example with 2 permanent protected branches: a main branch and a protected develop branch.
When a release is merged into main it should create a downstream merge back into develop branch automatically without the need for approval (bypass branch protection).

### Steps to setup
1. Create a [ssh-keypair](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key)
2. Add the public key as a deploy key for your repository and make sure it has write access
3. Add the private key as a secret in your repository with the name of `DOWNSTREAM_MERGE_SECRET`
4. In your repository settings, go to the Rules > Rulesets and add a bypass in the Bypass list of your develop rule. Add Deploy keys as a bypass
