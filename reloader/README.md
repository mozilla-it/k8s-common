Reloader watches for changes in ConfigMaps and can perform rolling upgrades on a Deployment or DaemonSet.
In order to get your application rolled when the configmap changes, you need to add the next annotation to your Deployment: `reloader.stakater.com/auto: "true"`

Read more about Reloader in the [official repository.](https://github.com/stakater/Reloader).
