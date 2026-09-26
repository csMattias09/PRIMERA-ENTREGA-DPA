# X-Chang — Despliegue local (Entrega 1 DPA)

Repositorio de orquestacion del proyecto X-Chang (intercambio de divisas). Contiene
el `docker-compose.yml` y referencia al backend y frontend como **git submodules**,
cada uno con su propio `Dockerfile` (contenedores separados).

- Backend: [exchange-divisas-DAW2026](https://github.com/csMattias09/exchange-divisas-DAW2026) (.NET 9 + PostgreSQL/Supabase)
- Frontend: [intercambio_Divisas_Front_Web](https://github.com/csMattias09/intercambio_Divisas_Front_Web) (Quasar/Vue 3)
- Base de datos: PostgreSQL gestionado en **Supabase Cloud** (no se levanta contenedor de BD local)

## Requisitos

- Docker Desktop
- Credenciales de la base de datos de Supabase del proyecto (pedirlas al equipo)

## Pasos para levantar el proyecto desde cero

```bash
git clone --recurse-submodules https://github.com/csMattias09/PRIMERA-ENTREGA-DPA.git
cd PRIMERA-ENTREGA-DPA
cp .env.example .env
# completar .env con la cadena de conexion real a Supabase y demas claves
docker compose up --build
```

- Frontend: http://localhost:9200
- Backend (API): http://localhost:5198/api
- Health check backend: http://localhost:5198/health

Si ya se clono el repo sin `--recurse-submodules`, ejecutar:

```bash
git submodule update --init --recursive
```

## Actualizar los submodulos a la ultima version de cada repo

```bash
git submodule update --remote --merge
git add backend frontend
git commit -m "Update submodules"
```
