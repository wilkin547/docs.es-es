---
title: Ejemplo de tabla UriTemplate
ms.date: 03/30/2017
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
ms.openlocfilehash: c0aed1a49faf74ab9fd463769aab66ad72e74038
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183262"
---
# <a name="uritemplate-table-sample"></a><span data-ttu-id="41007-102">Ejemplo de tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="41007-102">UriTemplate Table Sample</span></span>
<span data-ttu-id="41007-103">La clase <xref:System.UriTemplateTable> proporciona una estructura de tabla asociativa similar a un diccionario para trabajar con un conjunto de instancias de `UriTemplate`.</span><span class="sxs-lookup"><span data-stu-id="41007-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of `UriTemplate` instances.</span></span> <span data-ttu-id="41007-104">Se puede hacer coincidir los identificadores uniformes de recursos (URI) concretos de manera eficaz con todas las plantillas de la tabla y se pueden recuperar los datos asociados con la plantilla con la que coincide.</span><span class="sxs-lookup"><span data-stu-id="41007-104">Specific Uniform Resource Identifiers (URIs) can be matched efficiently against all templates in the table, and data associated with the matched template can be retrieved.</span></span>  
  
 <span data-ttu-id="41007-105">Este ejemplo muestra los conceptos clave siguientes relacionados con la clase `UriTemplateTable`:</span><span class="sxs-lookup"><span data-stu-id="41007-105">This sample demonstrates the following key concepts related to the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="41007-106">Sintaxis para crear instancias de un `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="41007-106">Syntax for instantiating a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="41007-107">Rellenar un `UriTemplateTable` con un conjunto de pares clave/valor.</span><span class="sxs-lookup"><span data-stu-id="41007-107">Populating a `UriTemplateTable` with a set of key/value pairs.</span></span>  
  
- <span data-ttu-id="41007-108">Hacer coincidir un URI de candidato con la tabla usando <xref:System.UriTemplateTable.MatchSingle%2A>.</span><span class="sxs-lookup"><span data-stu-id="41007-108">Matching a candidate URI against the table using <xref:System.UriTemplateTable.MatchSingle%2A>.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="41007-109">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="41007-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="41007-110">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="41007-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="41007-111">Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="41007-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="41007-112">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="41007-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="41007-113">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="41007-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="41007-114">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="41007-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="41007-115">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="41007-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a><span data-ttu-id="41007-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41007-116">See also</span></span>

- [<span data-ttu-id="41007-117">Distribuidor de tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="41007-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
- [<span data-ttu-id="41007-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="41007-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
