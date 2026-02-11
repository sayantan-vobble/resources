# Get git tags with date
```
git for-each-ref --sort=creatordate \
  --format '%(refname:short) %(creatordate:iso8601)' refs/tags
```
