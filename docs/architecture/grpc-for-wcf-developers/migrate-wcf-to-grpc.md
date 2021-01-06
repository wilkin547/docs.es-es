---
title: Migración de una solución WCF a gRPC-gRPC para desarrolladores de WCF
description: Cómo migrar distintos tipos de servicios WCF al equivalente en gRPC.
ms.date: 12/15/2020
ms.openlocfilehash: 3bd35cb6119368ff3db3be9ab5fabf89f2652b29
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97937966"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a>Migración de una solución WCF a gRPC

En este capítulo se describe cómo trabajar con proyectos de ASP.NET Core 5,0 gRPC y se muestra cómo migrar distintos tipos de servicios de Windows Communication Foundation (WCF) al equivalente de gRPC:

- Cree un proyecto ASP.NET Core 5,0 gRPC.
- Operaciones simples de solicitud-respuesta para el RPC unario de gRPC.
- Operaciones unidireccionales al RPC de streaming de cliente de gRPC.
- Servicios de dúplex completo para gRPCr RPC de streaming bidireccional.

También hay una comparación entre el uso de servicios de streaming y campos repetidos para devolver conjuntos de valores, y se explica el uso de bibliotecas de cliente al final del capítulo.

La aplicación WCF de ejemplo es un código auxiliar mínimo de un conjunto de servicios bursátiles. Usa la biblioteca de contenedores de inversión de control (IoC) de código abierto denominada Autofac para la inserción de dependencias. Incluye tres servicios, uno para cada tipo de servicio WCF. Los servicios se tratarán con más detalle en las secciones siguientes. Puede descargar las soluciones de [dotnet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) en github. Los servicios usan datos falsos para minimizar las dependencias externas.

Los ejemplos incluyen las implementaciones WCF y gRPC de cada servicio.

>[!div class="step-by-step"]
>[Anterior](ws-protocols.md)
>[Siguiente](create-project.md)
