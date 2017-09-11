---
title: "Pasar parámetros Reference-Type (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: 14
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
ms.openlocfilehash: 3f57dc9f0de6fae6da3ec8e6e6cfdc3a21baeaea
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="passing-reference-type-parameters-c-programming-guide"></a><span data-ttu-id="7ce03-102">Pasar parámetros Reference-Type (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7ce03-102">Passing Reference-Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="7ce03-103">Una variable de un [tipo de referencia](../../../csharp/language-reference/keywords/reference-types.md) no contiene sus datos directamente, contiene una referencia a sus datos.</span><span class="sxs-lookup"><span data-stu-id="7ce03-103">A variable of a [reference type](../../../csharp/language-reference/keywords/reference-types.md) does not contain its data directly; it contains a reference to its data.</span></span> <span data-ttu-id="7ce03-104">Al pasar un parámetro de tipo de referencia por valor, es posible cambiar los datos a los que apunta el tipo de referencia, como el valor de un miembro de clase.</span><span class="sxs-lookup"><span data-stu-id="7ce03-104">When you pass a reference-type parameter by value, it is possible to change the data pointed to by the reference, such as the value of a class member.</span></span> <span data-ttu-id="7ce03-105">En cambio, no se puede cambiar el valor de la propia referencia; es decir, no puede usar la misma referencia para asignar memoria para una nueva clase y hacer que persista fuera del bloque.</span><span class="sxs-lookup"><span data-stu-id="7ce03-105">However, you cannot change the value of the reference itself; that is, you cannot use the same reference to allocate memory for a new class and have it persist outside the block.</span></span> <span data-ttu-id="7ce03-106">Para ello, pase el parámetro mediante las palabras clave [ref](../../../csharp/language-reference/keywords/ref.md) u [out](../../../csharp/language-reference/keywords/out.md).</span><span class="sxs-lookup"><span data-stu-id="7ce03-106">To do that, pass the parameter using the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) keyword.</span></span> <span data-ttu-id="7ce03-107">Para simplificar, en el ejemplo siguiente se usa `ref`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-107">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-reference-types-by-value"></a><span data-ttu-id="7ce03-108">Pasar tipos de referencia en función del valor</span><span class="sxs-lookup"><span data-stu-id="7ce03-108">Passing Reference Types by Value</span></span>  
 <span data-ttu-id="7ce03-109">En el ejemplo siguiente, se muestra cómo pasar un parámetro de tipo de referencia, `arr`, en función del valor a un método, `Change`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-109">The following example demonstrates passing a reference-type parameter, `arr`, by value, to a method, `Change`.</span></span> <span data-ttu-id="7ce03-110">Dado que el parámetro es una referencia a `arr`, es posible cambiar los valores de los elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="7ce03-110">Because the parameter is a reference to `arr`, it is possible to change the values of the array elements.</span></span> <span data-ttu-id="7ce03-111">En cambio, el intento de volver a asignar el parámetro a otra ubicación de memoria solo funciona dentro del método y no afecta a la variable original, `arr`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-111">However, the attempt to reassign the parameter to a different memory location only works inside the method and does not affect the original variable, `arr`.</span></span>  
  
 <span data-ttu-id="7ce03-112">[!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7ce03-112">[!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="7ce03-113">En el ejemplo anterior, la matriz, `arr`, que es un tipo de referencia, se pasa al método sin el parámetro `ref`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-113">In the preceding example, the array, `arr`, which is a reference type, is passed to the method without the `ref` parameter.</span></span> <span data-ttu-id="7ce03-114">En tal caso, se pasa al método una copia de la referencia, que apunta a `arr`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-114">In such a case, a copy of the reference, which points to `arr`, is passed to the method.</span></span> <span data-ttu-id="7ce03-115">El resultado muestra que es posible que el método cambie el contenido de un elemento de matriz, en este caso de `1` a `888`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-115">The output shows that it is possible for the method to change the contents of an array element, in this case from `1` to `888`.</span></span> <span data-ttu-id="7ce03-116">En cambio, si se asigna una nueva porción de memoria al usar el operador [new](../../../csharp/language-reference/keywords/new.md) dentro del método `Change`, la variable `pArray` hace referencia a una nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="7ce03-116">However, allocating a new portion of memory by using the [new](../../../csharp/language-reference/keywords/new.md) operator inside the `Change` method makes the variable `pArray` reference a new array.</span></span> <span data-ttu-id="7ce03-117">Por tanto, cualquier cambio que hubiese después no afectará a la matriz original, `arr`, que se ha creado dentro de `Main`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-117">Thus, any changes after that will not affect the original array, `arr`, which is created inside `Main`.</span></span> <span data-ttu-id="7ce03-118">De hecho, se crean dos matrices en este ejemplo, una dentro de `Main` y otra dentro del método `Change`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-118">In fact, two arrays are created in this example, one inside `Main` and one inside the `Change` method.</span></span>  
  
## <a name="passing-reference-types-by-reference"></a><span data-ttu-id="7ce03-119">Pasar tipos de referencia en función de la referencia</span><span class="sxs-lookup"><span data-stu-id="7ce03-119">Passing Reference Types by Reference</span></span>  
 <span data-ttu-id="7ce03-120">El ejemplo siguiente es el mismo que el anterior, salvo que la palabra clave `ref` se agrega a la llamada y al encabezado de método.</span><span class="sxs-lookup"><span data-stu-id="7ce03-120">The following example is the same as the previous example, except that the `ref` keyword is added to the method header and call.</span></span> <span data-ttu-id="7ce03-121">Los cambios que tengan lugar en el método afectan a la variable original en el programa que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="7ce03-121">Any changes that take place in the method affect the original variable in the calling program.</span></span>  
  
 <span data-ttu-id="7ce03-122">[!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="7ce03-122">[!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]</span></span>  
  
 <span data-ttu-id="7ce03-123">Todos los cambios que tienen lugar dentro del método afectan a la matriz original en `Main`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-123">All of the changes that take place inside the method affect the original array in `Main`.</span></span> <span data-ttu-id="7ce03-124">De hecho, la matriz original se reasigna mediante el operador `new`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-124">In fact, the original array is reallocated using the `new` operator.</span></span> <span data-ttu-id="7ce03-125">Por tanto, después de llamar al método `Change`, cualquier referencia a `arr` apunta a la matriz de cinco elementos, que se crea en el método `Change`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-125">Thus, after calling the `Change` method, any reference to `arr` points to the five-element array, which is created in the `Change` method.</span></span>  
  
## <a name="swapping-two-strings"></a><span data-ttu-id="7ce03-126">Intercambiar dos cadenas</span><span class="sxs-lookup"><span data-stu-id="7ce03-126">Swapping Two Strings</span></span>  
 <span data-ttu-id="7ce03-127">Intercambiar cadenas es un buen ejemplo de pasar parámetros de tipo de referencia en función de la referencia.</span><span class="sxs-lookup"><span data-stu-id="7ce03-127">Swapping strings is a good example of passing reference-type parameters by reference.</span></span> <span data-ttu-id="7ce03-128">En el ejemplo, se inicializan dos cadenas, `str1` y `str2`, en `Main` y se pasan al método `SwapStrings` como parámetros modificados por la palabra clave `ref`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-128">In the example, two strings, `str1` and `str2`, are initialized in `Main` and passed to the `SwapStrings` method as parameters modified by the `ref` keyword.</span></span> <span data-ttu-id="7ce03-129">Las dos cadenas se intercambian dentro del método y también dentro de `Main`.</span><span class="sxs-lookup"><span data-stu-id="7ce03-129">The two strings are swapped inside the method and inside `Main` as well.</span></span>  
  
 <span data-ttu-id="7ce03-130">[!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="7ce03-130">[!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]</span></span>  
  
 <span data-ttu-id="7ce03-131">En este ejemplo, los parámetros tienen que pasarse en función de la referencia para afectar a las variables en el programa que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="7ce03-131">In this example, the parameters need to be passed by reference to affect the variables in the calling program.</span></span> <span data-ttu-id="7ce03-132">Si quita la palabra clave `ref` tanto del encabezado de método como de la llamada al método, no se llevará a cabo ningún cambio en el programa que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="7ce03-132">If you remove the `ref` keyword from both the method header and the method call, no changes will take place in the calling program.</span></span>  
  
 <span data-ttu-id="7ce03-133">Para obtener más información sobre las cadenas, vea [string](../../../csharp/language-reference/keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="7ce03-133">For more information about strings, see [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce03-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ce03-134">See Also</span></span>  
 <span data-ttu-id="7ce03-135">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7ce03-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7ce03-136">[Pasar parámetros](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="7ce03-136">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 <span data-ttu-id="7ce03-137">[Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md) </span><span class="sxs-lookup"><span data-stu-id="7ce03-137">[Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md) </span></span>  
 <span data-ttu-id="7ce03-138">[ref](../../../csharp/language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="7ce03-138">[ref](../../../csharp/language-reference/keywords/ref.md) </span></span>  
 [<span data-ttu-id="7ce03-139">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="7ce03-139">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)

