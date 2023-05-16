### mostrar tipos de citas

```
  SELECT tipo_cita_id, tipo_cita_nombre FROM tipos_citas;
```

### mostrar estados

```
  SELECT estado_id, estado_nombre FROM estados;
```

### mostrar pacientes

```
  -- paciente_id = 1

    CREATE VIEW vista_pacientes AS SELECT
      per.persona_id, per.persona_nombre || ' ' || per.persona_apellido paciente, per.persona_telefono, per.persona_email, per.persona_edad, tp.tipo_persona_nombre
    FROM (select * from personas where tipo_persona_id = 1) per
    INNER JOIN tipos_personas tp ON tp.tipo_persona_id = per.tipo_persona_id
    INNER JOIN generos ge ON per.genero_id = ge.genero_id;

    select * from vista_pacientes;
```

### mostrar medicos

```
  -- medico_id = 2

    CREATE VIEW vista_medicos AS SELECT
      per.persona_id, per.persona_nombre || ' ' || per.persona_apellido medico, per.persona_telefono, per.persona_email, per.persona_edad, tp.tipo_persona_nombre
    FROM (select * from personas where tipo_persona_id = 2) per
    INNER JOIN tipos_personas tp ON tp.tipo_persona_id = per.tipo_persona_id
    INNER JOIN generos ge ON per.genero_id = ge.genero_id;

    select * from vista_medicos;
```

### mostrar citas

```

  CREATE VIEW vista_citas AS SELECT
    rcitas.cita_id,
    rcitas.persona_nombre || ' '|| rcitas.persona_apellido paciente,
    rcitas.persona_telefono "paciente telf",
    rcitas.genero_nombre "paciente genero",
    per.persona_nombre || ' '|| per.persona_apellido medico,
    per.persona_telefono "medico telf",
    ge.genero_nombre "medico genero",
    rcitas.estado_nombre "estado cita",
    rcitas.tipo_cita_nombre "tipo cita",
    rcitas.cita_hora "hora cita",
    rcitas.cita_fecha "fecha cita"
    FROM (
    SELECT *
        FROM citas ci
        INNER JOIN estados es ON ci.estado_id = es.estado_id
        INNER JOIN tipos_citas tc ON ci.tipo_cita_id = tc.tipo_cita_id
        INNER JOIN personas per ON ci.paciente_id = per.persona_id
        INNER JOIN generos ge ON per.genero_id = ge.genero_id
    ) rcitas
    INNER JOIN personas per ON rcitas.doctor_id = per.persona_id
    INNER JOIN generos ge ON ge.genero_id = per.genero_id;

  SELECT * FROM vista_citas;
```

### mostrar recaetados

```

  CREATE VIEW vista_recetas AS SELECT
		re.receta_id,
		vc.*,
		es.estado_nombre "receta estado"
	FROM recetas re
	INNER JOIN vista_citas vc ON re.cita_id = vc.cita_id
	INNER JOIN estados es ON es.estado_id = re.estado_id;

  select * from vista_recetas;
```
