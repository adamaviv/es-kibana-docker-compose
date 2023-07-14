# Simple Ealstic Search / Kibana Docker Compose Setup

Cone this repo to the location you want to run elastic search and kibana

1. Bring up the service

   ```
   docker compose up -d
   ```

2. Reset elastic search password (save this!)

   ```
   docker compose exec elasticsearch /usr/share/elasticsearch/bin/elasticsearch-reset-password -u elastic
   ```

3. Generate a kibana access token 

   ```
   docker compose  exec elasticsearch /usr/share/elasticsearch/bin/elasticsearch-create-enrollment-token -s kibana
   ```
   
4. Go to https://locahost:5601 and paste in the enrollment token

5. You'll be prompted for a verification code, which you can get via


   ```
   docker compose exec kibana bin/kibana-verification-code
   ```

6. Log into Kimbana with username `elastic` and the password from step 2
