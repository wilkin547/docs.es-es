---
ms.openlocfilehash: 33178637c4fcfb21e8190c3d2593f09326ea5995
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73166639"
---
# <a name="github-issues-process-and-policy"></a>Directiva y proceso en relación con las incidencias en GitHub

Los objetivos del proceso son los siguientes:

1. Garantizar que los errores u omisiones en la documentación no impidan a los clientes trabajar correctamente.
1. Responder a los comentarios y las preocupaciones de los clientes.
1. Mejorar la experiencia de los usuarios de forma continuada.
1. Obtener más información sobre las experiencias de los clientes a través de un diálogo abierto sobre los desafíos y las soluciones.

En el proceso se usan dos fases para garantizar la capacidad de respuesta al tiempo que se prioriza el trabajo. En la fase inicial se diagnostica y evalúa la incidencia. En la segunda fase, se resuelve. En los casos en los que una incidencia es sencilla y urgente, las dos fases se pueden combinar.

El proceso implica tareas con asignaciones de tiempo fijas:

- Cada miembro del equipo dedica un máximo de 30 minutos de un día laborable a [clasificar las incidencias entrantes](#diagnosis-phase), incluidas las respuestas iniciales. Esto garantiza la capacidad de respuesta a las incidencias nuevas.
- Cada miembro del equipo dedica un máximo de medio día por semana a [actualizar los documentos](#resolution-phase) para solucionar incidencias de GitHub generadas por los clientes.

## <a name="diagnosis-phase"></a>Fase de diagnóstico

Cada miembro del equipo dedica un máximo de 30 minutos de un día laborable a clasificar las incidencias nuevas. Se responden las preguntas siguientes:

- ¿Se trata de una incidencia del producto o de la documentación?
- Si no se trata de una incidencia, ¿quizás es una pregunta más adecuada para un foro o sitio de soporte técnico?
- ¿Cuál es la prioridad de la incidencia?
- ¿En qué área se administra esta incidencia?

Si durante el examen inicial no se puede responder a estas preguntas, en los comentarios se realizan preguntas aclaratorias.

Hay tipos de incidencias que se cierran durante la fase de diagnóstico y evaluación:

- **Kudos**: expresamos nuestro agradecimiento y cerramos la incidencia.
- **Incidencia del producto**: se cierran las incidencias relacionadas con el producto, pero no con la documentación. También es posible que se tomen medidas adicionales, como se describe a continuación.
- **Infracciones de CoC**: estas incidencias se cierran y se notifican si la [infracción de CoC](https://dotnetfoundation.org/code-of-conduct) requiere la creación de un informe y su bloqueo.
- **Duplicados**: los duplicados se cierran con un comentario que haga referencia a la incidencia existente.
- **Doc-ok**: el cliente no es correcto; la documentación, sí.
- **Foro**: las incidencias de soporte técnico o las solicitudes relativas al foro se dirigen a Stack Overflow o a otros sitios de soporte técnico y se cierran.

### <a name="actions-on-product-issues"></a>Acciones sobre incidencias del producto

En función de la naturaleza de la incidencia del producto, se puede optar por lo siguiente:

- Transferir la incidencia al repositorio del producto adecuado.
- Cerrar la incidencia como un duplicado de solicitudes de producto existentes.
- Cerrar la incidencia con una recomendación para abrirla en el repositorio del producto.

La evaluación del curso de acción correcto es subjetiva. Los miembros del equipo deben emplear su buen juicio para adoptar la acción correcta.

### <a name="actions-on-content-issues"></a>Acciones sobre incidencias de contenido

Para otras incidencias, el equipo:

- Asigna una prioridad.
- Asigna un hito, normalmente "Trabajo pendiente".
- Evalúa si una incidencia es de tipo "Up for grabs" (Para seleccionar), o bien para los [Proyectos para colaboradores de la comunidad de .NET](https://github.com/dotnet/docs/projects/35).

Los niveles de prioridad se basan en las instrucciones siguientes, pero son subjetivos. Los hitos también son subjetivos y se basan en otras prioridades, como las programaciones de lanzamiento de productos actuales y los próximos lanzamientos.

- **P0**: error u omisión de la documentación que impide a los clientes desarrollar un escenario común de forma correcta.
  - Las incidencias **P0** se abordan en las tres semanas siguientes, con prioridad sobre el trabajo programado previamente.
- **P1**: error u omisión de la documentación que dificulta mucho más un escenario común o bloquea otros escenarios conocidos.
  - Las incidencias **P1** se programan de manera oportuna. A menudo, las incidencias P1 se planean para un hito futuro.
- **P2**: incidencias que causan inconvenientes menores o que afectan a un artículo de vista de página baja.
  - Las incidencias **P2** normalmente se corrigen al actualizar un artículo por motivos de mayor prioridad.
- **P3**: incidencias que son solicitudes de escenarios de casos perimetrales.
  - Las incidencias **P3** se colocan en el trabajo pendiente y se valoran para su actualización cuando los artículos se actualizan por motivos de mayor prioridad.

Los miembros del equipo emplean una cantidad limitada de tiempo en el diagnóstico y la evaluación para poder progresar en las tareas programadas. Cada miembro del equipo dedica un máximo de 30 minutos al día a las tareas de diagnóstico y evaluación.

La etiqueta **Up-for-grabs** se aplica cuando una incidencia es una candidata correcta para que un miembro de la comunidad (posiblemente el autor) envíe una corrección. El miembro del equipo que aplica la etiqueta **Up-for-grabs** ayudará a los miembros de la comunidad (o buscará a alguien que lo haga) a trabajar en el proceso de creación de la PR. Las incidencias etiquetadas como "Up for grabs" se suelen agregar a los [Proyectos de colaboración de la comunidad](https://github.com/dotnet/docs/projects/35).

> NOTA: La convención anterior se ha adoptado recientemente. Es posible que la persona que ha agregado la etiqueta le remita a otro miembro del equipo para que le ayude.

## <a name="resolution-phase"></a>Fase de resolución

Las incidencias generadas por los clientes se ponderan como parte del planeamiento de tareas programadas. Cada miembro del equipo dedica 4 horas por semana a abordar las incidencias de los clientes con mayor prioridad.

La resolución de incidencias sigue el nivel de prioridad establecido durante el diagnóstico. Las incidencias de los clientes entrantes se priorizan con otro trabajo programado de prioridad similar.

- **P0**: en cuanto sea razonable, en las tres semanas siguientes.
- **P1**: se programa con otro trabajo de P1 planeado; suele ser durante los tres meses siguientes.
- **P2**: se programa con otro trabajo de P2 planeado. Las incidencias P2 se programan de forma periódica según el área y la visibilidad. A menudo, las incidencias P2 se abordan al actualizar un artículo.
- **P3**: no hay ninguna fecha de corrección garantizada. Cuando se actualiza un artículo, se examina el trabajo pendiente de otras incidencias en el mismo artículo.

Se puede cambiar la prioridad de las incidencias en función de nuevos comentarios y datos sobre la visibilidad del artículo.
