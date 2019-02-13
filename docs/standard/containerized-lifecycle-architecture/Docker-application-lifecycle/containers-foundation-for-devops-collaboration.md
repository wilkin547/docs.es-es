---
title: Contenedores como base para la colaboración de DevOps
description: Comprender la función clave de contenedores para agilizar DevOps.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: d0339199092304dd6c91707d8cf4da213f110b58
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219298"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>Contenedores como base para la colaboración de DevOps

Por la propia naturaleza de la tecnología de Docker y contenedores, los desarrolladores pueden compartir su software y las dependencias fácilmente con las operaciones de TI y los entornos de producción mientras se elimina la típica excusa "funciona en mi equipo". Contenedores de resolución los conflictos de aplicaciones entre distintos entornos. Indirectamente, contenedores y Docker reunir a los desarrolladores y las operaciones de TI más cerca, lo que facilita a colaborar de forma eficaz. Adoptar el flujo de trabajo de contenedor proporciona a muchos clientes con la continuidad se ha buscado pero antes tenía que implementar a través de la configuración más compleja de versión y crear canalizaciones de DevOps. Los contenedores simplifican las canalizaciones de compilación o prueba e implementación de DevOps.

![](./media/image1.png)

Figura 2-1: Cargas de trabajo principales por "roles" en el ciclo de vida de aplicaciones en contenedores de Docker

Con contenedores de Docker, los desarrolladores propios lo que está dentro del contenedor (aplicación y servicio y las dependencias entre componentes y marcos de trabajo) y cómo los contenedores y servicios se comportan como una aplicación compuesta por una colección de servicios. Las interdependencias de los diversos contenedores se definen en un archivo docker-compose.yml, o lo que podría llamarse una *manifiesto de implementación*. Mientras tanto, los equipos de operaciones de TI (administración y los profesionales de TI) pueden centrarse en la administración de entornos de producción; infraestructura; escalabilidad; supervisión; y, en última instancia, lo que garantiza que las aplicaciones están ofreciendo correctamente para los usuarios finales, sin tener que conocer el contenido de los diversos contenedores. Por lo tanto, el nombre "container," recordando la analogía de contenedores de transporte del mundo real. Por lo tanto, los propietarios de contenido de un contenedor necesitan no se refieren a cómo se va a enviar el contenedor y los transportes de empresa de trasvase de registros un contenedor de su punto de origen a su destino sin saber ni preocuparse sobre el contenido. De forma similar, los desarrolladores pueden crear y poseer el contenido dentro de un contenedor de Docker sin necesidad de preocuparse de los mecanismos de "transport".

En el pilar del lado izquierdo de la figura 2-1, los desarrolladores escribirán y ejecutan código localmente en contenedores de Docker mediante el uso de Docker para Windows o Mac. Definen el entorno operativo para el código mediante el uso de un Dockerfile que especifica el sistema operativo básico para ejecutar, así como los pasos de compilación para compilar su código en una imagen de Docker. Los desarrolladores definen cómo las imágenes de uno o más pueden interoperar utilizando la mencionada anteriormente *docker-compose.yml* manifiesto de implementación del archivo. Medida que se completa su desarrollo local, inserte su código de la aplicación además de los archivos de configuración de Docker en el repositorio de código de su elección (es decir, el repositorio de Git).

El pilar de DevOps define las canalizaciones de integración (CI) de compilación – Continuous mediante el Dockerfile que se proporciona en el repositorio de código. El sistema de CI extrae las imágenes del contenedor base desde el registro de Docker seleccionado y compila las imágenes de Docker personalizadas para la aplicación. Las imágenes, a continuación, se validan e insertadas en el registro de Docker que se usa para las implementaciones en varios entornos.

En el pilar de la derecha, las operaciones de administración de equipos implementan aplicaciones e infraestructura en producción al supervisar el entorno y las aplicaciones para que pueden proporcionar comentarios e información al equipo de desarrollo acerca de cómo podría ser la aplicación mejorado. Las aplicaciones de contenedor normalmente se ejecutan en producción con orquestadores de contenedor.

Los dos equipos son colaborar a través de una plataforma fundamental (contenedores de Docker) que proporciona una separación de intereses como un contrato, al tiempo que mejora en gran medida la colaboración de los dos equipos en el ciclo de vida de la aplicación. Los desarrolladores poseen el contenido del contenedor, su entorno operativo y las interdependencias de contenedor, mientras que los equipos de operaciones tomar las imágenes compiladas junto con el manifiesto y se ejecutan en su sistema de orquestación.

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>Introducción a un genérico flujo de trabajo ciclo de vida-to-end Docker aplicación

Figura 2-2 presenta un flujo de trabajo más detallada para un ciclo de vida de aplicaciones de Docker, centrándose en esta instancia en activos y actividades específicas de DevOps.

![](./media/image2.png)

Figura 2-2: Flujo de trabajo de alto nivel para el ciclo de vida de la aplicación en contenedores de Docker

Todo comienza con el desarrollador, que comienza a escribir código en el flujo de trabajo de bucle interno. El escenario de bucle interno es donde los desarrolladores definen todo lo que ocurre antes de insertar código en el repositorio de código (por ejemplo, un sistema de control de código fuente como Git). Una vez confirmada, desencadena el repositorio de integración continua (CI) y el resto del flujo de trabajo.

El bucle interno básicamente consta de los pasos típicos, como "código", "run", "test","y"debug", además de los pasos adicionales directamente antes de ejecutar la aplicación localmente. Esto es cuando el programador se ejecuta y prueba la aplicación como un contenedor de Docker. El flujo de trabajo de bucle interno se explican en las secciones siguientes.

Dar un paso atrás para observar el flujo de trabajo end-to-end, el flujo de trabajo de DevOps es más que una tecnología o un conjunto de herramientas: es una actitud que requiere la evolución de referencia cultural. Resulta que las personas, procesos y las herramientas adecuadas para realizar su ciclo de vida de aplicación más rápido y más predecible. Las empresas que adoptan un flujo de trabajo en contenedores normalmente reestructuración sus organizaciones para representar las personas y procesos que coinciden con el flujo de trabajo en contenedores.

Practicar DevOps puede ayudar a los equipos a responder con mayor rapidez conjuntamente presiones competitivas reemplazando los procesos manuales propensos a errores con la automatización, lo que resulta en rastreabilidad mejorada y flujos de trabajo repetibles. Las organizaciones también pueden administrar entornos de manera más eficaz y darse cuenta de ahorro de costos con una combinación de servidores locales y recursos en la nube, así como herramientas estrechamente integradas.

Al implementar el flujo de trabajo de DevOps para aplicaciones de Docker, verá que las tecnologías de Docker están presentes en casi cada etapa del flujo de trabajo, desde el cuadro de desarrollo mientras trabaja en el bucle interno (código, ejecutar, depurar), en la fase de compilación-test-CI y, por supuesto, en la producción y entornos de ensayo y al implementar los contenedores en esos entornos.

Mejora de prácticas de calidad ayuda a identificar los defectos al principio del ciclo de desarrollo, lo que reduce el costo de corregirlos. Con la inclusión del entorno y dependencias en la imagen y adoptar una filosofía de la implementación de la misma imagen en varios entornos, promover una disciplina de extraer las configuraciones específicas del entorno que las implementaciones sean más confiables.

Datos enriquecidos obtenidos a través de la instrumentación efectivo (supervisión y diagnóstico) proporcionan una visión de los problemas de rendimiento y el comportamiento de usuario para guiar las inversiones y las prioridades de futuras.

DevOps debe considerarse un viaje, no un destino. Debe implementarse incrementalmente a través de los proyectos adecuadamente con ámbito desde el que puede demostrar éxito, aprender y desarrollar.

## <a name="benefits-of-devops-for-containerized-applications"></a>Ventajas de DevOps para aplicaciones en contenedor

Estas son algunas de las ventajas más importantes proporcionadas por un flujo de trabajo de DevOps sólida:

-   Entregar software de mayor calidad con más rapidez y con un mejor cumplimiento

-   Unidad ajustes y la mejora continua de versiones anteriores y más económico

-   Aumentar la transparencia y colaboración entre las partes interesadas implicadas en la entrega y el software operativo

-   Controlar los costos y utilizar recursos aprovisionados de forma más eficaz mientras se minimizan los riesgos de seguridad

-   Bien con muchos de sus inversiones existentes de DevOps, incluidas las inversiones en código abierto de Plug and play

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](../Microsoft-platform-tools-containerized-apps/index.md)