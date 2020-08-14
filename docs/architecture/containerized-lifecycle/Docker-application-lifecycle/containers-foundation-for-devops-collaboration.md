---
title: Contenedores como base para la colaboración de DevOps
description: Descripción del papel clave de los contenedores en la optimización de DevOps.
ms.date: 08/06/2020
ms.openlocfilehash: af28c1add8b2e6befbd2f3e6ae9fe707ccc5b106
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916016"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>Contenedores como base para la colaboración de DevOps

Gracias a la naturaleza intrínseca de la tecnología de Docker y los contenedores, los desarrolladores pueden compartir el software y las dependencias fácilmente con los equipos de operaciones de TI y los entornos de producción, lo que pone fin a la típica excusa de "funciona en mi equipo". Los contenedores solucionan los conflictos de las aplicaciones entre distintos entornos. De manera indirecta, los contenedores y Docker acercan todavía más a los desarrolladores y los equipos de operaciones de TI, lo que les permite colaborar de forma eficaz. Al adoptar el flujo de trabajo de contenedor, muchos clientes tienen acceso a la continuidad de DevOps que tanto ansiaban y que antes debían implementar a través de una configuración más compleja de las canalizaciones de versión y compilación. Los contenedores simplifican las canalizaciones de compilación, prueba e implementación de DevOps.

![Diagrama que muestra la propiedad del ciclo de vida de una aplicación de Docker.](./media/containers-foundation-for-devops-collaboration/persona-workloads-docker-container-lifecycle.png)

**Figura 2-1.** Cargas de trabajo principales por "roles" en el ciclo de vida de aplicaciones en contenedor de Docker.

Con los contenedores de Docker, los desarrolladores controlan lo que está dentro del contenedor (la aplicación y el servicio, así como las dependencias de los marcos y los componentes) y la manera en que los contenedores y los servicios se comportan juntos como una aplicación compuesta por una colección de servicios. Las interdependencias de los diversos contenedores se definen en un archivo `docker-compose.yml`, o lo que podría llamarse *manifiesto de implementación*. Mientras tanto, los equipos de operaciones de TI (profesionales de TI y administración) pueden centrarse en la gestión de los entornos de producción, la infraestructura, la escalabilidad, la supervisión y, en última instancia, la verificación de que las aplicaciones ofrecen un servicio adecuado a los usuarios finales, sin necesidad de conocer el contenido de los diversos contenedores. A esto se debe el término "contenedor," como analogía con los contenedores de transporte del mundo real. Los propietarios del contenido de un contenedor no necesitan preocuparse por cómo se enviará el contenedor y la empresa de transporte envía el contenedor desde el punto de origen al destino sin conocer el contenido ni preocuparse por él. De forma similar, los desarrolladores pueden crear y poseer el contenido de un contenedor de Docker sin necesidad de preocuparse por los mecanismos de "transporte".

En el bloque de la izquierda de la figura 2-1, los desarrolladores escriben y ejecutan código localmente en contenedores de Docker mediante Docker para Windows o Mac. Definen el entorno operativo para el código a través de un archivo Dockerfile que especifica el sistema operativo básico que se va a ejecutar, así como los pasos de compilación para compilar el código en una imagen de Docker. Los desarrolladores definen cómo interactuarán una o varias imágenes mediante el manifiesto de implementación del archivo `docker-compose.yml` mencionado anteriormente. A medida que completan el desarrollo local, insertan el código de la aplicación y los archivos de configuración de Docker en el repositorio de código de su elección (es decir, el repositorio GIT).

El bloque de DevOps define las canalizaciones de compilación e integración continua (CI) mediante el archivo Dockerfile que se proporciona en el repositorio de código. El sistema de CI extrae las imágenes del contenedor base del registro de Docker seleccionado y compila las imágenes de Docker personalizadas para la aplicación. Después, las imágenes se validan y se insertan en el registro de Docker que se usa para las implementaciones en varios entornos.

En el bloque de la derecha, los equipos de operaciones administran la infraestructura y las aplicaciones implementadas en producción al mismo tiempo que supervisan el entorno y las aplicaciones, de modo que puedan proporcionar comentarios e información al equipo de desarrollo sobre la manera en que podría mejorarse la aplicación. Las aplicaciones de contenedor normalmente se ejecutan en producción mediante orquestadores de contenedores como [Kubernetes](https://kubernetes.io/). Asimismo, con frecuencia se emplean [gráficos de Helm](https://helm.sh/) para configurar unidades de implementación, en lugar de archivos docker-compose.

Los dos equipos colaboran mediante una plataforma fundamental (contenedores de Docker) que proporciona una "separación de intereses" de forma contractual, al tiempo que mejora en gran medida la colaboración de los dos equipos en el ciclo de vida de la aplicación. Los desarrolladores poseen el contenido del contenedor, su entorno operativo y las interdependencias del contenedor, mientras que los equipos de operaciones toman las imágenes compiladas junto con el manifiesto y las ejecutan en su sistema de orquestación.

## <a name="challenges-in-the-application-life-cycle-when-using-docker"></a>Desafíos del ciclo de vida de la aplicación al usar Docker.

Hay muchas razones que aumentarán el número de aplicaciones en contenedores en los próximos años; una de ellas es la creación de aplicaciones basadas en microservicios.

Durante los últimos 15 años, el uso de servicios web ha sido la base de miles de aplicaciones y, probablemente, dentro de unos años estemos en la misma situación con las aplicaciones basadas en microservicios que se ejecutan en contenedores de Docker.

Además, merece la pena mencionar que también se pueden usar contenedores de Docker para aplicaciones monolíticas y disfrutar de la mayoría de las ventajas de Docker. Los contenedores no se centran únicamente en los microservicios.

El uso de los microservicios y la inclusión en contenedores de Docker plantea nuevos desafíos en el proceso de desarrollo de las organizaciones. Por lo tanto, se necesita una estrategia sólida para mantener en ejecución muchos contenedores y microservicios en sistemas de producción. A la larga, las aplicaciones empresariales tendrán cientos e incluso miles de contenedores o instancias que se ejecutan en producción.

Estos desafíos generan nuevas demandas al usar herramientas de DevOps, por lo que tiene que definir nuevos procesos en las actividades de DevOps y encontrar respuestas para el siguiente tipo de preguntas:

- ¿Qué herramientas puedo usar para el desarrollo, CI/CD, la administración y las operaciones?

- ¿Cómo puede mi empresa administrar los errores de los contenedores cuando se ejecutan en producción?

- ¿Cómo se pueden cambiar elementos de software en producción con un tiempo mínimo de inactividad?

- ¿Cómo se puede escalar y supervisar el sistema de producción?

- ¿Cómo se pueden incluir las pruebas y la implementación de contenedores en la canalización de versión?

- ¿Cómo se pueden usar las herramientas y plataformas de código abierto para contenedores en Microsoft Azure?

Si puede responder a todas esas preguntas, estará mejor preparado para mover las aplicaciones (nuevas o existentes) a contenedores de Docker.

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>Introducción a un flujo de trabajo genérico de ciclo de vida de aplicaciones de Docker de un extremo a otro

En la figura 2-2 se muestra un flujo de trabajo más detallado del ciclo de vida de aplicaciones de Docker, centrado en este caso en actividades y activos de DevOps específicos.

![Diagrama que muestra el ciclo de vida de un extremo a otro genérico de una aplicación de Docker.](./media/containers-foundation-for-devops-collaboration/generic-end-to-enddpcker-app-life-cycle.png)

**Figura 2-2.** Flujo de trabajo de alto nivel para el ciclo de vida de aplicaciones en contenedor de Docker

Todo comienza con el desarrollador, que empieza a escribir código en el flujo de trabajo del bucle interno. La fase de bucle interno es donde los desarrolladores definen todo lo que ocurre antes de insertar código en el repositorio de código (por ejemplo, un sistema de control de código fuente, como GIT). Una vez confirmado, el repositorio desencadena la integración continua (CI) y el resto del flujo de trabajo.

El bucle interno consta de los pasos típicos, como "programación", "ejecución", "prueba" y "depuración", además de los pasos adicionales necesarios justo antes de ejecutar la aplicación en local. Este es el proceso del desarrollador para ejecutar y probar la aplicación como contenedor de Docker. El flujo de trabajo del bucle interno se explicará en las secciones siguientes.

Si se da un paso atrás para observar el flujo de trabajo de un extremo a otro, el flujo de trabajo de DevOps es algo más que una tecnología o un conjunto de herramientas: es una actitud que exige una evolución cultural. Lo integran personas, procesos y herramientas adecuadas que hacen que el ciclo de vida de la aplicación sea más rápido y predecible. Las empresas que adoptan un flujo de trabajo en contenedores suelen reestructurar su organización para que represente a personas y procesos que coincidan con el flujo de trabajo en contenedores.

La práctica con DevOps puede ayudar a los equipos a responder juntos con mayor rapidez ante presiones competitivas, al reemplazar por la automatización los procesos manuales propensos a errores, lo que conlleva una rastreabilidad mejorada y flujos de trabajo repetibles. Las organizaciones también pueden administrar los entornos de manera más eficaz y ahorrar costes gracias a una combinación de recursos locales y en la nube, así como herramientas estrechamente integradas.

Al implementar el flujo de trabajo de DevOps para aplicaciones de Docker, verá que las tecnologías de Docker están presentes en prácticamente todas las etapas del flujo de trabajo, desde el cuadro de desarrollo, durante el trabajo en el bucle interno (programación, ejecución y depuración), en la fase de compilación, prueba y CI y, por último, en la implementación de los contenedores en los entornos de ensayo y producción.

La mejora de las prácticas de calidad ayuda a identificar los defectos al principio del ciclo de desarrollo, lo que reduce el coste que supone corregirlos. Al incluir el entorno y las dependencias en la imagen y adoptar la filosofía de implementar la misma imagen en varios entornos, se fomenta la disciplina de extraer las configuraciones específicas del entorno, lo cual conlleva implementaciones más fiables.

Los datos enriquecidos que se obtienen a través de la instrumentación efectiva (supervisión y diagnóstico) permiten comprender mejor los problemas de rendimiento y el comportamiento del usuario, algo que resulta muy útil como orientación para las prioridades e inversiones futuras.

DevOps debe considerarse un viaje, no un destino. Debe implementarse de forma incremental a través de proyectos con un ámbito adecuado con los que se pueda demostrar su éxito, aprender y evolucionar.

## <a name="benefits-of-devops-for-containerized-applications"></a>Ventajas de DevOps para las aplicaciones en contenedor

Estas son algunas de las ventajas más importantes que proporciona un flujo de trabajo sólido de DevOps:

- Entregar software de mayor calidad con más rapidez y un mejor cumplimiento.

- Impulsar la mejora y los ajustes continuos en fases más tempranas y de forma más económica.

- Aumentar la transparencia y la colaboración entre las partes interesadas que participan en la entrega y el funcionamiento del software.

- Controlar los costes y usar recursos aprovisionados de forma más eficaz mientras se minimizan los riesgos de seguridad.

- Conectarse y funcionar automáticamente con muchas de las inversiones existentes de DevOps, incluidas las inversiones en código abierto.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](../Microsoft-platform-tools-containerized-apps/index.md)
