# Init cluster

```cd cluster/kind```

```chmod +x cluster/kind/create-cluster.sh```

```./create-cluster.sh```

# Test ansible playbook
You must be at the root path of DebugK8s

```ansible-playbook -i prerequisites/ansible/inventory/local.yml prerequisites/ansible/playbook/01_dependency_installation_debug.yml```

# cloud-provider-kind installation(MacOs) for loadbalancing

```brew install cloud-provider-kind```

```sudo cp /opt/homebrew/Cellar/cloud-provider-kind/0.6.0/bin/cloud-provider-kind /usr/local/bin ```

```source $HOME/.zshrc```

```sudo cloud-provider-kind -enable-lb-port-mapping="true"```

# Load an image on your kind cluster
```kind load docker-image xxx/yyy:tagxx```

# How to connect to the database

jdbc:postgresql://**\<StatefulSet Name\>**.**\<NameSpace\>**.svc.cluster.local:**\<Service exposed port\>**/**\<Database Name\>**

**Ex:** jdbc:postgresql://postgres.test-ns.svc.cluster.local:5432/security