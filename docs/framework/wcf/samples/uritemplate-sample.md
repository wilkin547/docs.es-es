---
title: Ejemplo UriTemplate
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: 42106daf9f40bbcf0393d3cbb91e6cfda58566ae
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662424"
---
# <a name="uritemplate-sample"></a><span data-ttu-id="7db18-102">Ejemplo UriTemplate</span><span class="sxs-lookup"><span data-stu-id="7db18-102">UriTemplate Sample</span></span>
<span data-ttu-id="7db18-103">La clase <xref:System.UriTemplate> proporciona los métodos por trabajar con conjuntos de URI que comparten una estructura común.</span><span class="sxs-lookup"><span data-stu-id="7db18-103">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="7db18-104">Este ejemplo muestra los siguientes conceptos clave relacionados con `UriTemplate`:</span><span class="sxs-lookup"><span data-stu-id="7db18-104">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
- <span data-ttu-id="7db18-105">Sintaxis para crear plantillas.</span><span class="sxs-lookup"><span data-stu-id="7db18-105">Syntax for creating templates.</span></span>  
  
- <span data-ttu-id="7db18-106">Crear instancias de URI de una `UriTemplate` utilizando los métodos <xref:System.UriTemplate.BindByName%2A> y <xref:System.UriTemplate.BindByPosition%2A>.</span><span class="sxs-lookup"><span data-stu-id="7db18-106">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
- <span data-ttu-id="7db18-107">El método <xref:System.UriTemplateTable.Match%2A>, que es la operación inversa de `BindByName` y `BindByPosition`.</span><span class="sxs-lookup"><span data-stu-id="7db18-107"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7db18-108">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7db18-108">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7db18-109">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7db18-109">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="7db18-110">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7db18-110">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7db18-111">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7db18-111">The samples may already be installed on your computer.</span></span> <span data-ttu-id="7db18-112">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7db18-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7db18-113">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7db18-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7db18-114">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7db18-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="7db18-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7db18-115">See also</span></span>

- [<span data-ttu-id="7db18-116">Tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="7db18-116">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [<span data-ttu-id="7db18-117">Distribuidor de tabla UriTemplate</span><span class="sxs-lookup"><span data-stu-id="7db18-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
