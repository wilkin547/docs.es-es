---
title: Inicio rápido (Servicios de datos de WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f20ffcf356aa0493b1e2356746d9ad7b27d9a1aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876205"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="70137-102">Inicio rápido (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="70137-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="70137-103">Este inicio rápido le ayudará a familiarizarse con WCF Data Services y el [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] a través de una serie de tareas relacionadas con los temas de [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="70137-103">This quickstart helps you become familiar with WCF Data Services and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="70137-104">¿Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="70137-104">What you'll learn</span></span>

<span data-ttu-id="70137-105">La primera tarea de este tutorial rápido muestra cómo crear un servicio de datos para exponer una fuente de OData desde la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="70137-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="70137-106">En temas posteriores, tendrá acceso a OData fuente mediante un explorador Web y también crear un Windows Presentation Foundation (WPF) aplicación cliente que consume el OData fuente mediante el uso de bibliotecas de cliente.</span><span class="sxs-lookup"><span data-stu-id="70137-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="70137-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="70137-107">Prerequisites</span></span>

<span data-ttu-id="70137-108">Para completar este tutorial rápido, debe instalar los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="70137-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="70137-109">Programa para la mejora</span><span class="sxs-lookup"><span data-stu-id="70137-109">Visual Studio</span></span>

- <span data-ttu-id="70137-110">Una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70137-110">An instance of SQL Server.</span></span> <span data-ttu-id="70137-111">Esto incluye SQL Server Express, que se incluye en una instalación predeterminada de Visual Studio 2015 o como parte de la **procesamiento y almacenamiento de datos** carga de trabajo en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="70137-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017.</span></span>

- <span data-ttu-id="70137-112">Base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="70137-112">The Northwind sample database.</span></span> <span data-ttu-id="70137-113">Para descargar esta base de datos de ejemplo, consulte la página de descargas, [Bases de datos de ejemplo de SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="70137-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="70137-114">Tareas del tutorial rápido de WCF data services</span><span class="sxs-lookup"><span data-stu-id="70137-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="70137-115">Crear el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="70137-115">Create the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

 <span data-ttu-id="70137-116">Defina la aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , defina el modelo de datos, cree el servicio de datos y habilite el acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="70137-116">Define the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="70137-117">Tener acceso al servicio desde un explorador Web</span><span class="sxs-lookup"><span data-stu-id="70137-117">Access the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="70137-118">Inicie el servicio desde Visual Studio y obtenga acceso a él enviando solicitudes GET de HTTP a través de un explorador web a las fuentes expuestas.</span><span class="sxs-lookup"><span data-stu-id="70137-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="70137-119">Crear la aplicación de cliente de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="70137-119">Create the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="70137-120">Crear una aplicación WPF para consumir la fuente de OData, enlazar datos a controles de Windows, cambie los datos en los controles enlazados y, a continuación, devuelva los cambios al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="70137-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="70137-121">Los archivos de proyecto de una versión completada del tutorial rápido se pueden descargar en la página de [ejemplos de documentación de Servicios de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=179994) .</span><span class="sxs-lookup"><span data-stu-id="70137-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="70137-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="70137-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="70137-123">Iniciar el tutorial rápido</span><span class="sxs-lookup"><span data-stu-id="70137-123">Start the quickstart</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="70137-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="70137-124">See also</span></span>

- [<span data-ttu-id="70137-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="70137-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)
