# PresidioTesting
Testing project Presidio

1. Download Docker

docker pull mcr.microsoft.com/presidio-analyzer

docker pull mcr.microsoft.com/presidio-anonymizer

# Run containers with default ports

docker run -d -p 5001:3000 mcr.microsoft.com/presidio-analyzer:latest

docker run -d -p 5002:3000 mcr.microsoft.com/presidio-anonymizer:latest


curl -X POST http://localhost:5002/anonymize -H "Content-type: application/json" --data "{\"text\": \"hello world, my name is Jane Doe.\", \"analyzer_results\": [{\"start\": 1, \"end\": 32, \"score\": 0.8, \"entity_type\": \"NAME\"}], \"anonymizers\": {\"DEFAULT\": { \"type\": \"hash\", \"new_value\": \"BIP\" }}}"


2. Outside Docker


pip install presidio_analyzer

pip install presidio_anonymizer

python -m spacy download en_core_web_lg