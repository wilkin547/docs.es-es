---
title: Contenedores como base para la colaboración de DevOps
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a6c33237d129fd269f2c0d1256b98be561673dce
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>Contenedores como base para la colaboración de DevOps

Debido a la naturaleza de la tecnología de Docker y contenedores, los desarrolladores pueden compartir su software y dependencias fácilmente con los entornos de producción y las operaciones de TI mientras se elimina la típica excusa "funciona en mi equipo". Contenedores de resolución conflictos de aplicaciones entre los distintos entornos. De forma indirecta, contenedores y Docker reunir a los desarrolladores y las operaciones de TI más cercano, facilitando la tarea para que puedan colaborar de forma eficaz. Adoptar el flujo de trabajo contenedor proporciona a muchos clientes con la continuidad de DevOps que hayan buscado sino que anteriormente tenían que implementar a través de la configuración más compleja de versión y compilar canalizaciones. Contenedores de simplifican las canalizaciones de compilación y prueba e implementación de DevOps.

![](./media/image1.png)

Figura 2-1: las cargas de trabajo principal por "roles" en el ciclo de vida de aplicaciones en contenedores de Docker

Con los contenedores de Docker, los desarrolladores propios lo que está dentro del contenedor (aplicación y servicio y dependencias a componentes y marcos de trabajo) y los contenedores y los servicios de comportan juntos como una aplicación compuesta por una colección de servicios. Se definen las interdependencias de los varios contenedores en un archivo de docker compose.yml o lo que se podría llamar un *manifiesto de implementación*. Mientras tanto, los equipos de operaciones de TI (administración y profesionales de TI) pueden centrarse en la administración de entornos de producción; infraestructura; escalabilidad; supervisión; y, en última instancia, asegurándose de que las aplicaciones se entrega correctamente para los usuarios finales, sin necesidad de conocer el contenido de los distintos contenedores. Por lo tanto, el nombre "container," recordando la analogía a contenedores de envío del mundo real. Por lo tanto, los propietarios del contenido de un contenedor necesitan no hacen referencia a ellos mismos con cómo se van a enviar el contenedor y los transportes de empresa de envío un contenedor desde su punto de origen a su destino sin saber ni preocuparse sobre el contenido. De forma similar, los programadores pueden crear y posee el contenido dentro de un contenedor de Docker sin necesidad de preocuparse de los mecanismos de "transporte".

En el pilar en el lado izquierdo de la figura 2-1, los desarrolladores escribirán y ejecutan código localmente en contenedores de Docker mediante el uso de Docker para Windows o Mac. Definen el entorno operativo para el código mediante el uso de un Dockerfile que especifica el sistema operativo básico para ejecutar, así como los pasos de compilación para compilar el código en una imagen de Docker. Los desarrolladores definen cómo las imágenes de uno o más interoperará utilizando el mencionado anteriormente *docker compose.yml* manifiesto de implementación del archivo. Cuando se completa el desarrollo local, insertar el código de aplicación además de los archivos de configuración de Docker en el repositorio de código de su elección (es decir, un repositorio Git).

El pilar de DevOps define las canalizaciones de integración (CI) de compilación: continuo con el Dockerfile proporcionado en el repositorio de código. El sistema de CI extrae las imágenes base del contenedor del registro de Docker seleccionada y crea las imágenes de Docker personalizadas para la aplicación. Las imágenes, a continuación, se validan e insertar en el registro de Docker utilizado para las implementaciones en varios entornos.

En el pilar de la derecha, administran los equipos de operaciones implementan aplicaciones e infraestructura en producción mientras supervisa el entorno y las aplicaciones para que puedan ofrecer comentarios e información al equipo de desarrollo acerca de cómo podría ser la aplicación mejorado. Aplicaciones de contenedor se ejecutan normalmente en producción mediante orchestrators de contenedor.

Los dos equipos colaboran a través de una plataforma atractivos (contenedores de Docker) que proporciona una separación de intereses como un contrato, al tiempo que mejora considerablemente la colaboración de los dos equipos en el ciclo de vida de la aplicación. Los desarrolladores de poseen el contenido del contenedor, su entorno operativo y las interdependencias de contenedor, mientras que los equipos de operaciones toman las imágenes integradas junto con el manifiesto y ejecuta en su sistema de orquestación.

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>Introducción a un flujo de ciclo de vida de aplicación de Docker-to-end genérico

Figura 2-2 presenta un flujo de trabajo más detallada de un ciclo de vida de aplicación de Docker, nos centraremos en esta instancia en activos y actividades específicas de DevOps.

![](./media/image2.png)

Figura 2-2: flujo de trabajo alto nivel para el ciclo de vida de la aplicación en contenedores de Docker

El proceso comienza con el desarrollador, que inicia la escritura de código en el flujo de trabajo de bucle interno. La fase de bucle interno es donde los desarrolladores definen todo lo que ocurre antes de insertar código en el repositorio de código (por ejemplo, un sistema de control de código fuente como Git). Una vez confirmada, desencadena el repositorio de integración continua (CI) y el resto del flujo de trabajo.

El bucle interno básicamente consta de los pasos típicos como "código", "run", "test" y "debug", más pasos adicionales directamente antes de ejecutar la aplicación localmente. Esto es cuando el programador se ejecuta y prueba la aplicación como un contenedor de Docker. El flujo de trabajo de bucle interno se explican en las secciones siguientes.

Retrocede un paso para buscar en el flujo de trabajo end-to-end, el flujo de trabajo de DevOps es mayor que una tecnología o un conjunto de herramientas: es un enfoque que requiere la evolución de la referencia cultural. Es personas, procesos y las herramientas adecuadas para realizar su ciclo de vida de aplicación más rápido y más predecible. Las empresas que adoptan un flujo de trabajo en contenedores normalmente reestructuración sus organizaciones para representar las personas y los procesos que coinciden con el flujo de trabajo en contenedores.

Practicando con DevOps puede ayudar a los equipos a responder con mayor rapidez juntos a presiones competitivas al reemplazar procesos manuales propensos a errores con automatización, lo que resulta en flujos de trabajo repetibles y rastreabilidad mejorada. Las organizaciones también pueden administrar entornos de manera más eficaz y tenga en cuenta los ahorros de costo con una combinación de recursos de nube y local, así como herramientas estrechamente integrado.

Al implementar el flujo de trabajo de DevOps para aplicaciones de Docker, verá que las tecnologías de Docker están presentes en casi cada etapa del flujo de trabajo, en el cuadro de desarrollo mientras trabaja en el bucle interno (código, ejecutar, depurar), a la fase de prueba de compilación de CI y, por supuesto, en la producción y entornos de ensayo y al implementar los contenedores en esos entornos.

Para la mejora de prácticas de calidad ayuda a identificar los defectos al principio del ciclo de desarrollo, lo que reduce el costo de su solución. Como el entorno y dependencias en la imagen y adoptar una filosofía de implementación de la misma imagen en varios entornos, promover una disciplina de extraer las configuraciones específicas del entorno realizar implementaciones más confiable.

Datos enriquecidos obtenidas a través de la instrumentación efectivo (supervisión y diagnóstico) proporcionan una visión general de los problemas de rendimiento y el comportamiento de usuario para guiar las inversiones y futuras prioridades.

DevOps debe considerarse un viaje, no un destino. Se debe implementar incrementalmente a través de proyectos adecuadamente con ámbito desde el que puede mostrar correcto, aprender y evolucionan.

## <a name="benefits-of-devops-for-containerized-applications"></a>Ventajas de DevOps para aplicaciones en contenedores

Estas son algunas de las ventajas más importantes que proporciona un flujo de trabajo de DevOps sólido:

-   Entregar software de mayor calidad, más rápido y mejor cumplimiento

-   Unidad ajustes y mejoras continuas anteriormente y resulta más económico

-   Aumentar la transparencia y la colaboración entre las partes interesadas participan en la entrega y el software operativo

-   Controlar los costos y utilizar recursos aprovisionados de forma más eficaz y minimizar los riesgos de seguridad

-   Plug and play bien con muchos de sus inversiones existentes de DevOps, incluidas las inversiones en código abierto

>[!div class="step-by-step"]
[Anterior] (index.md) [siguiente] (.. /Microsoft-Platform-Tools-containerized-Apps/index.MD)
