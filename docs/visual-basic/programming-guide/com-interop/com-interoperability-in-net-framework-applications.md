---
title: Interoperabilidad COM en aplicaciones .NET Framework (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 28ec54dc062d4fdea4836b0ecc8699982dace623
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="53342-102">Interoperabilidad COM en aplicaciones .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53342-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="53342-103">Si desea utilizar objetos COM y objetos de .NET Framework en la misma aplicación, debe resolver las diferencias en cómo los objetos existen en la memoria.</span><span class="sxs-lookup"><span data-stu-id="53342-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="53342-104">Un objeto de .NET Framework se encuentra en la memoria administrada, la memoria controlada por common language runtime y se pueden mover en tiempo de ejecución según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="53342-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="53342-105">Un objeto COM se encuentra en la memoria no administrada y no se prevé que se mueva a otra ubicación de memoria.</span><span class="sxs-lookup"><span data-stu-id="53342-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="53342-106">y el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] proporcionan herramientas para controlar la interacción de estos administrados y componentes.</span><span class="sxs-lookup"><span data-stu-id="53342-106"> and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="53342-107">Para obtener más información sobre el código administrado, consulte [Common Language Runtime](../../../standard/clr.md).</span><span class="sxs-lookup"><span data-stu-id="53342-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>  
  
 <span data-ttu-id="53342-108">Además de usar objetos COM en aplicaciones. NET, también puede usar [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] para desarrollar objetos accesibles desde código no administrado a través de COM.</span><span class="sxs-lookup"><span data-stu-id="53342-108">In addition to using COM objects in .NET applications, you may also want to use [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="53342-109">Los vínculos en esta página proporcionan detalles sobre las interacciones entre objetos COM y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="53342-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="53342-110">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="53342-110">Related Sections</span></span>  
 [<span data-ttu-id="53342-111">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="53342-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="53342-112">Proporciona vínculos a temas que tratan sobre la interoperabilidad COM en Visual Basic, incluidos objetos de COM, los controles de ActiveX, archivos DLL para Win32, los objetos administrados y herencia de objetos COM.</span><span class="sxs-lookup"><span data-stu-id="53342-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="53342-113">Error de contenedor de interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="53342-113">COM Interop Wrapper Error</span></span>](/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="53342-114">Describe las opciones y las consecuencias si el sistema del proyecto no puede crear un contenedor de interoperabilidad COM para un componente determinado.</span><span class="sxs-lookup"><span data-stu-id="53342-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 <span data-ttu-id="53342-115">[Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="53342-115">[Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md)</span></span>  
 <span data-ttu-id="53342-116">Describe algunos de los problemas de interacción entre código administrado y brevemente y proporciona vínculos a más información.</span><span class="sxs-lookup"><span data-stu-id="53342-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="53342-117">Contenedores COM</span><span class="sxs-lookup"><span data-stu-id="53342-117">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md)  
 <span data-ttu-id="53342-118">Describe contenedores invocables en tiempo de ejecución, lo que permite al código administrado llamar a métodos COM, y los contenedores CCW, que permiten a los clientes COM llamar a métodos de objeto. NET.</span><span class="sxs-lookup"><span data-stu-id="53342-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="53342-119">Interoperabilidad COM avanzada</span><span class="sxs-lookup"><span data-stu-id="53342-119">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 <span data-ttu-id="53342-120">Proporciona vínculos a temas que tratan sobre la interoperabilidad COM con respecto a los contenedores, excepciones, herencia, subprocesos, eventos, conversiones y el cálculo de referencias.</span><span class="sxs-lookup"><span data-stu-id="53342-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="53342-121">TlbImp.exe (Importador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="53342-121">Tlbimp.exe (Type Library Importer)</span></span>](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 <span data-ttu-id="53342-122">Describe la herramienta que puede usar para convertir las definiciones de tipos encontradas en una biblioteca de tipos COM en las definiciones equivalentes en un ensamblado de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="53342-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>
