# Releasing ZAI CLI

This project uses manual releases with Git tags and release notes derived from CHANGELOG.md.

## Checklist

1. Make sure the working tree is clean.
2. Update `CHANGELOG.md` with the new version and date.
3. Bump the version in `packages/zai-cli/package.json`.
4. Build and test the CLI:

```bash
cd packages/zai-cli
npm install
npm run build
npm test
```

5. Publish to npm:

```bash
cd packages/zai-cli
npm publish --access public
```

6. Create and push a git tag:

```bash
git tag vX.Y.Z
git push origin vX.Y.Z
```

7. Create a GitHub Release and paste the matching CHANGELOG section as release notes.

## Notes

- The npm package name is `zai-cli`.
- Use semantic versioning (major.minor.patch).
