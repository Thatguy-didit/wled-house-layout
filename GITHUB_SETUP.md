# GitHub Setup For Public Source Compliance

The current Git remote may still point to the upstream WLED repository. Do not
push this modified build to the official WLED repository.

## Recommended Setup

1. Create a new public GitHub repository under your business account.

Suggested name:

`wled-house-layout`

2. Update the Git remote in this local folder.

```powershell
git remote rename origin upstream
git remote add origin https://github.com/Thatguy-didit/wled-house-layout.git
```

3. Commit the modified source.

```powershell
git add .
git commit -m "Add House Layout custom WLED build"
```

4. Push to your public repository.

```powershell
git push -u origin main
```

If your local branch is named something else, replace `main` with the branch
shown by:

```powershell
git branch --show-current
```

5. Tag the exact source used for a customer firmware release.

```powershell
git tag wled-16.0.0-house-layout-v1
git push origin wled-16.0.0-house-layout-v1
```

6. Build the firmware from that tagged source and attach the `.bin` to the
matching GitHub release.

## Customer-Facing Source URL

After the repo is public, replace the placeholders in these files:

- `CUSTOM_BUILD.md`
- `CUSTOMER_SOURCE_NOTICE.md`
- `RELEASE_TEMPLATE.md`

Use the public repo URL or the exact release/tag URL.
