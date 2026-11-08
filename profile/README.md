# MacBrains Labs

**Independent research on Apple Silicon, Apple Neural Engine execution, and Core ML compilation.**

We publish measured, bounded technical findings rather than claims inferred from compiler success, marketing specifications, or synthetic benchmarks.

**Researcher:** [Nayte Wilson (ORCID iD 0009-0003-4026-8212)](https://orcid.org/0009-0003-4026-8212) — independent research attribution, not an institutional credential.

**[Research home](https://macbrainslabs.org/)** | **[Research index](https://macbrainslabs.org/research/)** | **[Methods](https://macbrainslabs.org/methods/)** | **[Contact](mailto:research@macbrainslabs.org)**

## Selected research records

| Investigation | Published finding | Limit |
| :-- | :-- | :-- |
| [Qwen2.5-1.5B LUT4 Core ML graph](https://macbrainslabs.org/notes/qwen-lut4/) | 2,090 operators assigned to ANE; 79 assigned to CPU | MLComputePlan assignment on the named 28-layer artifact. Not proof of full ANE-only inference or direct silicon tracing. |
| [LFM S2 numerical parity](https://macbrainslabs.org/notes/lfm-parity/) | 743/743 compute operations assigned to ANE, with both specified production outputs passing the declared parity gate | A separate 46-output diagnostic graph had only 34/46 ANE parity passes and is reported independently. |
| [Qwen decode batch sweep](https://macbrainslabs.org/notes/decode-regimes/) | 45.4 (B=1), 68.1 (B=2), 102.1 (B=4), 125.8 (B=8) aggregate tokens/s | Five-round interleaved steady-state on the tested A18 Pro substrate. These are aggregate, shape-specific measurements on single-function probe artifacts; output quality was not validated. |

## Published research records

Each record is a tagged release of [macbrainslabs/ane-research-records](https://github.com/macbrainslabs/ane-research-records) with its own Zenodo version DOI, under the all-versions DOI [10.5281/zenodo.23798036](https://doi.org/10.5281/zenodo.23798036). Current verification status for every record is on [Publications](https://macbrainslabs.org/publications/).

| Version | Record | Scope as published | DOI |
| :-- | :-- | :-- | :-- |
| v0.3.0 | [ANERECore cross-repo MIL parity: tap, steer and functionWide](https://macbrainslabs.org/research/records/ane-record-b8f78a146608021d974dcdec/) | Same chip, single device. MIL text byte equality on one Qwen fixture; 10 of 10 counted runs pass across two clean-room arms. No Core ML compile, ANE execution or numerics claimed. | [10.5281/zenodo.24034510](https://doi.org/10.5281/zenodo.24034510) |
| v0.2.0 | [LFM3-1.7B layer-14 diagnostic under Core ML `cpuAndNeuralEngine`](https://macbrainslabs.org/research/records/ane-record-c188def1e88a0d94018dfe99/) | Same chip, single device (A18 Pro). ANE execution inferred from compute-plan placement; 8 executions disclosed, 5 counted. | [10.5281/zenodo.23905811](https://doi.org/10.5281/zenodo.23905811) |
| v0.1.0 | [Public measurement summaries](https://github.com/macbrainslabs/ane-research-records/releases/tag/v0.1.0) | Source-pinned summary tables, fingerprint metadata and a verification script; derived summaries, not private raw experiment files. | [10.5281/zenodo.23798037](https://doi.org/10.5281/zenodo.23798037) |

v0.2.0 and v0.3.0 were each released only after a final reviewer INCLUDE on their exact package hash; the procedure is on the [methods page](https://macbrainslabs.org/methods/#review). Same-chip reruns are reported as repeatability, never as cross-device replication. No record claims novelty, and an archived DOI is not peer review.

## Public implementation (distinct artifact)

The [qwen2.5-ane Swift server](https://github.com/naytewilson/qwen2.5-ane) is a separately compiled, MIT-licensed public implementation with source provenance and [citation metadata](https://github.com/naytewilson/qwen2.5-ane/blob/main/CITATION.cff). Its published infer/prefill placement counts refer to a **different compiled artifact** than the 2,090 ANE / 79 CPU research-table observation above. It is not a full release of private ANE research fixtures.

## Engineering method

Our native workflow uses Swift/MIL authoring, Core ML graph compilation and inspection, numerical parity against specified fixtures, and explicit hardware-placement evidence. We retain falsified hypotheses, diagnostic divergences, and output-layout constraints rather than silently omitting them.

The public site documents selected results and methodology. References to private source repositories, fixtures, model weights, or raw receipts are *not* claims that those artifacts have been published.

### Boundaries and affiliation

MacBrains Labs is an **independent technical research identity**, not an assertion of incorporation, academic affiliation, Apple partnership, or third-party device testing authorization. All disclosed work is scoped to equipment, software, and artifacts the researcher is authorized to examine.

For technical correspondence: **research@macbrainslabs.org**

[Browse the research notes](https://macbrainslabs.org/research/) | [Read the experimental methods](https://macbrainslabs.org/methods/) | [Contact and disclosure](https://macbrainslabs.org/contact/)
