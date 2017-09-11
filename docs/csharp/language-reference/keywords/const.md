---
title: const (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- const_CSharpKeyword
- const
dev_langs:
- CSharp
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: 28
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
ms.openlocfilehash: b8f6d567deed513ff5693fe39bd21c8607677402
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="const-c-reference"></a><span data-ttu-id="51247-102">const (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="51247-102">const (C# Reference)</span></span>
<span data-ttu-id="51247-103">La palabra clave `const` se usa para declarar un campo constante o una local constante.</span><span class="sxs-lookup"><span data-stu-id="51247-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="51247-104">Los campos y locales constantes no son variables y no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="51247-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="51247-105">Las constantes pueden ser números, valores booleanos, cadenas o una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="51247-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="51247-106">No cree una constante para representar información que esperas que cambie en algún momento.</span><span class="sxs-lookup"><span data-stu-id="51247-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="51247-107">Por ejemplo, no use un campo constante para almacenar el precio de un servicio, un número de versión de producto o el nombre comercial de una compañía.</span><span class="sxs-lookup"><span data-stu-id="51247-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="51247-108">Estos valores pueden cambiar con el tiempo y, como los compiladores propagan las constantes, otro código compilado con sus bibliotecas tendrán que volver a compilarse para ver los cambios.</span><span class="sxs-lookup"><span data-stu-id="51247-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="51247-109">Vea también la palabra clave [readonly](../../../csharp/language-reference/keywords/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="51247-109">See also the [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword.</span></span> <span data-ttu-id="51247-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="51247-110">For example:</span></span>  
  
```csharp
const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## <a name="remarks"></a><span data-ttu-id="51247-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51247-111">Remarks</span></span>  
 <span data-ttu-id="51247-112">El tipo de una declaración constante especifica el tipo de los miembros que la declaración presenta.</span><span class="sxs-lookup"><span data-stu-id="51247-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="51247-113">El inicializador de una local constante o de un campo constante debe ser una expresión constante que se pueda convertir implícitamente al tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="51247-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>  
  
 <span data-ttu-id="51247-114">Una expresión constante es una expresión que se puede evaluar por completo en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="51247-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="51247-115">Por lo tanto, los únicos valores posibles para las constantes de tipos de referencia son `string` y una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="51247-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>  
  
 <span data-ttu-id="51247-116">La declaración de constante puede declarar varias constantes, tales como:</span><span class="sxs-lookup"><span data-stu-id="51247-116">The constant declaration can declare multiple constants, such as:</span></span>  
  
```csharp
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 <span data-ttu-id="51247-117">El modificador `static` no se permite en una declaración de constante.</span><span class="sxs-lookup"><span data-stu-id="51247-117">The `static` modifier is not allowed in a constant declaration.</span></span>  
  
 <span data-ttu-id="51247-118">Una constante puede participar en una expresión constante, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="51247-118">A constant can participate in a constant expression, as follows:</span></span>  
  
```csharp
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  <span data-ttu-id="51247-119">La palabra clave [readonly](../../../csharp/language-reference/keywords/readonly.md) difiere de la palabra clave `const`.</span><span class="sxs-lookup"><span data-stu-id="51247-119">The [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="51247-120">Un campo `const` solo se puede inicializar en la declaración del campo.</span><span class="sxs-lookup"><span data-stu-id="51247-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="51247-121">Un campo `readonly` se puede inicializar en la declaración o en un constructor.</span><span class="sxs-lookup"><span data-stu-id="51247-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="51247-122">Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use.</span><span class="sxs-lookup"><span data-stu-id="51247-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="51247-123">Además, aunque un campo `const` es una constante en tiempo de compilación, el campo `readonly` se puede usar para constantes en tiempo de ejecución, como en esta línea: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="51247-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>  
  
## <a name="example"></a><span data-ttu-id="51247-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51247-124">Example</span></span>  
 <span data-ttu-id="51247-125">[!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="51247-125">[!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="51247-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51247-126">Example</span></span>  
 <span data-ttu-id="51247-127">Este ejemplo demuestra cómo usar las constantes como variables locales.</span><span class="sxs-lookup"><span data-stu-id="51247-127">This example demonstrates how to use constants as local variables.</span></span>  
  
 <span data-ttu-id="51247-128">[!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="51247-128">[!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="51247-129">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="51247-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="51247-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="51247-130">See Also</span></span>  
 <span data-ttu-id="51247-131">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="51247-131">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="51247-132">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="51247-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="51247-133">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="51247-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="51247-134">[Modificadores](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="51247-134">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="51247-135">readonly</span><span class="sxs-lookup"><span data-stu-id="51247-135">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)

