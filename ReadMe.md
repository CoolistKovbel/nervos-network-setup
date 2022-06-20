# Basically setting up on Nervos Network

This is on a wsl linux ubuntu 20.04 system

1. Setup CKB Node
 - create projects folder
 - curl -LO https://github.com/nervosnetwork/ckb/releases/download/v0.103.0/ckb_v0.103.0_x86_64-unknown-linux-gnu.tar.gz
 - tar xzf ckb_v0.103.0_x86_64-unknown-linux-gnu.tar.gz
 - mv ckb_v0.103.0_x86_64-unknown-linux-gnu ckb_v0.103.0
 - cd ckb_v0.103.0
 - ./ckb run

2. use script to download bootstap
  - cd projects/ckb_v0.103.0
  - bash ../../scripts/install_ckb_node_snapshot_data.sh
  - ./ckb run

3. Setup CKB indexer
- mkdir projects/ckb-indexer-0.4.0
- curl -LO  https://github.com/nervosnetwork/ckb-indexer/releases/download/v0.4.0/ckb-indexer-0.4.0-linux-x86_64.tar.gz
- tar xzf ckb-indexer-0.4.0-linux-x86_64.tar.gz
- RUST_LOG=info ./ckb-indexer -s ./indexer-data

4. use script to download bootstrap
  - cd projects/ckb-indexer-0.4.0
  - bash ../../scripts/install_ckb_indexer_snapshot_data.sh
  - RUST_LOG=info ./ckb-indexer -s ./indexer-data