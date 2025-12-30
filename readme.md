# zinit-direnv

**Note: zinit and zplugin are different names of the same thing**

An empty repository to aid zplugin's hooks-hacks. You can fork it to have a private copy of it :)

Example uses:

When what's needed is an atclone'' hook to e.g. install a software (plus atpull'' hook to update it):

```
# The invocation uses https://github.com/zdharma-continuum/null repo as a placeholder
# for the atclone'' and atpull'' hooks
# run-atpull：Even if this repository has not been updated, atpull will still be executed during `zinit update weineel/zinit-direnv`.
# atpull"%atclone" :If the same command is used for installation and updating.

zinit as"program" pick"direnv" \
  atclone"curl -sfL https://direnv.net/install.sh | bash" \
  atpull"curl -sfL https://direnv.net/install.sh | bash" \
  run-atpull \
  for weineel/zinit-direnv
eval "$(direnv hook zsh)"
```
