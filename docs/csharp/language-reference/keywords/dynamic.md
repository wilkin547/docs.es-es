---
title: dynamic (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- dynamic_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
caps.latest.revision: 25
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
ms.openlocfilehash: b68a6ef4dc3dda01638b9bb84db58ba77214f490
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="dynamic-c-reference"></a><span data-ttu-id="33279-102">dynamic (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="33279-102">dynamic (C# Reference)</span></span>
<span data-ttu-id="33279-103">El tipo `dynamic` permite que las operaciones en las que se produce omitan la comprobación de tipo en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="33279-103">The `dynamic` type enables the operations in which it occurs to bypass compile-time type checking.</span></span> <span data-ttu-id="33279-104">En su lugar, se resuelven estas operaciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="33279-104">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="33279-105">El tipo `dynamic` simplifica el acceso a las API de COM como las API de automatización de Office y también a API dinámicas como las bibliotecas de IronPython, y a Document Object Model (DOM) HTML.</span><span class="sxs-lookup"><span data-stu-id="33279-105">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, and also to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="33279-106">El tipo `dynamic` se comporta como el tipo `object` en la mayoría de las circunstancias.</span><span class="sxs-lookup"><span data-stu-id="33279-106">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="33279-107">En cambio, el compilador no resuelve o no comprueba el tipo de las operaciones que contienen expresiones de tipo `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="33279-107">However, operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="33279-108">El compilador empaqueta información sobre la operación y esa información se usa después para evaluar la operación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="33279-108">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="33279-109">Como parte del proceso, las variables de tipo `dynamic` están compiladas en las variables de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="33279-109">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="33279-110">Por consiguiente, el tipo `dynamic` solo existe en tiempo de compilación, no en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="33279-110">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>  
  
 <span data-ttu-id="33279-111">En el siguiente ejemplo se contrasta una variable de tipo `dynamic` con una variable de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="33279-111">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="33279-112">Para comprobar el tipo de cada variable en tiempo de compilación, coloque el puntero del mouse sobre `dyn` u `obj` en las instrucciones `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="33279-112">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="33279-113">IntelliSense muestra **dynamic** para `dyn` y **object** para `obj`.</span><span class="sxs-lookup"><span data-stu-id="33279-113">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>  
  
 <span data-ttu-id="33279-114">[!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="33279-114">[!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]</span></span>  
  
 <span data-ttu-id="33279-115">Las instrucciones `WriteLine` muestran los tipos en tiempo de ejecución de `dyn` y `obj`.</span><span class="sxs-lookup"><span data-stu-id="33279-115">The `WriteLine` statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="33279-116">En ese punto, ambos tienen el mismo tipo, entero.</span><span class="sxs-lookup"><span data-stu-id="33279-116">At that point, both have the same type, integer.</span></span> <span data-ttu-id="33279-117">Se produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="33279-117">The following output is produced:</span></span>  
  
 `System.Int32`  
  
 `System.Int32`  
  
 <span data-ttu-id="33279-118">Para ver la diferencia entre `dyn` y `obj` en tiempo de compilación, agregue las dos líneas siguientes entre las declaraciones y las instrucciones `WriteLine` en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="33279-118">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>  
  
```csharp  
dyn = dyn + 3;  
obj = obj + 3;  
```  
  
 <span data-ttu-id="33279-119">Un error del compilador se notifica para el intento de suma de un entero y un objeto en la expresión `obj + 3`.</span><span class="sxs-lookup"><span data-stu-id="33279-119">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="33279-120">En cambio, no se notifica ningún error para `dyn + 3`.</span><span class="sxs-lookup"><span data-stu-id="33279-120">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="33279-121">En tiempo de compilación no se comprueba la expresión que contiene `dyn` porque el tipo de `dyn` es `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="33279-121">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>  
  
## <a name="context"></a><span data-ttu-id="33279-122">Contexto</span><span class="sxs-lookup"><span data-stu-id="33279-122">Context</span></span>  
 <span data-ttu-id="33279-123">La palabra clave `dynamic` puede aparecer directamente o como un componente de un tipo construido en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="33279-123">The `dynamic` keyword can appear directly or as a component of a constructed type in the following situations:</span></span>  
  
-   <span data-ttu-id="33279-124">En declaraciones, como el tipo de una propiedad, un campo, un indexador, un parámetro, un valor devuelto, una variable local o una restricción de tipo.</span><span class="sxs-lookup"><span data-stu-id="33279-124">In declarations, as the type of a property, field, indexer, parameter, return value, local variable, or type constraint.</span></span> <span data-ttu-id="33279-125">La siguiente definición de clase usa `dynamic` en varias declaraciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="33279-125">The following class definition uses `dynamic` in several different declarations.</span></span>  
  
     <span data-ttu-id="33279-126">[!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="33279-126">[!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]</span></span>  
  
-   <span data-ttu-id="33279-127">En conversiones de tipos explícitas, como el tipo de destino de una conversión.</span><span class="sxs-lookup"><span data-stu-id="33279-127">In explicit type conversions, as the target type of a conversion.</span></span>  
  
     <span data-ttu-id="33279-128">[!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="33279-128">[!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]</span></span>  
  
-   <span data-ttu-id="33279-129">En cualquier contexto donde los tipos actúen como valores, por ejemplo, en el lado derecho de un operador `is` o un operador `as`, o como argumento de `typeof` como parte de un tipo construido.</span><span class="sxs-lookup"><span data-stu-id="33279-129">In any context where types serve as values, such as on the right side of an `is` operator or an `as` operator, or as the argument to `typeof` as part of a constructed type.</span></span> <span data-ttu-id="33279-130">Por ejemplo, se puede usar `dynamic` en las siguientes expresiones.</span><span class="sxs-lookup"><span data-stu-id="33279-130">For example, `dynamic` can be used in the following expressions.</span></span>  
  
     <span data-ttu-id="33279-131">[!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="33279-131">[!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="33279-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33279-132">Example</span></span>  
 <span data-ttu-id="33279-133">El ejemplo siguiente usa `dynamic` en varias declaraciones.</span><span class="sxs-lookup"><span data-stu-id="33279-133">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="33279-134">El método `Main` también contrasta la comprobación de tipo en tiempo de compilación con la comprobación de tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="33279-134">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>  
  
 <span data-ttu-id="33279-135">[!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="33279-135">[!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]</span></span>  
  
 <span data-ttu-id="33279-136">Para obtener más información y ejemplos, vea [Uso de tipo dinámico (Guía de programación de C#)](../../../csharp/programming-guide/types/using-type-dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="33279-136">For more information and examples, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33279-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="33279-137">See Also</span></span>  
 <span data-ttu-id="33279-138"><xref:System.Dynamic.ExpandoObject?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="33279-138"><xref:System.Dynamic.ExpandoObject?displayProperty=fullName></span></span>   
 <span data-ttu-id="33279-139"><xref:System.Dynamic.DynamicObject?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="33279-139"><xref:System.Dynamic.DynamicObject?displayProperty=fullName></span></span>   
 <span data-ttu-id="33279-140">[Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="33279-140">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="33279-141">[object](../../../csharp/language-reference/keywords/object.md) </span><span class="sxs-lookup"><span data-stu-id="33279-141">[object](../../../csharp/language-reference/keywords/object.md) </span></span>  
 <span data-ttu-id="33279-142">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="33279-142">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="33279-143">[as](../../../csharp/language-reference/keywords/as.md) </span><span class="sxs-lookup"><span data-stu-id="33279-143">[as](../../../csharp/language-reference/keywords/as.md) </span></span>  
 <span data-ttu-id="33279-144">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span><span class="sxs-lookup"><span data-stu-id="33279-144">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span></span>  
 <span data-ttu-id="33279-145">[Cómo: Realizar conversiones seguras usando los operadores is y as (Guía de programación de C#)](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md) </span><span class="sxs-lookup"><span data-stu-id="33279-145">[How to: Safely Cast by Using as and is Operators](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md) </span></span>  
 <span data-ttu-id="33279-146">[Walkthrough: Creating and Using Dynamic Objects](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) (Tutorial: Crear y usar objetos dinámicos [C# y Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="33279-146">[Walkthrough: Creating and Using Dynamic Objects](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)</span></span>

