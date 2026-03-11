# feature-store-example
Enables the feature store with a sample project to integrate with RHOAI

## Usage

To spin up the feature store, use
`oc apply -f manifests/`.
Please note that this will run in whichever namespace is your current one.

This will spin up a successful feature store. In order to get it to appear in RHOAI, you MUST run a terminal in the feature store pod and run the command
`feast apply`.
In fact, any time you make changes to your store code, you will need to reapply.

A common pattern of usage in Feast is to materialize data from the offline store to the online store when ready. This requires using the `feast materialize` family of commands. The most common use I have seen is to run this periodically or on an event basis. Please see the documentation to familiarize yourself with how this works.

## Workbench Integration

The feature store will be selectable from the dropdown when creating a workbench. This mounts the connection into an immutable file.

In my experience the file is not at the default location provided in the UI, rather it is at `/opt/app-root/src/feast-config/<name of feature store>`. If you want a sample notebook on how to use it, see `notebook/feature_store_calls.ipynb`. Critically, don't forget to `pip install feast[postgres] grpcio`!