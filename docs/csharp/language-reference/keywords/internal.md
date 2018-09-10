---
title: internal (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: 54ec003683953b53dedf8885a41350daf5338f83
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523366"
---
# <a name="internal-c-reference"></a><span data-ttu-id="6412c-102">internal (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6412c-102">internal (C# Reference)</span></span>
<span data-ttu-id="6412c-103">La palabra clave `internal` es un [modificador de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) para tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="6412c-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> 
  
 > <span data-ttu-id="6412c-104">Esta página trata sobre el modificador de acceso `internal`.</span><span class="sxs-lookup"><span data-stu-id="6412c-104">This page covers `internal` access.</span></span> <span data-ttu-id="6412c-105">La palabra clave `internal` también forma parte del modificador de acceso [`protected internal`](./protected-internal.md).</span><span class="sxs-lookup"><span data-stu-id="6412c-105">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="6412c-106">Solo se puede tener acceso a los tipos internos o los miembros desde los archivos del mismo ensamblado, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6412c-106">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```csharp  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  

 <span data-ttu-id="6412c-107">Para obtener una comparación de `internal` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) y [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="6412c-107">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="6412c-108">Para más información sobre los ensamblados, vea [Ensamblados y caché global de ensamblados](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span><span class="sxs-lookup"><span data-stu-id="6412c-108">For more information about assemblies, see [Assemblies and the Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
 <span data-ttu-id="6412c-109">Un uso común del acceso interno se da en el desarrollo basado en componentes porque permite que un grupo de componentes cooperen de manera privada sin estar expuesto al resto del código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6412c-109">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="6412c-110">Por ejemplo, un marco para crear interfaces gráficas de usuario podría proporcionar las clases `Control` y `Form` que cooperan mediante miembros con acceso interno.</span><span class="sxs-lookup"><span data-stu-id="6412c-110">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="6412c-111">Como estos miembros son internos, no se exponen al código que usa el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6412c-111">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="6412c-112">Es un error hacer referencia a un tipo o miembro con acceso interno fuera del ensamblado en el que se definió.</span><span class="sxs-lookup"><span data-stu-id="6412c-112">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6412c-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6412c-113">Example</span></span>  
 <span data-ttu-id="6412c-114">Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="6412c-114">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="6412c-115">El primer archivo contiene una clase base interna, `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="6412c-115">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="6412c-116">En el segundo archivo, un intento de crear una instancia de `BaseClass` producirá un error.</span><span class="sxs-lookup"><span data-stu-id="6412c-116">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
```csharp  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```csharp  
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
  
## <a name="example"></a><span data-ttu-id="6412c-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6412c-117">Example</span></span>  
 <span data-ttu-id="6412c-118">En este ejemplo, use los mismos archivos usados en el ejemplo 1 y cambie el nivel de accesibilidad de `BaseClass` a `public`.</span><span class="sxs-lookup"><span data-stu-id="6412c-118">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="6412c-119">Cambie también el nivel de accesibilidad del miembro `IntM` a `internal`.</span><span class="sxs-lookup"><span data-stu-id="6412c-119">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="6412c-120">En este caso, se puede crear una instancia de la clase, pero no se puede tener acceso al miembro interno.</span><span class="sxs-lookup"><span data-stu-id="6412c-120">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
```csharp  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```csharp  
// Assembly2_a.cs  
// Compile with: /reference:Assembly2.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="6412c-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6412c-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6412c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6412c-122">See Also</span></span>

- [<span data-ttu-id="6412c-123">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6412c-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6412c-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6412c-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6412c-125">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="6412c-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="6412c-126">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="6412c-126">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [<span data-ttu-id="6412c-127">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="6412c-127">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
- [<span data-ttu-id="6412c-128">Modificadores</span><span class="sxs-lookup"><span data-stu-id="6412c-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
- [<span data-ttu-id="6412c-129">public</span><span class="sxs-lookup"><span data-stu-id="6412c-129">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
- [<span data-ttu-id="6412c-130">private</span><span class="sxs-lookup"><span data-stu-id="6412c-130">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="6412c-131">protected</span><span class="sxs-lookup"><span data-stu-id="6412c-131">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
