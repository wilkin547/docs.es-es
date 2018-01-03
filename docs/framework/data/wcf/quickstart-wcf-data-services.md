---
title: "Inicio rápido (Servicios de datos de WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa6711ef5591110c74a1da95358aac4d8a8da655
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="7bb05-102">Inicio rápido (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="7bb05-102">Quickstart (WCF Data Services)</span></span>
<span data-ttu-id="7bb05-103">Este inicio rápido le ayuda a familiarizarse con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] y [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] a través de una serie de tareas que admiten los temas de [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7bb05-103">This quickstart helps you become familiar with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="7bb05-104">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="7bb05-104">What You Will Learn</span></span>  
 <span data-ttu-id="7bb05-105">La primera tarea de este tutorial rápido muestra cómo crear un servicio de datos para exponer una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] procedente de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="7bb05-105">The first task in this quickstart shows how to create a data service to expose an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from the Northwind sample database.</span></span> <span data-ttu-id="7bb05-106">En temas posteriores, podrá obtener acceso a la fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] utilizando un explorador web y, además,  crear una aplicación cliente de [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] que use la fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] a través de las bibliotecas de cliente.</span><span class="sxs-lookup"><span data-stu-id="7bb05-106">In later topics, you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using a Web browser, and also create a [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] client application that consumes the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using client libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7bb05-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7bb05-107">Prerequisites</span></span>  
 <span data-ttu-id="7bb05-108">Para completar este tutorial rápido, debe instalar los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="7bb05-108">To complete this quickstart, you must install the following components:</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]<span data-ttu-id="7bb05-109">.</span><span class="sxs-lookup"><span data-stu-id="7bb05-109">.</span></span>  
  
-   <span data-ttu-id="7bb05-110">Una instancia de [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bb05-110">An instance of [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7bb05-111">Esto incluye SQL Server Express, que está incluido en una instalación predeterminada de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bb05-111">This includes SQL Server Express, which is included in a default installation of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="7bb05-112">Base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="7bb05-112">The Northwind sample database.</span></span> <span data-ttu-id="7bb05-113">Para descargar esta base de datos de ejemplo, consulte la página de descargas, [Bases de datos de ejemplo de SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="7bb05-113">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="7bb05-114">Tareas del tutorial rápido de WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="7bb05-114">WCF Data Services Quickstart Tasks</span></span>  
 [<span data-ttu-id="7bb05-115">Crear el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="7bb05-115">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
 <span data-ttu-id="7bb05-116">Defina la aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , defina el modelo de datos, cree el servicio de datos y habilite el acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="7bb05-116">Define the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application, define the data model, create the data service, and enable access to resources.</span></span>  
  
 [<span data-ttu-id="7bb05-117">Acceso al servicio desde un explorador web</span><span class="sxs-lookup"><span data-stu-id="7bb05-117">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
 <span data-ttu-id="7bb05-118">Inicie el servicio desde [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] y obtenga acceso a él enviando solicitudes GET de HTTP a través de un explorador web a las fuentes expuestas.</span><span class="sxs-lookup"><span data-stu-id="7bb05-118">Start the service from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>  
  
 [<span data-ttu-id="7bb05-119">Creación de la aplicación cliente de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7bb05-119">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
 <span data-ttu-id="7bb05-120">Cree una aplicación cliente de [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] para usar la fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] , enlace datos a controles de Windows, cambie los datos en los controles enlazados y, a continuación, devuelva los cambios al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="7bb05-120">Create a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] client application to consume the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bb05-121">Los archivos de proyecto de una versión completada del tutorial rápido se pueden descargar en la página de [ejemplos de documentación de Servicios de datos de WCF](http://go.microsoft.com/fwlink/?LinkId=179994) .</span><span class="sxs-lookup"><span data-stu-id="7bb05-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](http://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7bb05-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7bb05-122">Next Steps</span></span>  
 <span data-ttu-id="7bb05-123">[Iniciar el tutorial rápido](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="7bb05-123">[Start the Quickstart](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bb05-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bb05-124">See Also</span></span>  
 [<span data-ttu-id="7bb05-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="7bb05-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)
