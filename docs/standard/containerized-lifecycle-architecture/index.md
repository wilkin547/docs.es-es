---
title: Introducción a Containers y Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: c2a6b9802bbb995939d33c5c40ef9c1afa1620e5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148826"
---
# <a name="introduction-to-containers-and-docker"></a>Introducción a Containers y Docker

La inclusión en contenedores es un enfoque de desarrollo de software en el que una aplicación o un servicio, sus dependencias y su configuración (extraídos como archivos de manifiesto de implementación) se empaquetan como una imagen de contenedor. Puede probar la aplicación en contenedor como una unidad e implementarla como una instancia de imagen de contenedor en el sistema operativo host.

Del mismo modo que el sector de transporte de mercancías usa contenedores normalizados para transportar mercancías por barco, tren o camión independientemente de la carga de su interior, los contenedores de software actúan como una unidad estándar de software que puede contener diferentes dependencias y código. La inclusión del software en contenedores permite a los desarrolladores y profesionales de TI implementar tales contenedores en entornos con pocas modificaciones o incluso ninguna.

Los contenedores también aíslan las aplicaciones entre sí en un sistema operativo compartido. Las aplicaciones en contenedor se ejecutan sobre un host de contenedor que a su vez se ejecuta en el sistema operativo (Linux o Windows). Por lo tanto, los contenedores tienen una superficie significativamente menor que las imágenes de máquina virtual (VM).

Cada contenedor puede ejecutar una aplicación web o un servicio al completo, como se muestra en la figura 1-1.

![](./media/image1.png)

Figura 1-1: Varios contenedores ejecutándose en un host de contenedor.

En este ejemplo, el host de Docker es un host de contenedor, y App 1, App 2, Svc 1 y Svc 2 son aplicaciones o servicios en contenedor.

Otra ventaja derivada de la inclusión en contenedores es la escalabilidad. La creación de contenedores para tareas a corto plazo permite escalar horizontalmente con gran rapidez. Desde el punto de vista de la aplicación, *la creación de instancias de una imagen* (la creación de un contenedor) es similar a la creación de instancias de un proceso como un servicio o una aplicación web. Para mayor confiabilidad, sin embargo, al ejecutar varias instancias de la misma imagen en varios servidores de host, normalmente desea que cada contenedor (instancia de imagen) para ejecutar en un servidor host diferente o una máquina virtual en distintos dominios de error.

En resumen, los contenedores ofrecen las ventajas del aislamiento, la portabilidad, la agilidad, la escalabilidad y el control a lo largo de todo el flujo de trabajo del ciclo de vida de la aplicación. La ventaja más importante es el aislamiento que se proporciona entre el desarrollo y las operaciones.

>[!div class="step-by-step"]
>[Siguiente](what-is-docker.md)