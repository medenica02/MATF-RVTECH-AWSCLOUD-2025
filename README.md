# EV Punjači - LocalStack Projekat

Ovaj projekat je **Serverless Fullstack** aplikacija koja omogucava pretragu stanica za punjenje elektricnih automobila. Sistem koristi **AWS Cloud** servise (Lambda, DynamoDB, S3) koji se simuliraju lokalno pomocu **LocalStack** alata.

## Preduslovi

Neophodno je instalirati sledece alate:

* **Docker & Docker Compose**: Za pokretanje LocalStack-a.
* **Node.js (v18+) & npm**: Za pokretanje JavaScript koda.
* **AWS CLI v2**: Za komunikaciju sa cloud servisima.
* **Serverless Framework**: Instaliraj globalno komandom:
    ```bash
    npm install -g serverless
    ```

---

## Pokretanje:

Ukoliko postoje aktivni docker kontejneri zaustaviti ih.

### 1. Pokreni infrastrukturu: 
    docker compose up -d

### 2. Podesavanje API kljuca
Kreiraj .env fajl u korenu projekta. Zatim dodaj svoj kljuc sa portala Open Charge Map u .env fajl:

    OCM_API_KEY=tvoj_api_kljuc_ovde
### 3. Backend deploy: 
    npm install
 
    npx serverless deploy
### 4. API_ID:  
Nakon uspesnog deploy-a u terminalu ce se pojaviti sledeci endpoint:

    http://localhost:4566/restapis/tvoj_api_id/dev/_user_request_

Neophodno je da u fajlu index.html za API_ID stavimo vrednost koja se nalazi u linku.
### 7. Frontend deploy: 
    npm run deploy-frontend-fixed-bucket
### 8. Pristup aplikaciji: 
**http://punjaci-website.s3-website.localhost.localstack.cloud:4566/**