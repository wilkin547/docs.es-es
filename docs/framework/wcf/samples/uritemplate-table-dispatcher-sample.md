---
title: Ejemplo de distribuidor de tabla de UriTemplate
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: 4c5f7172543f575655faafad781a272e355224b6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662415"
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="adc45-102">Ejemplo de distribuidor de tabla de UriTemplate</span><span class="sxs-lookup"><span data-stu-id="adc45-102">UriTemplate Table Dispatcher Sample</span></span>
<span data-ttu-id="adc45-103">La clase <xref:System.UriTemplateTable> proporciona una estructura de tabla asociativa similar a un diccionario para trabajar con un conjunto de instancias de <xref:System.UriTemplate>.</span><span class="sxs-lookup"><span data-stu-id="adc45-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="adc45-104">Este ejemplo muestra un motor de distribución básico generado usando `UriTemplateTable`, un escenario de uso común para la clase `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="adc45-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="adc45-105">Este ejemplo muestra los conceptos clave siguientes para la clase `UriTemplateTable`:</span><span class="sxs-lookup"><span data-stu-id="adc45-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="adc45-106">Asociar los delegados a `UriTemplates` en `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="adc45-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="adc45-107">Utilizar <xref:System.UriTemplateTable.MatchSingle%2A> para obtener el delegado del controlador correcto para un URI determinado.</span><span class="sxs-lookup"><span data-stu-id="adc45-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
- <span data-ttu-id="adc45-108">Invocar el delegado de controlador para procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="adc45-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="adc45-109">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="adc45-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="adc45-110">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="adc45-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="adc45-111">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="adc45-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="adc45-112">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="adc45-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="adc45-113">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="adc45-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="adc45-114">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="adc45-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="adc45-115">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="adc45-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="adc45-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="adc45-116">See also</span></span>

- [<span data-ttu-id="adc45-117">Tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="adc45-117">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [<span data-ttu-id="adc45-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="adc45-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
