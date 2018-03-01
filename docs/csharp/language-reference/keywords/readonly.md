---
title: readonly (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b499f9fc5121afe6c2e92bcf8c5d2ac593b4c06c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="readonly-c-reference"></a><span data-ttu-id="33dc6-102">readonly (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="33dc6-102">readonly (C# Reference)</span></span>
<span data-ttu-id="33dc6-103">La palabra clave `readonly` corresponde a un modificador que se puede usar en campos.</span><span class="sxs-lookup"><span data-stu-id="33dc6-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="33dc6-104">Cuando una declaración de campo incluye un modificador `readonly`, las asignaciones a los campos que aparecen en la declaración solo pueden tener lugar en la propia declaración o en un constructor de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="33dc6-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33dc6-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33dc6-105">Example</span></span>  
 <span data-ttu-id="33dc6-106">En este ejemplo, el valor del campo `year` no se puede cambiar en el método `ChangeYear`, aunque se asigne un valor en el constructor de clase:</span><span class="sxs-lookup"><span data-stu-id="33dc6-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 <span data-ttu-id="33dc6-107">Solo se puede asignar un valor a un campo `readonly` en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="33dc6-107">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="33dc6-108">Cuando la variable se inicializa en la declaración, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="33dc6-108">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="33dc6-109">Para un campo de instancia, en los constructores de instancia de la clase que contiene la declaración de campo; para un campo estático, en el constructor estático de la clase que contiene la declaración de campo.</span><span class="sxs-lookup"><span data-stu-id="33dc6-109">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="33dc6-110">Estos son también los únicos contextos en los que es válido pasar un campo `readonly` como parámetro [out](../../../csharp/language-reference/keywords/out.md) o [ref](../../../csharp/language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="33dc6-110">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33dc6-111">La palabra clave `readonly` es diferente de la palabra clave [const](../../../csharp/language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="33dc6-111">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="33dc6-112">Un campo `const` solo se puede inicializar en la declaración del campo.</span><span class="sxs-lookup"><span data-stu-id="33dc6-112">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="33dc6-113">Un campo `readonly` se puede inicializar en la declaración o en un constructor.</span><span class="sxs-lookup"><span data-stu-id="33dc6-113">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="33dc6-114">Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use.</span><span class="sxs-lookup"><span data-stu-id="33dc6-114">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="33dc6-115">Además, mientras que un campo `const` es una constante en tiempo de compilación, el campo `readonly` puede usarse para constantes en tiempo de ejecución, como muestra el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="33dc6-115">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a><span data-ttu-id="33dc6-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33dc6-116">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 <span data-ttu-id="33dc6-117">En el ejemplo anterior, si se usa una instrucción como:</span><span class="sxs-lookup"><span data-stu-id="33dc6-117">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="33dc6-118">se obtendrá el siguiente mensaje de error del compilador:</span><span class="sxs-lookup"><span data-stu-id="33dc6-118">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="33dc6-119">que es el mismo error que se obtiene al intentar asignar un valor a una constante.</span><span class="sxs-lookup"><span data-stu-id="33dc6-119">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="33dc6-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="33dc6-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33dc6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="33dc6-121">See Also</span></span>  
 [<span data-ttu-id="33dc6-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="33dc6-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="33dc6-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="33dc6-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="33dc6-124">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="33dc6-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="33dc6-125">Modificadores</span><span class="sxs-lookup"><span data-stu-id="33dc6-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="33dc6-126">const</span><span class="sxs-lookup"><span data-stu-id="33dc6-126">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
 [<span data-ttu-id="33dc6-127">Campos</span><span class="sxs-lookup"><span data-stu-id="33dc6-127">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)
