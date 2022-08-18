To package a local Helm chart, run the following command in the chart's folder:
```
helm package .
```

To publish this chart to GitLab Helm package registry:
```
curl --request POST \
     --form 'chart=@<package_chart_name>.tgz' \
     --user <username>:<access_token> \
     <CI_API_V4_URL>/projects/<project_id>/packages/helm/api/<channel>/charts
```

* `<username>`: the GitLab username or the deploy token username.
* `<access_token>`: the personal access token or the deploy token.
* `<project_id>`: the project ID (like 42) or the URL-encoded path of the project (like group%2Fproject).
* `<channel>`: the name of the channel (like stable).

To install a remotely located Helm chart, first, you need to add this Gitlab Helm package registry:
```
helm repo add --username <username> --password <access_token> <your_proposed_repo_name> <CI_API_V4_URL>/projects/<project_id>/packages/helm/<channel>
```

Then install the cart as usual:
```
helm install <release_name> <your_proposed_repo_name>/<chart_name>
``` 