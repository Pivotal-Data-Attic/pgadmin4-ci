
## To push to CF

Push a branch from the `pgadmin4` repo, which will trigger a git hook that updates this repository and it's submodules. 

Then login to CF using the following command:

```bash
$ cf login -a https://api.run.pivotal.io
> USERNAME
> PASSWORD
```

Run the script that will push:

```bash
$ ./push_cf.sh
```


### Push to CF didn't work

If the following message is displayed:

`Not deploying because couldn't find the branch name in the git message`

Check the last git message, it should look like this:

`[branch-name-id] Run tests for.....`

If it doesn't, the commit was not generated by the Git Hook in the `pgadmin4` repo and will not be pushed to CF

###Create a Docker Image

```bash
$ docker build -t chrome-python-2.7.10 .

$ docker tag chrome-python-2.7.10 joaopapereira/chrome-python-2.7.10

$ docker push joaopapereira/chrome-python-2.7.10
```

