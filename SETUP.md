# Diet Support Application Setup

## Prerequisites
- Docker and Docker Compose installed
- Git

## Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd diet-support
   ```

2. **Create required secret files**
   Create a `secrets/` directory and add the following files:
   
   ```bash
   mkdir -p secrets
   echo "dev_admin" > secrets/postgres_user.txt
   echo "your_secure_password" > secrets/postgres_password.txt
   echo "admin@example.com" > secrets/pgadmin_email.txt
   echo "your_pgadmin_password" > secrets/pgadmin_password.txt
   echo "postgresql://dev_admin:your_secure_password@postgres:5432/diet_support_db" > secrets/database_url.txt
   ```

   **Note**: Replace `your_secure_password` and `your_pgadmin_password` with your own secure passwords.

3. **Start the application**
   ```bash
   docker-compose up -d
   ```

4. **Access the services**
   - **Frontend**: http://localhost:4200
   - **API**: http://localhost:3333/api
   - **PgAdmin**: http://localhost:8080
   - **Database**: localhost:5432

## Service Details

### Database
- **Type**: PostgreSQL 15
- **Database**: `diet_support_db`
- **Port**: 5432
- **Tables**: `users`, `diet_plans`

### PgAdmin
- **URL**: http://localhost:8080
- **Login**: Use email/password from `secrets/pgadmin_email.txt` and `secrets/pgadmin_password.txt`

## Stopping the Application
```bash
docker-compose down
```

## Reset Database (remove all data)
```bash
docker-compose down -v
docker-compose up -d
```