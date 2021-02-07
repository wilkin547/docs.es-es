---
description: 'Más información sobre: ejemplo de UriTemplate'
title: Ejemplo UriTemplate
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: 80e932c06a6819ef7e1e289d9eacab6cd4e55f92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685444"
---
# <a name="uritemplate-sample"></a><span data-ttu-id="05a52-103">Ejemplo UriTemplate</span><span class="sxs-lookup"><span data-stu-id="05a52-103">UriTemplate Sample</span></span>

<span data-ttu-id="05a52-104">La clase <xref:System.UriTemplate> proporciona los métodos por trabajar con conjuntos de URI que comparten una estructura común.</span><span class="sxs-lookup"><span data-stu-id="05a52-104">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="05a52-105">Este ejemplo muestra los siguientes conceptos clave relacionados con `UriTemplate`:</span><span class="sxs-lookup"><span data-stu-id="05a52-105">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
- <span data-ttu-id="05a52-106">Sintaxis para crear plantillas.</span><span class="sxs-lookup"><span data-stu-id="05a52-106">Syntax for creating templates.</span></span>  
  
- <span data-ttu-id="05a52-107">Crear instancias de URI de una `UriTemplate` utilizando los métodos <xref:System.UriTemplate.BindByName%2A> y <xref:System.UriTemplate.BindByPosition%2A>.</span><span class="sxs-lookup"><span data-stu-id="05a52-107">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
- <span data-ttu-id="05a52-108">El método <xref:System.UriTemplateTable.Match%2A>, que es la operación inversa de `BindByName` y `BindByPosition`.</span><span class="sxs-lookup"><span data-stu-id="05a52-108"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="05a52-109">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="05a52-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="05a52-110">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="05a52-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="05a52-111">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="05a52-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="05a52-112">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="05a52-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="05a52-113">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="05a52-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="05a52-114">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="05a52-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="05a52-115">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="05a52-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="05a52-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="05a52-116">See also</span></span>

- [<span data-ttu-id="05a52-117">Tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="05a52-117">UriTemplate Table</span></span>](uritemplate-table-sample.md)
- [<span data-ttu-id="05a52-118">Distribuidor de tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="05a52-118">UriTemplate Table Dispatcher</span></span>](uritemplate-table-dispatcher-sample.md)
