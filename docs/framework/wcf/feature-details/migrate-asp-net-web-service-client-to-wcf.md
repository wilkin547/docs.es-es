---
title: "Cómo: Migrar el código de cliente de servicio web ASP.NET a Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b93460fd6d331b43b49f10cf78fc8863ca1d8d88
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a><span data-ttu-id="74417-102">Cómo: Migrar el código de cliente de servicio web ASP.NET a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="74417-102">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="74417-103">El procedimiento siguiente describe los amplios pasos que se han de seguir para migrar el código de cliente del servicio web de ASP.NET a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74417-103">The following procedure describes the broad steps that need to be followed to migrate ASP.NET Web Service client code to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="74417-104">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="74417-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a><span data-ttu-id="74417-105">Para migrar un código de cliente de servicio web de ASP.NET a WCF</span><span class="sxs-lookup"><span data-stu-id="74417-105">To migrate ASP.NET Web Service client code to WCF</span></span>  
  
1.  <span data-ttu-id="74417-106">Asegúrese de que existe un conjunto completo de pruebas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="74417-106">Ensure that a comprehensive set of tests exist for the client.</span></span>  
  
2.  <span data-ttu-id="74417-107">Utilice Visual Studio 2005 para actualizar la aplicación cliente a .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="74417-107">Use Visual Studio 2005 to upgrade the client application to .NET 2.0.</span></span> <span data-ttu-id="74417-108">Ejecute el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="74417-108">Run the set of tests.</span></span>  
  
3.  <span data-ttu-id="74417-109">Elimine el código de cliente de ASP.NET del proyecto de cliente.</span><span class="sxs-lookup"><span data-stu-id="74417-109">Remove ASP.NET client code from the client project.</span></span> <span data-ttu-id="74417-110">Ese código está en módulos generados mediante la herramienta WSDL.exe.</span><span class="sxs-lookup"><span data-stu-id="74417-110">That code is in modules generated using the WSDL.exe tool.</span></span>  
  
4.  <span data-ttu-id="74417-111">Generar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] código de cliente mediante la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="74417-111">Generate [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client code using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="74417-112">Agregue ese código al proyecto de cliente y fusione mediante combinación el resultado de configuración con el archivo de configuración existente del cliente.</span><span class="sxs-lookup"><span data-stu-id="74417-112">Add that code to the client project and merge the configuration output into the client’s existing configuration file.</span></span>  
  
5.  <span data-ttu-id="74417-113">Compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="74417-113">Compile the application.</span></span> <span data-ttu-id="74417-114">Repare los errores de compilación reemplazando las referencias a los tipos de cliente de ASP.NET anteriores por referencias a los nuevos tipos de cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74417-114">Repair the compilation errors by replacing references to the former ASP.NET client types with references to the new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client types.</span></span>  
  
6.  <span data-ttu-id="74417-115">Ejecute el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="74417-115">Run the set of tests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74417-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="74417-116">See Also</span></span>  
 [<span data-ttu-id="74417-117">Cómo: migrar código del servicio Web de ASP.NET a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="74417-117">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
