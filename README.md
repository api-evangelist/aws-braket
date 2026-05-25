# AWS Braket (aws-braket)
Amazon Braket is AWS's fully managed quantum computing service. It provides a unified API and SDK for exploring, designing, simulating, and running quantum algorithms across a single point of access to multiple third-party QPU technologies (trapped-ion, superconducting, neutral-atom) and AWS-managed cloud simulators. Braket handles device queueing, S3-backed result delivery, IAM, hybrid quantum-classical job orchestration, Braket Direct reservations, and opt-in spending limits, with native PennyLane, Qiskit, and OpenQASM 3 support.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/aws-braket/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - Quantum Computing, AWS, QPU, Simulator, Hybrid Jobs, OpenQASM, PennyLane, Qiskit, Quantum

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Devices

| Provider | Device | Type | Paradigm | Region |
|---|---|---|---|---|
| AQT | IBEX-Q1 | QPU | gate-based (ion-trap) | eu-north-1 |
| IonQ | Forte-1 | QPU | gate-based (ion-trap) | us-east-1 |
| IonQ | Forte-Enterprise-1 | QPU | gate-based (ion-trap) | us-east-1 |
| IQM | Garnet | QPU | gate-based (superconducting) | eu-north-1 |
| IQM | Emerald | QPU | gate-based (superconducting) | eu-north-1 |
| QuEra | Aquila | QPU | Analog Hamiltonian Simulation (neutral-atom) | us-east-1 |
| Rigetti | Ankaa-3 | QPU | gate-based (superconducting) | us-west-1 |
| Rigetti | Cepheus-1-108Q | QPU | gate-based (superconducting) | us-west-1 |
| AWS | SV1 | On-demand simulator | gate-based state-vector | us-east-1, us-west-1, us-west-2, eu-west-2 |
| AWS | DM1 | On-demand simulator | gate-based density-matrix | us-east-1, us-west-1, us-west-2, eu-west-2 |
| AWS | TN1 | On-demand simulator | gate-based tensor-network | us-east-1, us-west-2, eu-west-2 |
| AWS | braket_sv / braket_dm / braket_ahs | Local simulator | bundled in SDK | client-side |

## APIs

### AWS Braket Quantum Tasks API
Create, retrieve, search, and cancel quantum tasks. A quantum task submits an OpenQASM 3, ProgramSet, or AHS program to a target QPU or simulator with a chosen shot count; results land in S3.

**Human URL:** [https://docs.aws.amazon.com/braket/latest/APIReference/API_CreateQuantumTask.html](https://docs.aws.amazon.com/braket/latest/APIReference/API_CreateQuantumTask.html)

- [OpenAPI](openapi/aws-braket-quantum-tasks-api-openapi.yml)
- [JSON Schema — Quantum Task](json-schema/aws-braket-quantum-task-schema.json)
- [JSON Structure](json-structure/aws-braket-quantum-task-structure.json)
- [JSON-LD](json-ld/aws-braket-context.jsonld)
- [Example — Create Quantum Task](examples/aws-braket-create-quantum-task-example.json)
- [Naftiko Capability — Quantum Tasks](capabilities/quantum-tasks.yaml)

### AWS Braket Devices API
Discover QPU and simulator devices and inspect provider, status, queue depth, paradigm, native gate set, and topology via `deviceCapabilities`.

**Human URL:** [https://docs.aws.amazon.com/braket/latest/APIReference/API_GetDevice.html](https://docs.aws.amazon.com/braket/latest/APIReference/API_GetDevice.html)

- [OpenAPI](openapi/aws-braket-devices-api-openapi.yml)
- [JSON Schema — Device](json-schema/aws-braket-device-schema.json)
- [Example — Get Device](examples/aws-braket-get-device-example.json)
- [Naftiko Capability — Devices](capabilities/devices.yaml)

### AWS Braket Hybrid Jobs API
Container-based orchestrator for variational quantum-classical algorithms (VQE, QAOA, QML). Couples ML-class EC2 instances with priority QPU/simulator access.

**Human URL:** [https://docs.aws.amazon.com/braket/latest/APIReference/API_CreateJob.html](https://docs.aws.amazon.com/braket/latest/APIReference/API_CreateJob.html)

- [OpenAPI](openapi/aws-braket-hybrid-jobs-api-openapi.yml)
- [JSON Schema — Hybrid Job](json-schema/aws-braket-hybrid-job-schema.json)
- [Example — Create Hybrid Job](examples/aws-braket-create-hybrid-job-example.json)
- [Naftiko Capability — Hybrid Jobs](capabilities/hybrid-jobs.yaml)

### AWS Braket Spending Limits API
Opt-in per-device cost ceilings that gate `CreateQuantumTask` at the API. Tasks whose estimated cost exceeds the remaining budget are rejected at submission. Applies only to on-demand and hybrid-job QPU tasks.

**Human URL:** [https://docs.aws.amazon.com/braket/latest/developerguide/braket-pricing.html](https://docs.aws.amazon.com/braket/latest/developerguide/braket-pricing.html)

- [OpenAPI](openapi/aws-braket-spending-limits-api-openapi.yml)
- [Example — Create Spending Limit](examples/aws-braket-create-spending-limit-example.json)
- [Naftiko Capability — Spending Limits](capabilities/spending-limits.yaml)

### AWS Braket Tags API
Tag quantum tasks, hybrid jobs, and spending limits for cost allocation, IAM ABAC, and resource organization. Tags propagate to AWS Cost Explorer and AWS Budgets.

**Human URL:** [https://docs.aws.amazon.com/braket/latest/APIReference/API_ListTagsForResource.html](https://docs.aws.amazon.com/braket/latest/APIReference/API_ListTagsForResource.html)

- [OpenAPI](openapi/aws-braket-tags-api-openapi.yml)
- [Naftiko Capability — Tags](capabilities/tags.yaml)

## Regions and Endpoints

| Region | Endpoint |
|---|---|
| us-east-1 (N. Virginia) | braket.us-east-1.amazonaws.com |
| us-west-1 (N. California) | braket.us-west-1.amazonaws.com |
| us-west-2 (Oregon) | braket.us-west-2.amazonaws.com |
| eu-north-1 (Stockholm) | braket.eu-north-1.amazonaws.com |
| eu-west-2 (London) | braket.eu-west-2.amazonaws.com |

## Pricing Highlights

- **Per-QPU-task fee:** $0.30 flat.
- **Per-shot fees (QPU):** AQT IBEX-Q1 $0.02350 | IonQ Forte $0.08000 | IQM Garnet $0.00145 | IQM Emerald $0.00160 | QuEra Aquila $0.01000 | Rigetti Cepheus $0.000425.
- **On-demand simulators:** SV1 $0.075/min | DM1 $0.075/min | TN1 $0.275/min (3-second minimum per task).
- **Hybrid jobs:** charged at ML-instance rates (ml.m5.xlarge default at $0.23/hr) plus underlying QPU/simulator usage.
- **Braket Direct reservations:** $2,500/hr (QuEra) to $7,000/hr (IonQ Forte).
- **Free tier:** 1 simulator hour per month for the first 12 months.

See [plans/aws-braket-plans-pricing.yml](plans/aws-braket-plans-pricing.yml), [rate-limits/aws-braket-rate-limits.yml](rate-limits/aws-braket-rate-limits.yml), and [finops/aws-braket-finops.yml](finops/aws-braket-finops.yml).

## SDKs and Tooling

- [Amazon Braket Python SDK (recommended)](https://github.com/amazon-braket/amazon-braket-sdk-python)
- [AWS CLI `aws braket`](https://docs.aws.amazon.com/cli/latest/reference/braket/) / [Boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/braket.html)
- AWS SDKs for .NET, C++, Go, Java, JavaScript, PHP, Ruby
- [Braket PennyLane plugin](https://github.com/amazon-braket/amazon-braket-pennylane-plugin-python)
- [Qiskit-Braket provider](https://github.com/amazon-braket/qiskit-braket-provider)
- [Braket.jl (Julia, experimental)](https://github.com/amazon-braket/Braket.jl)
- [AutoQASM](https://github.com/amazon-braket/autoqasm)
- [Amazon Braket Examples](https://github.com/amazon-braket/amazon-braket-examples)
- [Amazon Braket Algorithm Library](https://github.com/amazon-braket/amazon-braket-algorithm-library)
- [Hybrid Job Containers](https://github.com/amazon-braket/amazon-braket-containers)

## Maintainers

- Kin Lane — [apievangelist.com](https://apievangelist.com)
