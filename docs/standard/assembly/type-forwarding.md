---
title: Reenvío de tipos en Common Language Runtime
description: El reenvío de tipos le permite mover un tipo a otro ensamblado sin tener que volver a compilar las aplicaciones que utilizan el ensamblado original.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: f0be61bd4ce88569e22a350a9ea9490d67e74ff3
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378599"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="32bd9-103">Reenvío de tipos en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="32bd9-103">Type forwarding in the common language runtime</span></span>
<span data-ttu-id="32bd9-104">El reenvío de tipos le permite mover un tipo a otro ensamblado sin tener que volver a compilar las aplicaciones que utilizan el ensamblado original.</span><span class="sxs-lookup"><span data-stu-id="32bd9-104">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="32bd9-105">Por ejemplo, suponga que una aplicación utiliza la clase `Example` en un ensamblado denominado *Utility.dll*.</span><span class="sxs-lookup"><span data-stu-id="32bd9-105">For example, suppose an application uses the `Example` class in an assembly named *Utility.dll*.</span></span> <span data-ttu-id="32bd9-106">Los desarrolladores de *Utility.dll* podrían decidir refactorizar el ensamblado y, en el proceso, podrían mover la clase `Example` a otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="32bd9-106">The developers of *Utility.dll* might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="32bd9-107">Si la versión anterior de *Utility.dll* se reemplaza por la nueva versión de *Utility.dll* y por su ensamblado complementario, la aplicación que usa la clase `Example` produce un error porque no puede encontrar la clase `Example` en la nueva versión de *Utility.dll*.</span><span class="sxs-lookup"><span data-stu-id="32bd9-107">If the old version of *Utility.dll* is replaced by the new version of *Utility.dll* and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of *Utility.dll*.</span></span>  
  
 <span data-ttu-id="32bd9-108">Los desarrolladores de *Utility.dll* pueden evitarlo mediante el reenvío de solicitudes para la clase `Example` con el atributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="32bd9-108">The developers of *Utility.dll* can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="32bd9-109">Si se ha aplicado el atributo a la nueva versión de *Utility.dll*, las solicitudes para la clase `Example` se reenvían al ensamblado que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="32bd9-109">If the attribute has been applied to the new version of *Utility.dll*, requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="32bd9-110">La aplicación existente continuará funcionando normalmente, sin necesidad de volver a compilarla.</span><span class="sxs-lookup"><span data-stu-id="32bd9-110">The existing application continues to function normally, without recompilation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32bd9-111">En la versión 2.0 de .NET Framework, no se pueden reenviar tipos desde ensamblados escritos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="32bd9-111">In the .NET Framework version 2.0, you cannot forward types from assemblies written in Visual Basic.</span></span> <span data-ttu-id="32bd9-112">Sin embargo, una aplicación escrita en Visual Basic puede utilizar tipos reenviados.</span><span class="sxs-lookup"><span data-stu-id="32bd9-112">However, an application written in Visual Basic can consume forwarded types.</span></span> <span data-ttu-id="32bd9-113">Es decir, si la aplicación utiliza un ensamblado codificado en C# o C++ y se reenvía un tipo de ese ensamblado a otro ensamblado, la aplicación de Visual Basic puede utilizar el tipo reenviado.</span><span class="sxs-lookup"><span data-stu-id="32bd9-113">That is, if the application uses an assembly coded in C# or C++, and a type from that assembly is forwarded to another assembly, the Visual Basic application can use the forwarded type.</span></span>  
  
## <a name="forward-types"></a><span data-ttu-id="32bd9-114">Reenvío de tipos</span><span class="sxs-lookup"><span data-stu-id="32bd9-114">Forward types</span></span>  
 <span data-ttu-id="32bd9-115">Hay cuatro pasos para reenviar un tipo:</span><span class="sxs-lookup"><span data-stu-id="32bd9-115">There are four steps to forwarding a type:</span></span>  
  
1. <span data-ttu-id="32bd9-116">Traslade el código fuente del tipo desde el ensamblado original al ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="32bd9-116">Move the source code for the type from the original assembly to the destination assembly.</span></span>  

2. <span data-ttu-id="32bd9-117">En el ensamblado en el que solía estar ubicado el tipo, agregue un atributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> para el tipo que se ha movido.</span><span class="sxs-lookup"><span data-stu-id="32bd9-117">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="32bd9-118">El código siguiente muestra el atributo para un tipo denominado `Example` que se ha movido.</span><span class="sxs-lookup"><span data-stu-id="32bd9-118">The following code shows the attribute for a type named `Example` that was moved.</span></span>  

   ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
   ```

   ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
   ```  

3. <span data-ttu-id="32bd9-119">Compile el ensamblado que contiene el tipo ahora.</span><span class="sxs-lookup"><span data-stu-id="32bd9-119">Compile the assembly that now contains the type.</span></span>  

4. <span data-ttu-id="32bd9-120">Vuelva a compilar el ensamblado donde se encontraba antes el tipo, con una referencia al ensamblado que contiene el tipo ahora.</span><span class="sxs-lookup"><span data-stu-id="32bd9-120">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="32bd9-121">Por ejemplo, si está compilando un archivo de C# desde la línea de comandos, utilice la opción [-reference (opciones del compilador de C#)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) para especificar el ensamblado que contiene el tipo.</span><span class="sxs-lookup"><span data-stu-id="32bd9-121">For example, if you are compiling a C# file from the command line, use the [-reference (C# compiler options)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="32bd9-122">En C++, utilice la directiva [#using](/cpp/preprocessor/hash-using-directive-cpp) en el archivo de código fuente para especificar el ensamblado que contiene el tipo.</span><span class="sxs-lookup"><span data-stu-id="32bd9-122">In C++, use the [#using](/cpp/preprocessor/hash-using-directive-cpp) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32bd9-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="32bd9-123">See also</span></span>

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [<span data-ttu-id="32bd9-124">Reenvío de tipos (C++/CLI)</span><span class="sxs-lookup"><span data-stu-id="32bd9-124">Type forwarding (C++/CLI)</span></span>](/cpp/windows/type-forwarding-cpp-cli)
- [<span data-ttu-id="32bd9-125">Directiva #using</span><span class="sxs-lookup"><span data-stu-id="32bd9-125">#using directive</span></span>](/cpp/preprocessor/hash-using-directive-cpp)
