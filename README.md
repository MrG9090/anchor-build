# anchor-build

Docker image for building Anchor programs.

### Usage

No inputs are required.

```yaml
- uses: wjthieme/anchor-build@v1
```

#### Run a different command

By default, `anchor build` is run. You can specify a different command with the `run` input.

```yaml
- uses: wjthieme/anchor-build@v1
  with:
    run: "cargo build-sbf"
```

#### Use a different version of Anchor

By default, the latest version of Anchor is used. You can specify a different version with the `anchor-version` input.

```yaml
- uses: wjthieme/anchor-build@v1
  with:
    anchor-version: "v0.29.0"
```

#### Supply a Solana private key

By default, you'll get a generated keypair to which 1 SOL is airdropped (devnet only). If you want to use your own keypair, you can supply it with the `solana-key` input.

```yaml
- uses: wjthieme/anchor-build@v1
  with:
    solana-key: ${{ secrets.SOLANA_PRIVATE_KEY }}
```

### Local Testing

Install `docker` and `act` and run:

```sh
act workflow_dispatch
```