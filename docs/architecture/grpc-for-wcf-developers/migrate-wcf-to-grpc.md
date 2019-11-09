---
title: Migración de una solución WCF a gRPC-gRPC para desarrolladores de WCF
description: Cómo migrar distintos tipos de servicio WCF al equivalente en gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 65c30b777d9981cb3291b846f698f2a69b4498fc
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841502"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a>Migración de una solución WCF a gRPC

En este capítulo se describe cómo trabajar con proyectos de ASP.NET Core 3,0 gRPC y se muestra cómo migrar distintos tipos de servicio WCF al equivalente gRPC:

- Cree un proyecto ASP.NET Core 3,0 gRPC.
- Operaciones simples de solicitud-respuesta para el RPC unario de gRPC.
- Operaciones unidireccionales al RPC de streaming de cliente de gRPC.
- Servicios dúplex completos para gRPCr RPC de streaming bidireccional.

También hay una comparación del uso de servicios de streaming en lugar de campos repetidos para devolver conjuntos de datos y el uso de bibliotecas de cliente al final del capítulo.

La aplicación WCF de ejemplo es un código auxiliar mínimo de un conjunto de servicios bursátiles, mediante la biblioteca de contenedores de inversión de código abierto (IoC) denominada *Autofac* para la inserción de dependencias. Incluye tres servicios, uno para cada tipo de servicio WCF. Los servicios se tratarán con más detalle en las secciones siguientes. Las soluciones se pueden descargar de [dotnet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) en github. Los servicios usan datos falsos para minimizar las dependencias externas.

Los ejemplos incluyen las implementaciones WCF y gRPC de cada servicio.

>[!div class="step-by-step"]
>[Anterior](ws-protocols.md)
>[Siguiente](create-project.md)
