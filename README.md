# feature-store-example
Enables the feature store with a sample project to integrate with RHOAI

## Usage

To spin up the feature store, use
`oc apply -f manifests/`

This will spin up a successful feature store. In order to get it to appear in RHOAI, you MUST run a terminal in the feature store pod and run the command
`feast apply`
