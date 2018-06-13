---
title: Interoperabilidad COM en aplicaciones .NET Framework (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: ceef4255321e208911a16db0227890bc6654b8c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642930"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="3d188-102">Interoperabilidad COM en aplicaciones .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d188-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="3d188-103">Si desea utilizar objetos COM y objetos de .NET Framework en la misma aplicación, debe resolver las diferencias en cómo los objetos existen en la memoria.</span><span class="sxs-lookup"><span data-stu-id="3d188-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="3d188-104">Un objeto de .NET Framework se encuentra en la memoria administrada, la memoria controlada por common language runtime y se pueden mover en tiempo de ejecución según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3d188-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="3d188-105">Un objeto COM se encuentra en la memoria no administrada y no se prevé que se mueva a otra ubicación de memoria.</span><span class="sxs-lookup"><span data-stu-id="3d188-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> <span data-ttu-id="3d188-106">Visual Studio y la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] proporcionan herramientas para controlar la interacción de estos administrados y componentes.</span><span class="sxs-lookup"><span data-stu-id="3d188-106">Visual Studio and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="3d188-107">Para obtener más información sobre el código administrado, consulte [Common Language Runtime](../../../standard/clr.md).</span><span class="sxs-lookup"><span data-stu-id="3d188-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>  
  
 <span data-ttu-id="3d188-108">Además de usar objetos COM en aplicaciones. NET, también puede utilizar Visual Basic para desarrollar objetos accesibles desde código no administrado a través de COM.</span><span class="sxs-lookup"><span data-stu-id="3d188-108">In addition to using COM objects in .NET applications, you may also want to use Visual Basic to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="3d188-109">Los vínculos en esta página proporcionan detalles sobre las interacciones entre objetos COM y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3d188-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3d188-110">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3d188-110">Related Sections</span></span>  
 [<span data-ttu-id="3d188-111">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="3d188-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="3d188-112">Proporciona vínculos a temas que tratan sobre la interoperabilidad COM en Visual Basic, incluidos objetos de COM, los controles de ActiveX, archivos DLL para Win32, los objetos administrados y herencia de objetos COM.</span><span class="sxs-lookup"><span data-stu-id="3d188-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="3d188-113">Error de contenedor de interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="3d188-113">COM Interop Wrapper Error</span></span>](/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="3d188-114">Describe las opciones y las consecuencias si el sistema del proyecto no puede crear un contenedor de interoperabilidad COM para un componente determinado.</span><span class="sxs-lookup"><span data-stu-id="3d188-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 <span data-ttu-id="3d188-115">[Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="3d188-115">[Interoperating with Unmanaged Code](../../../framework/interop/index.md)</span></span>  
 <span data-ttu-id="3d188-116">Describe algunos de los problemas de interacción entre código administrado y brevemente y proporciona vínculos a más información.</span><span class="sxs-lookup"><span data-stu-id="3d188-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="3d188-117">Contenedores COM</span><span class="sxs-lookup"><span data-stu-id="3d188-117">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md)  
 <span data-ttu-id="3d188-118">Describe contenedores invocables en tiempo de ejecución, lo que permite al código administrado llamar a métodos COM, y los contenedores CCW, que permiten a los clientes COM llamar a métodos de objeto. NET.</span><span class="sxs-lookup"><span data-stu-id="3d188-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="3d188-119">Interoperabilidad COM avanzada</span><span class="sxs-lookup"><span data-stu-id="3d188-119">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="3d188-120">Proporciona vínculos a temas que tratan sobre la interoperabilidad COM con respecto a los contenedores, excepciones, herencia, subprocesos, eventos, conversiones y el cálculo de referencias.</span><span class="sxs-lookup"><span data-stu-id="3d188-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="3d188-121">TlbImp.exe (Importador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="3d188-121">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 <span data-ttu-id="3d188-122">Describe la herramienta que puede usar para convertir las definiciones de tipos encontradas en una biblioteca de tipos COM en las definiciones equivalentes en un ensamblado de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="3d188-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>
