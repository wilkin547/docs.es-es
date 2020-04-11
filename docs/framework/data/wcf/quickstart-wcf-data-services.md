---
title: Inicio rápido (Servicios de datos de WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f945d33a4fc789b3c73c1c80040fc8527301758b
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121222"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="efca0-102">Inicio rápido (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="efca0-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="efca0-103">Esta guía de inicio rápido le ayuda a familiarizarse con WCF Data Services y el protocolo de datos abiertos (OData) a través de una serie de tareas que admiten los temas de [Introducción](getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="efca0-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="efca0-104">Temas que se abordarán</span><span class="sxs-lookup"><span data-stu-id="efca0-104">What you'll learn</span></span>

<span data-ttu-id="efca0-105">La primera tarea de esta guía de inicio rápido muestra cómo crear un servicio de datos para exponer una fuente de OData de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="efca0-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="efca0-106">En temas posteriores, tendrá acceso a la fuente de OData mediante un explorador web y también creará una aplicación cliente de Windows Presentation Foundation (WPF) que consume la fuente de OData mediante bibliotecas de cliente.</span><span class="sxs-lookup"><span data-stu-id="efca0-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="efca0-107">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="efca0-107">Prerequisites</span></span>

<span data-ttu-id="efca0-108">Para completar esta guía de inicio rápido, instale los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="efca0-108">To complete this quickstart, install the following components:</span></span>

- <span data-ttu-id="efca0-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="efca0-109">Visual Studio</span></span>

- <span data-ttu-id="efca0-110">Una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="efca0-110">An instance of SQL Server.</span></span> <span data-ttu-id="efca0-111">Esto incluye SQL Server Express, que se incluye en una instalación predeterminada de Visual Studio 2015, o como parte de la carga de trabajo de **almacenamiento y procesamiento** de datos en Visual Studio 2017 o posterior.</span><span class="sxs-lookup"><span data-stu-id="efca0-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017 or later.</span></span>

- <span data-ttu-id="efca0-112">Base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="efca0-112">The Northwind sample database.</span></span> <span data-ttu-id="efca0-113">Para instalar la base de datos, ejecute el script DeTransact-SQL desde [Northwind y las bases](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)de datos de ejemplo pubs para Microsoft SQL Server .</span><span class="sxs-lookup"><span data-stu-id="efca0-113">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="efca0-114">Tareas de inicio rápido de servicios de datos WCF</span><span class="sxs-lookup"><span data-stu-id="efca0-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="efca0-115">Crear el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="efca0-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="efca0-116">Defina la aplicación ASP.NET, defina el modelo de datos, cree el servicio de datos y habilite el acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="efca0-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="efca0-117">Acceda al servicio desde un navegador web</span><span class="sxs-lookup"><span data-stu-id="efca0-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="efca0-118">Inicie el servicio desde Visual Studio y obtenga acceso a él enviando solicitudes GET de HTTP a través de un explorador web a las fuentes expuestas.</span><span class="sxs-lookup"><span data-stu-id="efca0-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="efca0-119">Cree la aplicación cliente de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="efca0-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="efca0-120">Cree una aplicación WPF para consumir la fuente de OData, enlazar datos a controles de Windows, cambiar datos en los controles enlazados y, a continuación, enviar los cambios al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="efca0-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="efca0-121">Los archivos de proyecto de una versión completa de la guía de inicio rápido se pueden descargar desde [GitHub.](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span><span class="sxs-lookup"><span data-stu-id="efca0-121">Project files from a completed version of the quickstart can be downloaded from [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).</span></span>

## <a name="next-steps"></a><span data-ttu-id="efca0-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="efca0-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="efca0-123">Inicie la guía de inicio rápido</span><span class="sxs-lookup"><span data-stu-id="efca0-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="efca0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="efca0-124">See also</span></span>

- [<span data-ttu-id="efca0-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="efca0-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
