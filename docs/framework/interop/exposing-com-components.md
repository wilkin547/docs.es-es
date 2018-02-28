---
title: Exponer componentes COM en .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c082ec115370ba60839d88e5af7df3585a8f8455
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="9c8dc-102">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c8dc-102">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="9c8dc-103">En esta sección se resume el proceso necesario para exponer un componente COM existente a código administrado.</span><span class="sxs-lookup"><span data-stu-id="9c8dc-103">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="9c8dc-104">Para obtener más detalles sobre cómo escribir servidores COM que se integren estrechamente con .NET Framework, vea [Consideraciones de diseño para interoperaciones](https://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9c8dc-104">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](https://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689(v=vs.100)).</span></span>
  
 <span data-ttu-id="9c8dc-105">Los componentes COM existentes son recursos valiosos en código administrado como aplicaciones empresariales de nivel medio o funcionalidad aislada.</span><span class="sxs-lookup"><span data-stu-id="9c8dc-105">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="9c8dc-106">Un componente ideal tiene un ensamblado de interoperabilidad primario y se ajusta totalmente a los estándares de programación impuestos por COM.</span><span class="sxs-lookup"><span data-stu-id="9c8dc-106">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="9c8dc-107">Para exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c8dc-107">To expose COM components to the .NET Framework</span></span>  
  
1.  <span data-ttu-id="9c8dc-108">[Importe una biblioteca de tipos como un ensamblado](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="9c8dc-108">[Import a type library as an assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="9c8dc-109">Common Language Runtime requiere metadatos para todos los tipos, incluidos los tipos COM.</span><span class="sxs-lookup"><span data-stu-id="9c8dc-109">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="9c8dc-110">Hay varias maneras de obtener un ensamblado que contiene tipos COM importados como metadatos.</span><span class="sxs-lookup"><span data-stu-id="9c8dc-110">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2.  <span data-ttu-id="9c8dc-111">[Cree tipos COM en código administrado](http://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span><span class="sxs-lookup"><span data-stu-id="9c8dc-111">[Create COM types in managed Code](http://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span></span>  
  
     <span data-ttu-id="9c8dc-112">Puede inspeccionar los tipos COM, activar instancias e invocar métodos en el objeto COM de la misma manera que lo hace para cualquier tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="9c8dc-112">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3.  <span data-ttu-id="9c8dc-113">[Compile un proyecto de interoperabilidad](../../../docs/framework/interop/compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="9c8dc-113">[Compile an interop project](../../../docs/framework/interop/compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="9c8dc-114">El [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] proporciona compiladores para varios lenguajes compatibles con Common Language Specification (CLS), incluidos [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# y C++.</span><span class="sxs-lookup"><span data-stu-id="9c8dc-114">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] provides compilers for several languages compliant with the Common Language Specification (CLS), including [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++.</span></span>  
  
4.  <span data-ttu-id="9c8dc-115">[Implemente una aplicación de interoperabilidad](../../../docs/framework/interop/deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="9c8dc-115">[Deploy an interop application](../../../docs/framework/interop/deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="9c8dc-116">Las aplicaciones de interoperabilidad se implementan mejor como ensamblados firmados [con nombre seguro](../../../docs/framework/app-domains/strong-named-assemblies.md) en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9c8dc-116">Interop applications are best deployed as [strong-named](../../../docs/framework/app-domains/strong-named-assemblies.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c8dc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c8dc-117">See Also</span></span>  
 <span data-ttu-id="9c8dc-118">[Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="9c8dc-118">[Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md)</span></span>  
 [<span data-ttu-id="9c8dc-119">Consideraciones de diseño para interoperaciones</span><span class="sxs-lookup"><span data-stu-id="9c8dc-119">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689)  
 [<span data-ttu-id="9c8dc-120">Ejemplo de interoperabilidad COM: cliente .NET y servidor COM</span><span class="sxs-lookup"><span data-stu-id="9c8dc-120">COM Interop Sample: .NET Client and COM Server</span></span>](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)  
 [<span data-ttu-id="9c8dc-121">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="9c8dc-121">Language Independence and Language-Independent Components</span></span>](../../../docs/standard/language-independence-and-language-independent-components.md)  
 [<span data-ttu-id="9c8dc-122">Gacutil.exe (Herramienta Caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="9c8dc-122">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
