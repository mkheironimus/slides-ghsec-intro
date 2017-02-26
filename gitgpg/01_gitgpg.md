!SLIDE
# GPG-signed git Commits

!SLIDE
# GPG-signed git Commits
## Why Sign Commits/Tags?

* Create locally with forged name/mail
* Push to remote repo and fake names are there
* Somebody else pulls from remote and also gets them

!SLIDE
# GPG-signed git Commits
## Signing Commits

* `git commit -S -m 'commit message'`
* `git tag -s tagname -m 'tag message'`

!SLIDE
# GPG-signed git Commits
## GitHub Support

* Upload your public signing key in settings
* GitHub will mark commits/tags as verified

