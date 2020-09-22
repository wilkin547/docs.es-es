---
title: Exponer componentes COM en .NET Framework
description: Conozca el proceso de exposición de componentes COM a .NET. Los componentes COM son valiosos en código administrado como aplicaciones empresariales de nivel medio o funcionalidad aislada.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
ms.openlocfilehash: 34dda58d9513874169927164706fafdd95e8ed84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554187"
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="ab126-104">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ab126-104">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="ab126-105">En esta sección se resume el proceso necesario para exponer un componente COM existente a código administrado.</span><span class="sxs-lookup"><span data-stu-id="ab126-105">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="ab126-106">Para obtener más detalles sobre cómo escribir servidores COM que se integren estrechamente con .NET Framework, vea [Consideraciones de diseño para interoperaciones](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ab126-106">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span></span>
  
 <span data-ttu-id="ab126-107">Los componentes COM existentes son recursos valiosos en código administrado como aplicaciones empresariales de nivel medio o funcionalidad aislada.</span><span class="sxs-lookup"><span data-stu-id="ab126-107">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="ab126-108">Un componente ideal tiene un ensamblado de interoperabilidad primario y se ajusta totalmente a los estándares de programación impuestos por COM.</span><span class="sxs-lookup"><span data-stu-id="ab126-108">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="ab126-109">Para exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ab126-109">To expose COM components to the .NET Framework</span></span>  
  
1. <span data-ttu-id="ab126-110">[Importe una biblioteca de tipos como un ensamblado](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="ab126-110">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="ab126-111">Common Language Runtime requiere metadatos para todos los tipos, incluidos los tipos COM.</span><span class="sxs-lookup"><span data-stu-id="ab126-111">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="ab126-112">Hay varias maneras de obtener un ensamblado que contiene tipos COM importados como metadatos.</span><span class="sxs-lookup"><span data-stu-id="ab126-112">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2. <span data-ttu-id="ab126-113">[Use tipos COM en código administrado](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ab126-113">[Use COM types in managed Code](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>  
  
     <span data-ttu-id="ab126-114">Puede inspeccionar los tipos COM, activar instancias e invocar métodos en el objeto COM de la misma manera que lo hace para cualquier tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="ab126-114">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3. <span data-ttu-id="ab126-115">[Compile un proyecto de interoperabilidad](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="ab126-115">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="ab126-116">Windows SDK proporciona compiladores para varios lenguajes de programación compatibles con Common Language Specification (CLS), como, por ejemplo, Visual Basic, C# y C++.</span><span class="sxs-lookup"><span data-stu-id="ab126-116">The Windows SDK provides compilers for several languages compliant with the Common Language Specification (CLS), including Visual Basic, C#, and C++.</span></span>  
  
4. <span data-ttu-id="ab126-117">[Implemente una aplicación de interoperabilidad](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="ab126-117">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="ab126-118">Las aplicaciones de interoperabilidad se implementan mejor como ensamblados firmados [con nombre seguro](../../standard/assembly/strong-named.md) en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ab126-118">Interop applications are best deployed as [strong-named](../../standard/assembly/strong-named.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab126-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab126-119">See also</span></span>

- [<span data-ttu-id="ab126-120">Interoperar con código no administrado</span><span class="sxs-lookup"><span data-stu-id="ab126-120">Interoperating with Unmanaged Code</span></span>](index.md)
- <span data-ttu-id="ab126-121">[Consideraciones de diseño para interoperaciones](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ab126-121">[Design Considerations for Interoperation](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span></span>
- [<span data-ttu-id="ab126-122">Ejemplo de interoperabilidad COM: cliente .NET y servidor COM</span><span class="sxs-lookup"><span data-stu-id="ab126-122">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)
- [<span data-ttu-id="ab126-123">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="ab126-123">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="ab126-124">Gacutil.exe (Herramienta Caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="ab126-124">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
