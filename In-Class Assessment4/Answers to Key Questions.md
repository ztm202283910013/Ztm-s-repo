# Answers to Key Questions

## 1. Serverless vs. Kubernetes Microservices

- **Core Problem Solved**: Eliminates infrastructure management and idle resource waste.
- **Better For**: Sporadic event-driven tasks (e.g., order confirmation emails).
- **Worse For**: Latency-sensitive apps (e.g., real-time trading) due to cold starts.

## 2. Service Mesh (Istio) Advantages Over Kubernetes Networking

- Adds layer-7 traffic control (e.g., weighted routing), mTLS encryption, and detailed telemetry.
- Enforces consistent policies (access control, rate limiting) without code changes.

## 3. Sidecar Proxy (Envoy) in Istio

- **Function**: Routes traffic, enforces security, collects telemetry, and implements traffic rules.
- **Need**: Decouples networking/security from app code, ensures consistency across services.

## 4. Istio Traffic Management

- **Key Features**: Weighted routing, circuit breaking.

- Examples

  :

  1. Canary deployments (route 10% traffic to new versions).
  2. Circuit breaking to prevent cascading failures.

## 5. Knative Serving Autoscaling

- **Mechanism**: Uses request-based scaling + scale-to-zero via Knative Activator.

- Triggers

  :

  - Scale up: Incoming requests or high resource usage.
  - Scale down: No requests for ~60 seconds (scale to zero).

## 6. Knative Eventing

- **Role**: Standardizes event ingestion/routing for event-driven architectures.
- **Support**: Integrates with sources (Kafka, S3), uses Brokers/Triggers for decoupled event delivery.

## 7. Knative & Kubernetes Primitives

- **Abstracted**: Deployments, Services, HPA.
- **Benefit**: Developers focus on code, not infrastructure; reduces operational overhead.

## 8. KServe InferenceService

- **Function**: Deploys ML models with standardized APIs, scaling, and versioning.
- **Simplification**: Framework-agnostic, no custom serving code, built-in monitoring.

## 9. KServe Data Flow & Latency

- **Flow**: Istio (ingress) → Knative (routing/scaling) → KServe (inference) → Response.
- **Bottlenecks**: Cold starts (Knative), large model inference (KServe), Istio proxy overhead.

## 10. Istio for Canary/A/B Testing

- **Use**: Granular traffic splitting (e.g., 30% to new model in KServe).
- **Pros**: Dynamic adjustment, real-time rollback.
- **Cons**: Added complexity, learning curve.