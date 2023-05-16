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

### mostrar recetados

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

### mostrar medicamentos

```
  CREATE VIEW vista_medicamentos AS SELECT
    me.medicamento_id,
    me.medicamento_nombre,
    me.medicamento_stock,
    me.medicamento_vencimiento,
    ma.marca_nombre,
    tm.tipo_medicamento_nombre,
    pm.porcion_medicamento_nombre,
    me.medicamento_precio
  from medicamentos me
  INNER JOIN marcas ma ON me.marca_id = ma.marca_id
  INNER JOIN tipos_medicamentos tm ON me.tipo_medicamento_id = tm.tipo_medicamento_id
  INNER JOIN porciones_medicamentos pm ON me.porcion_medicamento_id = pm.porcion_medicamento_id;

  select * from vista_medicamentos;
```

### receta_detalles

```
  create view vista_receta_detalles AS SELECT rd.receta_detalle_id, vr.receta_id , vr.paciente, vr.medico, es.estado_nombre, vm.*  FROM receta_detalles rd
    INNER JOIN estados es ON rd.estado_id = es.estado_id
    INNER JOIN vista_recetas vr ON rd.receta_id = vr.receta_id
    INNER JOIN vista_medicamentos vm ON rd.medicamento_id = vm.medicamento_id;

    select *  from vista_receta_detalles;
```

### notificaciones

```
  noti.notificacion_id, vrd.receta_id, vrd.receta_detalle_id, noti.notificacion_fecha ||' '|| noti.notificacion_hora notificacion, noti.notificacion_confirmada, es.estado_nombre, vrd.medicamento_nombre, vrd.paciente, vrd.medico FROM notificaciones noti
      INNER JOIN vista_receta_detalles vrd ON noti.receta_detalle_id = vrd.receta_detalle_id
      INNER JOIN estados es ON noti.estado_id = es.estado_id
```
