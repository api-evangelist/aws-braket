# AWS Braket (aws-braket)

Amazon Braket is AWS's fully managed quantum computing service. It provides a unified API and SDK for exploring, designing, simulating, and running quantum algorithms across a single point of access to multiple third-party QPU technologies (trapped-ion, superconducting, neutral-atom) and AWS-managed cloud simulators. Braket handles device queueing, S3-backed result delivery, IAM, hybrid quantum-classical job orchestration, Braket Direct reservations, and opt-in spending limits, with native PennyLane, Qiskit, and OpenQASM 3 support.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/aws-braket/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/aws-braket/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Quantum Computing
- AWS
- QPU
- Simulator
- Hybrid Jobs
- OpenQASM
- PennyLane
- Qiskit
- Quantum

## Timestamps

- **Created:** 2026-05-25T00:00:00.000Z
- **Modified:** 2026-05-25

## APIs

### AWS Braket Quantum Tasks API

Create, retrieve, search, and cancel quantum tasks on Amazon Braket. A quantum task submits a single OpenQASM 3, ProgramSet, or Analog Hamiltonian Simulation program to a target QPU or simulator device with a chosen shot count; result files are written to a customer S3 location.

- **Human URL:** [https://docs.aws.amazon.com/braket/latest/APIReference/API_CreateQuantumTask.html](https://docs.aws.amazon.com/braket/latest/APIReference/API_CreateQuantumTask.html)

#### Tags

- Quantum Computing
- Quantum Tasks
- AWS
- OpenQASM

#### Properties

- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_CreateQuantumTask.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_GetQuantumTask.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_CancelQuantumTask.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_SearchQuantumTasks.html)
- [OpenAPI](openapi/aws-braket-quantum-tasks-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/aws-braket-quantum-tasks-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/aws-braket-quantum-tasks-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/aws-braket-quantum-task-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/aws-braket-quantum-task-structure.json)
- [JSON-LD](json-ld/aws-braket-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Example](examples/aws-braket-create-quantum-task-example.json)

### AWS Braket Devices API

Discover the QPU and simulator devices available on Amazon Braket. Returns device ARN, provider (AQT, IonQ, IQM, QuEra, Rigetti, Amazon), status (ONLINE/OFFLINE/RETIRED), queue depth, paradigm (gate-based or AHS), native gate set, and topology via deviceCapabilities.

- **Human URL:** [https://docs.aws.amazon.com/braket/latest/APIReference/API_GetDevice.html](https://docs.aws.amazon.com/braket/latest/APIReference/API_GetDevice.html)

#### Tags

- Quantum Computing
- Devices
- QPU
- Simulator
- AWS

#### Properties

- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_GetDevice.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_SearchDevices.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/developerguide/braket-devices.html)
- [OpenAPI](openapi/aws-braket-devices-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/aws-braket-devices-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/aws-braket-devices-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/aws-braket-device-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/aws-braket-get-device-example.json)

### AWS Braket Hybrid Jobs API

Orchestrate hybrid quantum-classical algorithms. A hybrid job runs a container or script-mode entry point on ML-class EC2 instances while consuming priority QPU/simulator capacity through the Braket service. Use for variational algorithms (VQE, QAOA, QML).

- **Human URL:** [https://docs.aws.amazon.com/braket/latest/APIReference/API_CreateJob.html](https://docs.aws.amazon.com/braket/latest/APIReference/API_CreateJob.html)

#### Tags

- Quantum Computing
- Hybrid Jobs
- VQE
- QAOA
- AWS

#### Properties

- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_CreateJob.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_GetJob.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_CancelJob.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_SearchJobs.html)
- [OpenAPI](openapi/aws-braket-hybrid-jobs-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/aws-braket-hybrid-jobs-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/aws-braket-hybrid-jobs-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/aws-braket-hybrid-job-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/aws-braket-create-hybrid-job-example.json)

### AWS Braket Spending Limits API

Opt-in per-device cost ceilings that gate CreateQuantumTask at the API. Spending limits validate each request against remaining budget (spending limit minus current and queued spend) and reject submissions whose estimated cost would exceed the cap. Applies to on-demand and hybrid-job QPU tasks only.

- **Human URL:** [https://docs.aws.amazon.com/braket/latest/developerguide/braket-pricing.html](https://docs.aws.amazon.com/braket/latest/developerguide/braket-pricing.html)

#### Tags

- Quantum Computing
- Spending Limits
- FinOps
- AWS

#### Properties

- [Documentation](https://docs.aws.amazon.com/braket/latest/developerguide/braket-pricing.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_CreateSpendingLimit.html)
- [OpenAPI](openapi/aws-braket-spending-limits-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/aws-braket-spending-limits-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/aws-braket-spending-limits-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Example](examples/aws-braket-create-spending-limit-example.json)

### AWS Braket Tags API

Tag quantum tasks, hybrid jobs, and spending limits for cost allocation, IAM ABAC, and resource organization. Tags propagate to AWS Cost Explorer and AWS Budgets and can be referenced in IAM condition keys to enforce fine-grained access controls.

- **Human URL:** [https://docs.aws.amazon.com/braket/latest/APIReference/API_ListTagsForResource.html](https://docs.aws.amazon.com/braket/latest/APIReference/API_ListTagsForResource.html)

#### Tags

- Quantum Computing
- Tags
- FinOps
- AWS

#### Properties

- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_ListTagsForResource.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_TagResource.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/API_UntagResource.html)
- [OpenAPI](openapi/aws-braket-tags-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/aws-braket-tags-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/aws-braket-tags-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://aws.amazon.com/braket/)
- [Documentation](https://docs.aws.amazon.com/braket/)
- [Getting Started](https://docs.aws.amazon.com/braket/latest/developerguide/what-is-braket.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/APIReference/Welcome.html)
- [Regions](https://docs.aws.amazon.com/braket/latest/developerguide/braket-devices.html)
- [Documentation](https://docs.aws.amazon.com/braket/latest/developerguide/braket-references.html)
- [Documentation](https://aws.amazon.com/braket/quantum-computers/)
- [Pricing](https://aws.amazon.com/braket/pricing/)
- [Documentation](https://docs.aws.amazon.com/braket/latest/developerguide/braket-pricing.html)
- [Status Page](https://health.aws.amazon.com/health/status)
- [Blog](https://aws.amazon.com/blogs/quantum-computing/)
- [Sign Up](https://signin.aws.amazon.com/signup)
- [GitHub Organization](https://github.com/amazon-braket)
- [SDK](https://github.com/amazon-braket/amazon-braket-sdk-python)
- [Documentation](https://amazon-braket-sdk-python.readthedocs.io/en/latest/)
- [SDK](https://github.com/amazon-braket/amazon-braket-schemas-python)
- [SDK](https://github.com/amazon-braket/amazon-braket-default-simulator-python)
- [Code Examples](https://github.com/amazon-braket/amazon-braket-examples)
- [Code Examples](https://github.com/amazon-braket/amazon-braket-algorithm-library)
- [Plugins](https://github.com/amazon-braket/amazon-braket-pennylane-plugin-python)
- [Plugins](https://github.com/amazon-braket/qiskit-braket-provider)
- [SDK](https://github.com/amazon-braket/Braket.jl)
- [SDK](https://github.com/amazon-braket/autoqasm)
- [Tool](https://github.com/amazon-braket/amazon-braket-containers)
- [SDK](https://docs.aws.amazon.com/cli/latest/reference/braket/)
- [SDK](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/braket.html)
- [SDK](https://docs.aws.amazon.com/sdkfornet/v3/apidocs/items/Braket/NBraket.html)
- [SDK](https://docs.aws.amazon.com/AWSJavaSDK/latest/javadoc/com/amazonaws/services/braket/package-summary.html)
- [SDK](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/Braket.html)
- [SDK](https://docs.aws.amazon.com/sdk-for-go/api/service/braket/)
- [SDK](https://docs.aws.amazon.com/aws-sdk-php/v3/api/class-Aws.Braket.BraketClient.html)
- [SDK](https://docs.aws.amazon.com/sdk-for-ruby/v3/api/Aws/Braket.html)
- [SDK](https://sdk.amazonaws.com/cpp/api/LATEST/namespace_aws_1_1_braket.html)
- [Documentation](https://openqasm.com/)
- [Documentation](https://pennylane.ai/)
- [Documentation](https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazonbraket.html)
- [Terms of Service](https://aws.amazon.com/service-terms/)
- [Privacy Policy](https://aws.amazon.com/privacy/)
- [Plans](plans/aws-braket-plans-pricing.yml)
- [Rate Limits](rate-limits/aws-braket-rate-limits.yml)
- [Fin Ops](finops/aws-braket-finops.yml)
- [Vocabulary](vocabulary/aws-braket-vocabulary.yml)
- [Spectral Ruleset](rules/aws-braket-rules.yml)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
