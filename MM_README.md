First, locally you need to setup the upstream path to the Prebid original repo:

```sh
git remote add upstream git@github.com:prebid/Prebid.js.git
```

and fetch all git tags:

```sh
git fetch upstream --tags
```

For example, we need the version 11.26.0 --> we should create a branch in our repo for this version:

```sh
git checkout -b mm/11.26.0 11.26.0
```

it creates a branch from their tag `11.26.0`

then we can do any changes to this branch and push to our repo

later when a newer Prebid version is released, let's say `11.26.1` and we want to start using it, we do:

```sh
git fetch upstream --tags                //  fetch new tags
git checkout -b mm/11.26.1 mm/11.26.0    //  create a new branch based on our branch (with all our changes)
git merge 11.26.1                        //  merge changes from the newer version 11.26.1 tag
git push -u origin mm/11.26.1            //  push it to our repo
```

This way we will have each version in a separate branch

And if we need to build a particular version, we can easily do this from `mm/11.26.0` branch or any other version
