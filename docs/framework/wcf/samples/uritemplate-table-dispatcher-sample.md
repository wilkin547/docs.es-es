---
description: 'Más información sobre: ejemplo de distribuidor de tabla de UriTemplate'
title: Ejemplo de distribuidor de tabla de UriTemplate
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: 68cd7e87c9768995210f369e2d55a10ad048e338
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798204"
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="beede-103">Ejemplo de distribuidor de tabla de UriTemplate</span><span class="sxs-lookup"><span data-stu-id="beede-103">UriTemplate Table Dispatcher Sample</span></span>

<span data-ttu-id="beede-104">La clase <xref:System.UriTemplateTable> proporciona una estructura de tabla asociativa similar a un diccionario para trabajar con un conjunto de instancias de <xref:System.UriTemplate>.</span><span class="sxs-lookup"><span data-stu-id="beede-104">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="beede-105">Este ejemplo muestra un motor de distribución básico generado usando `UriTemplateTable`, un escenario de uso común para la clase `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="beede-105">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="beede-106">Este ejemplo muestra los conceptos clave siguientes para la clase `UriTemplateTable`:</span><span class="sxs-lookup"><span data-stu-id="beede-106">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="beede-107">Asociar los delegados a `UriTemplates` en `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="beede-107">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="beede-108">Utilizar <xref:System.UriTemplateTable.MatchSingle%2A> para obtener el delegado del controlador correcto para un URI determinado.</span><span class="sxs-lookup"><span data-stu-id="beede-108">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
- <span data-ttu-id="beede-109">Invocar el delegado de controlador para procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="beede-109">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="beede-110">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="beede-110">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="beede-111">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="beede-111">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="beede-112">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="beede-112">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="beede-113">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="beede-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="beede-114">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="beede-114">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="beede-115">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="beede-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="beede-116">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="beede-116">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="beede-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="beede-117">See also</span></span>

- [<span data-ttu-id="beede-118">Tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="beede-118">UriTemplate Table</span></span>](uritemplate-table-sample.md)
- [<span data-ttu-id="beede-119">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="beede-119">UriTemplate</span></span>](uritemplate-sample.md)
