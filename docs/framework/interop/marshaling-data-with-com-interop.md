---
title: serialización de datos con la interoperabilidad COM
description: Consulte los artículos que tratan de la serialización de datos con la interoperabilidad COM. Las herramientas Tlbimp.exe y Tlbexp.exe realizan conversiones entre una biblioteca de tipos COM y un ensamblado de interoperabilidad.
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
ms.openlocfilehash: bcbd2c50fcbd9af3f2eead57ac2e26f8db0c6ad6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275949"
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="24823-104">serialización de datos con la interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="24823-104">Marshaling Data with COM Interop</span></span>

<span data-ttu-id="24823-105">La interoperabilidad COM proporciona compatibilidad para usar objetos COM desde código administrado y para exponer objetos administrados en COM.</span><span class="sxs-lookup"><span data-stu-id="24823-105">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="24823-106">La compatibilidad con el cálculo de referencias de datos desde y hacia COM es exhaustiva y el comportamiento de serialización casi siempre es correcto.</span><span class="sxs-lookup"><span data-stu-id="24823-106">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="24823-107">Windows SDK incluye las siguientes herramientas de interoperabilidad COM:</span><span class="sxs-lookup"><span data-stu-id="24823-107">The Windows SDK includes the following COM interop tools:</span></span>  
  
- <span data-ttu-id="24823-108">[Importador de la biblioteca de tipos (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), que convierte una biblioteca de tipos COM en un ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="24823-108">[Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="24823-109">Desde este ensamblado, el servicio de cálculo de referencias de interoperabilidad genera contenedores que realizan el cálculo de referencias de datos entre la memoria administrada y la no administrada.</span><span class="sxs-lookup"><span data-stu-id="24823-109">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
- <span data-ttu-id="24823-110">[Exportador de la biblioteca de tipos (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), que crea una biblioteca de tipos COM a partir un ensamblado y genera un contenedor que realiza la serialización durante las llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="24823-110">[Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="24823-111">Las secciones siguientes se vinculan a los temas que describen los procesos para personalizar los contenedores de interoperabilidad si puede (o debe) suministrar información adicional sobre tipos al contador al serializador.</span><span class="sxs-lookup"><span data-stu-id="24823-111">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24823-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="24823-112">In This Section</span></span>  

<span data-ttu-id="24823-113">[Cómo: para la creación manual de contenedores](how-to-create-wrappers-manually.md) Describe cómo crear manualmente un contenedor COM en código fuente administrado.</span><span class="sxs-lookup"><span data-stu-id="24823-113">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) Describes how to create a COM wrapper manually in managed source code.</span></span>

 [<span data-ttu-id="24823-114">Cómo: Migrar código administrado DCOM a WCF</span><span class="sxs-lookup"><span data-stu-id="24823-114">How to: Migrate Managed-Code DCOM to WCF</span></span>](how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="24823-115">Describe cómo migrar código DCOM administrado a WCF para obtener la solución más segura.</span><span class="sxs-lookup"><span data-stu-id="24823-115">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="24823-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="24823-116">Related Sections</span></span>  

 <span data-ttu-id="24823-117">[Tipos de datos COM](/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24823-117">[COM Data Types](/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>  
 <span data-ttu-id="24823-118">Proporciona los tipos de datos administrados y no administrados correspondientes.</span><span class="sxs-lookup"><span data-stu-id="24823-118">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="24823-119">[Personalización de contenedores CCW](/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24823-119">[Customizing COM Callable Wrappers](/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span></span>  
 <span data-ttu-id="24823-120">Describe cómo serializar tipos de datos explícitamente mediante el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="24823-120">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="24823-121">[Personalización de contenedores RCW](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24823-121">[Customizing Runtime Callable Wrappers](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>  
 <span data-ttu-id="24823-122">Describe cómo ajustar el comportamiento de cálculo de referencias de tipos en un ensamblado de interoperabilidad y cómo definir tipos COM manualmente.</span><span class="sxs-lookup"><span data-stu-id="24823-122">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="24823-123">[Interoperabilidad COM avanzada](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24823-123">[Advanced COM Interoperability](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>  
 <span data-ttu-id="24823-124">Proporciona vínculos a más información sobre la incorporación de componentes COM en una aplicación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="24823-124">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="24823-125">[Resumen de la conversión de ensamblados en bibliotecas de tipos](/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24823-125">[Assembly to Type Library Conversion Summary](/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span></span>  
 <span data-ttu-id="24823-126">Describe el proceso de conversión de la exportación de ensamblado a biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="24823-126">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="24823-127">[Resumen de la conversión de bibliotecas de tipos en ensamblados](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24823-127">[Type Library to Assembly Conversion Summary](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>  
 <span data-ttu-id="24823-128">Describe el proceso de conversión de la importación de biblioteca de tipos a ensamblado.</span><span class="sxs-lookup"><span data-stu-id="24823-128">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="24823-129">[Interoperar mediante tipos genéricos](/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24823-129">[Interoperating Using Generic Types](/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span></span>  
 <span data-ttu-id="24823-130">Describe qué acciones se admiten al usar tipos genéricos para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="24823-130">Describes which actions are supported when using generic types for COM interoperability.</span></span>
