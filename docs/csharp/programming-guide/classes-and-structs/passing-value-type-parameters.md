---
title: "Pasar parámetros de tipo de valor (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
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
ms.openlocfilehash: a3377630fc4294831f6b9d66a69377aa42d973f1
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="passing-value-type-parameters-c-programming-guide"></a><span data-ttu-id="9b442-102">Pasar parámetros de tipo de valor (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9b442-102">Passing Value-Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="9b442-103">Una variable [tipo de valor](../../../csharp/language-reference/keywords/value-types.md) contiene sus datos directamente, en oposición a la variable [tipo de referencia](../../../csharp/language-reference/keywords/reference-types.md), que contiene una referencia a sus datos.</span><span class="sxs-lookup"><span data-stu-id="9b442-103">A [value-type](../../../csharp/language-reference/keywords/value-types.md) variable contains its data directly as opposed to a [reference-type](../../../csharp/language-reference/keywords/reference-types.md) variable, which contains a reference to its data.</span></span> <span data-ttu-id="9b442-104">Pasar una variable tipo de valor a un método en función del valor significa pasar una copia de la variable al método.</span><span class="sxs-lookup"><span data-stu-id="9b442-104">Passing a value-type variable to a method by value means passing a copy of the variable to the method.</span></span> <span data-ttu-id="9b442-105">Ningún cambio realizado en el parámetro dentro del método afecta a los datos originales almacenados en la variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="9b442-105">Any changes to the parameter that take place inside the method have no affect on the original data stored in the argument variable.</span></span> <span data-ttu-id="9b442-106">Si desea que el método al que se llama cambie el valor del parámetro, debe pasarlo en función de la referencia, con la palabra clave [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out.md).</span><span class="sxs-lookup"><span data-stu-id="9b442-106">If you want the called method to change the value of the parameter, you must pass it by reference, using the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) keyword.</span></span> <span data-ttu-id="9b442-107">Para simplificar, en el ejemplo siguiente se usa `ref`.</span><span class="sxs-lookup"><span data-stu-id="9b442-107">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-value-types-by-value"></a><span data-ttu-id="9b442-108">Pasar tipos de valor en función del valor</span><span class="sxs-lookup"><span data-stu-id="9b442-108">Passing Value Types by Value</span></span>  
 <span data-ttu-id="9b442-109">En el ejemplo siguiente se muestra cómo pasar los parámetros de tipo de valor en función del valor.</span><span class="sxs-lookup"><span data-stu-id="9b442-109">The following example demonstrates passing value-type parameters by value.</span></span> <span data-ttu-id="9b442-110">La variable `n` se pasa en función del valor al método `SquareIt`.</span><span class="sxs-lookup"><span data-stu-id="9b442-110">The variable `n` is passed by value to the method `SquareIt`.</span></span> <span data-ttu-id="9b442-111">Los cambios que tienen lugar dentro del método no tienen ningún efecto en el valor original de la variable.</span><span class="sxs-lookup"><span data-stu-id="9b442-111">Any changes that take place inside the method have no affect on the original value of the variable.</span></span>  
  
 <span data-ttu-id="9b442-112">[!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9b442-112">[!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="9b442-113">La variable `n` es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="9b442-113">The variable `n` is a value type.</span></span> <span data-ttu-id="9b442-114">Contiene sus datos, el valor `5`.</span><span class="sxs-lookup"><span data-stu-id="9b442-114">It contains its data, the value `5`.</span></span> <span data-ttu-id="9b442-115">Cuando se invoca `SquareIt`, el contenido de `n` se copia en el parámetro `x`, que se multiplica dentro del método.</span><span class="sxs-lookup"><span data-stu-id="9b442-115">When `SquareIt` is invoked, the contents of `n` are copied into the parameter `x`, which is squared inside the method.</span></span> <span data-ttu-id="9b442-116">En `Main`, sin embargo, el valor de `n` es el mismo después de llamar al método`SquareIt` que el que era antes.</span><span class="sxs-lookup"><span data-stu-id="9b442-116">In `Main`, however, the value of `n` is the same after calling the `SquareIt` method as it was before.</span></span> <span data-ttu-id="9b442-117">El cambio que tiene lugar dentro del método solo afecta a la variable local `x`.</span><span class="sxs-lookup"><span data-stu-id="9b442-117">The change that takes place inside the method only affects the local variable `x`.</span></span>  
  
## <a name="passing-value-types-by-reference"></a><span data-ttu-id="9b442-118">Pasar tipos de valor en función de la referencia</span><span class="sxs-lookup"><span data-stu-id="9b442-118">Passing Value Types by Reference</span></span>  
 <span data-ttu-id="9b442-119">El ejemplo siguiente es el mismo que el anterior, salvo que el argumento se pasa como un parámetro `ref`.</span><span class="sxs-lookup"><span data-stu-id="9b442-119">The following example is the same as the previous example, except that the argument is passed as a `ref` parameter.</span></span> <span data-ttu-id="9b442-120">El valor del argumento subyacente, `n`, se cambia cuando se modifica `x` en el método.</span><span class="sxs-lookup"><span data-stu-id="9b442-120">The value of the underlying argument, `n`, is changed when `x` is changed in the method.</span></span>  
  
 <span data-ttu-id="9b442-121">[!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9b442-121">[!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]</span></span>  
  
 <span data-ttu-id="9b442-122">En este ejemplo, no es el valor de `n` el que se pasa, sino una referencia a `n`.</span><span class="sxs-lookup"><span data-stu-id="9b442-122">In this example, it is not the value of `n` that is passed; rather, a reference to `n` is passed.</span></span> <span data-ttu-id="9b442-123">El parámetro `x` no es un [entero](../../../csharp/language-reference/keywords/int.md); se trata de una referencia a `int`, en este caso, una referencia a `n`.</span><span class="sxs-lookup"><span data-stu-id="9b442-123">The parameter `x` is not an [int](../../../csharp/language-reference/keywords/int.md); it is a reference to an `int`, in this case, a reference to `n`.</span></span> <span data-ttu-id="9b442-124">Por tanto, cuando `x` se multiplica dentro del método, lo que realmente se multiplica es a lo que `x` hace referencia, `n`.</span><span class="sxs-lookup"><span data-stu-id="9b442-124">Therefore, when `x` is squared inside the method, what actually is squared is what `x` refers to, `n`.</span></span>  
  
## <a name="swapping-value-types"></a><span data-ttu-id="9b442-125">Intercambiar tipos de valor</span><span class="sxs-lookup"><span data-stu-id="9b442-125">Swapping Value Types</span></span>  
 <span data-ttu-id="9b442-126">Un ejemplo común de modificación de valores de argumentos es un método de intercambio, donde se pasan dos variables al método, y el método intercambia su contenido.</span><span class="sxs-lookup"><span data-stu-id="9b442-126">A common example of changing the values of arguments is a swap method, where you pass two variables to the method, and the method swaps their contents.</span></span> <span data-ttu-id="9b442-127">Debe pasar los argumentos al método de intercambio en función de la referencia.</span><span class="sxs-lookup"><span data-stu-id="9b442-127">You must pass the arguments to the swap method by reference.</span></span> <span data-ttu-id="9b442-128">De lo contrario, se intercambian copias locales de los parámetros dentro del método, y no se produce ningún cambio en el método de llamada.</span><span class="sxs-lookup"><span data-stu-id="9b442-128">Otherwise, you swap local copies of the parameters inside the method, and no change occurs in the calling method.</span></span> <span data-ttu-id="9b442-129">En el ejemplo siguiente se intercambian valores enteros.</span><span class="sxs-lookup"><span data-stu-id="9b442-129">The following example swaps integer values.</span></span>  
  
 <span data-ttu-id="9b442-130">[!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="9b442-130">[!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]</span></span>  
  
 <span data-ttu-id="9b442-131">Al llamar al método `SwapByRef`, use la palabra clave `ref` en la llamada, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9b442-131">When you call the `SwapByRef` method, use the `ref` keyword in the call, as shown in the following example.</span></span>  
  
 <span data-ttu-id="9b442-132">[!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="9b442-132">[!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b442-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b442-133">See Also</span></span>  
 <span data-ttu-id="9b442-134">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9b442-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9b442-135">[Pasar parámetros](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="9b442-135">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 [<span data-ttu-id="9b442-136">Pasar parámetros Reference-Type</span><span class="sxs-lookup"><span data-stu-id="9b442-136">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)

