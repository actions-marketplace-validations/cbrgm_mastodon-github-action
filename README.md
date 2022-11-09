# Mastodon Send GitHub Action

Use this action to send a toot (message) from a GitHub actions workflow to Mastodon.

## Workflow Usage

First, open `/settings/applications/new` of your instance on your browser and create new application. Once the application is created set the following repository secrets

* `MASTODON_URL` - Your instance URL, e.g. `https://example.social`
* `MASTODON_ACCESS_TOKEN` - Your access token obtained from your newly created application

Use the following step in your GitHub Actions Workflow:

```yaml

- name: Send toot to Mastodon
  id: mastodon
  uses: cbrgm/mastodon-github-action@v1
  with:
    message: "Hello from GitHub Actions!"
    visibility: "public" # default: public
  env:
    MASTODON_URL: ${{ secrets.MASTODON_URL }} # https://example.social
    MASTODON_ACCESS_TOKEN: ${{ secrets.MASTODON_ACCESS_TOKEN }} # access token

```

## Contributing & License

Feel free to submit changes! See the [Contributing Guide](https://github.com/cbrgm/contributing/blob/master/CONTRIBUTING.md). This project is open-source
and is developed under the terms of the [Apache 2.0 License](https://github.com/cbrgm/mastodon-github-action/blob/master/LICENSE).
