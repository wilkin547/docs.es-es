---
title: Exponer componentes COM en .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f644e4f4ff47e31c0f2aaadb577aa6715b445d29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33388227"
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="b2fb5-102">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b2fb5-102">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="b2fb5-103">En esta sección se resume el proceso necesario para exponer un componente COM existente a código administrado.</span><span class="sxs-lookup"><span data-stu-id="b2fb5-103">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="b2fb5-104">Para obtener más detalles sobre cómo escribir servidores COM que se integren estrechamente con .NET Framework, vea [Consideraciones de diseño para interoperaciones](https://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b2fb5-104">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](https://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689(v=vs.100)).</span></span>
  
 <span data-ttu-id="b2fb5-105">Los componentes COM existentes son recursos valiosos en código administrado como aplicaciones empresariales de nivel medio o funcionalidad aislada.</span><span class="sxs-lookup"><span data-stu-id="b2fb5-105">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="b2fb5-106">Un componente ideal tiene un ensamblado de interoperabilidad primario y se ajusta totalmente a los estándares de programación impuestos por COM.</span><span class="sxs-lookup"><span data-stu-id="b2fb5-106">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="b2fb5-107">Para exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b2fb5-107">To expose COM components to the .NET Framework</span></span>  
  
1.  <span data-ttu-id="b2fb5-108">[Importe una biblioteca de tipos como un ensamblado](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="b2fb5-108">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="b2fb5-109">Common Language Runtime requiere metadatos para todos los tipos, incluidos los tipos COM.</span><span class="sxs-lookup"><span data-stu-id="b2fb5-109">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="b2fb5-110">Hay varias maneras de obtener un ensamblado que contiene tipos COM importados como metadatos.</span><span class="sxs-lookup"><span data-stu-id="b2fb5-110">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2.  <span data-ttu-id="b2fb5-111">[Cree tipos COM en código administrado](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b2fb5-111">[Create COM types in managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).</span></span>  
  
     <span data-ttu-id="b2fb5-112">Puede inspeccionar los tipos COM, activar instancias e invocar métodos en el objeto COM de la misma manera que lo hace para cualquier tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="b2fb5-112">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3.  <span data-ttu-id="b2fb5-113">[Compile un proyecto de interoperabilidad](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="b2fb5-113">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="b2fb5-114">El [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] proporciona compiladores para varios lenguajes compatibles con Common Language Specification (CLS), incluidos [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# y C++.</span><span class="sxs-lookup"><span data-stu-id="b2fb5-114">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] provides compilers for several languages compliant with the Common Language Specification (CLS), including [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++.</span></span>  
  
4.  <span data-ttu-id="b2fb5-115">[Implemente una aplicación de interoperabilidad](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="b2fb5-115">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="b2fb5-116">Las aplicaciones de interoperabilidad se implementan mejor como ensamblados firmados [con nombre seguro](../app-domains/strong-named-assemblies.md) en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b2fb5-116">Interop applications are best deployed as [strong-named](../app-domains/strong-named-assemblies.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2fb5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2fb5-117">See Also</span></span>  
 <span data-ttu-id="b2fb5-118">[Interoperating with Unmanaged Code](index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="b2fb5-118">[Interoperating with Unmanaged Code](index.md)</span></span>  
 <span data-ttu-id="b2fb5-119">[Consideraciones de diseño para interoperaciones](https://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b2fb5-119">[Design Considerations for Interoperation](https://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689(v=vs.100))</span></span>  
 [<span data-ttu-id="b2fb5-120">Ejemplo de interoperabilidad COM: cliente .NET y servidor COM</span><span class="sxs-lookup"><span data-stu-id="b2fb5-120">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)  
 [<span data-ttu-id="b2fb5-121">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="b2fb5-121">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)  
 [<span data-ttu-id="b2fb5-122">Gacutil.exe (Herramienta Caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="b2fb5-122">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
