# BUILD

Here were the steps I neeed to build locally on my M2 Max:

## One-time setup

It's assumed you've already installed Slipstream once.

```shell
xcodebuild -downloadComponent MetalToolchain
```

## Per build

```shell
make -j 12

sudo sysctl iogpu.wired_limit_mb=60416

./slipstream serve --model nitinpanj/Swift-Qwen3.8-Flash-Next-Q4_0-Q8out-v3-GGUF --max-memory 59G --max-context 131072 --no-webui --host 0.0.0.0 --port 8088
```
