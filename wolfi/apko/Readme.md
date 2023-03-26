**Local packages** 

Link or copy to . package directory from Melange output

**Local keyring** 

Link or copy to . public certificate from Melange (used to sign local packages)

**Build container TAR** 

```bash
docker run --rm -v ${PWD}:/work -w /work cgr.dev/chainguard/apko build wolfi-base.yaml wolfi-base:test wolfi-test.tar
```

**Load container into docker**

```bash
docker load <  wolfi-test.tar
```

**Run container**

```bash
docker run -it wolfi-base:test-amd64
``` 
