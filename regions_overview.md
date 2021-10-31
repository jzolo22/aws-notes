## What is a region?

- Cluster of data centers
- Most services are scoped to a specific region
- Each region has many availability zones (usually 3)

## What is an availability zone?

- One or more discrete data centers with its own networking, power, connectivity
  - e.g. `us-east-1` will have `us-east-1-a`, `us-east-1-b`, `us-east-1-c` that make up one region
- Separated from each other so they're isolated from disasters
- Connected with high-bandwidth, low latency networking

## How to choose a region?

- Compliance (data governance/legal requirements)
  - data never leaves a region without explicit permission
- Proximity to customers
  - reduced latency when using region that's closer to customer base
- Not all service are available in each region
- Pricing
