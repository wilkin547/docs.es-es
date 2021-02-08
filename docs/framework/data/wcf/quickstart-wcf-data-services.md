---
description: 'Más información acerca de: Inicio rápido (Servicios de datos de WCF)'
title: Inicio rápido (Servicios de datos de WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: 92a1b8882f6a7db2ed33f032ad434efd06400421
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794954"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="0af07-103">Inicio rápido (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="0af07-103">Quickstart (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="0af07-104">Esta guía de inicio rápido le ayudará a familiarizarse con Servicios de datos de WCF y el Open Data Protocol (OData) a través de una serie de tareas que admiten los temas de [Introducción](getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0af07-104">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="0af07-105">Temas que se abordarán</span><span class="sxs-lookup"><span data-stu-id="0af07-105">What you'll learn</span></span>

<span data-ttu-id="0af07-106">En la primera tarea de esta guía de inicio rápido se muestra cómo crear un servicio de datos para exponer una fuente de OData desde la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="0af07-106">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="0af07-107">En temas posteriores, tendrá acceso a la fuente de OData mediante un explorador Web y también creará una aplicación cliente Windows Presentation Foundation (WPF) que consume la fuente de OData mediante las bibliotecas de cliente.</span><span class="sxs-lookup"><span data-stu-id="0af07-107">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0af07-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0af07-108">Prerequisites</span></span>

<span data-ttu-id="0af07-109">Para completar esta guía de inicio rápido, instale los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="0af07-109">To complete this quickstart, install the following components:</span></span>

- <span data-ttu-id="0af07-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0af07-110">Visual Studio</span></span>

- <span data-ttu-id="0af07-111">Instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0af07-111">An instance of SQL Server.</span></span> <span data-ttu-id="0af07-112">Esto incluye SQL Server Express, que se incluye en una instalación predeterminada de Visual Studio 2015, o como parte de la carga de trabajo de **procesamiento y almacenamiento de datos** en Visual Studio 2017 o posterior.</span><span class="sxs-lookup"><span data-stu-id="0af07-112">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017 or later.</span></span>

- <span data-ttu-id="0af07-113">Base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="0af07-113">The Northwind sample database.</span></span> <span data-ttu-id="0af07-114">Para instalar la base de datos, ejecute el script Transact-SQL desde las bases de datos de [ejemplo Northwind y pubs para Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span><span class="sxs-lookup"><span data-stu-id="0af07-114">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="0af07-115">Tareas del tutorial rápido de WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="0af07-115">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="0af07-116">Crear el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="0af07-116">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="0af07-117">Defina la aplicación ASP.NET, defina el modelo de datos, cree el servicio de datos y habilite el acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="0af07-117">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="0af07-118">Acceder al servicio desde un explorador Web</span><span class="sxs-lookup"><span data-stu-id="0af07-118">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="0af07-119">Inicie el servicio desde Visual Studio y obtenga acceso a él enviando solicitudes GET de HTTP a través de un explorador web a las fuentes expuestas.</span><span class="sxs-lookup"><span data-stu-id="0af07-119">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="0af07-120">Crear la aplicación cliente de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0af07-120">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="0af07-121">Cree una aplicación de WPF para usar la fuente de OData, enlace datos a controles de Windows, cambie los datos en los controles enlazados y, a continuación, envíe los cambios de vuelta al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="0af07-121">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="0af07-122">Los archivos de proyecto de una versión completada del tutorial rápido se pueden descargar desde [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).</span><span class="sxs-lookup"><span data-stu-id="0af07-122">Project files from a completed version of the quickstart can be downloaded from [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0af07-123">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0af07-123">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0af07-124">Inicio de la guía de inicio rápido</span><span class="sxs-lookup"><span data-stu-id="0af07-124">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="0af07-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0af07-125">See also</span></span>

- [<span data-ttu-id="0af07-126">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="0af07-126">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
