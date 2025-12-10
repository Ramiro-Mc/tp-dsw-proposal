# Propuesta TP DSW

## Grupo
### Integrantes
* 52992 - Martinez Castro, Ramiro Facundo
* 52838 - López, Joaquín
* 52959 - García Marianelli, Matías Fernando
* 53020 - Busnadiego, Martín
* 53400 - Spedaliere, Mateo

### Repositorios
* [fullstack app](https://github.com/Ramiro-Mc/dsw-fullstack-app)

## Tema

Plataforma de cursos educativos online (Utndemy)

### Descripción

**Utndemy** es una plataforma de educación online que permite a usuarios aprender y a profesores enseñar cursos en línea.

* El sistema permite a los usuarios registrarse, navegar un catálogo de cursos organizados por categorías y comprar cursos para acceder a su contenido educativo.

* Los profesores pueden crear cursos estructurados en módulos y lecciones. Cada curso debe ser aprobado por un administrador antes de estar disponible públicamente. Los profesores pueden gestionar el precio y aplicar descuentos a sus cursos.

* Un usuario puede ser simultáneamente estudiante (comprando cursos) y profesor (creando y vendiendo cursos).

* Los profesores tienen acceso a una interfaz para administrar sus cursos, donde pueden crear, editar y eliminar módulos y lecciones, además de configurar sus datos bancarios para recibir pagos.

* Los estudiantes acceden al contenido del curso a través de una interfaz que muestra los módulos y lecciones organizadas, permitiendo llevar un seguimiento del progreso.

* Cada curso cuenta con un foro (comunidad) donde los estudiantes pueden publicar dudas, comentarios y discutir con otros usuarios. Los profesores aparecen identificados con un badge especial en el foro.

* El sistema incluye roles diferenciados: usuarios estándar (estudiantes/profesores) y administradores que gestionan la aprobación de cursos y usuarios del sistema.

### Modelo de Dominio

![Alt]([https://github.com/Ramiro-Mc/tp-dsw/blob/main/Diagrama.png?raw=true](https://github.com/Ramiro-Mc/tp-dsw-proposal/blob/main/Diagrama.png))

### Funcionalidades Adicionales Implementadas

Se agregaron las siguientes funcionalidades no contempladas en la propuesta original:

1. **Sistema de aprobación de cursos**: Los cursos creados por profesores pasan por un estado de "Pendiente" hasta ser aprobados o rechazados por un administrador.

2. **Identificación de profesor en foro**: Los profesores aparecen con un badge especial y estilo diferenciado en las publicaciones del foro.

3. **Gestión de información bancaria**: Los profesores pueden configurar y actualizar sus datos bancarios de forma segura (con encriptación).

4. **Dashboard de administrador**: Panel completo para gestionar usuarios, cursos pendientes y estadísticas del sistema.

5. **Seguimiento de progreso**: Sistema de marcado de lecciones vistas con la entidad AlumnoLeccion.

6. **Gestión de perfil completo**: Los usuarios pueden actualizar su información personal, foto de perfil, cambiar contraseña y configurar datos bancarios.

7. **Tipos de curso con badges visuales**: Cada categoría tiene colores y estilos distintivos en la interfaz.

## Alcance Funcional 

### Alcance Mínimo

Regularidad (5 integrantes):
|Req|Detalle|
|:-|:-|
|CRUD simple|1. CRUD Usuario<br>2. CRUD Curso<br>3. CRUD TipoCurso<br>4. CRUD Módulo<br>5. CRUD Lección|
|CRUD dependiente|1. CRUD Módulo {depende de} Curso<br>2. CRUD Lección {depende de} Módulo<br>3. CRUD AlumnoCurso {depende de} Usuario y Curso|
|Listado<br>+<br>detalle|1. Listado de cursos aprobados filtrado por categoría ⇒ detalle muestra curso completo con módulos y lecciones<br>2. Listado de cursos comprados por usuario ⇒ detalle con acceso al contenido<br>3. Listado de cursos creados por profesor ⇒ detalle con opciones de edición|
|CUU/Epic|1. Inscribirse a un curso (Epic completo: navegar → ver detalle → comprar → acceder)<br>2. Publicar un curso (Epic: crear curso → agregar módulos → agregar lecciones → esperar aprobación)<br>3. Gestión de foro (Epic: ver publicaciones → crear → editar → eliminar)|

Adicionales para Aprobación (5 integrantes):
|Req|Detalle|
|:-|:-|
|CRUD completos|1. CRUD Usuario<br>2. CRUD Curso<br>3. CRUD TipoCurso<br>4. CRUD Módulo<br>5. CRUD Lección<br>6. CRUD AlumnoCurso<br>7. CRUD Comunidad<br>8. CRUD Publicación<br>9. CRUD AlumnoLeccion|
|CUU/Epic (5)|1. **Aplicar Descuento**: Crear usuario → Login → Obtener perfil<br>2. **Comprar un curso**: Listar cursos → Filtrar por categoría → Ver detalle → Comprar<br>3. **Acceso a Contenido**: Ver módulos → Ver lecciones → Marcar como vista<br>4. **Creación de Cursos**: Crear curso → Agregar módulos → Agregar lecciones → Editar precio/descuento<br>5. **Gestión Administrativa**: Aprobar/Rechazar cursos → Gestionar usuarios → Ver estadísticas|

### Alcance Adicional Implementado

|Req|Detalle|
|:-|:-|
|Listados|1. Listado de cursos adquiridos por usuario<br>2. Listado de cursos con descuento (promoción)<br>3. Listado de cursos creados por profesor<br>4. Listado de publicaciones por comunidad|
|Funcionalidades|1. Sistema de aprobación de cursos por admin<br>2. Foro/comunidad por curso con identificación de profesor<br>3. Gestión de información bancaria encriptada<br>4. Seguimiento de progreso de lecciones<br>5. Cambio de contraseña seguro<br>6. Actualización de foto de perfil|

---

