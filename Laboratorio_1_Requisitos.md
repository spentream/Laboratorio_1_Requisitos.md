Laboratorio 1: Identificación de requisitos y reglas de negocio verificables.

***Integrantes:***  
***ELIAS ROSAS GARCIA***  
***ANGEL GABRIEL ANGULO SOTO***  
***VALENTINA FLORES LOPEZ***  
***ESAU VILLA CORRALES***

| ID | Tipo | Categoria | Descripción verificable | Fuente |
| :---- | :---- | :---- | :---- | :---- |
| RF-01 | Funcional | Consulta | El sistema debe permitir al paciente consultar en tiempo real los horarios disponibles de los médicos. | Proyecto base |
| RF-02 | Funcional | Agendamiento | El sistema debe permitir al paciente agendar una cita médica seleccionando un médico, una fecha y un horario disponible. | Proyecto base |
| RF-03 | Funcional | Notificaciones | El sistema debe notificar al paciente mediante correo electrónico la confirmación de la cita, incluyendo médico, fecha, hora y estado de la misma. | Proyecto base |
| RF-04 | Funcional | Gestión de citas | El sistema debe permitir al paciente reagendar una cita registrada seleccionando una nueva fecha u horario disponible. | Proyecto base |
| RF-05 | Funcional | Gestión de citas | El sistema debe permitir al paciente cancelar una cita agendada, liberando automáticamente la disponibilidad de esa fecha y hora para otros usuarios. | Proyecto base |
| RNF-01 | No funcional | Seguridad | El sistema debe exigir la autenticación e identificación del usuario mediante su ID de paciente antes de permitir la consulta de disponibilidad o el agendamiento de citas. | Derivado |
| RNF-02 | No funcional | Rendimiento | El sistema debe mostrar los horarios disponibles al usuario en un tiempo máximo de 3 segundos y desplegar la confirmación en pantalla dentro de ese mismo lapso tras agendar, previo al envío del correo. | Derivado |
| RNF-03 | No funcional | Usabilidad/Disponibilidad | El sistema debe enviar la notificación por correo electrónico con el estado de la cita en un tiempo no mayor a $5minutos$ posterior al agendamiento. | Derivado |
| RN-01 | Regla de negocio | Gestión de citas  | Un paciente no puede tener más de una cita médica activa registrada para la misma fecha y la misma franja horaria, independientemente de si es con médicos distintos. | Proyecto base |
| RN-02 | Regla de negocio | Gestión de citas | Solo se podrán agendar citas en las fechas y franjas horarias que el médico tenga explícitamente configuradas como disponibles en su agenda laboral. | Proyecto base |
| RN-03 | Regla de negocio | Politicas de cancelacion | Las solicitudes de cancelación o reagendamiento de citas deben realizarse con una anticipación mínima de 1 día hábil previo a la fecha y hora programada. | Proyecto base |
| RN-04 | Regla de negocio | Gestión de citas | Un horario confirmado por un paciente debe ser bloqueado y removido de la lista de horarios disponibles de forma inmediata para evitar reservas duplicadas por otros usuarios. | Proyecto base |

***RNF-01:***  
***Requisito:*** El sistema debe exigir la autenticación e identificación del usuario mediante su ID de paciente antes de permitir la consulta de disponibilidad o el agendamiento de citas.

***Justificación:*** Este requisito ayuda a mantener el orden y la seriedad en la disponibilidad de las citas, siendo importante para evitar que se saturen los horarios con reservas de usuarios no registrados. Se puede verificar intentando acceder a la consulta de agenda o al formulario de agendamiento sin haberse identificado previamente como paciente, comprobando que el sistema restrinja el acceso.

***RNF-02:***  
***Requisito:*** El sistema debe mostrar los horarios disponibles al usuario en un tiempo máximo de $3segundos$ y desplegar la confirmación en pantalla dentro de ese mismo lapso tras agendar, previo al envío del correo.

***Justificación:*** Este requisito garantiza una respuesta ágil de la interfaz para no fatigar al usuario ni generar incertidumbre durante el proceso de reserva. Se verifica agendando citas bajo diversas condiciones (variando médicos, fechas y horarios disponibles) y midiendo el tiempo de respuesta en pantalla para comprobar que no supere el límite de 3 segundos.

***RNF-03:***

***Requisito:*** El sistema debe enviar la notificación por correo electrónico con el estado de la cita en un tiempo no mayor a 5 minutos posterior al agendamiento.

***Justificación:*** Este requisito notifica al usuario vía correo electrónico para confirmar la cita formalmente fuera del sistema, lo cual es importante para generar confianza y otorgarle un comprobante digital de su reserva. Se verifica cronometrando el tiempo transcurrido desde que se confirma el agendamiento en el sistema hasta la recepción de la notificación en la bandeja de entrada del paciente, validando que sea menor o igual a 5 minutos.

