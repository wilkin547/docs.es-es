---
title: dynamic (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- dynamic_CSharpKeyword
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
ms.openlocfilehash: 59957ce6b2a26c1d24dc1178630eef8551db3340
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33217144"
---
# <a name="dynamic-c-reference"></a><span data-ttu-id="1ee7a-102">dynamic (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1ee7a-102">dynamic (C# Reference)</span></span>
<span data-ttu-id="1ee7a-103">El tipo `dynamic` permite que las operaciones en las que se produce omitan la comprobación de tipo en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-103">The `dynamic` type enables the operations in which it occurs to bypass compile-time type checking.</span></span> <span data-ttu-id="1ee7a-104">En su lugar, se resuelven estas operaciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-104">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="1ee7a-105">El tipo `dynamic` simplifica el acceso a las API de COM como las API de automatización de Office y también a API dinámicas como las bibliotecas de IronPython, y a Document Object Model (DOM) HTML.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-105">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, and also to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="1ee7a-106">El tipo `dynamic` se comporta como el tipo `object` en la mayoría de las circunstancias.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-106">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="1ee7a-107">En cambio, el compilador no resuelve o no comprueba el tipo de las operaciones que contienen expresiones de tipo `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-107">However, operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="1ee7a-108">El compilador empaqueta información sobre la operación y esa información se usa después para evaluar la operación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-108">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="1ee7a-109">Como parte del proceso, las variables de tipo `dynamic` están compiladas en las variables de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-109">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="1ee7a-110">Por consiguiente, el tipo `dynamic` solo existe en tiempo de compilación, no en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-110">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>  
  
 <span data-ttu-id="1ee7a-111">En el siguiente ejemplo se contrasta una variable de tipo `dynamic` con una variable de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-111">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="1ee7a-112">Para comprobar el tipo de cada variable en tiempo de compilación, coloque el puntero del mouse sobre `dyn` u `obj` en las instrucciones `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-112">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="1ee7a-113">IntelliSense muestra **dynamic** para `dyn` y **object** para `obj`.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-113">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]  
  
 <span data-ttu-id="1ee7a-114">Las instrucciones `WriteLine` muestran los tipos en tiempo de ejecución de `dyn` y `obj`.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-114">The `WriteLine` statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="1ee7a-115">En ese punto, ambos tienen el mismo tipo, entero.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-115">At that point, both have the same type, integer.</span></span> <span data-ttu-id="1ee7a-116">Se produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="1ee7a-116">The following output is produced:</span></span>  
  
 `System.Int32`  
  
 `System.Int32`  
  
 <span data-ttu-id="1ee7a-117">Para ver la diferencia entre `dyn` y `obj` en tiempo de compilación, agregue las dos líneas siguientes entre las declaraciones y las instrucciones `WriteLine` en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-117">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>  
  
```csharp  
dyn = dyn + 3;  
obj = obj + 3;  
```  
  
 <span data-ttu-id="1ee7a-118">Un error del compilador se notifica para el intento de suma de un entero y un objeto en la expresión `obj + 3`.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-118">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="1ee7a-119">En cambio, no se notifica ningún error para `dyn + 3`.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-119">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="1ee7a-120">En tiempo de compilación no se comprueba la expresión que contiene `dyn` porque el tipo de `dyn` es `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-120">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>  
  
## <a name="context"></a><span data-ttu-id="1ee7a-121">Contexto</span><span class="sxs-lookup"><span data-stu-id="1ee7a-121">Context</span></span>  
 <span data-ttu-id="1ee7a-122">La palabra clave `dynamic` puede aparecer directamente o como un componente de un tipo construido en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="1ee7a-122">The `dynamic` keyword can appear directly or as a component of a constructed type in the following situations:</span></span>  
  
-   <span data-ttu-id="1ee7a-123">En declaraciones, como el tipo de una propiedad, un campo, un indexador, un parámetro, un valor devuelto, una variable local o una restricción de tipo.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-123">In declarations, as the type of a property, field, indexer, parameter, return value, local variable, or type constraint.</span></span> <span data-ttu-id="1ee7a-124">La siguiente definición de clase usa `dynamic` en varias declaraciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-124">The following class definition uses `dynamic` in several different declarations.</span></span>  
  
     [!code-csharp[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]  
  
-   <span data-ttu-id="1ee7a-125">En conversiones de tipos explícitas, como el tipo de destino de una conversión.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-125">In explicit type conversions, as the target type of a conversion.</span></span>  
  
     [!code-csharp[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]  
  
-   <span data-ttu-id="1ee7a-126">En cualquier contexto donde los tipos actúen como valores, por ejemplo, en el lado derecho de un operador `is` o un operador `as`, o como argumento de `typeof` como parte de un tipo construido.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-126">In any context where types serve as values, such as on the right side of an `is` operator or an `as` operator, or as the argument to `typeof` as part of a constructed type.</span></span> <span data-ttu-id="1ee7a-127">Por ejemplo, se puede usar `dynamic` en las siguientes expresiones.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-127">For example, `dynamic` can be used in the following expressions.</span></span>  
  
     [!code-csharp[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="1ee7a-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ee7a-128">Example</span></span>  
 <span data-ttu-id="1ee7a-129">El ejemplo siguiente usa `dynamic` en varias declaraciones.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-129">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="1ee7a-130">El método `Main` también contrasta la comprobación de tipo en tiempo de compilación con la comprobación de tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ee7a-130">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]  
  
 <span data-ttu-id="1ee7a-131">Para obtener más información y ejemplos, vea [Uso de tipo dinámico (Guía de programación de C#)](../../../csharp/programming-guide/types/using-type-dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="1ee7a-131">For more information and examples, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee7a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ee7a-132">See Also</span></span>  
 <xref:System.Dynamic.ExpandoObject?displayProperty=nameWithType>  
 <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>  
 [<span data-ttu-id="1ee7a-133">Uso de tipo dinámico</span><span class="sxs-lookup"><span data-stu-id="1ee7a-133">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [<span data-ttu-id="1ee7a-134">object</span><span class="sxs-lookup"><span data-stu-id="1ee7a-134">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
 [<span data-ttu-id="1ee7a-135">is</span><span class="sxs-lookup"><span data-stu-id="1ee7a-135">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
 [<span data-ttu-id="1ee7a-136">as</span><span class="sxs-lookup"><span data-stu-id="1ee7a-136">as</span></span>](../../../csharp/language-reference/keywords/as.md)  
 [<span data-ttu-id="1ee7a-137">typeof</span><span class="sxs-lookup"><span data-stu-id="1ee7a-137">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)  
 [<span data-ttu-id="1ee7a-138">Cómo: Realizar conversiones seguras usando los operadores is y as</span><span class="sxs-lookup"><span data-stu-id="1ee7a-138">How to: Safely Cast by Using as and is Operators</span></span>](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)  
 <span data-ttu-id="1ee7a-139">[Walkthrough: Creating and Using Dynamic Objects](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) (Tutorial: Crear y usar objetos dinámicos [C# y Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="1ee7a-139">[Walkthrough: Creating and Using Dynamic Objects](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)</span></span>
