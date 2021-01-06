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
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="4ed59-103">Migración de una solución WCF a gRPC</span><span class="sxs-lookup"><span data-stu-id="4ed59-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="4ed59-104">En este capítulo se describe cómo trabajar con proyectos de ASP.NET Core 5,0 gRPC y se muestra cómo migrar distintos tipos de servicios de Windows Communication Foundation (WCF) al equivalente de gRPC:</span><span class="sxs-lookup"><span data-stu-id="4ed59-104">This chapter will describe how to work with ASP.NET Core 5.0 gRPC projects and demonstrate migrating different types of Windows Communication Foundation (WCF) services to the gRPC equivalent:</span></span>

- <span data-ttu-id="4ed59-105">Cree un proyecto ASP.NET Core 5,0 gRPC.</span><span class="sxs-lookup"><span data-stu-id="4ed59-105">Create an ASP.NET Core 5.0 gRPC project.</span></span>
- <span data-ttu-id="4ed59-106">Operaciones simples de solicitud-respuesta para el RPC unario de gRPC.</span><span class="sxs-lookup"><span data-stu-id="4ed59-106">Simple request-reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="4ed59-107">Operaciones unidireccionales al RPC de streaming de cliente de gRPC.</span><span class="sxs-lookup"><span data-stu-id="4ed59-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="4ed59-108">Servicios de dúplex completo para gRPCr RPC de streaming bidireccional.</span><span class="sxs-lookup"><span data-stu-id="4ed59-108">Full-duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="4ed59-109">También hay una comparación entre el uso de servicios de streaming y campos repetidos para devolver conjuntos de valores, y se explica el uso de bibliotecas de cliente al final del capítulo.</span><span class="sxs-lookup"><span data-stu-id="4ed59-109">There's also a comparison of using streaming services versus repeated fields for returning datasets, and there's a discussion of the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="4ed59-110">La aplicación WCF de ejemplo es un código auxiliar mínimo de un conjunto de servicios bursátiles.</span><span class="sxs-lookup"><span data-stu-id="4ed59-110">The sample WCF application is a minimal stub of a set of stock trading services.</span></span> <span data-ttu-id="4ed59-111">Usa la biblioteca de contenedores de inversión de control (IoC) de código abierto denominada Autofac para la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="4ed59-111">It uses the open-source Inversion of Control (IoC) container library called Autofac for dependency injection.</span></span> <span data-ttu-id="4ed59-112">Incluye tres servicios, uno para cada tipo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="4ed59-112">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="4ed59-113">Los servicios se tratarán con más detalle en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="4ed59-113">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="4ed59-114">Puede descargar las soluciones de [dotnet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) en github.</span><span class="sxs-lookup"><span data-stu-id="4ed59-114">You can download the solutions from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="4ed59-115">Los servicios usan datos falsos para minimizar las dependencias externas.</span><span class="sxs-lookup"><span data-stu-id="4ed59-115">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="4ed59-116">Los ejemplos incluyen las implementaciones WCF y gRPC de cada servicio.</span><span class="sxs-lookup"><span data-stu-id="4ed59-116">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4ed59-117">[Anterior](ws-protocols.md)
>[Siguiente](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="4ed59-117">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
