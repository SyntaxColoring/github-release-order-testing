# Conclusions

The GitHub web UI appears to sort releases based on semver order, assuming the tags follow the usual `vX.Y.Z` pattern.

*However,* [the HTTP API for getting the latest release](https://docs.github.com/en/rest/releases/releases#list-releases) follows different rules, and won't necessarily return the same thing.

Try running this:

```
curl -H "Accept: application/vnd.github+json" \
  -H "Authorization: token <your personal access token>" \
  "https://api.github.com/repos/syntaxcoloring/github-release-order-testing/releases/latest"
```

You won't get the release that appears topmost in the list in the web UI.
