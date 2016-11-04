## How to fix this vsphere error

* Add a new remote
```
git remote add central https://github.com/hashicorp/terraform
```

* create a branch from the targeted tag
```
git checkout -b fix_vsphere v0.7.4
```

* Push your updates
```
git push origin your_branch
```

* Make your modifications

* Start a GO container with a local folder as volume
```
docker run -ti --rm -v yourlocalpath:/go/src golang bash
```

* Fetch the hashicorp project
```
go get github.com/hashicorp/terraform
```
* Report your modifications
```
git remote add notuscloud https://github.com/notuscloud/terraform
git fetch notuscloud fix_vsphere:fix_vsphere
git checkout fix_vsphere
```
* Build
```
make fmt
XC_OS="darwin" XC_ARCH="amd64" make bin
```

* Exit the golang container
