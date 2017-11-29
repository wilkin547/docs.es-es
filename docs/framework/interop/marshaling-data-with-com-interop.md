---
title: "serialización de datos con la interoperabilidad COM"
ms.custom: 
ms.date: 09/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2def27790a1727bda524b8c14a93f7b78127a569
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="fb336-102">serialización de datos con la interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="fb336-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="fb336-103">La interoperabilidad COM proporciona compatibilidad para usar objetos COM desde código administrado y para exponer objetos administrados en COM.</span><span class="sxs-lookup"><span data-stu-id="fb336-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="fb336-104">La compatibilidad con el cálculo de referencias de datos desde y hacia COM es exhaustiva y el comportamiento del cálculo de referencias casi siempre es correcto.</span><span class="sxs-lookup"><span data-stu-id="fb336-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="fb336-105">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] incluye las siguientes herramientas de interoperabilidad COM:</span><span class="sxs-lookup"><span data-stu-id="fb336-105">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] includes the following COM interop tools:</span></span>  
  
-   <span data-ttu-id="fb336-106">[Importador de la biblioteca de tipos (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), que convierte una biblioteca de tipos COM en un ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="fb336-106">[Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="fb336-107">Desde este ensamblado, el servicio de serialización de interoperabilidad genera contenedores que realizan el cálculo de referencias de datos entre la memoria administrada y la no administrada.</span><span class="sxs-lookup"><span data-stu-id="fb336-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
-   <span data-ttu-id="fb336-108">[Exportador de la biblioteca de tipos (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), que crea una biblioteca de tipos COM a partir un ensamblado y genera un contenedor que realiza la serialización durante las llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="fb336-108">[Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="fb336-109">En las secciones siguientes se vinculan a temas que describen los procesos para personalizar los contenedores de interoperabilidad si puede (o debe) suministrar información adicional sobre tipos al contador de referencias.</span><span class="sxs-lookup"><span data-stu-id="fb336-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fb336-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fb336-110">In This Section</span></span>  
<span data-ttu-id="fb336-111">[Cómo: crear contenedores manualmente](how-to-create-wrappers-manually.md) </span><span class="sxs-lookup"><span data-stu-id="fb336-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) </span></span>  
<span data-ttu-id="fb336-112">Describe cómo crear manualmente un contenedor COM en código fuente administrado.</span><span class="sxs-lookup"><span data-stu-id="fb336-112">Describes how to create a COM wrapper manually in managed source code.</span></span> 
 
 [<span data-ttu-id="fb336-113">Cómo: Migrar código administrado DCOM a WCF</span><span class="sxs-lookup"><span data-stu-id="fb336-113">How to: Migrate Managed-Code DCOM to WCF</span></span>](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="fb336-114">Describe cómo migrar código DCOM administrado a WCF para la solución más segura.</span><span class="sxs-lookup"><span data-stu-id="fb336-114">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fb336-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="fb336-115">Related Sections</span></span>  
 <span data-ttu-id="fb336-116">[Tipos de datos COM](https://msdn.microsoft.com/en-us/library/sak564ww(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="fb336-116">[COM Data Types](https://msdn.microsoft.com/en-us/library/sak564ww(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="fb336-117">Proporciona los tipos de datos administrados y no administrados correspondientes.</span><span class="sxs-lookup"><span data-stu-id="fb336-117">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="fb336-118">[Personalización de contenedores CCW](https://msdn.microsoft.com/en-us/library/3bwc828w(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="fb336-118">[Customizing COM Callable Wrappers](https://msdn.microsoft.com/en-us/library/3bwc828w(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="fb336-119">Describe cómo calcular explícitamente las referencias de tipos de datos mediante el <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributos en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="fb336-119">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="fb336-120">[Personalización de contenedores RCW](https://msdn.microsoft.com/en-us/library/e753eftz(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="fb336-120">[Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/en-us/library/e753eftz(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="fb336-121">Describe cómo ajustar el comportamiento de serialización de tipos en un ensamblado de interoperabilidad y cómo definir tipos COM manualmente.</span><span class="sxs-lookup"><span data-stu-id="fb336-121">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="fb336-122">[Interoperabilidad COM avanzada](https://msdn.microsoft.com/en-us/library/bd9cdfyx(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="fb336-122">[Advanced COM Interoperability](https://msdn.microsoft.com/en-us/library/bd9cdfyx(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="fb336-123">Proporciona vínculos a más información sobre la incorporación de componentes COM en una aplicación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fb336-123">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="fb336-124">[Resumen de la conversión de ensamblados en bibliotecas de tipos](https://msdn.microsoft.com/en-us/library/xk1120c3(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="fb336-124">[Assembly to Type Library Conversion Summary](https://msdn.microsoft.com/en-us/library/xk1120c3(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="fb336-125">Describe el proceso de conversión de la exportación de ensamblado a biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="fb336-125">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="fb336-126">[Resumen de la conversión de bibliotecas de tipos en ensamblados](https://msdn.microsoft.com/en-us/library/k83zzh38(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="fb336-126">[Type Library to Assembly Conversion Summary](https://msdn.microsoft.com/en-us/library/k83zzh38(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="fb336-127">Describe el proceso de conversión de la importación de biblioteca de tipos a ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fb336-127">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="fb336-128">[Interoperar mediante tipos genéricos](https://msdn.microsoft.com/en-us/library/ms229590(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="fb336-128">[Interoperating Using Generic Types](https://msdn.microsoft.com/en-us/library/ms229590(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="fb336-129">Describe qué acciones se admiten al usar tipos genéricos para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="fb336-129">Describes which actions are supported when using generic types for COM interoperability.</span></span>
