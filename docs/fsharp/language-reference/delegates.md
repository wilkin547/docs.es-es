---
title: Delegados
description: Obtenga información sobre cómo trabajar con delegados en F#.
ms.date: 05/16/2016
ms.openlocfilehash: 65875897d5fc4b2ac66f1dfbe913f29fb74137cd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630371"
---
# <a name="delegates"></a><span data-ttu-id="cd1e8-103">Delegados</span><span class="sxs-lookup"><span data-stu-id="cd1e8-103">Delegates</span></span>

<span data-ttu-id="cd1e8-104">Un delegado representa una llamada de función como un objeto.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="cd1e8-105">En F#, normalmente debería usar valores de función para representar funciones como valores de primera clase; sin embargo, los delegados se usan en el .NET Framework y, por tanto, son necesarios cuando se interoperan con las API que los esperan.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="cd1e8-106">También se pueden usar al crear bibliotecas diseñadas para su uso desde otros lenguajes .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="cd1e8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd1e8-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="cd1e8-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd1e8-108">Remarks</span></span>

<span data-ttu-id="cd1e8-109">En la sintaxis anterior, `type1` representa el tipo de argumento o los `type2` tipos y representa el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="cd1e8-110">Los tipos de argumento que se representan `type1` mediante se convierten automáticamente en currificados.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="cd1e8-111">Esto sugiere que, para este tipo, se usa un formato de tupla si los argumentos de la función de destino son currificados y una tupla entre paréntesis para los argumentos que ya están en el formato de tupla.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="cd1e8-112">La currificación automática quita un conjunto de paréntesis y mantiene un argumento de tupla que coincide con el método de destino.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="cd1e8-113">Consulte el ejemplo de código para la sintaxis que se debe usar en cada caso.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="cd1e8-114">Los delegados se F# pueden adjuntar a valores de función y métodos estáticos o de instancia.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="cd1e8-115">F#los valores de función se pueden pasar directamente como argumentos a los constructores de delegado.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="cd1e8-116">Para un método estático, se construye el delegado utilizando el nombre de la clase y el método.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="cd1e8-117">Para un método de instancia, debe proporcionar la instancia de objeto y el método en un argumento.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="cd1e8-118">En ambos casos, se utiliza el operador de`.`acceso a miembros ().</span><span class="sxs-lookup"><span data-stu-id="cd1e8-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="cd1e8-119">El `Invoke` método en el tipo de delegado llama a la función encapsulada.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="cd1e8-120">Además, los delegados se pueden pasar como valores de función haciendo referencia al nombre del método de invocación sin los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="cd1e8-121">En el código siguiente se muestra la sintaxis para crear delegados que representan varios métodos de una clase.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="cd1e8-122">Dependiendo de si el método es un método estático o un método de instancia, y si tiene argumentos en el formato de tupla o en el formato currificados, la sintaxis para declarar y asignar el delegado es un poco diferente.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="cd1e8-123">En el código siguiente se muestran algunas de las distintas formas en que puede trabajar con los delegados.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="cd1e8-124">La salida del ejemplo de código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd1e8-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="cd1e8-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd1e8-125">See also</span></span>

- [<span data-ttu-id="cd1e8-126">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="cd1e8-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="cd1e8-127">Parámetros y argumentos</span><span class="sxs-lookup"><span data-stu-id="cd1e8-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="cd1e8-128">Eventos</span><span class="sxs-lookup"><span data-stu-id="cd1e8-128">Events</span></span>](./members/events.md)
