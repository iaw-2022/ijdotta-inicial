# Proyecto Inicial

## Idea a Implementar


Se quiere desarrollar una aplicación web que mejore la experiencia con relación al sistema de turnos y administración de la información de un paciente en una clínica médica. 


En cuanto al sistema de turnos, cada **médico** podrá crear, consultar, modificar o eliminar los turnos disponibles. Incluso puede cancelar un turno ya reservado, provocando que se notifique adecuadamente al paciente. Se podrán definir distintos patrones de turnos *(por ejemplo, lunes, martes y miércoles de 14 a 18 hs con una duración de 30 minutos por turno, entre el 01/04/2022 y el 30/06/2022)* para poder determinar los turnos que están disponibles. 
Mientras tanto, el **paciente** puede consultar, solicitar y cancelar turnos. Análogamente, se notifica al médico de forma adecuada. 
- Para **solicitar turnos**, solamente se requiere cargar sus datos personales si es la primera vez o bien con el DNI se recuperan automáticamente del sistema si ya es paciente. Luego, debe seleccionar médico, especialidad y turno. Es decir, no requiere iniciar sesión con contraseña.
- Para poder **consultar y cancelar turnos**, debe ingresar al sistema con un código recibido al email (luego puede definir una contraseña propia o continuar utilizando el mecanismo anterior).


Con respecto a la **administración del paciente**, luego de cada consulta el profesional debe añadir un detalle (que lleva la fecha de la consulta) con información relevante que queda asociada al paciente y registrada en el sistema. Incluso, se pueden cargar tratamientos o medicaciones asignadas durante la consulta en cuestión.


Los profesionales de la clínica pueden buscar los pacientes del sistema y ver su información. Esto es especialmente útil cuando el paciente decide atenderse con otro profesional de la misma clínica porque permite al médico acceder al historial de consultas, detalles y tratamientos.


Al mismo tiempo, el paciente puede consultar sus tratamientos asociados, no así el detalle de su historial. Para cada tratamiento, cuando es posible, el sistema recupera información adicional y de interés para el paciente. Por ejemplo, dada una droga en particular, puede mostrarse el prospecto (utilizando un API externa). Para poder acceder a esta información, el paciente debe antes iniciar sesión, como se explicó previamente.


## Diagrama ER
![idea-iaw-ClinicApp@3 1 1](https://user-images.githubusercontent.com/67470951/162467297-7621498c-d209-4f79-b0fa-0627f4f8834f.svg)


## Actualizaciones a los datos


En Laravel habrá dos roles: el médico y el administrador.


El médico debe poder hacer:
- Iniciar sesión,
- CRUD turnos (podría asignar un turno a un paciente específico, siempre que haya habilitado turnos para la fecha dada),
- Consultar pacientes (por apellido, nombre, DNI),
- CRUD detalle historia paciente (eventualmente se podría establecer un periodo de tiempo durante el que el médico puede eliminar o modificar una historia y luego solo poder consultarla. El administrador sí tiene control total),
- CRUD tratamiento paciente


El administrador puede hacer todo lo que un médico y además:
- CRUD médicos,
- CRUD pacientes




## Información del Servicio Web


El servicio debe permitir:
- Recuperar turnos disponibles dado un médico (y opcionalmente filtros adicionales, como fecha),
- Solicitar un turno,
- Consultar y cancelar turnos dado un paciente,
- Recuperar tratamientos de un paciente




## Visualización y Acceso a la Información


A través de una interfaz amigable, el paciente podrá consultar turnos disponibles luego de haber introducido algunos datos y solicitar un turno. También será posible iniciar sesión en el sistema para consultar y cancelar turnos, y para consultar los tratamientos asignados.

