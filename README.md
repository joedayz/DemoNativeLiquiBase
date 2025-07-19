# GraalVM Liquibase Gradle REST API

Este proyecto es una API REST con Spring Boot, Java 17, Liquibase y H2 Database.

## Características

- Java 17
- Spring Boot 3.3.0
- Liquibase para migraciones de base de datos
- H2 Database en memoria
- API REST completa para gestión de personas
- Datos de prueba cargados automáticamente

## Cómo ejecutar

### Requisitos
- Java 17 o superior
- Gradle

### Ejecutar la aplicación
```bash
./gradlew bootRun
```

La aplicación se ejecutará en `http://localhost:8080`

## Endpoints de la API

### Obtener todas las personas
```
GET /api/persons
```

### Obtener una persona por ID
```
GET /api/persons/{id}
```

### Crear una nueva persona
```
POST /api/persons
Content-Type: application/json

{
  "name": "Nuevo Usuario"
}
```

### Actualizar una persona
```
PUT /api/persons/{id}
Content-Type: application/json

{
  "name": "Usuario Actualizado"
}
```

### Eliminar una persona
```
DELETE /api/persons/{id}
```

### Health check
```
GET /api/persons/health
```

## Base de datos

- **H2 Console**: http://localhost:8080/h2-console
- **JDBC URL**: `jdbc:h2:mem:testdb`
- **Usuario**: `sa`
- **Contraseña**: (vacía)

## Datos de prueba

La aplicación carga automáticamente 10 personas de prueba desde `src/main/resources/data.sql`.

## Ejemplos de uso con curl

### Obtener todas las personas
```bash
curl http://localhost:8080/api/persons
```

### Crear una nueva persona
```bash
curl -X POST http://localhost:8080/api/persons \
  -H "Content-Type: application/json" \
  -d '{"name": "Nuevo Usuario"}'
```

### Obtener una persona específica
```bash
curl http://localhost:8080/api/persons/1
```

### Actualizar una persona
```bash
curl -X PUT http://localhost:8080/api/persons/1 \
  -H "Content-Type: application/json" \
  -d '{"name": "Usuario Modificado"}'
```

### Eliminar una persona
```bash
curl -X DELETE http://localhost:8080/api/persons/1
``` 