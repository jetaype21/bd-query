# CREACION DE TABLAS

## Tablas independientes

---

_Personas_

### Generos

```
  CREATE TABLE generos (
	    genero_id SERIAL PRIMARY KEY NOT NULL,
	    genero_nombre VARCHAR(10) NOT NULL,
	    genero_abreviatura CHAR(1) NOT NULL
  );

  SELECT * FROM generos;
```

### Tipo personas

```
  CREATE TABLE tipos_personas (
    tipo_persona_id SERIAL PRIMARY KEY NOT NULL,
    tipo_persona_nombre VARCHAR(25) NOT NULL
  );

  SELECT * FROM tipos_personas;
```

---

_Medicamentos_

### MARCAS

```
  CREATE TABLE marcas (
    marca_id SERIAL PRIMARY KEY NOT NULL,
    marca_nombre VARCHAR(25) NOT NULL UNIQUE
  );

  SELECT * FROM marcas;
```

### Tipos medicamentos

```
  CREATE TABLE tipos_medicamentos(
    tipo_medicamento_id SERIAL PRIMARY KEY NOT NULL,
    tipo_medicamento_nombre VARCHAR(20) NOT NULL,
    tipo_medicamento_descripcion VARCHAR(150) NOT NULL
  );

  SELECT * FROM tipos_medicamentos;
```
