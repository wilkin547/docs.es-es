---
title: private protected (Referencia de C#)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: ee36cc713dd5fdb90ae20ef992f8e75eca09597d
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="c07dc-102">private protected (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c07dc-102">private protected (C# Reference)</span></span>
<span data-ttu-id="c07dc-103">La combinación de palabras claves `private protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="c07dc-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="c07dc-104">Los miembros private protected están accesibles para los tipos que se deriven de la clase contenedora, pero solo desde dentro del ensamblado correspondiente que lo contenga.</span><span class="sxs-lookup"><span data-stu-id="c07dc-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="c07dc-105">Para obtener una comparación de `private protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c07dc-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="c07dc-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c07dc-106">Example</span></span>  
 <span data-ttu-id="c07dc-107">Se puede tener acceso a un miembro private protected de una clase base desde tipos derivados en el ensamblado que lo contiene solo si el tipo estático de la variable es el tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c07dc-107">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="c07dc-108">Por ejemplo, vea el siguiente segmento de código:</span><span class="sxs-lookup"><span data-stu-id="c07dc-108">For example, consider the following code segment:</span></span>  
  
 ```csharp
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
  
```csharp  
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
 <span data-ttu-id="c07dc-109">Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="c07dc-109">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="c07dc-110">El primer archivo contiene una clase base pública, `BaseClass`, y un tipo derivado de ella, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="c07dc-110">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="c07dc-111">`BaseClass` posee un miembro private protected, `myValue`, al que `DerivedClass1` intenta tener acceso de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="c07dc-111">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="c07dc-112">El primer intento de acceso a `myValue` a través de una instancia de `BaseClass` generará un error.</span><span class="sxs-lookup"><span data-stu-id="c07dc-112">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="c07dc-113">En cambio, el intento de usarlo como un miembro heredado en `DerivedClass1` se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="c07dc-113">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="c07dc-114">En el segundo archivo, un intento de tener acceso a `myValue` como un miembro heredado de `DerivedClass2` generará un error, ya que solo está accesible para los tipos derivados en Assembly1.</span><span class="sxs-lookup"><span data-stu-id="c07dc-114">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="c07dc-115">Los miembros de struct no pueden ser `private protected`, porque los structs no se heredan.</span><span class="sxs-lookup"><span data-stu-id="c07dc-115">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c07dc-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c07dc-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c07dc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c07dc-117">See Also</span></span>  
 <span data-ttu-id="c07dc-118">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c07dc-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c07dc-119">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c07dc-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c07dc-120">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c07dc-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c07dc-121">[Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="c07dc-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="c07dc-122">[Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="c07dc-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="c07dc-123">[Modificadores](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="c07dc-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="c07dc-124">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="c07dc-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="c07dc-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="c07dc-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="c07dc-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="c07dc-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="c07dc-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110)) (Problemas de seguridad de palabras clave virtuales internas)</span><span class="sxs-lookup"><span data-stu-id="c07dc-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
