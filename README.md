# twitter-purge

> Unfollows a list of accounts you're following that haven't tweeted in over 30 days.

## Getting started

Make sure to have [ruby](https://www.ruby-lang.org/en/) installed (you can use [rvm](https://rvm.io/)), and then install dependencies with [bundler](https://bundler.io/):

```bash
bundle install
```

Set the required environment variables in `.env` containing your twitter API credentials:

- `TWITTER_CONSUMER_KEY`
- `TWITTER_CONSUMER_SECRET`
- `TWITTER_ACCESS_TOKEN_KEY`
- `TWITTER_ACCESS_TOKEN_SECRET`

You can use the sample env file for reference:

```bash
mv .env.sample .env
```

You can get Twitter API credentials from the Twitter [apps page](https://developer.twitter.com/en/apps).

Run the script passing your username:

```bash
$ ruby purge.rb @username

Twitter account: @username
following count: 4154
checking user: 45409867
checking user: 133008925
checking user: 26318018
...
```

The script will check if the user has tweeted in the last 30 days. If they haven't tweeted in that timeframe, then it will unfollow them. The script creates a `.cache` file containing checked users so if the script is halted you can resume skipping already checked users. The script is simple and easy to modify to your own criteria.

## License

[MIT](LICENSE)
