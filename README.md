# owf-helm-charts

This repo can contain multiple charts. Charts should be placed under `/charts` directory at the top-level of directory tree. 

## Chart Releaser Action

GitHub Action workflow automates releasing charts through GitHub pages. 

The sources of all the charts can be placed under the `main` branch. The charts should be placed under `/charts` directory at the top-level of the directory tree. There should be another branch named `gh-pages` to publish the charts. The changes to that branch will be automatically created by the Chart Releaser Action.

 It does this - during every push to main - by checking each chart in your project, and whenever there's a new chart version, creates a corresponding GitHub release named for the chart version, adds Helm chart artifacts to the release, and creates or updates an `index.yaml` file with metadata about those releases, which is then hosted on GitHub pages.

## Chart Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

  helm repo add <alias> https://<orgname>.github.io/helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
<alias>` to see the charts.

To install the `<chart-name>` chart:
    
    helm install my-<chart-name> <alias>/<chart-name>

To uninstall the chart:
    
    helm delete my-<chart-name>
    
## Reference

[GitHub repo into a Helm Chart repo](https://blog.knoldus.com/how-to-turn-your-git-hub-repo-into-a-helm-charts-repo/)