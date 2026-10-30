# MacBrains Labs

**Independent research on Apple Silicon, Apple Neural Engine execution, and Core ML compilation.**

We publish measured, bounded technical findings rather than claims inferred from compiler success, marketing specifications, or synthetic benchmarks.

**[Research home](https://macbrainslabs.org/)** | **[Research index](https://macbrainslabs.org/research/)** | **[Methods](https://macbrainslabs.org/methods/)** | **[Contact](mailto:research@macbrainslabs.org)**

## Selected research records

| Investigation | Published finding | Limit |
| :-- | :-- | :-- |
| [Qwen2.5-1.5B LUT4 Core ML graph](https://macbrainslabs.org/notes/qwen-lut4/) | 2,090 operators assigned to ANE; 79 assigned to CPU | MLComputePlan assignment on the named 28-layer artifact. Not proof of full ANE-only inference or direct silicon tracing. |
| [LFM S2 numerical parity](https://macbrainslabs.org/notes/lfm-parity/) | 743/743 compute operations assigned to ANE, with both specified production outputs passing the declared parity gate | A separate 46-output diagnostic graph had only 34/46 ANE parity passes and is reported independently. |
| [Qwen decode batch sweep](https://macbrainslabs.org/notes/decode-regimes/) | 45.4 (B=1), 68.1 (B=2), 102.1 (B=4), 125.8 (B=8) aggregate tokens/s | Five-round interleaved steady-state on the tested A18 Pro substrate. These are aggregate, shape-specific measurements. |

**[Machine-readable ANE research records](https://github.com/macbrainslabs/ane-research-records):** source-pinned public summary tables, fingerprint metadata, and a verification script. These are derived summaries rather than private raw experiment files.

## Engineering method

Our native workflow uses Swift/MIL authoring, Core ML graph compilation and inspection, numerical parity against specified fixtures, and explicit hardware-placement evidence. We retain falsified hypotheses, diagnostic divergences, and output-layout constraints rather than silently omitting them.

The public site documents selected results and methodology. References to private source repositories, fixtures, model weights, or raw receipts are *not* claims that those artifacts have been published.

### Boundaries and affiliation

MacBrains Labs is an **independent technical research identity**, not an assertion of incorporation, academic affiliation, Apple partnership, or third-party device testing authorization. All disclosed work is scoped to equipment, software, and artifacts the researcher is authorized to examine.

For technical correspondence: **research@macbrainslabs.org**

[Browse the research notes](https://macbrainslabs.org/research/) | [Read the experimental methods](https://macbrainslabs.org/methods/) | [Contact and disclosure](https://macbrainslabs.org/contact/)
