# [Helm HUB]
https://artifacthub.io


# [helm repo]
helm repo add stable https://charts.helm.sh/stable
helm repo list
helm repo remove stable
helm repo list

helm repo add stable https://charts.helm.sh/stable

# [helm search] (Used to show Info before helm Install)
helm search repo apache
helm serach repo tomcat

# [helm show]
helm show values stable/spark
helm show chart stable/spark
helm show all stable/spark  ---> Display all Information about Chart

# [helm create]
helm create helloworld

# [helm install]
INSTALL :-
    helm install testchart stable/tomcat
    helm install --wait --timeout 20s <RELEASE NAME> <REPO>/<CHART NAME>
    helm install --wait --timeout 20s testtomcat stable/tomcat
    helm install release2 bitnami/mysql --version 8.8.21

DRYRUN :-
    helm install --dry-run testchart stable/tomcat


# [helm --set] (Specifies Overrides on the command line)
helm install <Release Name> <repo>/<> --set service.type=NodePort
helm install testchart stable/tomcat --set service.type=NodePort


# [helm list]
helm list

# [helm get] (Used after helm is installed and when Named Release Information to be collected)
helm list --->  Lists all named Release
helm get <all|manifest|values> <Release Name>                              e.g helm get all mychart
helm status <Release Name>  ---> Display the status of Named Release.      e.g helm status mychart

# [helm history] (Fetch Release History)
helm history <Release Name>

# [helm delete] (Uninstall the deployed Release)
helm delete <Release Name>

# [helm upgrade] (Upgrade a Release)
helm upgrade <ReleaseName> <ChartName>                                      e.g helm upgrade mychart stable/tomcat

# [helm Rollback] (Rollback a Release to a previous version)
helm rollback <Release Name> <Revision>

# [helm pull] (Download a chart from a repo)
helm pull <ChartName> # download in form of tar file
helm pull --untar <ChartName>                                               e.g helm pull --untar stable/tomcat


INSTALL FROM A LOCAL CHART ARCHIVE
helm install mychart tomcat-0.4.3.tgz

INSTALL FROM AN UNPACK CHART DIRECTORY
helm install mychart

INSTALL FROM A FULL URL
helm install mychart <URL>

