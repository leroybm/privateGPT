## Commands

### Select profile

```bash
export PGPT_PROFILES=ng
```

### Ingest files with log

```bash
make ingest files-to-ingest -- --watch
```

## Data transformaiton

### Add path to files in a folder (recursive)

```bash
find . -type f -exec sh -c 'for file; do echo "path: $PWD/$file" | cat - "$file" > temp && mv temp "$file"; done' sh {} +
```

### Remove files from a folder (recursive)

```bash
find . -type f ! -name "*.ts" ! -name "*.tsx" ! -name "*.md" ! -name "*.js" -exec rm -f {} +
```