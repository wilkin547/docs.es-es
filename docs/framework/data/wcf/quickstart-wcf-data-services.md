---
title: Inicio rápido (Servicios de datos de WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: d0002182c5ae519c36348acdd2587bca499fe72e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975133"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="4855e-102">Inicio rápido (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="4855e-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="4855e-103">Esta guía de inicio rápido le ayudará a familiarizarse con WCF Data Services y el Open Data Protocol (OData) a través de una serie de tareas que admiten los temas de [Introducción](getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4855e-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="4855e-104">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="4855e-104">What you'll learn</span></span>

<span data-ttu-id="4855e-105">En la primera tarea de esta guía de inicio rápido se muestra cómo crear un servicio de datos para exponer una fuente de OData desde la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="4855e-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="4855e-106">En temas posteriores, tendrá acceso a la fuente de OData mediante un explorador Web y también creará una aplicación cliente Windows Presentation Foundation (WPF) que consume la fuente de OData mediante las bibliotecas de cliente.</span><span class="sxs-lookup"><span data-stu-id="4855e-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4855e-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4855e-107">Prerequisites</span></span>

<span data-ttu-id="4855e-108">Para completar este tutorial rápido, debe instalar los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="4855e-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="4855e-109">Programa para la mejora</span><span class="sxs-lookup"><span data-stu-id="4855e-109">Visual Studio</span></span>

- <span data-ttu-id="4855e-110">Instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4855e-110">An instance of SQL Server.</span></span> <span data-ttu-id="4855e-111">Esto incluye SQL Server Express, que se incluye en una instalación predeterminada de Visual Studio 2015, o como parte de la carga de trabajo de **procesamiento y almacenamiento de datos** en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="4855e-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017.</span></span>

- <span data-ttu-id="4855e-112">Base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="4855e-112">The Northwind sample database.</span></span> <span data-ttu-id="4855e-113">Para descargar esta base de datos de ejemplo, consulte la página de descargas, [Bases de datos de ejemplo de SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="4855e-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="4855e-114">Tareas del tutorial rápido de WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="4855e-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="4855e-115">Crear el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="4855e-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="4855e-116">Defina la aplicación ASP.NET, defina el modelo de datos, cree el servicio de datos y habilite el acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="4855e-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="4855e-117">Acceder al servicio desde un explorador Web</span><span class="sxs-lookup"><span data-stu-id="4855e-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="4855e-118">Inicie el servicio desde Visual Studio y obtenga acceso a él enviando solicitudes GET de HTTP a través de un explorador web a las fuentes expuestas.</span><span class="sxs-lookup"><span data-stu-id="4855e-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="4855e-119">Crear la aplicación cliente de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4855e-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="4855e-120">Cree una aplicación de WPF para usar la fuente de OData, enlace datos a controles de Windows, cambie los datos en los controles enlazados y, a continuación, envíe los cambios de vuelta al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="4855e-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="4855e-121">Los archivos de proyecto de una versión completada del tutorial rápido se pueden descargar en la página de [ejemplos de documentación de Servicios de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=179994) .</span><span class="sxs-lookup"><span data-stu-id="4855e-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4855e-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4855e-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4855e-123">Inicio de la guía de inicio rápido</span><span class="sxs-lookup"><span data-stu-id="4855e-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="4855e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="4855e-124">See also</span></span>

- [<span data-ttu-id="4855e-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="4855e-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
