## Needed repo secrets and variables:

### Youtube cookies: `secrets.YOUTUBE_COOKIES`:

Follow the instructions at [yt-dlp wiki](https://github.com/yt-dlp/yt-dlp/wiki/Extractors#exporting-youtube-cookies) to get the cookies.txt file.

Encode the cookies.txt file in Base64 using this command `base64 -w 0 cookies.txt` and paste it to the `YOUTUBE_COOKIES` secret.

> [!CAUTION]
> Do not use your personal account for cookies. Use a dummy account, and create a brand account inside of it, and use that to sign in. This passing the cookies method may result in your account being 


### GitHub token: `secrets.GH_PAT`

This repo automatically uses a GitHub token in order to authenticate with the GitHub API and avoid rate limiting. You can also specify your own read-only fine-grained personal access token.

Also cookies have expiration, which means it has to be refreshed, or else it will expire and it will not work anymore. To prevent expiration, yt-dlp automatically refreshes the cookies as needed.
To update those cookies in GitHub secrets, requires a fine-grained personal access token that has read and write access to the secrets scope in the current repository to update the secret as the default GITHUB_TOKEN does not have access to the secrets scope.

```yaml
steps:
  - name: Setup yt-dlp
    uses: AnimMouse/setup-yt-dlp@v3
    with:
      token: ${{ secrets.GH_PAT }}
```

### Youtube Test Url (optional) `vars.YT_DLP_TEST_VIDEO`


## Usage
Enables actions in your repor and use the Actions tab..
