---
title: 'Cómo: Migrar el código de cliente de servicio web ASP.NET a Windows Communication Foundation'
ms.date: 03/30/2017
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
ms.openlocfilehash: cb60f9cb2e8f35ee703b049eae9e3d99c1ec7d49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491135"
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a><span data-ttu-id="66a1f-102">Cómo: Migrar el código de cliente de servicio web ASP.NET a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="66a1f-102">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="66a1f-103">El procedimiento siguiente describe los amplios pasos que deben seguirse para migrar el código de cliente de servicio Web ASP.NET a WCF.</span><span class="sxs-lookup"><span data-stu-id="66a1f-103">The following procedure describes the broad steps that need to be followed to migrate ASP.NET Web Service client code to WCF.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="66a1f-104">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="66a1f-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a><span data-ttu-id="66a1f-105">Para migrar un código de cliente de servicio web de ASP.NET a WCF</span><span class="sxs-lookup"><span data-stu-id="66a1f-105">To migrate ASP.NET Web Service client code to WCF</span></span>  
  
1.  <span data-ttu-id="66a1f-106">Asegúrese de que existe un conjunto completo de pruebas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="66a1f-106">Ensure that a comprehensive set of tests exist for the client.</span></span>  
  
2.  <span data-ttu-id="66a1f-107">Utilice Visual Studio 2005 para actualizar la aplicación cliente a .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="66a1f-107">Use Visual Studio 2005 to upgrade the client application to .NET 2.0.</span></span> <span data-ttu-id="66a1f-108">Ejecute el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="66a1f-108">Run the set of tests.</span></span>  
  
3.  <span data-ttu-id="66a1f-109">Elimine el código de cliente de ASP.NET del proyecto de cliente.</span><span class="sxs-lookup"><span data-stu-id="66a1f-109">Remove ASP.NET client code from the client project.</span></span> <span data-ttu-id="66a1f-110">Ese código está en módulos generados mediante la herramienta WSDL.exe.</span><span class="sxs-lookup"><span data-stu-id="66a1f-110">That code is in modules generated using the WSDL.exe tool.</span></span>  
  
4.  <span data-ttu-id="66a1f-111">Generar código de cliente WCF mediante el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="66a1f-111">Generate WCF client code using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="66a1f-112">Agregue ese código al proyecto de cliente y fusione mediante combinación el resultado de configuración con el archivo de configuración existente del cliente.</span><span class="sxs-lookup"><span data-stu-id="66a1f-112">Add that code to the client project and merge the configuration output into the client’s existing configuration file.</span></span>  
  
5.  <span data-ttu-id="66a1f-113">Compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66a1f-113">Compile the application.</span></span> <span data-ttu-id="66a1f-114">Reparar los errores de compilación reemplazando las referencias a los tipos de cliente ASP.NET anteriores con referencias a los nuevos tipos de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="66a1f-114">Repair the compilation errors by replacing references to the former ASP.NET client types with references to the new WCF client types.</span></span>  
  
6.  <span data-ttu-id="66a1f-115">Ejecute el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="66a1f-115">Run the set of tests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a1f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="66a1f-116">See Also</span></span>  
 [<span data-ttu-id="66a1f-117">Migración del código del servicio web ASP.NET a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="66a1f-117">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
