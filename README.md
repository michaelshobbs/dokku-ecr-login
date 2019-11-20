# dokku-ecr-login

dokku-ecr-login is a plugin for [dokku][dokku] that makes sure the instance's AWS ECR login is current

## Requirements

This plugin uses the `pre-deploy` hook to grab `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` in order to execute `$(aws ecr get-login)`. Also requires `aws` CLI version >= 1.11.0.

## Installation & Example

```sh
# Install awscli
sudo pip install awscli

# Install the plugin:
# dokku 0.4+
dokku plugin:install https://github.com/michaelshobbs/dokku-ecr-login.git

dokku config:set <app> AWS_DEFAULT_REGION=some-value
dokku config:set <app> AWS_ACCESS_KEY_ID=some-value
dokku config:set <app> AWS_SECRET_ACCESS_KEY=some-value

git push dokku@dokku.me:<app> master
```

## License

This plugin is released under the MIT license. See the file [LICENSE](LICENSE).

[dokku]: https://github.com/dokku/dokku
[herokuish]: https://github.com/gliderlabs/herokuish
