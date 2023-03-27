**Generate Keys**

```bash
docker run --rm -v "${PWD}":/work cgr.dev/chainguard/melange keygen
```

**Build Packages**
docker run --privileged --rm -v "${PWD}":/work \
  cgr.dev/chainguard/melange build melange.yaml \
  --arch aarch64 \
  --signing-key melange.rsa

**Packages output**

Same directory ./packages 
