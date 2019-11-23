---
title: serialización de datos con la interoperabilidad COM
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
ms.openlocfilehash: 24fa390c94baaa0fe009ebe513f2eb7aa34d34fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113996"
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="b1cb7-102">serialización de datos con la interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="b1cb7-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="b1cb7-103">La interoperabilidad COM proporciona compatibilidad para usar objetos COM desde código administrado y para exponer objetos administrados en COM.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="b1cb7-104">La compatibilidad con el cálculo de referencias de datos desde y hacia COM es exhaustiva y el comportamiento de serialización casi siempre es correcto.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="b1cb7-105">Windows SDK incluye las siguientes herramientas de interoperabilidad COM:</span><span class="sxs-lookup"><span data-stu-id="b1cb7-105">The Windows SDK includes the following COM interop tools:</span></span>  
  
- <span data-ttu-id="b1cb7-106">[Importador de la biblioteca de tipos (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), que convierte una biblioteca de tipos COM en un ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-106">[Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="b1cb7-107">Desde este ensamblado, el servicio de cálculo de referencias de interoperabilidad genera contenedores que realizan el cálculo de referencias de datos entre la memoria administrada y la no administrada.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
- <span data-ttu-id="b1cb7-108">[Exportador de la biblioteca de tipos (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), que crea una biblioteca de tipos COM a partir un ensamblado y genera un contenedor que realiza la serialización durante las llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-108">[Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="b1cb7-109">Las secciones siguientes se vinculan a los temas que describen los procesos para personalizar los contenedores de interoperabilidad si puede (o debe) suministrar información adicional sobre tipos al contador al serializador.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1cb7-110">Esta sección</span><span class="sxs-lookup"><span data-stu-id="b1cb7-110">In This Section</span></span>  
<span data-ttu-id="b1cb7-111">[Creación manual de contenedores](how-to-create-wrappers-manually.md) </span><span class="sxs-lookup"><span data-stu-id="b1cb7-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) </span></span>  
<span data-ttu-id="b1cb7-112">Describe cómo crear manualmente un contenedor COM en código fuente administrado.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-112">Describes how to create a COM wrapper manually in managed source code.</span></span> 
 
 [<span data-ttu-id="b1cb7-113">Cómo: Migrar código administrado DCOM a WCF</span><span class="sxs-lookup"><span data-stu-id="b1cb7-113">How to: Migrate Managed-Code DCOM to WCF</span></span>](how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="b1cb7-114">Describe cómo migrar código DCOM administrado a WCF para obtener la solución más segura.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-114">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b1cb7-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b1cb7-115">Related Sections</span></span>  
 <span data-ttu-id="b1cb7-116">[Tipos de datos COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b1cb7-116">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>  
 <span data-ttu-id="b1cb7-117">Proporciona los tipos de datos administrados y no administrados correspondientes.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-117">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="b1cb7-118">[Personalización de contenedores CCW](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b1cb7-118">[Customizing COM Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span></span>  
 <span data-ttu-id="b1cb7-119">Describe cómo serializar tipos de datos explícitamente mediante el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-119">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="b1cb7-120">[Personalización de contenedores RCW](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b1cb7-120">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>  
 <span data-ttu-id="b1cb7-121">Describe cómo ajustar el comportamiento de cálculo de referencias de tipos en un ensamblado de interoperabilidad y cómo definir tipos COM manualmente.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-121">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="b1cb7-122">[Interoperabilidad COM avanzada](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b1cb7-122">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>  
 <span data-ttu-id="b1cb7-123">Proporciona vínculos a más información sobre la incorporación de componentes COM en una aplicación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-123">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="b1cb7-124">[Resumen de la conversión de ensamblados en bibliotecas de tipos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b1cb7-124">[Assembly to Type Library Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span></span>  
 <span data-ttu-id="b1cb7-125">Describe el proceso de conversión de la exportación de ensamblado a biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-125">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="b1cb7-126">[Resumen de la conversión de bibliotecas de tipos en ensamblados](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b1cb7-126">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>  
 <span data-ttu-id="b1cb7-127">Describe el proceso de conversión de la importación de biblioteca de tipos a ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-127">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="b1cb7-128">[Interoperar mediante tipos genéricos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b1cb7-128">[Interoperating Using Generic Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span></span>  
 <span data-ttu-id="b1cb7-129">Describe qué acciones se admiten al usar tipos genéricos para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="b1cb7-129">Describes which actions are supported when using generic types for COM interoperability.</span></span>
