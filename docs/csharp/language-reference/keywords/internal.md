---
title: 'internal: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: aefb806b452452d4837b29b6ab11ce158ea412bc
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745426"
---
# <a name="internal-c-reference"></a><span data-ttu-id="d565d-102">internal (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d565d-102">internal (C# Reference)</span></span>
<span data-ttu-id="d565d-103">La palabra clave `internal` es un [modificador de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) para tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="d565d-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> 
  
 > <span data-ttu-id="d565d-104">Esta página trata sobre el modificador de acceso `internal`.</span><span class="sxs-lookup"><span data-stu-id="d565d-104">This page covers `internal` access.</span></span> <span data-ttu-id="d565d-105">La palabra clave `internal` también forma parte del modificador de acceso [`protected internal`](./protected-internal.md).</span><span class="sxs-lookup"><span data-stu-id="d565d-105">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="d565d-106">Solo se puede tener acceso a los tipos internos o los miembros desde los archivos del mismo ensamblado, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d565d-106">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```csharp  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  

 <span data-ttu-id="d565d-107">Para obtener una comparación de `internal` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) y [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d565d-107">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="d565d-108">Para más información sobre los ensamblados, consulte [Ensamblados en .NET](../../../standard/assembly/index.md).</span><span class="sxs-lookup"><span data-stu-id="d565d-108">For more information about assemblies, see [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
 <span data-ttu-id="d565d-109">Un uso común del acceso interno se da en el desarrollo basado en componentes porque permite que un grupo de componentes cooperen de manera privada sin estar expuesto al resto del código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d565d-109">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="d565d-110">Por ejemplo, un marco para crear interfaces gráficas de usuario podría proporcionar las clases `Control` y `Form` que cooperan mediante miembros con acceso interno.</span><span class="sxs-lookup"><span data-stu-id="d565d-110">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="d565d-111">Como estos miembros son internos, no se exponen al código que usa el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d565d-111">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="d565d-112">Es un error hacer referencia a un tipo o miembro con acceso interno fuera del ensamblado en el que se definió.</span><span class="sxs-lookup"><span data-stu-id="d565d-112">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d565d-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d565d-113">Example</span></span>  
 <span data-ttu-id="d565d-114">Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="d565d-114">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="d565d-115">El primer archivo contiene una clase base interna, `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="d565d-115">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="d565d-116">En el segundo archivo, un intento de crear una instancia de `BaseClass` producirá un error.</span><span class="sxs-lookup"><span data-stu-id="d565d-116">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="d565d-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d565d-117">Example</span></span>  
 <span data-ttu-id="d565d-118">En este ejemplo, use los mismos archivos usados en el ejemplo 1 y cambie el nivel de accesibilidad de `BaseClass` a `public`.</span><span class="sxs-lookup"><span data-stu-id="d565d-118">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="d565d-119">Cambie también el nivel de accesibilidad del miembro `IntM` a `internal`.</span><span class="sxs-lookup"><span data-stu-id="d565d-119">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="d565d-120">En este caso, se puede crear una instancia de la clase, pero no se puede tener acceso al miembro interno.</span><span class="sxs-lookup"><span data-stu-id="d565d-120">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
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
  
## <a name="c-language-specification"></a><span data-ttu-id="d565d-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d565d-121">C# Language Specification</span></span>  

<span data-ttu-id="d565d-122">Para obtener más información, vea la sección [Accesibilidad declarada](~/_csharplang/spec/basic-concepts.md#declared-accessibility) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d565d-122">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="d565d-123">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="d565d-123">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d565d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d565d-124">See also</span></span>

- [<span data-ttu-id="d565d-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d565d-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="d565d-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d565d-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d565d-127">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="d565d-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="d565d-128">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="d565d-128">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="d565d-129">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="d565d-129">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)
- [<span data-ttu-id="d565d-130">Modificadores</span><span class="sxs-lookup"><span data-stu-id="d565d-130">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
- [<span data-ttu-id="d565d-131">public</span><span class="sxs-lookup"><span data-stu-id="d565d-131">public</span></span>](../../../csharp/language-reference/keywords/public.md)
- [<span data-ttu-id="d565d-132">private</span><span class="sxs-lookup"><span data-stu-id="d565d-132">private</span></span>](../../../csharp/language-reference/keywords/private.md)
- [<span data-ttu-id="d565d-133">protected</span><span class="sxs-lookup"><span data-stu-id="d565d-133">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
