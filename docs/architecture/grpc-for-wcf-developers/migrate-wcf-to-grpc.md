---
title: Migración de una solución WCF a gRPC-gRPC para desarrolladores de WCF
description: Cómo migrar distintos tipos de servicios WCF al equivalente en gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 12e724ab46a33547d352da7a604a5a994e617bc2
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628519"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a>Migración de una solución WCF a gRPC

En este capítulo se describe cómo trabajar con proyectos de ASP.NET Core 3,0 gRPC y se muestra cómo migrar distintos tipos de servicios de Windows Communication Foundation (WCF) al equivalente de gRPC:

- Cree un proyecto ASP.NET Core 3,0 gRPC.
- Operaciones simples de solicitud-respuesta para el RPC unario de gRPC.
- Operaciones unidireccionales al RPC de streaming de cliente de gRPC.
- Servicios de dúplex completo para gRPCr RPC de streaming bidireccional.

También hay una comparación entre el uso de servicios de streaming y campos repetidos para devolver conjuntos de valores, y se explica el uso de bibliotecas de cliente al final del capítulo.

La aplicación WCF de ejemplo es un código auxiliar mínimo de un conjunto de servicios bursátiles. Usa la biblioteca de contenedores de inversión de control (IoC) de código abierto denominada Autofac para la inserción de dependencias. Incluye tres servicios, uno para cada tipo de servicio WCF. Los servicios se tratarán con más detalle en las secciones siguientes. Puede descargar las soluciones de [dotnet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) en github. Los servicios usan datos falsos para minimizar las dependencias externas.

Los ejemplos incluyen las implementaciones WCF y gRPC de cada servicio.

>[!div class="step-by-step"]
>[Anterior](ws-protocols.md)
>[Siguiente](create-project.md)
