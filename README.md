# Terraform Github Actions

This repository contains GitHub actions to assist in working with Terraform automation.

## apply

Plans and applies the module at `path` in `workspace`, skipping the apply when the plan has no
changes. Tools are installed with asdf from the nearest `.tool-versions` files, searching from
`path` up to the repository root.

A `path` with a `terragrunt.hcl` is a Terragrunt unit, and is run with `terragrunt` in place of
`terraform`. List `terragrunt` in `.tool-versions` alongside `terraform`:

```plain
terraform 1.15.8
terragrunt 1.1.2
```

```yaml
- uses: tfext/actions/apply@<ref>
  with:
    path: core/organization
    workspace: default
```
