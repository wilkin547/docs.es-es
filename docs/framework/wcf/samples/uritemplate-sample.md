---
title: Ejemplo UriTemplate
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: e08333235b22e3c24fc6f4855fec43ef8b95fa5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183273"
---
# <a name="uritemplate-sample"></a><span data-ttu-id="e9cfb-102">Ejemplo UriTemplate</span><span class="sxs-lookup"><span data-stu-id="e9cfb-102">UriTemplate Sample</span></span>
<span data-ttu-id="e9cfb-103">La clase <xref:System.UriTemplate> proporciona los métodos por trabajar con conjuntos de URI que comparten una estructura común.</span><span class="sxs-lookup"><span data-stu-id="e9cfb-103">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="e9cfb-104">Este ejemplo muestra los siguientes conceptos clave relacionados con `UriTemplate`:</span><span class="sxs-lookup"><span data-stu-id="e9cfb-104">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
- <span data-ttu-id="e9cfb-105">Sintaxis para crear plantillas.</span><span class="sxs-lookup"><span data-stu-id="e9cfb-105">Syntax for creating templates.</span></span>  
  
- <span data-ttu-id="e9cfb-106">Crear instancias de URI de una `UriTemplate` utilizando los métodos <xref:System.UriTemplate.BindByName%2A> y <xref:System.UriTemplate.BindByPosition%2A>.</span><span class="sxs-lookup"><span data-stu-id="e9cfb-106">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
- <span data-ttu-id="e9cfb-107">El método <xref:System.UriTemplateTable.Match%2A>, que es la operación inversa de `BindByName` y `BindByPosition`.</span><span class="sxs-lookup"><span data-stu-id="e9cfb-107"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e9cfb-108">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9cfb-108">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e9cfb-109">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e9cfb-109">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="e9cfb-110">Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="e9cfb-110">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e9cfb-111">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e9cfb-111">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e9cfb-112">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e9cfb-112">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e9cfb-113">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e9cfb-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e9cfb-114">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e9cfb-114">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="e9cfb-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9cfb-115">See also</span></span>

- [<span data-ttu-id="e9cfb-116">Tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="e9cfb-116">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [<span data-ttu-id="e9cfb-117">Distribuidor de tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="e9cfb-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
