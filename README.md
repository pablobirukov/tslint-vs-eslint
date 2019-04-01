
## Install dependencies

`yarn install`

## All scripts duplicated in package.json

```bash
time node_modules/.bin/tslint "coc.nvim/src/**/*.ts" -c tslint.json
time node_modules/.bin/eslint "coc.nvim/src/**/*.ts" -c eslint.json

time node_modules/.bin/tslint "coc.nvim/src/**/*.ts" -c tslint-single-rule.json
time node_modules/.bin/eslint "coc.nvim/src/**/*.ts" -c eslint-single-rule.json

time node_modules/.bin/tslint "coc.nvim/src/**/*.ts" -c tslint-single-rule-with-project.json 
time node_modules/.bin/eslint "coc.nvim/src/**/*.ts" -c eslint-single-rule-with-project.json

time node_modules/.bin/tslint "coc.nvim/src/**/*.ts" -c tslint.json
time node_modules/.bin/eslint "coc.nvim/src/**/*.ts" -c eslint.json

```

## Results MBP 17, base

### *slint:recommended

tslint  8.19s user 0.47s system 142% cpu 6.102 total
eslint  7.29s user 0.40s system 150% cpu 5.112 total

### just `no-unnecessary-type-assertion`

tslint  3.03s user 0.33s system 140% cpu 2.390 total
eslint  7.43s user 0.52s system 138% cpu 5.735 total

### *slint:recommended, --project, `no-unnecessary-type-assertion`

tslint  11.27s user 0.60s system 154% cpu 7.693 total
eslint  9.99s user 0.63s system 156% cpu 6.775 total

### --project, just `no-unnecessary-type-assertion`

tslint  4.01s user 0.30s system 158% cpu 2.714 total
eslint  9.60s user 0.69s system 153% cpu 6.696 total