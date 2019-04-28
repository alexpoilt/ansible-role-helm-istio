Role install helm and istio
==============

This role install and configure helm, istio and initialize kiali on cluster kubernetes

Variables
---------

Variables default this role for access on kiali and namespace deploy kiali:
```yml
user_kiali: admin
pass_kiali: admin
namespace_kiali: istio-system
```

Linki default for download helm and kiali:
```yml
_link_helm: https://storage.googleapis.com/kubernetes-helm/helm-v2.13.1-linux-amd64.tar.gz
_link_istio: "https://github.com/istio/istio/releases/download/{{ version_istio }}/istio-{{ version_istio }}-linux.tar.gz"
```

If you want change this is values, set on your playbook or files of variables ansible. Example:

```yml
---
- hosts: server
  vars:
    user_kiali: <some-value>
    pass_kiali: <some-value>
    namespace_kiali: <some-value>
  ...
  roles:
    - ansible-role-helm-istio
```
This role install too kiali, if you don't install kiali, set variable kiali_install with false:
```yml
- hosts: server
  vars:
  ...
    kiali_install: false
  ...
  roles:
    - ansible-role-helm-istio
```