# Real-Time Crypto Data Ingestion Pipeline (Apache NiFi)

A production-ready data engineering pipeline built with **Apache NiFi** that automates real-time data ingestion, transformation, and structural flattening of live cryptocurrency financial metrics.

## Pipeline Architecture
1. **Ingestion (`InvokeHTTP`)**: Queries the public CoinGecko REST API every 60 seconds to fetch live market prices for Bitcoin (BTC) and Ethereum (ETH).
2. **Extraction (`EvaluateJsonPath`)**: Parses the raw, multi-layered nested JSON payload using JSONPath expressions to isolate specific target variables.
3. **Transformation (`AttributesToJSON`)**: Flattens the extracted flowfile attributes, creating a new, highly optimized flat JSON payload.
4. **Target Sink (`LogAttribute`)**: Routes the structured payloads to standard output logs for ingestion by downstream analytics engines.

##  Repository Structure
* `README.md` - Project documentation and setup guide.
* `crypto_nifi_pipeline.json` - The complete, importable NiFi Flow Definition file.

##  Setup & Deployment Instructions
1. Download the `crypto_nifi_pipeline.json` file from this repository.
2. Open your local or cloud-hosted **Apache NiFi Canvas UI**.
3. Right-click on an empty space on the canvas or use the global menu and select **Upload Flow Definition** (or drag a **Process Group** component onto the canvas and select "Upload definition").
4. Upload `crypto_nifi_pipeline.json`.
5. Start the components by right-clicking the process group and selecting **Start**.
