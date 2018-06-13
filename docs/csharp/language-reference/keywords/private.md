---
title: private (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: 89bc23e91bf693f0a95b75dffe2399cb7e865b50
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171868"
---
# <a name="private-c-reference"></a><span data-ttu-id="593d0-102">private (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="593d0-102">private (C# Reference)</span></span>
<span data-ttu-id="593d0-103">La palabra clave `private` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="593d0-103">The `private` keyword is a member access modifier.</span></span> 
   
 > <span data-ttu-id="593d0-104">Esta página trata sobre el modificador de acceso `private`.</span><span class="sxs-lookup"><span data-stu-id="593d0-104">This page covers `private` access.</span></span> <span data-ttu-id="593d0-105">La palabra clave `private` también forma parte del modificador de acceso [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="593d0-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>
  
<span data-ttu-id="593d0-106">El acceso privado es el nivel de acceso menos permisivo.</span><span class="sxs-lookup"><span data-stu-id="593d0-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="593d0-107">Los miembros privados solo son accesibles dentro del cuerpo de la clase o el struct en el que se declaran, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="593d0-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>  
  
```csharp  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  

 <span data-ttu-id="593d0-108">Los tipos anidados en el mismo cuerpo también pueden tener acceso a los miembros privados.</span><span class="sxs-lookup"><span data-stu-id="593d0-108">Nested types in the same body can also access those private members.</span></span>  
  
 <span data-ttu-id="593d0-109">Hacer referencia a un miembro privado fuera de la clase o el struct en el que se declara es un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="593d0-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>  
  
 <span data-ttu-id="593d0-110">Para obtener una comparación de `private` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) y [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="593d0-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="593d0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="593d0-111">Example</span></span>  
 <span data-ttu-id="593d0-112">En este ejemplo, la clase `Employee` contiene dos miembros de datos privados, `name` y `salary`.</span><span class="sxs-lookup"><span data-stu-id="593d0-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="593d0-113">Como miembros privados, solo pueden tener acceso a ellos los métodos de miembro.</span><span class="sxs-lookup"><span data-stu-id="593d0-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="593d0-114">Los métodos públicos denominados `GetName` y `Salary` se agregan para permitir un acceso controlado a los miembros privados.</span><span class="sxs-lookup"><span data-stu-id="593d0-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="593d0-115">Se tiene acceso al miembro `name` a través de un método público, mientras que se tiene acceso al miembro `salary` a través de una propiedad pública de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="593d0-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="593d0-116">(Para obtener más información, vea [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)).</span><span class="sxs-lookup"><span data-stu-id="593d0-116">(See [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) for more information.)</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="593d0-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="593d0-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="593d0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="593d0-118">See Also</span></span>  
 [<span data-ttu-id="593d0-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="593d0-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="593d0-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="593d0-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="593d0-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="593d0-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="593d0-122">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="593d0-122">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="593d0-123">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="593d0-123">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="593d0-124">Modificadores</span><span class="sxs-lookup"><span data-stu-id="593d0-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="593d0-125">public</span><span class="sxs-lookup"><span data-stu-id="593d0-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="593d0-126">protected</span><span class="sxs-lookup"><span data-stu-id="593d0-126">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="593d0-127">internal</span><span class="sxs-lookup"><span data-stu-id="593d0-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
