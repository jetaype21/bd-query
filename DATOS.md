## TABLA INDEPENDIENTES

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

---

_Personas_

### Tabla generos

| genero_id | genero_nombre | genero_abreviatura |
| --------- | ------------- | ------------------ |
| 1         | Masculino     | M                  |
| 2         | Femenino      | F                  |

```
  INSERT INTO generos VALUES
  (default, 'Masculino', 'M'),
  (default, 'Femenino', 'F');

  SELECT * FROM generos;
```

### Tipos personas

| tipo_persona_id | tipo_persona_nombre |
| --------------- | ------------------- |
| 1               | 'Paciente'          |
| 2               | 'Médico'            |

```
  INSERT INTO tipos_personas VALUES
  (default, 'Paciente'),
  (default, 'Médico');

  SELECT * FROM tipos_personas;
```

---

_Medicamentos_

### Marcas

> _INFO_ _[marcas top](https://consultorsalud.com/top-10-companias-farmaceuticas-mas-grandes-2019-a-nivel-mundial/)_

| marca_id | marca_nombre            |
| -------- | ----------------------- |
| 1        | Pfizer                  |
| 2        | Lilly                   |
| 3        | Roche                   |
| 4        | Merck                   |
| 5        | Novartis                |
| 6        | Sanofi                  |
| 7        | GSK                     |
| 8        | Abbott Laboratories     |
| 9        | Bayer                   |
| 10       | AstraZeneca             |
| 11       | Teva                    |
| 12       | Bristol-Myers Squibb    |
| 13       | Boehringer Ingelheim    |
| 14       | Johnson & Johnson       |
| 15       | Amgen                   |
| 16       | Gilead Sciences         |
| 17       | Biogen                  |
| 18       | Celgene                 |
| 19       | Allergan                |
| 20       | Alexion Pharmaceuticals |

```
  INSERT INTO marcas VALUES
  (default, 'Pfizer'),
  (default, 'Lilly'),
  (default, 'Roche'),
  (default, 'Merck'),
  (default, 'Novartis'),
  (default, 'Sanofi'),
  (default, 'GSK'),
  (default, 'Abbott Laboratories'),
  (default, 'Bayer'),
  (default, 'AstraZeneca'),
  (default, 'Teva'),
  (default, 'Bristol-Myers Squibb'),
  (default, 'Boehringer Ingelheim'),
  (default, 'Johnson & Johnson'),
  (default, 'Amgen'),
  (default, 'Gilead Sciences'),
  (default, 'Biogen'),
  (default, 'Celgene'),
  (default, 'Allergan'),
  (default, 'Alexion Pharmaceuticals');

  SELECT * FROM marcas;
```

### Tipos medicamentos

> _*INFO*_ _[TIPOS DE MEDICAMENTOS](https://www.genfar.com/te-cuidamos/aprende-sobre-el-uso-racional-de-los-diferentes-tipos-de-medicamentos/)_

| tipo_medicamento_id | tipo_medicamento_nombre | tipo_medicamento_descripcion                                                                    |                               |
| ------------------- | ----------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------- |
| 1                   | Analgésicos             | Medicamentos para aliviar el dolor, como el paracetamol, el ibuprofeno o la aspirina.           |
| 2                   | Antidepresivos          | Medicamentos para tratar la depresión, como la fluoxetina o la sertralina.                      |
| 3                   | Antibióticos            | Medicamentos para tratar las infecciones bacterianas, como la amoxicilina o la penicilina.      |
| 4                   | Antiinflamatorios       | Medicamentos para reducir la inflamación, como el naproxeno o el diclofenaco.                   |
| 5                   | Antihistamínicos        | Medicamentos para tratar las alergias, como la loratadina o la cetirizina.                      |
| 6                   | Antipsicóticos          | Medicamentos para tratar la esquizofrenia y otros trastornos psiquiátricos, como la             | risperidona o el haloperidol. |
| 7                   | Antiulcerosos           | Medicamentos para tratar las úlceras estomacales, como el omeprazol o la ranitidina.            |
| 8                   | Hipnóticos              | y sedantes Medicamentos para ayudar a dormir o para reducir la ansiedad, como el lorazepam o el | diazepam.                     |
| 9                   | Inmunosupresores        | Medicamentos para suprimir el sistema inmunológico, como la ciclosporina o el tacrolimus.       |
| 10                  | Vasodilatadores         | Medicamentos para ensanchar los vasos sanguíneos, como el nitroglicerina o el diltiazem.        |

```
  INSERT INTO tipos_medicamentos VALUES
    (default, 'Analgésicos', 'Medicamentos para aliviar el dolor, como el paracetamol, el ibuprofeno o la aspirina.'),
    (default, 'Antidepresivos', 'Medicamentos para tratar la depresión, como la fluoxetina o la sertralina.'),
    (default, 'Antibióticos', 'Medicamentos para tratar las infecciones bacterianas, como la amoxicilina o la penicilina.'),
    (default, 'Antiinflamatorios', 'Medicamentos para reducir la inflamación, como el naproxeno o el diclofenaco.'),
    (default, 'Antihistamínicos', 'Medicamentos para tratar las alergias, como la loratadina o la cetirizina.'),
    (default, 'Antipsicóticos', 'Medicamentos para tratar la esquizofrenia y otros trastornos psiquiátricos, como la risperidona o el haloperidol.'),
    (default, 'Antiulcerosos', 'Medicamentos para tratar las úlceras estomacales, como el omeprazol o la ranitidina.'),
    (default, 'Hipnóticos y sedantes', 'Medicamentos para ayudar a dormir o para reducir la ansiedad, como el lorazepam o el diazepam.'),
    (default, 'Inmunosupresores', 'Medicamentos para suprimir el sistema inmunológico, como la ciclosporina o el tacrolimus.'),
    (default, 'Vasodilatadores', 'Medicamentos para ensanchar los vasos sanguíneos, como el nitroglicerina o el diltiazem.');

    SELECT * FROM tipos_medicamentos;
```
