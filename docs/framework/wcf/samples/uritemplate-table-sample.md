---
description: 'Más información acerca de: ejemplo de tabla UriTemplate'
title: Ejemplo de tabla UriTemplate
ms.date: 03/30/2017
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
ms.openlocfilehash: 505fb810c1543b3526955eccc2d5b2a5d041acb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685431"
---
# <a name="uritemplate-table-sample"></a><span data-ttu-id="8a193-103">Ejemplo de tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="8a193-103">UriTemplate Table Sample</span></span>

<span data-ttu-id="8a193-104">La clase <xref:System.UriTemplateTable> proporciona una estructura de tabla asociativa similar a un diccionario para trabajar con un conjunto de instancias de `UriTemplate`.</span><span class="sxs-lookup"><span data-stu-id="8a193-104">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of `UriTemplate` instances.</span></span> <span data-ttu-id="8a193-105">Se puede hacer coincidir los identificadores uniformes de recursos (URI) concretos de manera eficaz con todas las plantillas de la tabla y se pueden recuperar los datos asociados con la plantilla con la que coincide.</span><span class="sxs-lookup"><span data-stu-id="8a193-105">Specific Uniform Resource Identifiers (URIs) can be matched efficiently against all templates in the table, and data associated with the matched template can be retrieved.</span></span>  
  
 <span data-ttu-id="8a193-106">Este ejemplo muestra los conceptos clave siguientes relacionados con la clase `UriTemplateTable`:</span><span class="sxs-lookup"><span data-stu-id="8a193-106">This sample demonstrates the following key concepts related to the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="8a193-107">Sintaxis para crear instancias de un `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="8a193-107">Syntax for instantiating a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="8a193-108">Rellenar un `UriTemplateTable` con un conjunto de pares clave/valor.</span><span class="sxs-lookup"><span data-stu-id="8a193-108">Populating a `UriTemplateTable` with a set of key/value pairs.</span></span>  
  
- <span data-ttu-id="8a193-109">Hacer coincidir un URI de candidato con la tabla usando <xref:System.UriTemplateTable.MatchSingle%2A>.</span><span class="sxs-lookup"><span data-stu-id="8a193-109">Matching a candidate URI against the table using <xref:System.UriTemplateTable.MatchSingle%2A>.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8a193-110">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a193-110">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8a193-111">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8a193-111">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="8a193-112">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8a193-112">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8a193-113">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8a193-113">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8a193-114">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8a193-114">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="8a193-115">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8a193-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8a193-116">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8a193-116">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a><span data-ttu-id="8a193-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a193-117">See also</span></span>

- [<span data-ttu-id="8a193-118">Distribuidor de tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="8a193-118">UriTemplate Table Dispatcher</span></span>](uritemplate-table-dispatcher-sample.md)
- [<span data-ttu-id="8a193-119">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="8a193-119">UriTemplate</span></span>](uritemplate-sample.md)
