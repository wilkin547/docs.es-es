---
title: Contenedores, imágenes y registros de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 43b76f738fa4b7c89423a5b9fac7ef91f40880c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568737"
---
# <a name="docker-containers-images-and-registries"></a>Contenedores, imágenes y registros de Docker

Al utilizar Docker, cree una aplicación o servicio y paquete y sus dependencias en una imagen de contenedor. Una imagen es una representación estática de la aplicación o el servicio y de su configuración y las dependencias.

Para ejecutar la aplicación o servicio, se crea una instancia de imagen de la aplicación para crear un contenedor, que se ejecutarán en el host Docker. Inicialmente, los contenedores se prueban en un entorno de desarrollo o un PC.

Almacenar imágenes en un registro, que actúa como una biblioteca de imágenes. Necesita un registro cuando se implementa en orchestrators de producción. Docker mantiene un registro público a través de [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para distintas colecciones de imágenes. Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.

Figura 1-4 se muestra cómo se relacionan las imágenes y los registros en Docker con otros componentes. También se muestran las diversas ofertas de registro de los proveedores.

![](./media/image4.png)

Figura 1-4: taxonomía de términos de Docker y conceptos

Al colocar imágenes en un registro, puede almacenar fragmentos de la aplicación estáticos e inmutable, incluidas todas sus dependencias, en un nivel de marco de trabajo. , A continuación, puede versión e implementar imágenes en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.

Registros de imagen privada, hospedado en local o en la nube, se recomienda en las siguientes situaciones:

-   Las imágenes no deben compartirse públicamente por motivos de confidencialidad.

-   Quiere tener una latencia de red mínima entre las imágenes y el entorno de implementación elegido. Por ejemplo, si el entorno de producción es Azure, probablemente desee almacenar las imágenes en el registro de contenedor de Azure para que la latencia de red será mínima. De forma similar, si el entorno de producción es local, puede tener un registro de confianza de Docker local disponible dentro de la misma red local.

>[!div class="step-by-step"]
[Anterior] (docker-terminology.md) [siguiente] (Docker-aplicaciones-ciclo de vida/index.md)
