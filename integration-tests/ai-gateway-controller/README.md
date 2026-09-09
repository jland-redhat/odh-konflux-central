# ai-gateway-controller integration test

Konflux group integration test for [ai-gateway-controller](https://github.com/opendatahub-io/ai-gateway-controller).

## Pipeline

`pr-group-testing-pipeline.yaml` — Tekton `Pipeline` `odh-pr-test-ai-gateway-controller`.

Provisions ephemeral Hypershift cluster (EaaS), exports `AI_GATEWAY_CONTROLLER_IMAGE` from
composite snapshot, runs `./test/e2e/scripts/prow_run_ai_gateway_controller_test.sh` in the
PR source repo.

## Trigger

PAC `PipelineRun` in ai-gateway-controller repo:

`.tekton/ai-gateway-controller-group-test.yaml`

Also mirrored here:

`pipelineruns/ai-gateway-controller/ai-gateway-controller-group-test.yaml`

## Konflux component

`ai-gateway-controller-group` under `group-testing` application — see
`gitops/integration-testing-prerequisites.yaml`.

## Task image

Uses `quay.io/rhoai/rhoai-task-toolset:maas` (same as models-as-a-service group test).
