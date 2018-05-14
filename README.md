# Standarlize Git Commit Message
git usage flow

# Generate the Commit Message
## Install `commitizen`
```shell
# install
yarn global add commitizen

# exec in project root
commitizen init cz-conventional-changelog --save --save-exact
```

# Validate the Commit Message
## Install `husky` to help us use git and npm hooks

> [husky hooks](https://github.com/typicode/husky/blob/master/HOOKS.md)

```shell
yarn add husky --dev
```

## Install `commitlint`

> [commitlint](https://github.com/marionebl/commitlint#getting-started)

### Installation
```shell
# Install commitlint cli and angular config
yarn add --dev @commitlint/{config-conventional,cli}
# For Windows:
yarn add --dev @commitlint/config-conventional @commitlint/cli

# Configure commitlint to use angular config
echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js
```

### Configuration
```json
{
  "scripts": {
    "commitmsg": "commitlint -e $GIT_PARAMS"
  }
}
```

# Generate ChangeLog
## Install `conventional-changelog-cli`
```shell
yarn add --dev conventional-changelog-cli
```

## Configuration
```json
{
  "scripts": {
    "version": "conventional-changelog -p angular -i CHANGELOG.md -s -r 0 && git add CHANGELOG.md"
  }
}
```


# Refs
- [Commit message 和 Change log 编写指南](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)
