# INDICE

- [tablas independientes](#tabla-independientes)
  - [tabla estados](#tabla-estados)
  - [tablas generos](#tabla-generos)
  - [tablas tipos personas](#tabla-tipos-personas)
  - [tablas marcas](#tabla-marcas)
  - [tablas tipos_medicamentos](#tabla-tipos-medicamentos)
  - [tablas porciones medicamentos](#tabla-porciones-medicamentos)
  - [tablas tipos citas](#tabla-tipos-citas)

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

### Tabla tipos personas

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

### Tabla marcas

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

### Tabla tipos medicamentos

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

### Tabla porciones medicamentos

| porcion_medicamento_id | porcion_medicamento_nombre | porcion_medicamento_descripcion |
| ---------------------- | -------------------------- | ------------------------------- |
| 1                      | "50 ml"                    | "Porción medida en 50 ml"       |
| 2                      | "75 ml"                    | "Porción medida en 75 ml"       |
| 3                      | "100 ml"                   | "Porción medida en 100 ml"      |
| 4                      | "200 ml"                   | "Porción medida en 200 ml"      |
| 5                      | "250 ml"                   | "Porción medida en 250 ml"      |
| 6                      | "300 ml"                   | "Porción medida en 300 ml"      |
| 7                      | "400 ml"                   | "Porción medida en 400 ml"      |
| 8                      | "500 ml"                   | "Porción medida en 500 ml"      |
| 9                      | "1000 ml"                  | "Porción medida en 1000 ml"     |
| 10                     | "1 unidad"                 | "Porción medida en unidad"      |

```
  INSERT INTO porciones_medicamentos VALUES
    (default, '50 ml', 'Porción medida en 50 ml'),
    (default, '75 ml', 'Porción medida en 75 ml'),
    (default, '100 ml', 'Porción medida en 100 ml'),
    (default, '200 ml', 'Porción medida en 200 ml'),
    (default, '250 ml', 'Porción medida en 250 ml'),
    (default, '300 ml', 'Porción medida en 300 ml'),
    (default, '400 ml', 'Porción medida en 400 ml'),
    (default, '500 ml', 'Porción medida en 500 ml'),
    (default, '1000 ml', 'Porción medida en 1000 ml'),
    (default, '1 unidad', 'Porción medida en unidad'),
    (default, '50 mg', 'Porción medida en 50 mg'),
    (default, '75 mg', 'Porción medida en 75 mg'),
    (default, '100 mg', 'Porción medida en 100 mg'),
    (default, '200 mg', 'Porción medida en 200 mg'),
    (default, '250 mg', 'Porción medida en 250 mg'),
    (default, '300 mg', 'Porción medida en 300 mg'),
    (default, '400 mg', 'Porción medida en 400 mg'),
    (default, '500 mg', 'Porción medida en 500 mg'),
    (default, '1000 mg', 'Porción medida en 1000 mg');

  SELECT * FROM porciones_medicamentos;
```

---

_Citas_

### Tabla tipos citas

| tipo_cita_id | tipo_cita_nombre                    |
| ------------ | ----------------------------------- |
| 1            | "Cita virtual - llamada telefónico" |
| 2            | "Cita virtual - videoconferencia"   |
| 3            | "Cita virtual - correo electrónico" |
| 4            | "Cita presencial"                   |

```
  INSERT INTO tipos_citas VALUES
    (default, 'Cita virtual - llamada telefónico'),
    (default, 'Cita virtual - videoconferencia'),
    (default, 'Cita virtual - correo electrónico'),
    (default, 'Cita presencial');

  SELECT * FROM tipos_citas;
```

---

## TABLAS RELACIONADAS

### Tabla personas

> _usar esta página [nombres random](https://fossbytes.com/tools/random-name-generator)_

| persona_id | persona_nombre | persona_apellido | persona_dni | persona_email                  | persona_telefono | persona_edad | tipo_persona_id | genero_id |
| ---------- | -------------- | ---------------- | ----------- | ------------------------------ | ---------------- | ------------ | --------------- | --------- |
| 1          | "María"        | "González"       | "12345678"  | "maria.gonzalez@gmail.com"     | "912345678"      | 25           | 2               | 2         |
| 2          | "Juan"         | "Pérez"          | "23456789"  | "juan.perez@hotmail.com"       | "923456789"      | 30           | 2               | 1         |
| 3          | "Ana"          | "Martínez"       | "34567890"  | "ana.martinez@yahoo.com"       | "934567890"      | 45           | 2               | 2         |
| 4          | "Pedro"        | "Sánchez"        | "45678901"  | NULL                           | "945678901"      | 18           | 2               | 1         |
| 5          | "Lucía"        | "López"          | "56789012"  | "lucia.lopez@outlook.com"      | "956789012"      | 60           | 2               | 2         |
| 6          | "Jorge"        | "García"         | "67890123"  | NULL                           | "967890123"      | 40           | 2               | 1         |
| 7          | "Sofía"        | "Fernández"      | "78901234"  | "sofia.fernandez@gmail.com"    | "978901234"      | 28           | 2               | 2         |
| 8          | "Miguel"       | "Romero"         | "89012345"  | NULL                           | "989012345"      | 50           | 2               | 1         |
| 9          | "Carla"        | "Jiménez"        | "90123456"  | "carla.jimenez@hotmail.com"    | "990123456"      | 23           | 2               | 2         |
| 10         | "David"        | "Gutiérrez"      | "01234567"  | NULL                           | "901234567"      | 33           | 2               | 1         |
| 11         | "Laura"        | "Ruiz"           | "12345670"  | "laura.ruiz@yahoo.com"         | "912345670"      | 48           | 2               | 2         |
| 12         | "Gabriel"      | "Gómez"          | "23456701"  | "gabriel.gomez@gmail.com"      | "923456701"      | 19           | 2               | 1         |
| 13         | "Carmen"       | "Sanz"           | "34567812"  | NULL                           | "934567812"      | 39           | 2               | 2         |
| 14         | "Daniel"       | "Castillo"       | "45678923"  | "daniel.castillo@hotmail.com"  | "945678923"      | 29           | 2               | 1         |
| 15         | "Alicia"       | "Moreno"         | "56789034"  | "alicia.moreno@outlook.com"    | "956789034"      | 42           | 2               | 2         |
| 16         | "Pablo"        | "Álvarez"        | "67890145"  | NULL                           | "967890145"      | 21           | 1               | 1         |
| 17         | "Beatriz"      | "Gallardo"       | "78901256"  | "beatriz.gallardo@yahoo.com"   | "978901256"      | 37           | 1               | 2         |
| 18         | "Rafael"       | "Muñoz"          | "89012367"  | NULL                           | "989012367"      | 55           | 1               | 1         |
| 19         | "Elena"        | "Vega"           | "90123478"  | "elena.vega@gmail.com"         | "990123478"      | 27           | 1               | 2         |
| 20         | "Alejandro"    | "Ramos"          | "01234589"  | "alejandro.ramos@hotmail.com"  | "901234589"      | 31           | 1               | 1         |
| 21         | "Isabel"       | "Hernández"      | "12345690"  | "isabel.hernandez@outlook.com" | "912345690"      | 47           | 1               | 2         |
| 22         | "Rosa"         | "Vidal"          | "34567803"  | "rosa.vidal@gmail.com"         | "934567803"      | 41           | 1               | 2         |
| 23         | "Javier"       | "Aguilar"        | "42678934"  | NULL                           | "942678934"      | 36           | 1               | 1         |
| 24         | "Marina"       | "Blanco"         | "56789345"  | "marina.blanco@hotmail.com"    | "956789345"      | 22           | 1               | 2         |
| 25         | "Francisco"    | "Moya"           | "67890146"  | NULL                           | "967890146"      | 52           | 1               | 1         |
| 26         | "Marisol"      | "Herrera"        | "28901267"  | "marisol.herrera@yahoo.com"    | "928901267"      | 43           | 1               | 2         |
| 27         | "Diego"        | "Santos"         | "89042378"  | NULL                           | "989042378"      | 32           | 1               | 1         |
| 28         | "Aurora"       | "Ortega"         | "90123989"  | "aurora.ortega@gmail.com"      | "990123989"      | 58           | 1               | 2         |
| 29         | "Emilio"       | "Nieto"          | "01233590"  | "emilio.nieto@hotmail.com"     | "901233590"      | 24           | 1               | 1         |
| 30         | "Esther"       | "Cabrera"        | "12345621"  | "esther.cabrera@outlook.com"   | "912345621"      | 49           | 1               | 2         |
| 31         | "Andrés"       | "Soto"           | "23456212"  | NULL                           | "923456212"      | 38           | 1               | 1         |
| 32         | "Marta"        | "León"           | "34567813"  | "marta.leon@gmail.com"         | "934567813"      | 35           | 1               | 2         |
| 33         | "Óscar"        | "Márquez"        | "45628934"  | "oscar.marquez@hotmail.com"    | "945628934"      | 30           | 1               | 1         |
| 34         | "Lorena"       | "Gálvez"         | "56729045"  | "lorena.galvez@yahoo.com"      | "956729045"      | 44           | 1               | 2         |
| 35         | "Carlos"       | "Cruz"           | "67860156"  | NULL                           | "967860156"      | 20           | 1               | 1         |
| 36         | "Raquel"       | "Ibáñez"         | "48901267"  | "raquel.ibañez@outlook.com"    | "948901267"      | 46           | 1               | 2         |
| 37         | "Mariano"      | "Rivas"          | "89512378"  | NULL                           | "989512378"      | 54           | 1               | 1         |
| 38         | "Nuria"        | "Sánchez"        | "90123499"  | "nuria.sanchez@gmail.com"      | "990123499"      | 25           | 1               | 2         |
| 39         | "Adrián"       | "García"         | "04234590"  | "adrian.garcia@hotmail.com"    | "904234590"      | 34           | 1               | 1         |
| 40         | "Cristina"     | "Rodríguez"      | "12335601"  | "cristina.rodriguez@yahoo.com" | "912335601"      | 51           | 1               | 2         |
| 41         | "Santiago"     | "González"       | "23426712"  | NULL                           | "923426712"      | 41           | 1               | 1         |
| 42         | "Victoria"     | "Pérez"          | "34567823"  | "victoria.perez@gmail.com"     | "934567823"      | 37           | 1               | 2         |
| 43         | "María"        | "López"          | "53789045"  | "maria.lopez@yahoo.com"        | "953789045"      | 48           | 1               | 2         |
| 44         | "Gustavo"      | "Romero"         | "63890156"  | NULL                           | "963890156"      | 27           | 1               | 1         |
| 45         | "Lucía"        | "Garrido"        | "38901267"  | "lucia.garrido@gmail.com"      | "938901267"      | 33           | 1               | 2         |
| 46         | "Daniel"       | "Fernández"      | "69012378"  | "daniel.fernandez@hotmail.com" | "969012378"      | 42           | 1               | 1         |
| 47         | "Carmen"       | "Moreno"         | "90223489"  | "carmen.moreno@outlook.com"    | "990223489"      | 57           | 1               | 2         |
| 48         | "Juan"         | "Díaz"           | "01232590"  | NULL                           | "901232590"      | 39           | 1               | 1         |
| 49         | "Eva"          | "Álvarez"        | "12345501"  | "eva.alvarez@yahoo.com"        | "912345501"      | 28           | 1               | 2         |
| 50         | "Fernando"     | "Giménez"        | "23356712"  | "fernando.gimenez@gmail.com"   | "923356712"      | 47           | 1               | 1         |
| 51         | "Leticia"      | "Rojas"          | "34567833"  | "leticia.rojas@hotmail.com"    | "934567833"      | 31           | 1               | 2         |
| 52         | "Manuel"       | "Navarro"        | "45673934"  | "manuel.navarro@yahoo.com"     | "945673934"      | 50           | 1               | 1         |
| 53         | "Silvia"       | "Sosa"           | "56783045"  | "silvia.sosa@gmail.com"        | "956783045"      | 23           | 1               | 2         |
| 54         | "Jesús"        | "Jiménez"        | "67890256"  | NULL                           | "967890256"      | 45           | 1               | 1         |
| 55         | "Ana"          | "Benítez"        | "78301267"  | "ana.benitez@hotmail.com"      | "978301267"      | 40           | 1               | 2         |
| 56         | "Rafael"       | "Vargas"         | "82012378"  | "rafael.vargas@outlook.com"    | "982012378"      | 53           | 1               | 1         |
| 57         | "Isabel"       | "Aguirre"        | "90121489"  | "isabel.aguirre@gmail.com"     | "990121489"      | 26           | 1               | 2         |
| 58         | "Pablo"        | "Cano"           | "01234590"  | "pablo.cano@yahoo.com"         | "901234590"      | 37           | 1               | 1         |
| 59         | "Natalia"      | "Castillo"       | "16345601"  | "natalia.castillo@hotmail.com" | "916345601"      | 42           | 1               | 2         |
| 60         | "Antonio"      | "Ruiz"           | "23456512"  | NULL                           | "923456512"      | 31           | 1               | 1         |
| 61         | "Sandra"       | "Sánchez"        | "34567843"  | "sandra.sanchez@gmail.com"     | "934567843"      | 35           | 1               | 2         |
| 62         | "Jorge"        | "González"       | "45675934"  | "jorge.gonzalez@hotmail.com"   | "945675934"      | 49           | 1               | 1         |
| 63         | "Cristina"     | "Hernández"      | "56785045"  | "cristina.hernandez@yahoo.com" | "956785045"      | 29           | 1               | 2         |
| 64         | "David"        | "Gómez"          | "67830156"  | "david.gomez@gmail.com"        | "967830156"      | 25           | 1               | 1         |
| 65         | "José"         | "Pérez"          | "78904267"  | "jose.perez@hotmail.com"       | "978904267"      | 44           | 1               | 1         |
| 66         | "Laura"        | "Muñoz"          | "89011378"  | NULL                           | "989011378"      | 30           | 1               | 2         |
| 67         | "Pedro"        | "Castro"         | "90123482"  | "pedro.castro@gmail.com"       | "990123482"      | 41           | 1               | 1         |
| 68         | "Luisa"        | "Molina"         | "01234593"  | "luisa.molina@yahoo.com"       | "901234593"      | 32           | 1               | 2         |
| 69         | "Mario"        | "Herrera"        | "12344601"  | "mario.herrera@hotmail.com"    | "912344601"      | 36           | 1               | 1         |
| 70         | "Carla"        | "Gutiérrez"      | "43456712"  | "carla.gutierrez@gmail.com"    | "943456712"      | 27           | 1               | 2         |
| 71         | "Emilio"       | "Flores"         | "34567853"  | "emilio.flores@yahoo.com"      | "934567853"      | 52           | 1               | 1         |
| 72         | "Julia"        | "Ortega"         | "55678934"  | "julia.ortega@hotmail.com"     | "955678934"      | 28           | 1               | 2         |
| 73         | "Álvaro"       | "Cabrera"        | "56779045"  | "alvaro.cabrera@gmail.com"     | "956779045"      | 43           | 1               | 1         |
| 74         | "Marta"        | "Montes"         | "47890156"  | "marta.montes@hotmail.com"     | "947890156"      | 39           | 1               | 2         |
| 75         | "Héctor"       | "Reyes"          | "7890126 "  | "hector.reyes@yahoo.com"       | "97890126 "      | 34           | 1               | 1         |
| 76         | "Lucas"        | "Mendez"         | "89012398"  | "lucas.mendez@gmail.com"       | "989012398"      | 25           | 1               | 1         |
| 77         | "Marina"       | "Alonso"         | "90123489"  | "marina.alonso@hotmail.com"    | "990123489"      | 29           | 1               | 2         |
| 78         | "Roberto"      | "Soria"          | "51234590"  | "roberto.soria@yahoo.com"      | "951234590"      | 48           | 1               | 1         |
| 79         | "Ana"          | "Lara"           | "12345601"  | "ana.lara@gmail.com"           | "912345601"      | 50           | 1               | 2         |
| 80         | "Diego"        | "Vera"           | "23456712"  | NULL                           | "923456712"      | 22           | 1               | 1         |
| 81         | "Natalia"      | "Ramos"          | "34567863"  | "natalia.ramos@hotmail.com"    | "934567863"      | 26           | 1               | 2         |
| 82         | "Javier"       | "Vidal"          | "45678934"  | "javier.vidal@yahoo.com"       | "945678934"      | 46           | 1               | 1         |
| 83         | "Raquel"       | "Fuentes"        | "56789045"  | "raquel.fuentes@hotmail.com"   | "956789045"      | 33           | 1               | 2         |
| 84         | "Francisco"    | "Gil"            | "67890156"  | "francisco.gil@gmail.com"      | "967890156"      | 38           | 1               | 1         |
| 85         | "Sara"         | "Rey"            | "7890127 "  | "sara.rey@yahoo.com"           | "97890127 "      | 31           | 1               | 2         |
| 86         | "Joaquín"      | "Ortiz"          | "89012378"  | "joaquin.ortiz@hotmail.com"    | "989012378"      | 47           | 1               | 1         |

|

```|
  INSERT INTO| personas VALUES|
    (default,| 'María', 'González', '12345678', 'maria.gonzalez@gmail.com', '912345678', 25, 2, 2),
    (default, 'Juan', 'Pérez', '23456789', 'juan.perez@hotmail.com', '923456789', 30, 2, 1),
    (default, 'Ana', 'Martínez', '34567890', 'ana.martinez@yahoo.com', '934567890', 45, 2, 2),
    (default, 'Pedro', 'Sánchez', '45678901', NULL, '945678901', 18, 2, 1),
    (default, 'Lucía', 'López', '56789012', 'lucia.lopez@outlook.com', '956789012', 60, 2, 2),
    (default, 'Jorge', 'García', '67890123', NULL, '967890123', 40, 2, 1),
    (default, 'Sofía', 'Fernández', '78901234', 'sofia.fernandez@gmail.com', '978901234', 28, 2, 2),
    (default, 'Miguel', 'Romero', '89012345', NULL, '989012345', 50, 2, 1),
    (default, 'Carla', 'Jiménez', '90123456', 'carla.jimenez@hotmail.com', '990123456', 23, 2, 2),
    (default, 'David', 'Gutiérrez', '01234567', NULL, '901234567', 33, 2, 1),
    (default, 'Laura', 'Ruiz', '12345670', 'laura.ruiz@yahoo.com', '912345670', 48, 2, 2),
    (default, 'Gabriel', 'Gómez', '23456701', 'gabriel.gomez@gmail.com', '923456701', 19, 2, 1),
    (default, 'Carmen', 'Sanz', '34567812', NULL, '934567812', 39, 2, 2),
    (default, 'Daniel', 'Castillo', '45678923', 'daniel.castillo@hotmail.com', '945678923', 29, 2, 1),
    (default, 'Alicia', 'Moreno', '56789034', 'alicia.moreno@outlook.com', '956789034', 42,2, 2),
    (default, 'Pablo', 'Álvarez', '67890145', NULL, '967890145', 21, 1, 1),
    (default, 'Beatriz', 'Gallardo', '78901256', 'beatriz.gallardo@yahoo.com', '978901256', 37, 1, 2),
    (default, 'Rafael', 'Muñoz', '89012367', NULL, '989012367', 55, 1, 1),
    (default, 'Elena', 'Vega', '90123478', 'elena.vega@gmail.com', '990123478', 27, 1, 2),
    (default, 'Alejandro', 'Ramos', '01234589', 'alejandro.ramos@hotmail.com', '901234589', 31, 1, 1),
    (default, 'Isabel', 'Hernández', '12345690', 'isabel.hernandez@outlook.com', '912345690', 47, 1, 2),
    (default, 'Rosa', 'Vidal', '34567803', 'rosa.vidal@gmail.com', '934567803', 41, 1, 2),
    (default, 'Javier', 'Aguilar', '42678934', NULL, '942678934', 36, 1, 1),
    (default, 'Marina', 'Blanco', '56789345', 'marina.blanco@hotmail.com', '956789345', 22, 1, 2),
    (default, 'Francisco', 'Moya', '67890146', NULL, '967890146', 52, 1, 1),
    (default, 'Marisol', 'Herrera', '28901267', 'marisol.herrera@yahoo.com', '928901267', 43, 1, 2),
    (default, 'Diego', 'Santos', '89042378', NULL, '989042378', 32, 1, 1),
    (default, 'Aurora', 'Ortega', '90123989', 'aurora.ortega@gmail.com', '990123989', 58, 1, 2),
    (default, 'Emilio', 'Nieto', '01233590', 'emilio.nieto@hotmail.com', '901233590', 24, 1, 1),
    (default, 'Esther', 'Cabrera', '12345621', 'esther.cabrera@outlook.com', '912345621', 49, 1, 2),
    (default, 'Andrés', 'Soto', '23456212', NULL, '923456212', 38, 1, 1),
    (default, 'Marta', 'León', '34567813', 'marta.leon@gmail.com', '934567813', 35, 1, 2),
    (default, 'Óscar', 'Márquez', '45628934', 'oscar.marquez@hotmail.com', '945628934', 30, 1, 1),
    (default, 'Lorena', 'Gálvez', '56729045', 'lorena.galvez@yahoo.com', '956729045', 44, 1, 2),
    (default, 'Carlos', 'Cruz', '67860156', NULL, '967860156', 20, 1, 1),
    (default, 'Raquel', 'Ibáñez', '48901267', 'raquel.ibañez@outlook.com', '948901267', 46, 1, 2),
    (default, 'Mariano', 'Rivas', '89512378', NULL, '989512378', 54, 1, 1),
    (default, 'Nuria', 'Sánchez', '90123499', 'nuria.sanchez@gmail.com', '990123499', 25, 1, 2),
    (default, 'Adrián', 'García', '04234590', 'adrian.garcia@hotmail.com', '904234590', 34, 1, 1),
    (default, 'Cristina', 'Rodríguez', '12335601', 'cristina.rodriguez@yahoo.com', '912335601', 51, 1, 2),
    (default, 'Santiago', 'González', '23426712', NULL, '923426712', 41, 1, 1),
    (default, 'Victoria', 'Pérez', '34567823', 'victoria.perez@gmail.com', '934567823', 37, 1, 2),
    (default, 'María', 'López', '53789045', 'maria.lopez@yahoo.com', '953789045', 48, 1, 2),
    (default, 'Gustavo', 'Romero', '63890156', NULL, '963890156', 27, 1, 1),
    (default, 'Lucía', 'Garrido', '38901267', 'lucia.garrido@gmail.com', '938901267', 33, 1, 2),
    (default, 'Daniel', 'Fernández', '69012378', 'daniel.fernandez@hotmail.com', '969012378', 42, 1, 1),
    (default, 'Carmen', 'Moreno', '90223489', 'carmen.moreno@outlook.com', '990223489', 57, 1, 2),
    (default, 'Juan', 'Díaz', '01232590', NULL, '901232590', 39, 1, 1),
    (default, 'Eva', 'Álvarez', '12345501', 'eva.alvarez@yahoo.com', '912345501', 28, 1, 2),
    (default, 'Fernando', 'Giménez', '23356712', 'fernando.gimenez@gmail.com', '923356712', 47, 1, 1),
    (default, 'Leticia', 'Rojas', '34567833', 'leticia.rojas@hotmail.com', '934567833', 31, 1, 2),
    (default, 'Manuel', 'Navarro', '45673934', 'manuel.navarro@yahoo.com', '945673934', 50, 1, 1),
    (default, 'Silvia', 'Sosa', '56783045', 'silvia.sosa@gmail.com', '956783045', 23, 1, 2),
    (default, 'Jesús', 'Jiménez', '67890256', NULL, '967890256', 45, 1, 1),
    (default, 'Ana', 'Benítez', '78301267', 'ana.benitez@hotmail.com', '978301267', 40, 1, 2),
    (default, 'Rafael', 'Vargas', '82012378', 'rafael.vargas@outlook.com', '982012378', 53, 1, 1),
    (default, 'Isabel', 'Aguirre', '90121489', 'isabel.aguirre@gmail.com', '990121489', 26, 1, 2),
    (default, 'Pablo', 'Cano', '01234590', 'pablo.cano@yahoo.com', '901234590', 37, 1, 1),
    (default, 'Natalia', 'Castillo', '16345601', 'natalia.castillo@hotmail.com', '916345601', 42, 1, 2),
    (default, 'Antonio', 'Ruiz', '23456512', NULL, '923456512', 31, 1, 1),
    (default, 'Sandra', 'Sánchez', '34567843', 'sandra.sanchez@gmail.com', '934567843', 35, 1, 2),
    (default, 'Jorge', 'González', '45675934', 'jorge.gonzalez@hotmail.com', '945675934', 49, 1, 1),
    (default, 'Cristina', 'Hernández', '56785045', 'cristina.hernandez@yahoo.com', '956785045', 29, 1, 2),
    (default, 'David', 'Gómez', '67830156', 'david.gomez@gmail.com', '967830156', 25, 1, 1),
    (default, 'José', 'Pérez', '78904267', 'jose.perez@hotmail.com', '978904267', 44, 1, 1),
    (default, 'Laura', 'Muñoz', '89011378', NULL, '989011378', 30, 1, 2),
    (default, 'Pedro', 'Castro', '90123482', 'pedro.castro@gmail.com', '990123482', 41, 1, 1),
    (default, 'Luisa', 'Molina', '01234593', 'luisa.molina@yahoo.com', '901234593', 32, 1, 2),
    (default, 'Mario', 'Herrera', '12344601', 'mario.herrera@hotmail.com', '912344601', 36, 1, 1),
    (default, 'Carla', 'Gutiérrez', '43456712', 'carla.gutierrez@gmail.com', '943456712', 27, 1, 2),
    (default, 'Emilio', 'Flores', '34567853', 'emilio.flores@yahoo.com', '934567853', 52, 1, 1),
    (default, 'Julia', 'Ortega', '55678934', 'julia.ortega@hotmail.com', '955678934', 28, 1, 2),
    (default, 'Álvaro', 'Cabrera', '56779045', 'alvaro.cabrera@gmail.com', '956779045', 43, 1, 1),
    (default, 'Marta', 'Montes', '47890156', 'marta.montes@hotmail.com', '947890156', 39, 1, 2),
    (default, 'Héctor', 'Reyes', '7890126', 'hector.reyes@yahoo.com', '97890126', 34, 1, 1),
    (default, 'Lucas', 'Mendez', '89012398', 'lucas.mendez@gmail.com', '989012398', 25, 1, 1),
    (default, 'Marina', 'Alonso', '90123489', 'marina.alonso@hotmail.com', '990123489', 29, 1, 2),
    (default, 'Roberto', 'Soria', '51234590', 'roberto.soria@yahoo.com', '951234590', 48, 1, 1),
    (default, 'Ana', 'Lara', '12345601', 'ana.lara@gmail.com', '912345601', 50, 1, 2),
    (default, 'Diego', 'Vera', '23456712', NULL, '923456712', 22, 1, 1),
    (default, 'Natalia', 'Ramos', '34567863', 'natalia.ramos@hotmail.com', '934567863', 26, 1, 2),
    (default, 'Javier', 'Vidal', '45678934', 'javier.vidal@yahoo.com', '945678934', 46, 1, 1),
    (default, 'Raquel', 'Fuentes', '56789045', 'raquel.fuentes@hotmail.com', '956789045', 33, 1, 2),
    (default, 'Francisco', 'Gil', '67890156', 'francisco.gil@gmail.com', '967890156', 38, 1, 1),
    (default, 'Sara', 'Rey', '7890127', 'sara.rey@yahoo.com', '97890127', 31, 1, 2),
    (default, 'Joaquín', 'Ortiz', '89012378', 'joaquin.ortiz@hotmail.com', '989012378', 47, 1, 1);

    SELECT * FROM personas;
```

---

_Medicamentos_

> _usar como referencia la siguiete pagina [link](http://observatorio.digemid.minsa.gob.pe/medicamentosesenciales/)_

### Tabla medicamentos
