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
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="1063a-103">Migración de una solución WCF a gRPC</span><span class="sxs-lookup"><span data-stu-id="1063a-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="1063a-104">En este capítulo se describe cómo trabajar con proyectos de ASP.NET Core 3,0 gRPC y se muestra cómo migrar distintos tipos de servicio WCF al equivalente gRPC:</span><span class="sxs-lookup"><span data-stu-id="1063a-104">This chapter will look at how to work with ASP.NET Core 3.0 gRPC projects and demonstrate migrating different types of WCF service to the gRPC equivalent:</span></span>

- <span data-ttu-id="1063a-105">Cree un proyecto ASP.NET Core 3,0 gRPC.</span><span class="sxs-lookup"><span data-stu-id="1063a-105">Create an ASP.NET Core 3.0 gRPC project.</span></span>
- <span data-ttu-id="1063a-106">Operaciones simples de solicitud-respuesta para el RPC unario de gRPC.</span><span class="sxs-lookup"><span data-stu-id="1063a-106">Simple Request-Reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="1063a-107">Operaciones unidireccionales al RPC de streaming de cliente de gRPC.</span><span class="sxs-lookup"><span data-stu-id="1063a-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="1063a-108">Servicios dúplex completos para gRPCr RPC de streaming bidireccional.</span><span class="sxs-lookup"><span data-stu-id="1063a-108">Full Duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="1063a-109">También hay una comparación del uso de servicios de streaming en lugar de campos repetidos para devolver conjuntos de datos y el uso de bibliotecas de cliente al final del capítulo.</span><span class="sxs-lookup"><span data-stu-id="1063a-109">There's also a comparison of using streaming services versus repeated fields for returning data sets, and the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="1063a-110">La aplicación WCF de ejemplo es un código auxiliar mínimo de un conjunto de servicios bursátiles, mediante la biblioteca de contenedores de inversión de código abierto (IoC) denominada *Autofac* para la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="1063a-110">The sample WCF application is a minimal stub of a set of stock trading services, using the open-source Inversion of Control (IoC) container library called *Autofac* for dependency injection.</span></span> <span data-ttu-id="1063a-111">Incluye tres servicios, uno para cada tipo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="1063a-111">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="1063a-112">Los servicios se tratarán con más detalle en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="1063a-112">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="1063a-113">Las soluciones se pueden descargar de [dotnet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) en github.</span><span class="sxs-lookup"><span data-stu-id="1063a-113">The solutions can be downloaded from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="1063a-114">Los servicios usan datos falsos para minimizar las dependencias externas.</span><span class="sxs-lookup"><span data-stu-id="1063a-114">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="1063a-115">Los ejemplos incluyen las implementaciones WCF y gRPC de cada servicio.</span><span class="sxs-lookup"><span data-stu-id="1063a-115">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1063a-116">[Anterior](ws-protocols.md)
>[Siguiente](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="1063a-116">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
