# helm-chart

# Quick Start
> helm repo add myrepo https://bangbangzheng.github.io/helm-chart

> helm install repo myrepo

# 检查配置

> helm lint helm-chart-sources/helloworld

# 打包应用

> helm package helm-chart-sources/helloworld

# 添加描述文件 index.yaml
> helm repo index --url https://bangbangzheng.github.io/helm-chart/helloworld .


# 更新仓库
> helm repo update
