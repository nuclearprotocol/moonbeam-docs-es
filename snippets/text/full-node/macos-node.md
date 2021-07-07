---
title: Nodo completo de Moonriver MacOS
---

# Collator de fragmentos de código/MacOS de nodo completo

## Nodo completo de Moonbase Alpha

```
docker run -p 9933:9933 -p 9944:9944 -v "{{ networks.moonbase.node_directory }}:/data" \
-u $(id -u ${USER}):$(id -g ${USER}) \
purestake/moonbeam:{{ networks.moonbase.parachain_release_tag }} \
--base-path=/data \
--chain {{ networks.moonbase.chain_spec }} \
--name="YOUR-NODE-NAME" \
--execution wasm \
--wasm-execution compiled \
--pruning archive \
--state-cache-size 1 \
-- \
--pruning archive \
--name="YOUR-NODE-NAME (Embedded Relay)"
```

## Moonbase Alpha Collator

```
docker run -p 9933:9933 -p 9944:9944 -v "{{ networks.moonbase.node_directory }}:/data" \
-u $(id -u ${USER}):$(id -g ${USER}) \
purestake/moonbeam:{{ networks.moonbase.parachain_release_tag }} \
--base-path=/data \
--chain {{ networks.moonbase.chain_spec }} \
--name="YOUR-NODE-NAME" \
--validator \
--execution wasm \
--wasm-execution compiled \
--pruning archive \
--state-cache-size 1 \
-- \
--pruning archive \
--name="YOUR-NODE-NAME (Embedded Relay)"
```

## Nodo completo de Moonriver

```
docker run -p 9933:9933 -p 9944:9944 -v "{{ networks.moonriver.node_directory }}:/data" \
-u $(id -u ${USER}):$(id -g ${USER}) \
purestake/moonbeam:{{ networks.moonriver.parachain_release_tag }} \
--base-path=/data \
--chain {{ networks.moonriver.chain_spec }} \
--name="YOUR-NODE-NAME" \
--execution wasm \
--wasm-execution compiled \
--pruning archive \
--state-cache-size 1 \
-- \
--pruning archive \
--name="YOUR-NODE-NAME (Embedded Relay)"
```

## Moonriver Collator

```
docker run -p 9933:9933 -p 9944:9944 -v "{{ networks.moonriver.node_directory }}:/data" \
-u $(id -u ${USER}):$(id -g ${USER}) \
purestake/moonbeam:{{ networks.moonriver.parachain_release_tag }} \
--base-path=/data \
--chain {{ networks.moonriver.chain_spec }} \
--name="YOUR-NODE-NAME" \
--validator \
--execution wasm \
--wasm-execution compiled \
--pruning archive \
--state-cache-size 1 \
-- \
--pruning archive \
--name="YOUR-NODE-NAME (Embedded Relay)"
```