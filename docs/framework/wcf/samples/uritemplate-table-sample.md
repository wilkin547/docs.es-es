---
title: Ejemplo de tabla UriTemplate
ms.date: 03/30/2017
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
ms.openlocfilehash: 004f02ac1399af093d541bc81fb74f51516fe91e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662436"
---
# <a name="uritemplate-table-sample"></a><span data-ttu-id="d5ce5-102">Ejemplo de tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="d5ce5-102">UriTemplate Table Sample</span></span>
<span data-ttu-id="d5ce5-103">La clase <xref:System.UriTemplateTable> proporciona una estructura de tabla asociativa similar a un diccionario para trabajar con un conjunto de instancias de `UriTemplate`.</span><span class="sxs-lookup"><span data-stu-id="d5ce5-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of `UriTemplate` instances.</span></span> <span data-ttu-id="d5ce5-104">Se puede hacer coincidir los identificadores uniformes de recursos (URI) concretos de manera eficaz con todas las plantillas de la tabla y se pueden recuperar los datos asociados con la plantilla con la que coincide.</span><span class="sxs-lookup"><span data-stu-id="d5ce5-104">Specific Uniform Resource Identifiers (URIs) can be matched efficiently against all templates in the table, and data associated with the matched template can be retrieved.</span></span>  
  
 <span data-ttu-id="d5ce5-105">Este ejemplo muestra los conceptos clave siguientes relacionados con la clase `UriTemplateTable`:</span><span class="sxs-lookup"><span data-stu-id="d5ce5-105">This sample demonstrates the following key concepts related to the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="d5ce5-106">Sintaxis para crear instancias de un `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="d5ce5-106">Syntax for instantiating a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="d5ce5-107">Rellenar un `UriTemplateTable` con un conjunto de pares clave/valor.</span><span class="sxs-lookup"><span data-stu-id="d5ce5-107">Populating a `UriTemplateTable` with a set of key/value pairs.</span></span>  
  
- <span data-ttu-id="d5ce5-108">Hacer coincidir un URI de candidato con la tabla usando <xref:System.UriTemplateTable.MatchSingle%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5ce5-108">Matching a candidate URI against the table using <xref:System.UriTemplateTable.MatchSingle%2A>.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d5ce5-109">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5ce5-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d5ce5-110">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d5ce5-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="d5ce5-111">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d5ce5-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d5ce5-112">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="d5ce5-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d5ce5-113">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d5ce5-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d5ce5-114">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="d5ce5-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d5ce5-115">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="d5ce5-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a><span data-ttu-id="d5ce5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5ce5-116">See also</span></span>

- [<span data-ttu-id="d5ce5-117">Distribuidor de tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="d5ce5-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
- [<span data-ttu-id="d5ce5-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="d5ce5-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
