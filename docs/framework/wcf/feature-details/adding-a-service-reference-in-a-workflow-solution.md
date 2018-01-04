---
title: "Agregar una referencia de servicio en una solución de flujo de trabajo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee974ee5a9f4564b0e44256bc4773f9898d89fc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a><span data-ttu-id="10b72-102">Agregar una referencia de servicio en una solución de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="10b72-102">Adding a Service Reference in a Workflow Solution</span></span>
<span data-ttu-id="10b72-103">Si se agrega una referencia de servicio en una aplicación de flujo de trabajo, el resultado es ligeramente distinto que una aplicación WCF normal.</span><span class="sxs-lookup"><span data-stu-id="10b72-103">Adding a service reference in a workflow application works a little differently than a regular WCF application.</span></span> <span data-ttu-id="10b72-104">Cuando seleccione Agregar referencia de servicio y especifique la dirección URL en el servicio, se descargan los metadatos y se generan las actividades personalizadas que le permiten llamar al servicio WCF o al servicio de flujo de trabajo WCF al que agregó una referencia.</span><span class="sxs-lookup"><span data-stu-id="10b72-104">When you select Add Service Reference and specify the URL to the service the metadata is downloaded and custom activities are generated that allow you to call the WCF service or WCF workflow service you added a reference to.</span></span> <span data-ttu-id="10b72-105">Después de agregar una referencia de servicio, recompile la solución para que se compilen las actividades generadas.</span><span class="sxs-lookup"><span data-stu-id="10b72-105">After adding a service reference, rebuild the solution so the generated activities are built.</span></span> <span data-ttu-id="10b72-106">Aparecerán en el cuadro de herramientas del diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="10b72-106">They will then appear in the workflow designer toolbox.</span></span> <span data-ttu-id="10b72-107">Tenga en cuenta, no obstante, que esto solo funcionará si agrega una referencia de servicio en una solución de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="10b72-107">Note however, that this will only work if you are adding a service reference within a workflow solution.</span></span> <span data-ttu-id="10b72-108">La difusión por web siguiente muestra cómo agregar una referencia de servicio en otros tipos de proyectos: [llamar a un servicio WCF desde un flujo de trabajo en un proyecto Web](http://go.microsoft.com/fwlink/?LinkId=207725).</span><span class="sxs-lookup"><span data-stu-id="10b72-108">The following web cast shows how to add a service reference in other types of projects: [Calling a WCF Service from a Workflow in a Web Project](http://go.microsoft.com/fwlink/?LinkId=207725).</span></span>  
  
 <span data-ttu-id="10b72-109">Si agrega dos o más referencias de servicio a servicios que contengan el mismo nombre de operación, se producirá un problema.</span><span class="sxs-lookup"><span data-stu-id="10b72-109">Adding two or more service references to services that contain the same operation name will cause a problem.</span></span> <span data-ttu-id="10b72-110">Las actividades generadas llamarán solo a la primera operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="10b72-110">The generated activities will call only the first service operation.</span></span> <span data-ttu-id="10b72-111">Para solucionar este problema cambie el nombre de las operaciones de servicio para que sean distintas o cambie el nombre de la configuración de punto de conexión de cada actividad generada.</span><span class="sxs-lookup"><span data-stu-id="10b72-111">To work around this issue rename the service operations so they are different or change the endpoint configuration name within each generated activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10b72-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="10b72-112">See Also</span></span>  
 [<span data-ttu-id="10b72-113">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="10b72-113">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="10b72-114">Creación de un servicio de flujo de trabajo que llame a otro servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="10b72-114">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)  
 [<span data-ttu-id="10b72-115">Llamar a un servicio WCF desde un flujo de trabajo en un proyecto Web</span><span class="sxs-lookup"><span data-stu-id="10b72-115">Calling a WCF Service from a Workflow in a Web Project</span></span>](http://go.microsoft.com/fwlink/?LinkId=207725)
