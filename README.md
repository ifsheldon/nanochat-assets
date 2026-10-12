# NanoChat assets

This repository stores the Git LFS payloads used by the [`h100-rlm` branch of ifsheldon/nanochat](https://github.com/ifsheldon/nanochat/tree/h100-rlm).
The code repository configures this LFS endpoint in `.lfsconfig`, so its normal clone and `git lfs pull` download the bundle automatically.
You do not need a separate clone of this repository to run pretraining.

## H100 initialization seed

`assets/h100-seed/` contains the original d24 step-5568 pretrained input embedding and its matching tokenizer.
The embedding is a BF16 tensor of shape `[32768, 1536]`; it is the only weight in `model_005568.pt`.
The complete bundle is 101,211,960 bytes.
The three binary files use Git LFS; `manifest.json` and `meta_005568.json` remain regular Git files.
The manifest records the payload checksums, tensor checksum, and original checkpoint provenance.

See the [H100 setup and training guide](https://github.com/ifsheldon/nanochat/blob/h100-rlm/dev/H100_RLM.md) for the launch command and experiment configuration.

## Maintain the bundle

Install Git LFS before cloning this repository, then run `git lfs pull` to obtain its payloads.
Keep the bundle filenames and manifest synchronized with the code repository.
Changes to the payloads require write access to this repository; its LFS objects are uploaded through the normal Git LFS pre-push hook.
