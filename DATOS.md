## TABLA GENERALDFG

### Tabla estados

| estado_id | estado_nombre | estado_descripcion                           |
| --------- | ------------- | -------------------------------------------- |
| 1         | pendiente     | la actividad aun no se a iniciado            |
| 2         | en curso      | la actividad esta en proceso                 |
| 3         | completado    | la actividad ah sido completado exitosamente |
| 4         | completado    | la actividad ah sido no ah sido completado   |

> Codigo sql

```
  INSERT INTO estados VALUES(
    default,
    'pendiente',
    'la actividad aun no se a iniciado'
  ),
  (
    default,
    'en curso',
    'la actividad esta en proceso'
  ),
  (
    default,
    'completado',
    'la actividad ah sido completado exitosamente'
  ),
  (
    default,
    'completado',
    'la actividad ah sido no ah sido completado'
  );

  SELECT * FROM estados;
```
