---
title: "Reenvío de tipos en Common Language Runtime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: c6e199800a86bc8b275fed4e3ba3ea6f77c7d2fa
ms.openlocfilehash: 2dad97aa9373f42e22690b0cc97de9d8c5b51d46
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="e0f75-102">Reenvío de tipos en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="e0f75-102">Type Forwarding in the Common Language Runtime</span></span>
<span data-ttu-id="e0f75-103">El reenvío de tipos le permite mover un tipo a otro ensamblado sin tener que volver a compilar las aplicaciones que utilizan el ensamblado original.</span><span class="sxs-lookup"><span data-stu-id="e0f75-103">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="e0f75-104">Por ejemplo, suponga que una aplicación utiliza la clase `Example` en un ensamblado denominado `Utility.dll`.</span><span class="sxs-lookup"><span data-stu-id="e0f75-104">For example, suppose an application uses the `Example` class in an assembly named `Utility.dll`.</span></span> <span data-ttu-id="e0f75-105">Los desarrolladores de `Utility.dll` podrían decidir refactorizar el ensamblado y, en el proceso, podrían mover la clase `Example` a otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e0f75-105">The developers of `Utility.dll` might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="e0f75-106">Si la versión anterior de `Utility.dll` se reemplaza por la nueva versión de `Utility.dll` y su ensamblado complementario, la aplicación que usa la clase `Example` produce un error porque no se puede encontrar la clase `Example` en la nueva versión de `Utility.dll`.</span><span class="sxs-lookup"><span data-stu-id="e0f75-106">If the old version of `Utility.dll` is replaced by the new version of `Utility.dll` and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of `Utility.dll`.</span></span>  
  
 <span data-ttu-id="e0f75-107">Los desarrolladores de `Utility.dll` pueden evitarlo mediante el reenvío de las solicitudes a la clase `Example` con el uso del atributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e0f75-107">The developers of `Utility.dll` can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="e0f75-108">Si se ha aplicado el atributo a la nueva versión de `Utility.dll`, las solicitudes para la clase `Example` se reenvían al ensamblado que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="e0f75-108">If the attribute has been applied to the new version of `Utility.dll`, requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="e0f75-109">La aplicación existente continuará funcionando normalmente, sin necesidad de volver a compilarla.</span><span class="sxs-lookup"><span data-stu-id="e0f75-109">The existing application continues to function normally, without recompilation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0f75-110">En la versión 2.0 de .NET Framework, no se pueden reenviar tipos desde ensamblados escritos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e0f75-110">In the .NET Framework version 2.0, you cannot forward types from assemblies written in Visual Basic.</span></span> <span data-ttu-id="e0f75-111">Sin embargo, una aplicación escrita en Visual Basic puede utilizar tipos reenviados.</span><span class="sxs-lookup"><span data-stu-id="e0f75-111">However, an application written in Visual Basic can consume forwarded types.</span></span> <span data-ttu-id="e0f75-112">Es decir, si la aplicación utiliza un ensamblado codificado en C# o C++ y se reenvía un tipo de ese ensamblado a otro ensamblado, la aplicación de Visual Basic puede utilizar el tipo reenviado.</span><span class="sxs-lookup"><span data-stu-id="e0f75-112">That is, if the application uses an assembly coded in C# or C++, and a type from that assembly is forwarded to another assembly, the Visual Basic application can use the forwarded type.</span></span>  
  
## <a name="forwarding-types"></a><span data-ttu-id="e0f75-113">Reenvío de tipos</span><span class="sxs-lookup"><span data-stu-id="e0f75-113">Forwarding Types</span></span>  
 <span data-ttu-id="e0f75-114">Hay cuatro pasos para reenviar un tipo:</span><span class="sxs-lookup"><span data-stu-id="e0f75-114">There are four steps to forwarding a type:</span></span>  
  
1.  <span data-ttu-id="e0f75-115">Traslade el código fuente del tipo desde el ensamblado original al ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="e0f75-115">Move the source code for the type from the original assembly to the destination assembly.</span></span>  
  
2.  <span data-ttu-id="e0f75-116">En el ensamblado en el que solía estar ubicado el tipo, agregue un atributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> para el tipo que se ha movido.</span><span class="sxs-lookup"><span data-stu-id="e0f75-116">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="e0f75-117">El código siguiente muestra el atributo para un tipo denominado `Example` que se ha movido.</span><span class="sxs-lookup"><span data-stu-id="e0f75-117">The following code shows the attribute for a type named `Example` that was moved.</span></span>  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3.  <span data-ttu-id="e0f75-118">Compile el ensamblado que contiene el tipo ahora.</span><span class="sxs-lookup"><span data-stu-id="e0f75-118">Compile the assembly that now contains the type.</span></span>  
  
4.  <span data-ttu-id="e0f75-119">Vuelva a compilar el ensamblado donde se encontraba antes el tipo, con una referencia al ensamblado que contiene el tipo ahora.</span><span class="sxs-lookup"><span data-stu-id="e0f75-119">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="e0f75-120">Por ejemplo, si está compilando un archivo de C# desde la línea de comandos, utilice la opción [/reference (opciones del compilador de C#)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) para especificar el ensamblado que contiene el tipo.</span><span class="sxs-lookup"><span data-stu-id="e0f75-120">For example, if you are compiling a C# file from the command line, use the [/reference (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="e0f75-121">En C++, utilice la directiva [#using](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a) en el archivo de código fuente para especificar el ensamblado que contiene el tipo.</span><span class="sxs-lookup"><span data-stu-id="e0f75-121">In C++, use the [#using](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0f75-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0f75-122">See Also</span></span>  
 <span data-ttu-id="e0f75-123"><xref:System.Runtime.CompilerServices.TypeForwardedToAttribute></span><span class="sxs-lookup"><span data-stu-id="e0f75-123"><xref:System.Runtime.CompilerServices.TypeForwardedToAttribute></span></span>   
 <span data-ttu-id="e0f75-124">[Reenvío de tipos (C++/CLI)](/cpp/windows/type-forwarding-cpp-cli) </span><span class="sxs-lookup"><span data-stu-id="e0f75-124">[Type Forwarding (C++/CLI)](/cpp/windows/type-forwarding-cpp-cli) </span></span>  
 [<span data-ttu-id="e0f75-125">#using (directiva)</span><span class="sxs-lookup"><span data-stu-id="e0f75-125">#using Directive</span></span>](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a)

