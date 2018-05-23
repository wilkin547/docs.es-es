---
title: protected internal (Referencia de C#)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 5ba2c811a1a4f095bcee65ed6678a7dc50fe94db
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="c1c05-102">protected internal (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c1c05-102">protected internal (C# Reference)</span></span>
<span data-ttu-id="c1c05-103">La combinación de palabras claves `protected internal` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="c1c05-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="c1c05-104">Se puede obtener acceso a un miembro protected internal desde el ensamblado actual o desde tipos que se deriven de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="c1c05-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="c1c05-105">Para obtener una comparación de `protected internal` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c1c05-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="c1c05-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c1c05-106">Example</span></span>  
 <span data-ttu-id="c1c05-107">Se puede obtener acceso a un miembro protected internal de una clase base desde cualquier tipo de ensamblado que lo contenga.</span><span class="sxs-lookup"><span data-stu-id="c1c05-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="c1c05-108">También estará accesible en una clase derivada ubicada en otro ensamblado, pero solo si el acceso se produce a través de una variable del tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c1c05-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="c1c05-109">Por ejemplo, vea el siguiente segmento de código:</span><span class="sxs-lookup"><span data-stu-id="c1c05-109">For example, consider the following code segment:</span></span>  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   protected internal int myValue = 0;  
}

class TestAccess 
{
    void Access()
    {
        BaseClass baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}  
```  
  
```csharp  
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass : BaseClass   
{  
    static void Main()
    {
        BaseClass baseObject = new BaseClass();
        DerivedClass derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10; 

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
} 
```  
 <span data-ttu-id="c1c05-110">Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="c1c05-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="c1c05-111">El primer archivo contiene una clase base interna, `BaseClass`, y otra clase, `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="c1c05-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="c1c05-112">`BaseClass` posee un miembro protected internal (`myValue`), al que se obtiene acceso por medio del tipo `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="c1c05-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span> <span data-ttu-id="c1c05-113">En el segundo archivo, un intento de tener acceso a `myValue` a través de una instancia de `BaseClass` generará un error, mientras que un acceso a este miembro a través de una instancia de una clase derivada (`DerivedClass`) se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1c05-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span> 

 <span data-ttu-id="c1c05-114">Los miembros de struct no pueden ser `protected internal`, porque los structs no se heredan.</span><span class="sxs-lookup"><span data-stu-id="c1c05-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c1c05-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c1c05-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c1c05-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1c05-116">See Also</span></span>  
 <span data-ttu-id="c1c05-117">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1c05-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c1c05-118">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1c05-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c1c05-119">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1c05-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c1c05-120">[Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="c1c05-120">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="c1c05-121">[Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="c1c05-121">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="c1c05-122">[Modificadores](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="c1c05-122">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="c1c05-123">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="c1c05-123">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="c1c05-124">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="c1c05-124">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="c1c05-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="c1c05-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="c1c05-126">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110)) (Problemas de seguridad de palabras clave virtuales internas)</span><span class="sxs-lookup"><span data-stu-id="c1c05-126">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
