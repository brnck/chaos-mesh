# Chaos Mesh Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

For more information and how-to, see [RFC: Keep A Changelog](https://github.com/chaos-mesh/rfcs/blob/main/text/2022-01-17-keep-a-changelog.md).

## [Unreleased]

### Added

- Add more status for record [#3170](https://github.com/chaos-mesh/chaos-mesh/pull/3170)
- Add `chaosDaemon.updateStrategy` to Helm chart to allow configuring `DaemonSetUpdateStrategy` for chaos-daemon [#3108](https://github.com/chaos-mesh/chaos-mesh/pull/3108)
- Add AArch64 support for TimeChaos [#3088](https://github.com/chaos-mesh/chaos-mesh/pull/3088)
- Add integration test and link test on arm [#3177](https://github.com/chaos-mesh/chaos-mesh/pull/3177)
- Add `spec.privateKey.rotationPolicy` to Certificates, to comply with requirements in cert-manager 1.8 [#3325](https://github.com/chaos-mesh/chaos-mesh/pull/3325)
- Add `RemoteCluster` resource type [#3342](https://github.com/chaos-mesh/chaos-mesh/pull/3342)
- Add `clusterregistry` package to help developers to develop multi-cluster reconciler [#3342](https://github.com/chaos-mesh/chaos-mesh/pull/3342)
- Support `Suspend` in next generation `New Workflow`'s UI [#3254](https://github.com/chaos-mesh/chaos-mesh/pull/3254)
- Add helm annotations for Artifact Hub [#3355](https://github.com/chaos-mesh/chaos-mesh/pull/3355)
- Add implementation of blockchaos in chaos-daemon [#2907](https://github.com/chaos-mesh/chaos-mesh/pull/2907)
- Bump chaos-tproxy to v0.5.1 [#3412](https://github.com/chaos-mesh/chaos-mesh/pull/3412)
- Allow importing external workflows and copying flow nodes in next generation `New Workflow` [#3368](https://github.com/chaos-mesh/chaos-mesh/pull/3368)
- Add `QPS` and `Burst` for Chaos Dashboard Configuration [#3476](https://github.com/chaos-mesh/chaos-mesh/pull/3476)
- Add guide and example for monitoring Chaos Mesh [#3030](https://github.com/chaos-mesh/chaos-mesh/pull/3030)
- Support `KernelChaos` in `AutoForm` [#3449](https://github.com/chaos-mesh/chaos-mesh/pull/3449)

### Changed

- Helm charts: update validate-auth to chaos-mesh-validation-auth [#3193](https://github.com/chaos-mesh/chaos-mesh/pull/3193)
- Helm charts: support latest api version of dashboard ingress [#3066](https://github.com/chaos-mesh/chaos-mesh/pull/3066)
- Update shell script to support shellchecks [#3230](https://github.com/chaos-mesh/chaos-mesh/pull/3230)
- CI: build dev-env and build-env for e2e tests if required [#3264](https://github.com/chaos-mesh/chaos-mesh/pull/3264)
- CI: version unrelated manifests [#3293](https://github.com/chaos-mesh/chaos-mesh/pull/3293)
- Bump chaos-tproxy to v0.4.6 [#3272](https://github.com/chaos-mesh/chaos-mesh/pull/3272)
- Helm charts: using 0.0.0 as version and appVersion [#3311](https://github.com/chaos-mesh/chaos-mesh/pull/3311)
- Add a comment to the flag size of memory stress in the dashboard [#3359](https://github.com/chaos-mesh/chaos-mesh/pull/3359)
- Refine logging in pkg/dashboard/store, removed global the log [#3143](https://github.com/chaos-mesh/chaos-mesh/pull/3143)
- Renamed namespace from chaos-testing to chaos-mesh [#3353](https://github.com/chaos-mesh/chaos-mesh/pull/3353)
- Use ContainerSelector in kernel chaos [#3395](https://github.com/chaos-mesh/chaos-mesh/pull/3395)
- Make possible to have more than one dns chaos server [#3381](https://github.com/chaos-mesh/chaos-mesh/pull/3381)
- Helm charts: Relax allowedHostPaths in chaos-daemon PSP [#3350](https://github.com/chaos-mesh/chaos-mesh/pull/3350)
- Run build image ci on self-hosted machine [#3429](https://github.com/chaos-mesh/chaos-mesh/pull/3429)
- Simplified logic and add test case about finalizers. [#3422](https://github.com/chaos-mesh/chaos-mesh/pull/3422)
- Update API requests with OpenAPI generated client [#2926](https://github.com/chaos-mesh/chaos-mesh/pull/2926)
- Implement some missing methods in ctrl server [#3462](https://github.com/chaos-mesh/chaos-mesh/pull/3462)

### Deprecated

- Nothing

### Removed

- Removed extra import of common pkg in chaosctl/cmd/logs.go
- Removed unused local function from statuscheck/manager.go [#3228](https://github.com/chaos-mesh/chaos-mesh/pull/3228)
- Removed ui build and test for arm64 [#3305](https://github.com/chaos-mesh/chaos-mesh/pull/3305)
- Remove sed need (SC2001) [#3248](https://github.com/chaos-mesh/chaos-mesh/pull/3248)
- Removed not used clientset in cmd/chaos-controller-manager/main.go [#3334](https://github.com/chaos-mesh/chaos-mesh/pull/3334)
- Removed not used globalCacheReader in cmd/chaos-controller-manager/provider/controller.go [#3343](https://github.com/chaos-mesh/chaos-mesh/pull/3343)
- Removed unsupported action comments of blockchaos [#3435](https://github.com/chaos-mesh/chaos-mesh/pull/3435)

### Fixed

- Update description of memory stressors [#3225](https://github.com/chaos-mesh/chaos-mesh/pull/3225)
- Isolate `target` field and `Scope` when creating `NetworkChaos` in UI [#3223](https://github.com/chaos-mesh/chaos-mesh/issues/3221)
- Add arm64 architecture to ci_skip to pass required test [#3305](https://github.com/chaos-mesh/chaos-mesh/pull/3305)
- Adapt install.sh for kubectl/kubernetes cluster greater than 1.24 [#3177](https://github.com/chaos-mesh/chaos-mesh/pull/3177)
- SC2166: Use || or && rather than -o or -a [#3235](https://github.com/chaos-mesh/chaos-mesh/pull/3235)
- SC2206: Use quote to prevent word splitting/globbing [#3234](https://github.com/chaos-mesh/chaos-mesh/pull/3234)
- Fix make check does not respect the env-images.yaml [#3210] (https://github.com/chaos-mesh/chaos-mesh/pull/3210)
- SC2004: Remove unnecessary $ on arithmetic variables [#3247](https://github.com/chaos-mesh/chaos-mesh/pull/3247)
- PhysicalMachineChaos: update stress options type [#3347](https://github.com/chaos-mesh/chaos-mesh/pull/3347)
- StressChaos: run `pause` before `choom` [#3405](https://github.com/chaos-mesh/chaos-mesh/pull/3405)
- JVMChaos: update the error message that can be ignored [#3415](https://github.com/chaos-mesh/chaos-mesh/pull/3415)
- Fix Workflow Validating Webhook Panic [#3413](https://github.com/chaos-mesh/chaos-mesh/pull/3413)
- Overwrite $IMAGE_BUILD_ENV_TAG with $IMAGE_TAG-$ARCH in `upload_env_image.yml` github action [#3444](https://github.com/chaos-mesh/chaos-mesh/pull/3444)
- Add a judgement of `enterNS` in `getAllInterfaces()` [#3459](https://github.com/chaos-mesh/chaos-mesh/pull/3459)
- Respect flag `enableProfiling` and do not register profiler endpoints when it's false [#3474](https://github.com/chaos-mesh/chaos-mesh/pull/3474)
- Fix JVMChaos loading missing jar file for injection [#3491](https://github.com/chaos-mesh/chaos-mesh/pull/3491)
- Fix the blank screen after creating chaos experiment with "By YAML" [#3489](https://github.com/chaos-mesh/chaos-mesh/pull/3489)

### Security

- Nothing

## [2.2.0] - 2022-04-29

### Added

- Add metrics for archived objects in chaos-dashboard [#2568](https://github.com/chaos-mesh/chaos-mesh/pull/2568)
- Add metrics for iptables, ipset and tc metrics in chaos-daemon [#2540](https://github.com/chaos-mesh/chaos-mesh/pull/2540)
- Add metrics for emitted event counter in chaos-controller-manager [#2435](https://github.com/chaos-mesh/chaos-mesh/pull/2435)
- Add metrics for grpc client [#2458](https://github.com/chaos-mesh/chaos-mesh/pull/2458)
- Add metrics for grpc and HTTP request duration histogram [#2543](https://github.com/chaos-mesh/chaos-mesh/pull/2543)
- Add metrics for bpm controlled processes [#2497](https://github.com/chaos-mesh/chaos-mesh/pull/2497)
- Provide additional printer columns for `action` and `duration` [#2526](https://github.com/chaos-mesh/chaos-mesh/pull/2526)
- Add PhysicalMachine CRD [#2587](https://github.com/chaos-mesh/chaos-mesh/pull/2587)
- New command `physical-machine` to `chaosctl` [#2624](https://github.com/chaos-mesh/chaos-mesh/pull/2624)
- Add status "Deleting" for chaos experiments on Chaos Dashboard [#2708](https://github.com/chaos-mesh/chaos-mesh/pull/2708)
- Add time skew for gettimeofday [#2742](https://github.com/chaos-mesh/chaos-mesh/pull/2742)
- Add support of the Unified cgroup mode (tested with containerd runtime only) for linux stress experiments [#2928](https://github.com/chaos-mesh/chaos-mesh/pull/2928)
- Add `StatusCheck` CRD [#2954](https://github.com/chaos-mesh/chaos-mesh/pull/2954)
- Add support for declaring ports in external targets in NetworkChaos experiments [#2932](https://github.com/chaos-mesh/chaos-mesh/pull/2932)
- Add forced recovery of httpchaos, iochaos, stresschaos, and networkchaos for chaosctl [#2992](https://github.com/chaos-mesh/chaos-mesh/pull/2992)
- Add namespace and pod name in failed event for podxxxchaos crd [#3178](https://github.com/chaos-mesh/chaos-mesh/pull/3178)
- Add next generation `New Workflow` in UI [#3185](https://github.com/chaos-mesh/chaos-mesh/pull/3185)
- JVMChaos: support inject fault into MySQL client [#3189](https://github.com/chaos-mesh/chaos-mesh/pull/3189)

### Changed

- Use pipeline controller to serialize common controllers [#2465](https://github.com/chaos-mesh/chaos-mesh/pull/2465)
- Enable mTLS between chaos-controller-manager and chaosd [#2580](https://github.com/chaos-mesh/chaos-mesh/pull/2580)
- Rename Physics to Host in Chaos Dashboard [#2645](https://github.com/chaos-mesh/chaos-mesh/pull/2645)
- Retry oneshot chaos if it's not selected [#2618](https://github.com/chaos-mesh/chaos-mesh/pull/2618)
- Bump gopsutil to v3 [#2681](https://github.com/chaos-mesh/chaos-mesh/pull/2681)
- Add prefix for identifier of toda and tproxy in bpm [#2673](https://github.com/chaos-mesh/chaos-mesh/pull/2673)
- Bump toda to v0.2.2 [#2747](https://github.com/chaos-mesh/chaos-mesh/pull/2747)
- Bump go to 1.17 [#2754](https://github.com/chaos-mesh/chaos-mesh/pull/2754)
- Use github.com/pkg/errors to replace fmt.Errorf and "errors" [#2779](https://github.com/chaos-mesh/chaos-mesh/pull/2779)
- Kill chaos-tproxy while failing to apply config [#2672](https://github.com/chaos-mesh/chaos-mesh/pull/2672)
- JVMChaos: ignore AgentLoadException when install agent [#2701](https://github.com/chaos-mesh/chaos-mesh/pull/2701)
- Bump container-runtime to v0.11.0 [#2778](https://github.com/chaos-mesh/chaos-mesh/pull/2778)
- Bump kubernetes dependencies to v1.23.1 [#2778](https://github.com/chaos-mesh/chaos-mesh/pull/2778)
- Removed docker registry mirror [#2797](https://github.com/chaos-mesh/chaos-mesh/pull/2797)
- Use OpenAPI definitions to generate API Client and Form data in UI [2770](https://github.com/chaos-mesh/chaos-mesh/pull/2770)
- Refine logging in pkg/selector/pod [#3002](https://github.com/chaos-mesh/chaos-mesh/pull/3002)
- Add `envFollowKubernetesPattern` to handle k8s-like format env in helm templates [2955](https://github.com/chaos-mesh/chaos-mesh/pull/2955)
- Bump chaos-tproxy to v0.4.5 [#2555](https://github.com/chaos-mesh/chaos-mesh/pull/2555)
- Re-implement chaosctl based on ctrlserver [#2950](https://github.com/chaos-mesh/chaos-mesh/pull/2950)
- Fix wrong zero value of httpchaos replace-body-action[#2990](https://github.com/chaos-mesh/chaos-mesh/pull/2990)
- Bump gqlgen to v0.17.2 [#3038](https://github.com/chaos-mesh/chaos-mesh/pull/3038)
- Bump go to v1.18 [#3055](https://github.com/chaos-mesh/chaos-mesh/pull/3055)
- Bump toda to v0.2.3 [#3131](https://github.com/chaos-mesh/chaos-mesh/pull/3131)
- refactor: rename reconcileContext to reconcileInfo [#3154](https://github.com/chaos-mesh/chaos-mesh/pull/3154)
- Migrate e2e tests from self-hosted Jenkins to Github Action [#2986](https://github.com/chaos-mesh/chaos-mesh/pull/2986)
- Bump minimist from 1.2.5 to 1.2.6 in /ui [#3058](https://github.com/chaos-mesh/chaos-mesh/pull/3058)
- Specify image tag of `build-env` and `dev-env` for each branch [#3071](https://github.com/chaos-mesh/chaos-mesh/pull/3071)
- Specify image tag in e2e tests [#3147](https://github.com/chaos-mesh/chaos-mesh/pull/3147)
- Must update CHANGELOG [#3148](https://github.com/chaos-mesh/chaos-mesh/pull/3148)
- Use chaosDaemon.mtls.enabled instead of dashboard.securityMode for chaos-daemon mtls [#3168](https://github.com/chaos-mesh/chaos-mesh/pull/3168)
- Helm charts: component chaos-dashboard use certain service account and roles [#3145](https://github.com/chaos-mesh/chaos-mesh/pull/3145)
- Refactor helm charts template, split out webhook configuration and secrets [#3159](https://github.com/chaos-mesh/chaos-mesh/pull/3159)
- Helm charts: apply webhook.FailurePolicy to all the webhooks with default value `Fail` [#3184](https://github.com/chaos-mesh/chaos-mesh/pull/3184)
- Bump memStress from v0.2.1 to v0.3 [#3186](https://github.com/chaos-mesh/chaos-mesh/pull/3186)
- Helm charts: configure ca bundle for webhook explicitly [#3190](https://github.com/chaos-mesh/chaos-mesh/pull/3190)
- Refine logging in pkg/selector/generic/namespace [#3214](https://github.com/chaos-mesh/chaos-mesh/pull/3214)

### Deprecated

- Nothing

### Removed

- Nothing

### Fixed

- Unable to load from saved objects [#2585](https://github.com/chaos-mesh/chaos-mesh/pull/2585)
- Fix helm install error [#2591](https://github.com/chaos-mesh/chaos-mesh/pull/2591)
- Fix helm conditions in ingress [#2604](https://github.com/chaos-mesh/chaos-mesh/pull/2604)
- Fix typo in NewExperiment [#2535](https://github.com/chaos-mesh/chaos-mesh/pull/2535)
- Fix chaos-kernel build, mark bcc version [#2693](https://github.com/chaos-mesh/chaos-mesh/pull/2693)
- Fix wrong field name of PhysicalMachineChaos on Chaos Dashboard [#2724](https://github.com/chaos-mesh/chaos-mesh/pull/2724)
- Fix field descriptions of GCPChaos [#2791](https://github.com/chaos-mesh/chaos-mesh/pull/2791)
- Fix `real_gettimeofday` on arm64 [#2849](https://github.com/chaos-mesh/chaos-mesh/pull/2849)
- Fix Github Action `upload-image` [#2935](https://github.com/chaos-mesh/chaos-mesh/pull/2935)
- Fix JVMChaos to handle the situation that the container which holds the JVM rules has been deleted [#2981](https://github.com/chaos-mesh/chaos-mesh/pull/2981)
- Fix typo in comments for Chaos API [#3109](https://github.com/chaos-mesh/chaos-mesh/pull/3109)

### Security

- Nothing

## [2.1.5] - 2022-04-18

### Added

- Nothing

### Changed

- Migrate e2e tests from self-hosted Jenkins to Github Action [#2986](https://github.com/chaos-mesh/chaos-mesh/pull/2986)
- Bump minimist from 1.2.5 to 1.2.6 in /ui [#3058](https://github.com/chaos-mesh/chaos-mesh/pull/3058)
- Specify image tag of `build-env` and `dev-env` for each branch [#3071](https://github.com/chaos-mesh/chaos-mesh/pull/3071)
- Bump toda to v0.2.3 [#3131](https://github.com/chaos-mesh/chaos-mesh/pull/3131)
- Specify image tag in e2e tests [#3147](https://github.com/chaos-mesh/chaos-mesh/pull/3147)

### Deprecated

- Nothing

### Removed

- Nothing

### Fixed

- Fix `real_gettimeofday` on arm64 [#2849](https://github.com/chaos-mesh/chaos-mesh/pull/2849)
- Fix Github Action `upload-image` [#2935](https://github.com/chaos-mesh/chaos-mesh/pull/2935)
- Fix JVMChaos to handle the situation that the container which holds the JVM rules has been deleted [#2981](https://github.com/chaos-mesh/chaos-mesh/pull/2981)
- Fix typo in comments for Chaos API [#3109](https://github.com/chaos-mesh/chaos-mesh/pull/3109)

### Security

- Nothing

## [2.1.4] - 2022-03-21

### Added

- Add time skew for gettimeofday [#2742](https://github.com/chaos-mesh/chaos-mesh/pull/2742)

### Changed

- Removed docker registry mirror [#2797](https://github.com/chaos-mesh/chaos-mesh/pull/2797)

### Deprecated

- Nothing

### Removed

- Nothing

### Fixed

- Fix default value for concurrencyPolicy [#2622](https://github.com/chaos-mesh/chaos-mesh/pull/2622)
- Enable the webhooks for `Schedule` and `Workflow` [#2622](https://github.com/chaos-mesh/chaos-mesh/pull/2622)
- Fix PhysicalMachineChaos to make it able to create network bandwidth experiment. [#2850](https://github.com/chaos-mesh/chaos-mesh/pull/2850)
- Fix workflow emit new events after accomplished [#2911](https://github.com/chaos-mesh/chaos-mesh/pull/2911)
- Fix human unreadable logging timestamp [#2808](https://github.com/chaos-mesh/chaos-mesh/pull/2808) [#2902](https://github.com/chaos-mesh/chaos-mesh/pull/2902) [#2973](https://github.com/chaos-mesh/chaos-mesh/pull/2973)
- Fix default value of percent field in iochaos [#3018](https://github.com/chaos-mesh/chaos-mesh/pull/3018)
- Fix the unexpected CPU stress for StressChaos with cpu resource limit [#3102](https://github.com/chaos-mesh/chaos-mesh/pull/3102)
- Fix the bug that create JVMChaos failed in workflow [#3156](https://github.com/chaos-mesh/chaos-mesh/pull/3156)

### Security

- Nothing

## [2.1.3] - 2022-01-27

### Added

- Add status "Deleting" for chaos experiments on Chaos Dashboard [#2708](https://github.com/chaos-mesh/chaos-mesh/pull/2708)

### Changed

- Add prefix for identifier of toda and tproxy in bpm [#2673](https://github.com/chaos-mesh/chaos-mesh/pull/2673)
- Bump toda to v0.2.2 [#2747](https://github.com/chaos-mesh/chaos-mesh/pull/2747)
- Bump go to 1.17 [#2754](https://github.com/chaos-mesh/chaos-mesh/pull/2754)
- JVMChaos ignore AgentLoadException when install agent [#2701](https://github.com/chaos-mesh/chaos-mesh/pull/2701)
- Bump container-runtime to v0.11.0 [#2807](https://github.com/chaos-mesh/chaos-mesh/pull/2807)
- Bump kubernetes dependencies to v1.23.1 [#2807](https://github.com/chaos-mesh/chaos-mesh/pull/2807)
- Kill chaos-tproxy while failing to apply config [#2672](https://github.com/chaos-mesh/chaos-mesh/pull/2672)

### Fixed

- Fix wrong field name of PhysicalMachineChaos on Chaos Dashboard [#2724](https://github.com/chaos-mesh/chaos-mesh/pull/2724)
- Fix field descriptions of GCPChaos [#2791](https://github.com/chaos-mesh/chaos-mesh/pull/2791)
- Fix chaos experiment "not found" on Chaos Dashboard [#2698](https://github.com/chaos-mesh/chaos-mesh/pull/2698)

## [2.1.2] - 2021-12-29

### Changed

- Provide additional print columns for chaos experiments [#2526](https://github.com/chaos-mesh/chaos-mesh/pull/2526)
- Refactor pkg/time [#2570](https://github.com/chaos-mesh/chaos-mesh/pull/2570)
- Rename “physic” to “host” on Chaos Dashboard [#2645](https://github.com/chaos-mesh/chaos-mesh/pull/2645)
- Restructure UI codebase [#2590](https://github.com/chaos-mesh/chaos-mesh/pull/2590)
- Upgrade UI dependencies [#2685](https://github.com/chaos-mesh/chaos-mesh/pull/2685)
- Set default selector mode from “one” to “all” [#2680](https://github.com/chaos-mesh/chaos-mesh/pull/2792)
- Workflow now ordered by creation time [#2680](https://github.com/chaos-mesh/chaos-mesh/pull/2680)
- Set up codecov for testing coverage reports [#2679](https://github.com/chaos-mesh/chaos-mesh/pull/2679)
- Speed up e2e tests [#2617](https://github.com/chaos-mesh/chaos-mesh/pull/2617) [#2702](https://github.com/chaos-mesh/chaos-mesh/pull/2702)

### Fixed

- Fixed: error when using Schedule and PodChaos for injecting PodChaos as a cron job [#2618](https://github.com/chaos-mesh/chaos-mesh/pull/2618)
- Fixed: chaos-kernel build failure [#2693](https://github.com/chaos-mesh/chaos-mesh/pull/2693)

## [2.0.7] - 2022-01-27

### Added

- Add status "Deleting" for chaos experiments on Chaos Dashboard [#2708](https://github.com/chaos-mesh/chaos-mesh/pull/2708)

### Changed

- Add prefix for identifier of toda and tproxy in bpm [#2673](https://github.com/chaos-mesh/chaos-mesh/pull/2673)
- Kill chaos-tproxy while failing to apply config [#2672](https://github.com/chaos-mesh/chaos-mesh/pull/2672)

### Fixed

- Fix chaos experiment "not found" on Chaos Dashboard [#2698](https://github.com/chaos-mesh/chaos-mesh/pull/2698)
- Fix field descriptions of GCPChaos [#2791](https://github.com/chaos-mesh/chaos-mesh/pull/2791)

## [2.0.6] - 2021-12-29

### Changed

- Provide additional print columns for chaos experiments [#2526](https://github.com/chaos-mesh/chaos-mesh/pull/2526)
- Remove redundant codes [#2704](https://github.com/chaos-mesh/chaos-mesh/pull/2704)
- Speed up e2e tests #2617 [#2718](https://github.com/chaos-mesh/chaos-mesh/pull/2718)

### Fixed

- Fixed: error when using Schedule and PodChaos for injecting PodChaos as a cron job [#2618](https://github.com/chaos-mesh/chaos-mesh/pull/2618)
- Fixed: fail to recover when Chaos CR was deleted before appending finalizers [#2624](https://github.com/chaos-mesh/chaos-mesh/pull/2624)
- Fixed: chaos-kernel build failure [#2693](https://github.com/chaos-mesh/chaos-mesh/pull/2693)
- Fixed: Chaos Dashboard panic when creating StressChaos [#2655](https://github.com/chaos-mesh/chaos-mesh/pull/2655)
