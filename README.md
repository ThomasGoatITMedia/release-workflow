## GOAL
Release workflow example with 2 permanent protected branches: a main branch and a protected develop branch.
When a release is merged into main it should create a downstream merge back into develop branch automatically without the need for approval (bypass branch protection), for example with a machine user that is allowed to bypass