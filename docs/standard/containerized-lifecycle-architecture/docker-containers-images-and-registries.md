---
title: "Registros, imágenes y contenedores de docker"
description: "Ciclo de vida de aplicación de Docker en contenedores con herramientas y plataforma de Microsoft"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: b115b25d8ae335aafbe41bac0d694170be7e3c49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="docker-containers-images-and-registries"></a>Registros, imágenes y contenedores de docker

Al utilizar Docker, cree una aplicación o servicio y paquete y sus dependencias en una imagen de contenedor. Una imagen es una representación estática de la aplicación o el servicio y su configuración y las dependencias.

Para ejecutar la aplicación o servicio, se crea una instancia de imagen de la aplicación para crear un contenedor, que se ejecutarán en el host Docker. Inicialmente se admiten los contenedores en un entorno de desarrollo o PC.

Almacenar imágenes en un registro, que actúa como una biblioteca de imágenes. Necesita un registro cuando se implementa en orchestrators de producción. Mantiene un registro público a través de docker [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para las diferentes colecciones de imágenes. Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.

Figura 1-4 se muestra cómo se relacionan las imágenes y los registros en Docker con otros componentes. También muestra las varias ofertas de registro de proveedores.

![](./media/image4.png)

Figura 1-4: taxonomía de términos de Docker y conceptos

Al colocar imágenes en un registro, puede almacenar fragmentos de la aplicación estáticos e inmutable, incluidas todas sus dependencias, en un nivel de marco de trabajo. , A continuación, puede versión e implementar imágenes en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.

Registros de imagen privada, hospedado en local o en la nube, se recomienda en las siguientes situaciones:

-   Las imágenes no deben compartirse públicamente debido a la confidencialidad.

-   Desea tener una latencia de red mínimas entre las imágenes y el entorno de implementación elegido. Por ejemplo, si el entorno de producción es Azure, probablemente desee almacenar las imágenes en el registro de contenedor de Azure para que la latencia de red será mínima. De forma similar, si el entorno de producción es local, puede tener un local Docker registro de confianza disponibles dentro de la misma red local.

>[!div class="step-by-step"]
[Anterior] (docker-terminology.md) [siguiente] (Docker-aplicaciones-ciclo de vida/index.md)
