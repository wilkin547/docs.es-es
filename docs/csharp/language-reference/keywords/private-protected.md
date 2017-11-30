---
title: privado protegido (referencia de C#)
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: 5f7abd2569d5bad5af64161042e4e5d21e741c8c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="92c57-102">privado protegido (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="92c57-102">private protected (C# Reference)</span></span>
<span data-ttu-id="92c57-103">El `private protected` combinación de palabra clave es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="92c57-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="92c57-104">Un miembro protegido privado es accesible por tipos derivados de la clase contenedora, pero sólo dentro de su ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="92c57-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="92c57-105">Para obtener una comparación de `private protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="92c57-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="92c57-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92c57-106">Example</span></span>  
 <span data-ttu-id="92c57-107">Un miembro privado protegido de una clase base es accesible desde tipos derivados en su ensamblado de contenedor solo si el tipo estático de la variable es el tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="92c57-107">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="92c57-108">Por ejemplo, vea el siguiente segmento de código:</span><span class="sxs-lookup"><span data-stu-id="92c57-108">For example, consider the following code segment:</span></span>  
  
 ```
 // Assembly1.cs  
 // Compile with: /target:library  
 public class BaseClass
 {
     private protected int myValue = 0;
 }
 
 public class DerivedClass1 : BaseClass
 {
     void Access()
     {
         BaseClass baseObject = new BaseClass();
 
         // Error CS1540, because myValue can only be accessed by
         // classes derived from BaseClass.
         // baseObject.myValue = 5;  
 
         // OK, accessed through the current derived class instance
         myValue = 5;
     }
 }
```  
  
```  
 // Assembly2.cs  
 // Compile with: /reference:Assembly1.dll  
 class DerivedClass2 : BaseClass
 {
     void Access()
     {
         // Error CS0122, because myValue can only be
         // accessed by types in Assembly1
         // myValue = 10;
     }
 }
```  
 <span data-ttu-id="92c57-109">Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="92c57-109">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="92c57-110">El primer archivo contiene una clase base pública, `BaseClass`y un tipo derivado de éste, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="92c57-110">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="92c57-111">`BaseClass`posee un miembro privado protegido, `myValue`, que `DerivedClass1` intenta tener acceso a de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="92c57-111">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="92c57-112">El primer intento de obtener acceso a `myValue` a través de una instancia de `BaseClass` generará un error.</span><span class="sxs-lookup"><span data-stu-id="92c57-112">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="92c57-113">Sin embargo, el intento de usar como un miembro heredado en `DerivedClass1` se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="92c57-113">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="92c57-114">En el segundo archivo, un intento para tener acceso a `myValue` como un miembro heredado de `DerivedClass2` generará un error, ya que solo es accesible por tipos derivados en ensamblado1.</span><span class="sxs-lookup"><span data-stu-id="92c57-114">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="92c57-115">Los miembros de estructura no pueden ser `private protected` porque el struct no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="92c57-115">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="92c57-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="92c57-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="92c57-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="92c57-117">See Also</span></span>  
 <span data-ttu-id="92c57-118">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="92c57-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="92c57-119">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="92c57-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="92c57-120">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="92c57-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="92c57-121">[Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="92c57-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="92c57-122">[Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="92c57-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="92c57-123">[Modificadores](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="92c57-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="92c57-124">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="92c57-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="92c57-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="92c57-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="92c57-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="92c57-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="92c57-127">[Cuestiones de seguridad para palabras clave virtuales internas](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="92c57-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
