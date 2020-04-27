---
title: Exponer componentes COM en .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
ms.openlocfilehash: 914f72b5e4840555541943620ca2df1f629b0604
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123522"
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="55fa9-102">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="55fa9-102">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="55fa9-103">En esta sección se resume el proceso necesario para exponer un componente COM existente a código administrado.</span><span class="sxs-lookup"><span data-stu-id="55fa9-103">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="55fa9-104">Para obtener más detalles sobre cómo escribir servidores COM que se integren estrechamente con .NET Framework, vea [Consideraciones de diseño para interoperaciones](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="55fa9-104">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span></span>
  
 <span data-ttu-id="55fa9-105">Los componentes COM existentes son recursos valiosos en código administrado como aplicaciones empresariales de nivel medio o funcionalidad aislada.</span><span class="sxs-lookup"><span data-stu-id="55fa9-105">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="55fa9-106">Un componente ideal tiene un ensamblado de interoperabilidad primario y se ajusta totalmente a los estándares de programación impuestos por COM.</span><span class="sxs-lookup"><span data-stu-id="55fa9-106">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="55fa9-107">Para exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="55fa9-107">To expose COM components to the .NET Framework</span></span>  
  
1. <span data-ttu-id="55fa9-108">[Importe una biblioteca de tipos como un ensamblado](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="55fa9-108">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="55fa9-109">Common Language Runtime requiere metadatos para todos los tipos, incluidos los tipos COM.</span><span class="sxs-lookup"><span data-stu-id="55fa9-109">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="55fa9-110">Hay varias maneras de obtener un ensamblado que contiene tipos COM importados como metadatos.</span><span class="sxs-lookup"><span data-stu-id="55fa9-110">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2. <span data-ttu-id="55fa9-111">[Use tipos COM en código administrado](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="55fa9-111">[Use COM types in managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>  
  
     <span data-ttu-id="55fa9-112">Puede inspeccionar los tipos COM, activar instancias e invocar métodos en el objeto COM de la misma manera que lo hace para cualquier tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="55fa9-112">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3. <span data-ttu-id="55fa9-113">[Compile un proyecto de interoperabilidad](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="55fa9-113">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="55fa9-114">Windows SDK proporciona compiladores para varios lenguajes de programación compatibles con Common Language Specification (CLS), como, por ejemplo, Visual Basic, C# y C++.</span><span class="sxs-lookup"><span data-stu-id="55fa9-114">The Windows SDK provides compilers for several languages compliant with the Common Language Specification (CLS), including Visual Basic, C#, and C++.</span></span>  
  
4. <span data-ttu-id="55fa9-115">[Implemente una aplicación de interoperabilidad](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="55fa9-115">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="55fa9-116">Las aplicaciones de interoperabilidad se implementan mejor como ensamblados firmados [con nombre seguro](../../standard/assembly/strong-named.md) en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="55fa9-116">Interop applications are best deployed as [strong-named](../../standard/assembly/strong-named.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55fa9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="55fa9-117">See also</span></span>

- [<span data-ttu-id="55fa9-118">Interoperar con código no administrado</span><span class="sxs-lookup"><span data-stu-id="55fa9-118">Interoperating with Unmanaged Code</span></span>](index.md)
- <span data-ttu-id="55fa9-119">[Consideraciones de diseño para interoperaciones](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="55fa9-119">[Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span></span>
- [<span data-ttu-id="55fa9-120">Ejemplo de interoperabilidad COM: cliente .NET y servidor COM</span><span class="sxs-lookup"><span data-stu-id="55fa9-120">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)
- [<span data-ttu-id="55fa9-121">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="55fa9-121">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="55fa9-122">Gacutil.exe (Herramienta Caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="55fa9-122">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
