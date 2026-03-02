<h1> awesome-smart-contract-analysis-tools
</h1>

<p>
A curated list of awesome smart contract analysis tools, including static analysis, dynamic analysis, fuzzing, formal verification and more.
</p>

<p>
The following two papers collected almost all existing smart contract security analysis tools back in 2021. However, the tools mentioned in these papers are now outdated, with some even deprecated, as newer tools have been developed. This repository aims to gather the most up-to-date smart contract security tools across various blockchains and smart contract languages.

S. S. Kushwaha, S. Joshi, D. Singh, M. Kaur and H. -N. Lee, "[Ethereum Smart Contract Analysis Tools: A Systematic Review,](https://ieeexplore.ieee.org/abstract/document/9762279)" in IEEE Access, vol. 10, pp. 57037-57062, 2022, doi: 10.1109/ACCESS.2022.3169902.


M. di Angelo and G. Salzer, "[A Survey of Tools for Analyzing Ethereum Smart Contracts,](https://ieeexplore.ieee.org/abstract/document/8782988)" 2019 IEEE International Conference on Decentralized Applications and Infrastructures (DAPPCON), Newark, CA, USA, 2019, pp. 69-78, doi: 10.1109/DAPPCON.2019.00018. 
</p>

**Content**
- [Tools](#tools)
  - [Static Analysis](#static-analysis)
  - [Symbolic Execution](#symbolic-execution)
  - [Fuzzing Tools](#fuzzing-tools)
  - [Formal Verification](#formal-verification)
  - [Mix](#mix)
- [Practical Audit Workflows](#practical-audit-workflows)
- [Research](#research)
- [Contributions](#contributions)

# Tools

## Static Analysis
<a id="Static-Analysis"></a>
+ [Aderyn](https://github.com/Cyfrin/aderyn) - Rust-based static analyzer for Solidity smart contracts by Cyfrin, outputs Markdown reports.
+ [AChecker](https://github.com/DependableSystemsLab/AChecker) - Automated access-control vulnerability checker for Solidity smart contracts.
+ [Clairvoyance](https://github.com/ToolmanInside/readthedocs/blob/master/docs/index.rst) - Taint analysis tool for detecting vulnerabilities in Solidity source code.
+ [Conkas](https://github.com/nveloso/conkas) - Modular static analysis tool for Ethereum smart contracts using symbolic execution on EVM bytecode.
+ [Eth2Vec](https://github.com/fseclab-osaka/eth2vec) - Machine-learning-based vulnerability detection using neural embeddings of EVM bytecode.
+ [EthIR](https://github.com/costa-group/EthIR) - Decompiler that lifts EVM bytecode to a high-level rule-based representation for analysis.
+ [Gas Gauge](https://github.com/gasgauge/gasgauge.github.io) - Static analysis tool for detecting gas-related vulnerabilities and estimating worst-case gas consumption.
+ [HoneyBadger](https://github.com/christoftorres/HoneyBadger?tab=readme-ov-file) - Tool for detecting honeypot smart contracts that trap funds sent by victims.
+ [NeuCheck](https://github.com/Northeastern-University-Blockchain/NeuCheck) - Neural-network-based vulnerability detector for Solidity source code.
+ [Osiris](https://github.com/christoftorres/Osiris) - Detects integer bugs (overflows/underflows) in Ethereum smart contracts using symbolic execution.
+ [Oyente](https://github.com/enzymefinance/oyente) - One of the earliest Ethereum smart contract analyzers; detects common security vulnerabilities via symbolic execution of EVM bytecode.
+ [Pyrometer](https://github.com/nascentxyz/pyrometer) - Semantic and range analysis tool for Solidity, tracks value ranges and access control through execution paths.
+ [rattle](https://github.com/crytic/rattle) - EVM binary static analysis framework by Trail of Bits that recovers SSA form from deployed bytecode.
+ [Securify v2.0](https://github.com/eth-sri/securify2?tab=readme-ov-file) - Security scanner for Ethereum smart contracts backed by a Datalog-based analysis from ETH Zurich.
+ [semgrep-solidity](https://github.com/Decurity/semgrep-solidity) - Semgrep rules for detecting security vulnerabilities and anti-patterns in Solidity source code.
+ [SIF](https://github.com/chao-peng/SIF) - Source-level instrumentation framework for Solidity that enables fine-grained program analysis.
+ [Slither](https://github.com/crytic/slither) - Fast, extensible static analysis framework for Solidity and Vyper by Trail of Bits; supports 100+ detectors and custom analysis.
+ [SmartBugs](https://github.com/smartbugs/smartbugs) - Automated framework for running multiple analysis tools on Solidity contracts and aggregating results.
+ [SmartCheck](https://github.com/smartdec/smartcheck) - XML-pattern-based static analyzer for Solidity that detects a wide range of security and code-quality issues.
+ [SmartEmbed](https://github.com/beyondacm/SmartEmbed) - Code-clone detection tool for Ethereum smart contracts based on deep-learning embeddings.
+ [SolAnalyzer](https://github.com/EricR/solanalyzer) - Archived static analysis tool for Solidity smart contracts.
+ [solhint](https://github.com/protofire/solhint?tab=readme-ov-file) - Open-source Solidity linter providing security, style-guide, and best-practice validations.
+ [SolidityCheck](https://github.com/xf97/SolidityCheck) - Automated vulnerability detection tool for Solidity based on regular-expression pattern matching.
+ [SolMet](https://github.com/sveneld/SolMet) - Solidity source code metrics tool for measuring complexity, lines of code, and other software metrics.
+ [teEther](https://github.com/nescio007/teether) - Automated exploit generation tool for Ethereum smart contracts using backward slicing on EVM bytecode.
+ [Vandal](https://github.com/usyd-blockchain/vandal) - Static analysis framework for Ethereum smart contract bytecode that decompiles EVM to Datalog relations.
+ [Wake](https://github.com/Ackee-Blockchain/wake) - Python-based Solidity development and testing framework with built-in static analysis detectors by Ackee Blockchain.
+ [4naly3er](https://github.com/Picodes/4naly3er) - Automated static analysis report generator for Solidity used widely in competitive audit contests.

## Symbolic Execution
<a id="Symbolic-Execution"></a>
+ [Manticore](https://github.com/trailofbits/manticore) - Symbolic execution tool for EVM smart contracts and native binaries by Trail of Bits; generates test inputs that trigger vulnerabilities.
+ [Pakala](https://github.com/palkeo/pakala) - Symbolic execution tool for finding exploitable bugs in EVM bytecode; focuses on ether theft and locked funds.
+ [RA](https://github.com/wanidon/RA) - Symbolic-execution-based vulnerability detector for Ethereum smart contracts.
+ [VeriSmart](https://github.com/kupl/VeriSmart-public) - Formally verified safety checker for Solidity arithmetic using constraint solving to prove absence of integer overflows.

## Fuzzing Tools
<a id="Fuzzing-Tools"></a>
+ [Echidna](https://github.com/crytic/echidna) - Property-based fuzzer for Ethereum smart contracts by Trail of Bits; tests user-defined invariants written in Solidity.
+ [EVMFuzzer](https://github.com/EVMFuzzer/EVMFuzzer) - Coverage-guided fuzzer that uses multiple EVM implementations as differential oracles to detect consensus bugs.
+ [ItyFuzz](https://github.com/fuzzland/ityfuzz) - Snapshot-based hybrid fuzzer for smart contracts that combines fuzzing with symbolic execution.
+ [Medusa](https://github.com/crytic/medusa) - Parallelized, coverage-guided smart contract fuzzer powered by go-ethereum by Trail of Bits; compatible with Echidna test properties.
+ [sFuzz](https://github.com/duytai/sFuzz) - Adaptive grey-box fuzzer for smart contracts that prioritizes branches with the help of static analysis.
+ [SoliAudit](https://github.com/jianwei76/SoliAudit) - Automated smart contract vulnerability auditing tool combining machine learning and grey-box fuzzing.

## Formal Verification
<a id="Formal-Verification"></a>
+ [EthVer](https://github.com/lukmaz/ethver) - Formal verification framework for Ethereum smart contracts based on the BIP component model.
+ [Halmos](https://github.com/a16z/halmos) - Symbolic testing tool for EVM-compatible smart contracts that reuses Foundry test suites for formal verification.
+ [VeriSol](https://github.com/microsoft/verisol) - Formal verifier for Solidity smart contracts developed by Microsoft Research using Boogie as the backend prover.

## Mix
<a id="Mix"></a>
+ [Maian](https://github.com/ivicanikolicsg/MAIAN) - Detects three classes of vulnerable contracts (prodigal, suicidal, and greedy) using inter-procedural symbolic analysis.
+ [Mythril](https://github.com/Consensys/mythril) - Multi-technique security analyzer combining symbolic execution, taint analysis, and control-flow checking for EVM bytecode.

# Practical Audit Workflows
<a id="practical-audit-workflows"></a>

This section shows how to combine tools from this list into effective, layered smart contract security assessments.

## Recommended Tool Stack by Audit Layer

| Layer | Recommended Tools | What it Catches |
|-------|-------------------|-----------------|
| Lint & Style | solhint, Slither | Code quality, naming, best practices |
| Static Analysis | Slither, Aderyn, Mythril | Reentrancy, access control, integer bugs, known patterns |
| Symbolic Execution | Manticore, Halmos | Deep path exploration, invariant violations |
| Fuzzing | Echidna, Medusa | Edge-case inputs, property violations, state invariants |
| Formal Verification | Halmos, VeriSol, VeriSmart | Mathematical correctness proofs |

## Quick Audit Workflow (Open Source)

**Step 1 — Lint the source code**
```bash
# Install: npm install -g solhint
solhint 'contracts/**/*.sol'
```

**Step 2 — Run static analysis with Slither**
```bash
# Install: pip install slither-analyzer
slither . --checklist --markdown-root https://github.com/your-org/your-repo/blob/main/
# Replace 'your-org/your-repo' with your actual GitHub repository path
```

**Step 3 — Run Aderyn for a Markdown audit report**
```bash
# Install: cargo install aderyn
aderyn .
```

**Step 4 — Fuzz with Echidna (property-based)**

Write invariants directly in Solidity, then run:
```bash
# Install: https://github.com/crytic/echidna#installation
echidna . --contract MyContractTest --test-mode property
```

**Step 5 — Symbolic testing with Halmos (Foundry projects)**
```bash
# Install: pip install halmos
halmos --contract MyContractTest --function testSymbolic
```

**Step 6 — Deep bytecode analysis with Mythril**
```bash
# Install: pip install mythril
myth analyze contracts/MyContract.sol
# For projects with remappings, pass them via --solc-remappings or a solc standard JSON config
```

## CI/CD Integration (GitHub Actions)

Add automated security scanning to every pull request:

```yaml
name: Smart Contract Security Audit

on: [push, pull_request]

jobs:
  slither:
    name: Slither Static Analysis
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: crytic/slither-action@v0.4.0
        with:
          target: 'contracts/'
          slither-args: '--exclude-dependencies'

  aderyn:
    name: Aderyn Static Analysis
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Install Aderyn
        run: cargo install aderyn
      - name: Run Aderyn
        run: aderyn .

  echidna:
    name: Echidna Fuzzing
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: crytic/echidna-action@v2
        with:
          files: .
          contract: MyContractTest
```

## Audit Checklist

Use this checklist as a starting point for any Solidity smart contract audit:

- [ ] Reentrancy vulnerabilities (Slither: `reentrancy-*`)
- [ ] Integer overflow/underflow (Osiris, Slither: `tautology`)
- [ ] Access control issues (Slither: `unprotected-upgrade`, AChecker)
- [ ] Unchecked external call return values (Slither: `unchecked-lowlevel`)
- [ ] Timestamp and block number dependence (Slither: `timestamp`)
- [ ] Gas limit and denial-of-service vectors (Gas Gauge)
- [ ] Front-running / transaction ordering (Manticore)
- [ ] Honeypot traps (HoneyBadger)
- [ ] Improper use of `tx.origin` for authorization (solhint, Slither)
- [ ] Logic bugs and invariant violations (Echidna / Medusa fuzzing)
- [ ] Formal correctness of critical math (Halmos, VeriSmart)

# Research
<a id="Research Paper"></a>
+ [ContractWard: Automated Vulnerability Detection Models for Ethereum Smart Contracts](https://ieeexplore.ieee.org/document/8967006)
+ [Ethainter: a smart contract security analyzer for composite vulnerabilities](https://dl.acm.org/doi/abs/10.1145/3385412.3385990)
+ [A Hybrid Formal Verification System in Coq for Ensuring the Reliability and Security of Ethereum-Based Service Smart Contracts](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8970279)
+ [Running on Fumes--Preventing Out-of-Gas Vulnerabilities in Ethereum Smart Contracts using Static Resource Analysis](https://arxiv.org/abs/1811.10403)
+ [MuSC: A Tool for Mutation Testing of Ethereum Smart Contract](https://ieeexplore.ieee.org/document/8952206)
+ [Security Assurance for Smart Contract](https://ieeexplore.ieee.org/document/8328743)
+ [sCompile: Critical Path Identification and Analysis for Smart Contracts](https://arxiv.org/abs/1808.00624)
+ [SESCon: Secure Ethereum Smart Contracts by Vulnerable Patterns’ Detection](https://dl.acm.org/doi/abs/10.1155/2021/2897565)
+ [SmartAnvil: Open-Source Tool Suite for Smart Contract Analysis](https://inria.hal.science/hal-01940287)
+ [SmartGraph: Static Analysis Tool for Solidity Smart Contracts](https://link.springer.com/chapter/10.1007/978-3-031-37105-9_39)
+ [SmartInspect: solidity smart contract inspector](https://ieeexplore.ieee.org/document/8327566)
+ [SmartScan: An approach to detect Denial of Service Vulnerability in Ethereum Smart Contracts](https://arxiv.org/abs/2105.02852)
+ [solc-verify: A Modular Verifier for Solidity Smart Contracts](https://arxiv.org/abs/1907.04262)
+ [SolGuard: Preventing external call issues in smart contract-based multi-agent robotic systems](https://www.sciencedirect.com/science/article/pii/S0020025521007994)
+ [VeriSolid: Correct-by-Design Smart Contracts for Ethereum](https://arxiv.org/abs/1901.01292)
+ [DEFECTCHECKER: Automated Smart Contract Defect Detection by Analyzing EVM Bytecode](https://arxiv.org/abs/2009.02663)
+ [Visual emulation for Ethereum's virtual machine](https://ieeexplore.ieee.org/document/8406332)
+ [ESCORT: Ethereum Smart COntRacTs Vulnerability Detection using Deep Neural Network and Transfer Learning](https://arxiv.org/abs/2103.12607)
+ [S-gram: Towards Semantic-Aware Security Auditing for Ethereum Smart Contracts](https://ieeexplore.ieee.org/document/9000031)
+ [eThor: Practical and Provably Sound Static Analysis of Ethereum Smart Contracts](https://arxiv.org/abs/2005.06227)
+ [ETHPLOIT: From Fuzzing to Efficient Exploit Generation against Smart Contracts](https://wcventure.github.io/FuzzingPaper/Paper/SANER20_ETHPLOIT.pdf)
+ [KEVM: A Complete Formal Semantics of the Ethereum Virtual Machine](https://ieeexplore.ieee.org/document/8429306)
+ [VerX: Safety Verification of Smart Contracts](https://ieeexplore.ieee.org/document/9152791)
+ [SAFEVM: a safety verifier for Ethereum smart contracts](https://dl.acm.org/doi/10.1145/3293882.3338999)
+ [ReGuard: Finding Reentrancy Bugs in Smart Contracts](https://ieeexplore.ieee.org/document/8449446)
+ [ContractGuard: Defend Ethereum Smart Contracts with Embedded Intrusion Detection](https://arxiv.org/abs/1911.10472)
+ [Etherolic: a practical security analyzer for smart contracts](https://dl.acm.org/doi/10.1145/3468264.3468546)
+ [HermHD: Enhancing smart contract security based on code obfuscation](https://dl.acm.org/doi/10.1145/3638985.3639001)
+ [MANDO-GURU: vulnerability detection for smart contract source code by heterogeneous graph embeddings](https://dl.acm.org/doi/10.1145/3540250.3558927)
+ [Lanturn: Measuring Economic Security of Smart Contracts Through Adaptive Learning](https://dl.acm.org/doi/10.1145/3576915.3623204)

# Contributions

Please see [Contribution Guideline](CONTRIBUTION.md) for more details.


