# neo4j-aura-go-cli

draft notes:

Command to set credentials
```bash

./neo4j-cli aura credential add --name "AuraDev1" --client-id AURA_CLIENT_ID --client-secret YOUR_AURA_CLIENT_SECRET
```


Command to state which credential (by name) to use:
```bash
./cli-binary aura credential use "AuraDev1"
```

Command to remove credential by name:
```bash
./cli-binary aura credential remove "CORRECT Aura API Credentials"
```