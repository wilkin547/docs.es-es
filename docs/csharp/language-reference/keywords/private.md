---
title: private (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- private_CSharpKeyword
- private
dev_langs:
- CSharp
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 17
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
ms.openlocfilehash: c18fd87b12bf3f7f1a1d1ef0dfded8643308169c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="private-c-reference"></a><span data-ttu-id="d0f52-102">private (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d0f52-102">private (C# Reference)</span></span>
<span data-ttu-id="d0f52-103">La palabra clave `private` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="d0f52-103">The `private` keyword is a member access modifier.</span></span> <span data-ttu-id="d0f52-104">El acceso privado es el nivel de acceso menos permisivo.</span><span class="sxs-lookup"><span data-stu-id="d0f52-104">Private access is the least permissive access level.</span></span> <span data-ttu-id="d0f52-105">Los miembros privados solo son accesibles dentro del cuerpo de la clase o el struct en el que se declaran, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d0f52-105">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  
  
 <span data-ttu-id="d0f52-106">Los tipos anidados en el mismo cuerpo también pueden tener acceso a los miembros privados.</span><span class="sxs-lookup"><span data-stu-id="d0f52-106">Nested types in the same body can also access those private members.</span></span>  
  
 <span data-ttu-id="d0f52-107">Hacer referencia a un miembro privado fuera de la clase o el struct en el que se declara es un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d0f52-107">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>  
  
 <span data-ttu-id="d0f52-108">Para obtener una comparación de `private` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) y [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d0f52-108">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0f52-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0f52-109">Example</span></span>  
 <span data-ttu-id="d0f52-110">En este ejemplo, la clase `Employee` contiene dos miembros de datos privados, `name` y `salary`.</span><span class="sxs-lookup"><span data-stu-id="d0f52-110">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="d0f52-111">Como miembros privados, solo pueden tener acceso a ellos los métodos de miembro.</span><span class="sxs-lookup"><span data-stu-id="d0f52-111">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="d0f52-112">Los métodos públicos denominados `GetName` y `Salary` se agregan para permitir un acceso controlado a los miembros privados.</span><span class="sxs-lookup"><span data-stu-id="d0f52-112">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="d0f52-113">Se tiene acceso al miembro `name` a través de un método público, mientras que se tiene acceso al miembro `salary` a través de una propiedad pública de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="d0f52-113">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="d0f52-114">(Para obtener más información, vea [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)).</span><span class="sxs-lookup"><span data-stu-id="d0f52-114">(See [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) for more information.)</span></span>  
  
 <span data-ttu-id="d0f52-115">[!code-cs[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d0f52-115">[!code-cs[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d0f52-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d0f52-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d0f52-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0f52-117">See Also</span></span>  
 <span data-ttu-id="d0f52-118">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d0f52-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d0f52-119">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d0f52-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d0f52-120">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d0f52-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d0f52-121">[Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d0f52-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="d0f52-122">[Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="d0f52-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="d0f52-123">[Modificadores](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d0f52-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="d0f52-124">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="d0f52-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="d0f52-125">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="d0f52-125">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="d0f52-126">internal</span><span class="sxs-lookup"><span data-stu-id="d0f52-126">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

