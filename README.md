# _Indice_

|Referencias bibliográfica| enlace|
|-| -|		
|Marcas de medicamentos| https://consultorsalud.com/top-10-companias-farmaceuticas-mas-grandes-2019-a-nivel-mundial/|
|Tipos de medicamentos| https://www.genfar.com/te-cuidamos/aprende-sobre-el-uso-racional-de-los-diferentes-tipos-de-medicamentos/|
|Generador de nombres random| https://fossbytes.com/tools/random-name-generator|
|Tipos de porciones| https://medlineplus.gov/spanish/ency/patientinstructions/000337.htm|


1. [Creacion de tablas](#creacion-de-tablas)
1. [Tablas independiente](#tablas-independientes)

   - [estados](#estados)
   - [generos](#generos)
   - [tipos personas](#tipos-personas)
   - [marcas](#marcas)
   - [tipos medicamentos](#tipos-medicamentos)
   - [tipos porciones](#porciones-medicamentos)
   - [tipos citas](#tipos-citas)

1. [Tablas relacionadas](#tablas-relacionadas)
   - [personas](#tabla-personas)
   - [medicamentos](#tabla-medicamentos)
   - [citas](#tabla-citas)
   - [recetas](#tabla-recetas)
   - [recetas detalles](#tabla-receta-detalles)
   - [notificaciones](#tabla-notificaciones)

# CREACION DE TABLAS

## Tablas independientes

---

### Estados

```
  CREATE TABLE estados(
    estado_id SERIAL PRIMARY KEY NOT NULL,
    estado_nombre VARCHAR(25) NOT NULL,
    estado_descripcion VARCHAR(150) NOT NULL
  );

  SELECT * FROM estados;
```

---

> _NOTA: ANTES DE CONTINUAR IR A [estados data](./DATOS.md#tabla-estados) y ejecutar el codigo de insercción de datos_

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

### Tipos personas

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
    tipo_medicamento_nombre VARCHAR(40) NOT NULL,
    tipo_medicamento_descripcion VARCHAR(150) NOT NULL
  );

  SELECT * FROM tipos_medicamentos;
```

### Porciones medicamentos

```
  CREATE TABLE porciones_medicamentos(
    porcion_medicamento_id SERIAL PRIMARY KEY NOT NULL,
    porcion_medicamento_nombre VARCHAR(30) NOT NULL,
    porcion_medicamento_descripcion VARCHAR(255) NOT NULL
  );

  SELECT * FROM porciones_medicamentos;
```

---

_Citas_

### Tipos citas

```
  CREATE TABLE tipos_citas (
    tipo_cita_id SERIAL PRIMARY KEY NOT NULL,
    tipo_cita_nombre VARCHAR(60) NOT NULL
  );

  SELECT * FROM tipos_citas;
```

---

## Tablas relacionadas

_Personas_

### Tabla personas

```
  CREATE TABLE personas(
    persona_id SERIAL PRIMARY KEY NOT NULL,
    persona_nombre VARCHAR(60),
    persona_apellido VARCHAR(60),
    persona_dni CHAR(8) NOT NULL UNIQUE,
    persona_email VARCHAR(50) UNIQUE DEFAULT NULL,
    persona_telefono CHAR(9) NOT NULL UNIQUE,
    persona_edad INT NOT NULL,
    tipo_persona_id INT NOT NULL REFERENCES tipos_personas(tipo_persona_id),
    genero_id INT NOT NULL REFERENCES generos(genero_id)
  );

  SELECT * FROM personas;
```

---

_Medicamentos_

### Tabla medicamentos

```
  CREATE TABLE medicamentos (
    medicamento_id SERIAL PRIMARY KEY NOT NULL,
    medicamento_nombre VARCHAR(50) NOT NULL,
    medicamento_stock INT NOT NULL,
    medicamento_vencimiento TIMESTAMP NOT NULL,
    marca_id INT NOT NULL REFERENCES marcas(marca_id),
    tipo_medicamento_id INT NOT NULL REFERENCES tipos_medicamentos(tipo_medicamento_id),
    porcion_medicamento_id INT REFERENCES porciones_medicamentos(porcion_medicamento_id),
    medicamento_precio DECIMAL(6, 2) NOT NULL
  );

  SELECT * FROM medicamentos;
```

---

_Citas_

### Tabla citas

```
  CREATE TABLE citas(
    cita_id SERIAL PRIMARY KEY NOT NULL,
    cita_hora TIME NOT NULL,
    cita_fecha DATE NOT NULL,
    estado_id INT NOT NULL DEFAULT 1  REFERENCES estados(estado_id),
    tipo_cita_id INT NOT NULL REFERENCES tipos_citas(tipo_cita_id),
    doctor_id INT NOT NULL REFERENCES personas(persona_id),
    paciente_id INT NOT NULL REFERENCES personas(persona_id)
  );

  SELECT * FROM citas;
```

---

_Recetas_

### Tabla recetas

```
  CREATE TABLE recetas(
    receta_id SERIAL PRIMARY KEY NOT NULL,
    receta_precio_subtotal DECIMAL(6, 2) DEFAULT 0.00,
    receta_precio_total DECIMAL(6, 2) DEFAULT 0.00,
    estado_id INT NOT NULL DEFAULT 1 REFERENCES estados(estado_id) ,
    cita_id INT NOT NULL UNIQUE REFERENCES citas(cita_id)
  );

  SELECT * FROM recetas;
```

### Tabla receta detalles

```
  CREATE TABLE receta_detalles (
    receta_detalle_id SERIAL PRIMARY KEY,
    medicamento_num_notificaciones INT DEFAULT 1,
    medicamento_intervalo_notificaciones INTERVAL DEFAULT '8 hours',
    medicamento_receta_creado TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    estado_id INT NOT NULL DEFAULT 1 REFERENCES estados(estado_id),
    receta_id INT NOT NULL REFERENCES recetas(receta_id),
    medicamento_id INT NOT NULL REFERENCES medicamentos(medicamento_id),
    medicamento_cantidad INT DEFAULT 1
  );

  SELECT * FROM receta_detalles;
```

### TABLA notificaciones

```
  CREATE TABLE notificaciones (
    notificacion_id SERIAL NOT NULL PRIMARY KEY,
    notificacion_fecha DATE NOT NULL,
    notificacion_hora TIME NOT NULL,
    notificacion_confirmada TIMESTAMP DEFAULT NULL,
    estado_id INT NOT NULL DEFAULT 1 REFERENCES estados(estado_id) ,
    receta_detalle_id INT NOT NULL REFERENCES receta_detalles(receta_detalle_id)
  );

  SELECT * FROM notificaciones;
```
