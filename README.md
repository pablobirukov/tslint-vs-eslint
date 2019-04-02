# Compares tslint vs eslint performance

Using forked (as there were minor changes required) https://github.com/pablobirukov/coc.nvim (166 TypeScript files).

## Install dependencies

`yarn install`

`postinstall` script fetches `coc.nvim` as a git submodule.

## Comparison

I compared several config options ([see the scripts in package.json](./package.json)).

### lint-recommended

Uses `:recommended` config

    tslint  8.19s user 0.47s system 142% cpu 6.102 total
    eslint  7.29s user 0.40s system 150% cpu 5.112 total

### lint-recommended-with-project

Uses `:recommended` config, passes `--project` flag and also has `no-unnecessary-type-assertion` rule on

    tslint  11.27s user 0.60s system 154% cpu 7.693 total
    eslint  9.99s user 0.63s system 156% cpu 6.775 total

### lint-single-rule

Uses config with the single `semicolon` rule on

    tslint  3.03s user 0.33s system 140% cpu 2.390 total
    eslint  7.43s user 0.52s system 138% cpu 5.735 total

### lint-single-rule-with-project

Uses config with the single `no-unnecessary-type-assertion` rule on, and passes required `--project` flag

    tslint  4.01s user 0.30s system 158% cpu 2.714 total
    eslint  9.60s user 0.69s system 153% cpu 6.696 total
