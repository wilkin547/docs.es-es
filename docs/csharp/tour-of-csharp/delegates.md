---
title: 'Delegados de C#: un paseo por el lenguaje C#'
description: Conozca los enlaces más recientes con delegados en C#.
ms.date: 08/10/2016
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: 35a1e212b50e77eb43271a657c8abb21eb6cfb4a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634627"
---
# <a name="delegates"></a><span data-ttu-id="641c4-103">Delegados</span><span class="sxs-lookup"><span data-stu-id="641c4-103">Delegates</span></span>

<span data-ttu-id="641c4-104">Un ***tipo de delegado*** representa las referencias a métodos con una lista de parámetros determinada y un tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="641c4-104">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="641c4-105">Los delegados permiten tratar métodos como entidades que se puedan asignar a variables y se puedan pasar como parámetros.</span><span class="sxs-lookup"><span data-stu-id="641c4-105">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="641c4-106">Los delegados son similares al concepto de punteros de función en otros lenguajes, pero a diferencia de los punteros de función, los delegados están orientados a objetos y presentan seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="641c4-106">Delegates are similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="641c4-107">En el siguiente ejemplo se declara y usa un tipo de delegado denominado `Function`.</span><span class="sxs-lookup"><span data-stu-id="641c4-107">The following example declares and uses a delegate type named `Function`.</span></span>

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

<span data-ttu-id="641c4-108">Una instancia del tipo de delegado `Function` puede hacer referencia a cualquier método que tome un argumento `double` y devuelva un valor `double`.</span><span class="sxs-lookup"><span data-stu-id="641c4-108">An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value.</span></span> <span data-ttu-id="641c4-109">El método `Apply` aplica una función dada a los elementos de un argumento `double[]`, y devuelve un valor `double[]` con los resultados.</span><span class="sxs-lookup"><span data-stu-id="641c4-109">The `Apply` method applies a given Function to the elements of a `double[]`, returning a `double[]` with the results.</span></span> <span data-ttu-id="641c4-110">En el método `Main`, `Apply` se usa para aplicar tres funciones diferentes a un valor `double[]`.</span><span class="sxs-lookup"><span data-stu-id="641c4-110">In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.</span></span>

<span data-ttu-id="641c4-111">Un delegado puede hacer referencia a un método estático (como `Square` o `Math.Sin` en el ejemplo anterior) o un método de instancia (como `m.Multiply` en el ejemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="641c4-111">A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example).</span></span> <span data-ttu-id="641c4-112">Un delegado que hace referencia a un método de instancia también hace referencia a un objeto determinado y, cuando se invoca el método de instancia a través del delegado, ese objeto se convierte en `this` en la invocación.</span><span class="sxs-lookup"><span data-stu-id="641c4-112">A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.</span></span>

<span data-ttu-id="641c4-113">Los delegados también pueden crearse mediante funciones anónimas, que son "métodos insertados" que se crean sobre la marcha.</span><span class="sxs-lookup"><span data-stu-id="641c4-113">Delegates can also be created using anonymous functions, which are "inline methods" that are created on the fly.</span></span> <span data-ttu-id="641c4-114">Las funciones anónimas pueden ver las variables locales de los métodos adyacentes.</span><span class="sxs-lookup"><span data-stu-id="641c4-114">Anonymous functions can see the local variables of the surrounding methods.</span></span> <span data-ttu-id="641c4-115">Por lo tanto, el ejemplo de multiplicador anterior puede escribirse más fácilmente sin utilizarse una clase de Multiplier:</span><span class="sxs-lookup"><span data-stu-id="641c4-115">Thus, the multiplier example above can be written more easily without using a Multiplier class:</span></span>

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

<span data-ttu-id="641c4-116">Una propiedad interesante y útil de un delegado es que no sabe ni necesita conocer la clase del método al que hace referencia; lo único que importa es que el método al que se hace referencia tenga los mismos parámetros y el tipo de valor devuelto que el delegado.</span><span class="sxs-lookup"><span data-stu-id="641c4-116">An interesting and useful property of a delegate is that it does not know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="641c4-117">[Anterior](enums.md)
>[Siguiente](attributes.md)</span><span class="sxs-lookup"><span data-stu-id="641c4-117">[Previous](enums.md)
[Next](attributes.md)</span></span>
