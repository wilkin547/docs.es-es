---
title: Introducción a Containers y Docker
description: Obtenga una introducción de alto nivel de las principales ventajas del uso de Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: aa3ead1cb184e23dd091822368e62f580ed73ee5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785637"
---
# <a name="introduction-to-containers-and-docker"></a>Introducción a Containers y Docker

*Inclusión en contenedores es un enfoque de desarrollo de software en el que una aplicación o servicio, sus dependencias y su configuración (extraídos como archivos de manifiesto de implementación) se empaquetan como una imagen de contenedor. A continuación, puede probar la aplicación en contenedores como una unidad e implementarlo como una instancia de la imagen de contenedor en el sistema operativo (SO) de host.*

Del mismo modo que los contenedores de mercancías permiten su transporte por barco, tren o camión independientemente de la carga de su interior, los contenedores de software actúan como una unidad estándar de implementación de software que puede contener diferentes dependencias y código. De esta manera, la inclusión del software en contenedor permite a los desarrolladores y los profesionales de TI implementarlo en entornos con pocas modificaciones o ninguna en absoluto.

Los contenedores también aíslan las aplicaciones entre sí en un sistema operativo compartido. Las aplicaciones en contenedor se ejecutan sobre un host de contenedor que a su vez se ejecuta en el sistema operativo (Linux o Windows). Contenedores, por tanto, tienen una superficie mucho menor que las imágenes de máquina virtual (VM).

Cada contenedor puede ejecutar una aplicación web completa o un servicio, tal como se muestra en la figura 1-1. En este ejemplo, el host de Docker es un host de contenedor y App1, App2, Svc1 y Svc2 son aplicaciones en contenedores o servicios.

![Dos aplicaciones y dos servicios que se ejecutan en el sistema operativo en una máquina virtual o en un servidor físico](./media/image1.png)

**Figura 1-1**. Varios contenedores ejecutándose en un host de contenedor.

Otra ventaja derivada de la inclusión en contenedores es la escalabilidad. La creación de contenedores para tareas a corto plazo permite escalar horizontalmente con gran rapidez. Desde el punto de vista de la aplicación, la creación de instancias de una imagen (la creación de un contenedor) es similar a la creación de instancias de un proceso como un servicio o una aplicación web. Pero con fines de confiabilidad, cuando ejecute varias instancias de la misma imagen en varios servidores host, seguramente le interesará que cada contenedor (instancia de imagen) se ejecute en un servidor host o máquina virtual diferente en dominios de error distintos.

En resumen, los contenedores ofrecen las ventajas del aislamiento, portabilidad, la agilidad, escalabilidad y control en el flujo de trabajo del ciclo de vida de toda la aplicación. La ventaja más importante es el aislamiento del entorno de desarrollo y operaciones que proporcionan.

>[!div class="step-by-step"]
>[Siguiente](what-is-docker.md)
