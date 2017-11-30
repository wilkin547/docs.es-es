---
title: protected internal (referencia de C#)
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: f9004a5e8d65179c9ff2e30688e63c14c95ab431
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="ba3af-102">protected internal (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ba3af-102">protected internal (C# Reference)</span></span>
<span data-ttu-id="ba3af-103">El `protected internal` combinación de palabra clave es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="ba3af-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="ba3af-104">Un miembro protected internal es accesible desde el ensamblado actual o desde tipos que se derivan de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="ba3af-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="ba3af-105">Para obtener una comparación de `protected internal` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ba3af-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="ba3af-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba3af-106">Example</span></span>  
 <span data-ttu-id="ba3af-107">Un miembro interno protegido de una clase base es accesible desde cualquier tipo de ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="ba3af-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="ba3af-108">También es accesible en una clase derivada que se encuentra en otro ensamblado sólo si el acceso se produce a través de una variable del tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="ba3af-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="ba3af-109">Por ejemplo, vea el siguiente segmento de código:</span><span class="sxs-lookup"><span data-stu-id="ba3af-109">For example, consider the following code segment:</span></span>  

```
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
  
```  
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
 <span data-ttu-id="ba3af-110">Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="ba3af-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="ba3af-111">El primer archivo contiene una clase base pública, `BaseClass`y otra clase, `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="ba3af-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="ba3af-112">`BaseClass`posee un miembro protected internal, `myValue`, que se obtiene acceso a la `TestAccess` tipo.</span><span class="sxs-lookup"><span data-stu-id="ba3af-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span> <span data-ttu-id="ba3af-113">En el segundo archivo, un intento para tener acceso a `myValue` a través de una instancia de `BaseClass` generará un error, mientras que un acceso a este miembro a través de una instancia de una clase derivada, `DerivedClass` se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba3af-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span> 

 <span data-ttu-id="ba3af-114">Los miembros de estructura no pueden ser `protected internal` porque el struct no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="ba3af-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ba3af-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ba3af-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ba3af-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba3af-116">See Also</span></span>  
 <span data-ttu-id="ba3af-117">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ba3af-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ba3af-118">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ba3af-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ba3af-119">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="ba3af-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="ba3af-120">[Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="ba3af-120">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="ba3af-121">[Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="ba3af-121">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="ba3af-122">[Modificadores](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="ba3af-122">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="ba3af-123">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="ba3af-123">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="ba3af-124">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="ba3af-124">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="ba3af-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="ba3af-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="ba3af-126">[Cuestiones de seguridad para palabras clave virtuales internas](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="ba3af-126">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
