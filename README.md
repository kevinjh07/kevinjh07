# Kevin Jhonson

Software engineer, 12 years — the last 8 on Java and Spring Boot backends for high-volume systems.

Today at **Zup (Itaú group)**, on real-estate-backed credit products: a regulated domain with external
integrations and direct financial impact when something fails. I build and maintain the services in that flow,
review the team's code, and take part in the architecture decisions.

What I do well: microservices that survive change — a test architecture that holds up under refactoring,
observability that surfaces the problem before the customer reports it, and APIs that absorb peaks without
doubling the infrastructure.

**Java · Spring Boot · AWS (ECS, SNS, SQS, S3) · PostgreSQL · Docker · Angular · TypeScript**

Belo Horizonte, Brazil · [LinkedIn](https://www.linkedin.com/in/kevinjh07) · [TabNews](https://www.tabnews.com.br/kevinjh07)

Open to conversations about tech lead and staff engineer roles.

---

## Selected work

What I ship professionally is private, so these are the public ones. Their documentation is in Portuguese.

### [finguard](https://github.com/kevinjh07/finguard) · Python, Amazon Bedrock

A complaint-analysis pipeline for financial services — the kind of complaint that arrives through SAC, Ouvidoria
or the Central Bank. Free text in, structured analysis and a risk opinion out.

The engineering is in the guardrails. Sanitization is deterministic and runs *before* any model call: it masks
personal data, obfuscates abusive language and flags adversarial content, on the way in and on the way out.
Urgency and risk floors only ever escalate, so an injection that talks the model into downgrading a case cannot
move what the rule already established — and the divergence is recorded in the opinion itself.

Cost is routed rather than accepted: across a 500-complaint batch, 23% of the opinions are issued by rules
without touching a model at all, and the rest split between a fast and a strong model according to the risk
floor. The figures come from the execution trace, not from an estimate. Three execution modes — `mock`
(deterministic, offline, zero cost), `replay` (recorded cassettes) and `live` (Bedrock Converse API with
adaptive retries). 25 test suites, mutation testing, and the architecture decisions written down.

### [Onde Tem Premium](https://ondetempremium.com.br) · source private

Finds the nearest filling station selling premium gasoline in Brazil. Web and Android, in production on
Cloudflare for **US$ 0/month**: static reads at the edge, a self-hosted vector basemap (2.1 GB of PMTiles in R2,
served by a Worker), weekly ingestion of the ANP public dataset with a guard against bad releases, and the
nearest-station search computed on the device — so the user's location never reaches a server.

### Smaller things

- [gerador-nfse-nacional-laravel](https://github.com/kevinjh07/gerador-nfse-nacional-laravel) — generator and
  XML signer for Brazil's national electronic service invoice (NFS-e). A regulated format where the signature
  either validates or the invoice does not exist.
- [homelab-observability-box](https://github.com/kevinjh07/homelab-observability-box) — a full Grafana and
  Prometheus stack on an old Amlogic ARM64 TV box. What observability costs when you cannot throw hardware at it.
- [homelab-media-box](https://github.com/kevinjh07/homelab-media-box) — the same box as a media server, running a
  24/7 channel.
- [triumph-tiger-obd-toolkit](https://github.com/kevinjh07/triumph-tiger-obd-toolkit) — OBD scripts to reset the
  service indicator on a Triumph Tiger, documented well enough to work on someone else's bike.
