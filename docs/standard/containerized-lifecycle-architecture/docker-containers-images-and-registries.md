---
title: Contenedores, imágenes y registros de Docker
description: Obtenga información sobre el papel fundamental que los registros de reproducirán generales de la manera de Docker de la implementación de aplicaciones.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: e69490734a03cf58bf8534bc9e31110a11d44c58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795335"
---
# <a name="docker-containers-images-and-registries"></a>Contenedores, imágenes y registros de Docker

Cuando se usa Docker, cree una aplicación o el servicio y el paquete y sus dependencias en una imagen de contenedor. Una imagen es una representación estática de la aplicación o el servicio y de su configuración y las dependencias.

Para ejecutar la aplicación o el servicio, se crea una instancia de la imagen de la aplicación para crear un contenedor, que se ejecutará en el host de Docker. Inicialmente, los contenedores se prueban en un entorno de desarrollo o un PC.

Almacenar imágenes en un registro, que actúa como una biblioteca de imágenes. Necesita un registro cuando se implementa en orquestadores de producción. Docker mantiene un registro público a través de [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para distintas colecciones de imágenes, incluido [Azure Container Registry](https://azure.microsoft.com/services/container-registry/). Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.

Figura 1-4 se muestra cómo se relacionan las imágenes y los registros de Docker a otros componentes. También se muestran las diversas ofertas de registro de los proveedores.

![Taxonomía básica en Docker: El registro es similar a una estantería donde las imágenes se almacenan y están disponibles para extraer para la creación de contenedores para ejecutar servicios o aplicaciones web. Hay privado Docker los registros de forma local y en la nube pública. Docker Hub es que un registro público mantenido por Docker; junto con Docker Trusted Registry, una solución a nivel empresarial, Azure ofrece Azure Container Registry. AWS, Google y otros también tienen registros de contenedor.](./media/image4.png)

**Figura 1-4**. Taxonomía de términos de Docker y conceptos

Al colocar imágenes en un registro, puede almacenar fragmentos de la aplicación estáticos e inmutables, incluidas todas sus dependencias en un nivel de marco. , A continuación, puede versión e implementar imágenes en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.

Los registros de imágenes privados, ya sean hospedados localmente o en la nube, se recomiendan cuando:

- Las imágenes no deben compartirse públicamente por motivos de confidencialidad.

- Quiere tener una latencia de red mínima entre las imágenes y el entorno de implementación elegido. Por ejemplo, si su entorno de producción es Azure, probablemente desea almacenar las imágenes en [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) para que la latencia de red es mínima. De forma similar, si el entorno de producción es local, puede tener un registro de confianza de Docker local disponible dentro de la misma red local.

>[!div class="step-by-step"]
>[Anterior](docker-terminology.md)
>[Siguiente](road-to-modern-applications-based-on-containers.md)
