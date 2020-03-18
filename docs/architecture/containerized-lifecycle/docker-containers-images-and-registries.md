---
title: Contenedores, imágenes y registros de Docker
description: Conozca el papel clave que, en general, desempeñan los registros en la forma de implementar aplicaciones de Docker.
ms.date: 02/15/2019
ms.openlocfilehash: bfef21cab7be89abaf33b89366d7cff2115a7cc6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72770928"
---
# <a name="docker-containers-images-and-registries"></a>Contenedores, imágenes y registros de Docker

Cuando se utiliza Docker, se crea una aplicación o un servicio que se empaqueta con sus dependencias en una imagen de contenedor. Una imagen es una representación estática de la aplicación o el servicio y de su configuración y las dependencias.

Para ejecutar la aplicación o el servicio, se crea una instancia de la imagen de la aplicación para crear un contenedor, que se ejecutará en el host de Docker. Inicialmente, los contenedores se prueban en un entorno de desarrollo o un PC.

Las imágenes se almacenan en un registro, que sirve como biblioteca de imágenes. Se necesita un registro al implementar en orquestadores de producción. Docker mantiene un registro público a través de [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para distintas colecciones de imágenes, incluido [Azure Container Registry](https://azure.microsoft.com/services/container-registry/). Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.

En la figura 1-4 se muestra cómo se relacionan las imágenes y los registros de Docker con otros componentes. También se muestran las diversas ofertas de registro de los proveedores.

![Diagrama que muestra la taxonomía básica en Docker.](./media/docker-containers-images-and-registries/taxonomy-docker-terms-concepts.png)

**Figura 1-4**. Taxonomía de términos de Docker y conceptos

el registro es como una estantería donde las imágenes se almacenan y están disponibles para extraerlas con el fin de compilar contenedores que ejecuten servicios o aplicaciones web. Hay registros de Docker privados a nivel local y en la nube pública. Docker Hub es que un registro público mantenido por Docker; junto con Docker Trusted Registry, una solución a nivel empresarial, Azure ofrece Azure Container Registry. AWS, Google y otros también tienen registros de contenedor.

Si coloca imágenes en un registro, puede almacenar bits de la aplicación estáticos e inmutables, con todas sus dependencias, a nivel de marco. Luego puede versionar e implementar imágenes en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.

Los registros de imágenes privados, ya sean hospedados localmente o en la nube, se recomiendan cuando:

- Las imágenes no deben compartirse públicamente por motivos de confidencialidad.

- Quiere tener una latencia de red mínima entre las imágenes y el entorno de implementación elegido. Por ejemplo, si el entorno de producción es Azure, probablemente quiera almacenar las imágenes en [Azure Container Registry](https://azure.microsoft.com/services/container-registry/), para que la latencia de red sea mínima. De forma similar, si el entorno de producción es local, puede tener un registro de confianza de Docker local disponible dentro de la misma red local.

>[!div class="step-by-step"]
>[Anterior](docker-terminology.md)
>[Siguiente](road-to-modern-applications-based-on-containers.md)
