---
title: "Registros, imágenes y contenedores de docker"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Registros, imágenes y contenedores de docker"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 224fed34f06d10760b14aa9ecbae6c0e912915cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="docker-containers-images-and-registries"></a>Registros, imágenes y contenedores de docker

Al usar Docker, un desarrollador crea una aplicación o servicio y paquetes y sus dependencias en una imagen de contenedor. Una imagen es una representación estática de la aplicación o el servicio y su configuración y las dependencias.

Para ejecutar la aplicación o servicio, se crea una instancia de imagen de la aplicación para crear un contenedor, que se ejecutarán en el host Docker. Inicialmente se admiten los contenedores en un entorno de desarrollo o PC.

Los desarrolladores deben almacenar imágenes en un registro, que actúa como una biblioteca de imágenes y es necesario cuando se implementa en orchestrators de producción. Mantiene un registro público a través de docker [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para las diferentes colecciones de imágenes. Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.

Figura 2-4 muestra cómo se relacionan las imágenes y los registros en Docker con otros componentes. También muestra las varias ofertas de registro de proveedores.

![](./media/image5.PNG)

**Figura 2-4**. Taxonomía de términos de Docker y conceptos

Colocar imágenes en un registro le permite almacenar fragmentos de la aplicación estáticos e inmutable, incluidas todas sus dependencias en un nivel de marco de trabajo. Esas imágenes pueden ser, a continuación, con control de versiones e implementado en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.

Registros de imagen privada, hospedado en local o en la nube, se recomienda cuando:

-   Las imágenes no deben compartirse públicamente debido a la confidencialidad.

-   Desea tener una latencia de red mínimas entre las imágenes y el entorno de implementación elegido. Por ejemplo, si el entorno de producción es la nube de Azure, probablemente desee almacenar las imágenes en el registro de contenedor de Azure para que la latencia de red será mínima. De forma similar, si el entorno de producción es local, puede tener un local Docker registro de confianza disponibles dentro de la misma red local.

>[!div class="step-by-step"]
[Anterior] (docker-terminology.md) [siguiente] (.. /NET-Core-NET-Framework-Containers/index.MD)
