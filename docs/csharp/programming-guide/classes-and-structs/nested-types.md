---
title: "Tipos anidados (Guía de programación de C#)"
ms.date: 07/10/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab13c68b638062ab89c90dbfc51b51b8d72d3bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="abd4f-102">Tipos anidados (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="abd4f-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="abd4f-103">Un tipo definido en una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md) se denomina tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="abd4f-103">A type defined within a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="abd4f-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abd4f-104">For example:</span></span>  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
<span data-ttu-id="abd4f-105">Con independencia de si el tipo externo es una clase o struct, los tipos anidados se establecen de manera predeterminada en [private](../../../csharp/language-reference/keywords/private.md), solo son accesibles desde su tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="abd4f-105">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../../csharp/language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="abd4f-106">En el ejemplo anterior, la clase `Nested` es inaccesible a los tipos externos.</span><span class="sxs-lookup"><span data-stu-id="abd4f-106">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="abd4f-107">También puede especificar un [modificador de acceso](../../language-reference/keywords/access-modifiers.md) para definir la accesibilidad de un tipo anidado, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="abd4f-107">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="abd4f-108">Anidar tipos de un **clase** puede ser [público](../../../csharp/language-reference/keywords/public.md), [protegido](../../../csharp/language-reference/keywords/protected.md), [interno](../../../csharp/language-reference/keywords/internal.md), [protegido interno](../../../csharp/language-reference/keywords/protected-internal.md), [privada](../../../csharp/language-reference/keywords/private.md) o [privado protegido](../../../csharp/language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="abd4f-108">Nested types of a **class** can be [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) or [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span></span> 

   <span data-ttu-id="abd4f-109">Sin embargo, definir una `protected`, `protected internal` o `private protected` dentro de la clase anidada un [clase sealed](../../language-reference/keywords/sealed.md) genera la advertencia del compilador [CS0628](../../misc/cs0628.md), "nuevo miembro protegido declarado en una clase sealed."</span><span class="sxs-lookup"><span data-stu-id="abd4f-109">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="abd4f-110">Los tipos anidados de un **struct** pueden ser [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="abd4f-110">Nested types of a **struct** can be [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="abd4f-111">En el ejemplo siguiente se convierte la clase `Nested` en public:</span><span class="sxs-lookup"><span data-stu-id="abd4f-111">The following example makes the `Nested` class public:</span></span>
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 <span data-ttu-id="abd4f-112">El tipo anidado o interno puede tener acceso al tipo contenedor o externo.</span><span class="sxs-lookup"><span data-stu-id="abd4f-112">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="abd4f-113">Para tener acceso al tipo contenedor, páselo como un argumento al constructor del tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="abd4f-113">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="abd4f-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abd4f-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 <span data-ttu-id="abd4f-115">Un tipo anidado tiene acceso a todos los miembros que estén accesibles para el tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="abd4f-115">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="abd4f-116">Puede tener acceso a los miembros privados y protegidos del tipo contenedor, incluidos los miembros protegidos heredados.</span><span class="sxs-lookup"><span data-stu-id="abd4f-116">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="abd4f-117">En la declaración anterior, el nombre completo de la clase `Nested` es `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="abd4f-117">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="abd4f-118">Este es el nombre que se utiliza para crear una instancia nueva de la clase anidada, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="abd4f-118">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="abd4f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="abd4f-119">See Also</span></span>  
 [<span data-ttu-id="abd4f-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="abd4f-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="abd4f-121">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="abd4f-121">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="abd4f-122">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="abd4f-122">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="abd4f-123">Constructores</span><span class="sxs-lookup"><span data-stu-id="abd4f-123">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
