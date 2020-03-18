---
title: 'Delegados de C#: un paseo por el lenguaje C#'
description: Conozca los enlaces más recientes con delegados en C#.
ms.date: 02/27/2020
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: b1740ddc65dcb0ee8775f4cbaa8356293ea55fae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78159174"
---
# <a name="delegates"></a><span data-ttu-id="0fbe9-103">Delegados</span><span class="sxs-lookup"><span data-stu-id="0fbe9-103">Delegates</span></span>

<span data-ttu-id="0fbe9-104">Un ***tipo de delegado*** representa las referencias a métodos con una lista de parámetros determinada y un tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-104">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="0fbe9-105">Los delegados permiten tratar métodos como entidades que se puedan asignar a variables y se puedan pasar como parámetros.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-105">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="0fbe9-106">Los delegados son similares al concepto de punteros de función de otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-106">Delegates are similar to the concept of function pointers found in some other languages.</span></span> <span data-ttu-id="0fbe9-107">A diferencia de los punteros de función, los delegados están orientados a objetos y tienen seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-107">Unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="0fbe9-108">En el siguiente ejemplo se declara y usa un tipo de delegado denominado `Function`.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-108">The following example declares and uses a delegate type named `Function`.</span></span>

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

<span data-ttu-id="0fbe9-109">Una instancia del tipo de delegado `Function` puede hacer referencia a cualquier método que tome un argumento `double` y devuelva un valor `double`.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-109">An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value.</span></span> <span data-ttu-id="0fbe9-110">El método `Apply` aplica una función dada a los elementos de un argumento `double[]`, y devuelve un valor `double[]` con los resultados.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-110">The `Apply` method applies a given Function to the elements of a `double[]`, returning a `double[]` with the results.</span></span> <span data-ttu-id="0fbe9-111">En el método `Main`, `Apply` se usa para aplicar tres funciones diferentes a un valor `double[]`.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-111">In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.</span></span>

<span data-ttu-id="0fbe9-112">Un delegado puede hacer referencia a un método estático (como `Square` o `Math.Sin` en el ejemplo anterior) o un método de instancia (como `m.Multiply` en el ejemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="0fbe9-112">A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example).</span></span> <span data-ttu-id="0fbe9-113">Un delegado que hace referencia a un método de instancia también hace referencia a un objeto determinado y, cuando se invoca el método de instancia a través del delegado, ese objeto se convierte en `this` en la invocación.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-113">A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.</span></span>

<span data-ttu-id="0fbe9-114">Los delegados también se pueden crear mediante funciones anónimas, que son "métodos insertados" que se crean al declararlos.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-114">Delegates can also be created using anonymous functions, which are "inline methods" that are created when declared.</span></span> <span data-ttu-id="0fbe9-115">Las funciones anónimas pueden ver las variables locales de los métodos adyacentes.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-115">Anonymous functions can see the local variables of the surrounding methods.</span></span> <span data-ttu-id="0fbe9-116">En el ejemplo siguiente no se crea una clase:</span><span class="sxs-lookup"><span data-stu-id="0fbe9-116">The following example doesn't create a class:</span></span>

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

<span data-ttu-id="0fbe9-117">Un delegado no sabe ni necesita conocer la clase del método al que hace referencia; lo único que importa es que el método al que se hace referencia tenga los mismos parámetros y el tipo de valor devuelto que el delegado.</span><span class="sxs-lookup"><span data-stu-id="0fbe9-117">A delegate doesn't know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0fbe9-118">[Anterior](interfaces.md)
>[Siguiente](attributes.md)</span><span class="sxs-lookup"><span data-stu-id="0fbe9-118">[Previous](interfaces.md)
[Next](attributes.md)</span></span>
