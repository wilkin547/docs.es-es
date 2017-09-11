---
title: internal (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- internal_CSharpKeyword
- internal
dev_langs:
- CSharp
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5674a78e2c317357c31d9e2661a25ce86cbf4f6a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="internal-c-reference"></a><span data-ttu-id="94114-102">internal (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="94114-102">internal (C# Reference)</span></span>
<span data-ttu-id="94114-103">La palabra clave `internal` es un [modificador de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) para tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="94114-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> <span data-ttu-id="94114-104">Solo se puede tener acceso a los tipos internos o los miembros desde los archivos del mismo ensamblado, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="94114-104">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  
  
 <span data-ttu-id="94114-105">Se puede obtener acceso a los tipos o miembros que tienen el modificador de acceso `protected internal` desde el ensamblado actual o desde tipos que se derivan de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="94114-105">Types or members that have access modifier `protected internal` can be accessed from the current assembly or from types that are derived from the containing class.</span></span>  
  
 <span data-ttu-id="94114-106">Para obtener una comparación de `internal` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) y [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="94114-106">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="94114-107">Para más información sobre los ensamblados, vea [Ensamblados y caché global de ensamblados](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span><span class="sxs-lookup"><span data-stu-id="94114-107">For more information about assemblies, see [Assemblies and the Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
 <span data-ttu-id="94114-108">Un uso común del acceso interno se da en el desarrollo basado en componentes porque permite que un grupo de componentes cooperen de manera privada sin estar expuesto al resto del código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="94114-108">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="94114-109">Por ejemplo, un marco para crear interfaces gráficas de usuario podría proporcionar las clases `Control` y `Form` que cooperan mediante miembros con acceso interno.</span><span class="sxs-lookup"><span data-stu-id="94114-109">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="94114-110">Como estos miembros son internos, no se exponen al código que usa el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="94114-110">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="94114-111">Es un error hacer referencia a un tipo o miembro con acceso interno fuera del ensamblado en el que se definió.</span><span class="sxs-lookup"><span data-stu-id="94114-111">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94114-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94114-112">Example</span></span>  
 <span data-ttu-id="94114-113">Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="94114-113">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="94114-114">El primer archivo contiene una clase base interna, `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="94114-114">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="94114-115">En el segundo archivo, un intento de crear una instancia de `BaseClass` producirá un error.</span><span class="sxs-lookup"><span data-stu-id="94114-115">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
```  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="94114-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94114-116">Example</span></span>  
 <span data-ttu-id="94114-117">En este ejemplo, use los mismos archivos usados en el ejemplo 1 y cambie el nivel de accesibilidad de `BaseClass` a `public`.</span><span class="sxs-lookup"><span data-stu-id="94114-117">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="94114-118">Cambie también el nivel de accesibilidad del miembro `IntM` a `internal`.</span><span class="sxs-lookup"><span data-stu-id="94114-118">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="94114-119">En este caso, se puede crear una instancia de la clase, pero no se puede tener acceso al miembro interno.</span><span class="sxs-lookup"><span data-stu-id="94114-119">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
```  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```  
// Assembly2_a.cs  
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="94114-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="94114-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="94114-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="94114-121">See Also</span></span>  
 <span data-ttu-id="94114-122">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="94114-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="94114-123">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="94114-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="94114-124">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="94114-124">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="94114-125">[Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="94114-125">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="94114-126">[Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="94114-126">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="94114-127">[Modificadores](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="94114-127">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="94114-128">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="94114-128">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="94114-129">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="94114-129">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 [<span data-ttu-id="94114-130">protected</span><span class="sxs-lookup"><span data-stu-id="94114-130">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)

