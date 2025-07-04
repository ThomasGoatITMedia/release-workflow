## GOAL
Release workflow example with 2 permanent protected branches: a main branch and a protected develop branch.
When a release is merged into main it should create a downstream merge back into develop branch automatically without the need for approval (bypass branch protection).

### Steps to setup
1. Create a [ssh-keypair](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key). 🚨 Make sure you don't have a passphrase set on the private key.
1. Add the public key as a deploy key for your repository and make sure it has write access
1. Add the private key as a secret in your repository with the name of `DOWNSTREAM_MERGE_SECRET`
1. In your repository settings, go to the Rules > Rulesets and add a bypass in the Bypass list of your develop rule. Add Deploy keys as a bypass
1. Make sure that  "Read and write permissions" are enabled in Settings -> Actions -> General -> Workflow permissions:
1. Create a branch from develop, create a PR and merge it into main after approval
1. The downstream merge action should run and automagically merge it into develop
1. ??? profit ???
