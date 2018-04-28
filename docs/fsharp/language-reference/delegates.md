---
title: Delegados (F#)
description: 'Obtenga información acerca de cómo trabajar con los delegados de F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 56520cc631d889f390a7d4300be1cb3185306be9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="delegates"></a><span data-ttu-id="c7c0b-103">Delegados</span><span class="sxs-lookup"><span data-stu-id="c7c0b-103">Delegates</span></span>

<span data-ttu-id="c7c0b-104">Un delegado representa una llamada de función como un objeto.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="c7c0b-105">En F #, normalmente debe utilizar valores de función para representar las funciones como valores de primera clase; Sin embargo, los delegados se utilizan en .NET Framework y por lo que son necesarios al interoperar con las API que espera.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="c7c0b-106">También puede usar al crear bibliotecas diseñadas para usan en otros lenguajes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>


## <a name="syntax"></a><span data-ttu-id="c7c0b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7c0b-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="c7c0b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c7c0b-108">Remarks</span></span>
<span data-ttu-id="c7c0b-109">En la sintaxis anterior, `type1` representa el tipo de argumento o los tipos y `type2` representa el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="c7c0b-110">Los tipos de argumentos que se representan mediante `type1` se currifican automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="c7c0b-111">Esto sugiere para este tipo que se utiliza una forma de tupla si los argumentos de la función de destino se currificadas y una tupla entre paréntesis para los argumentos que ya están en el formulario de la tupla.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="c7c0b-112">La currificación automática quita un conjunto de paréntesis, si deja un argumento de tupla que coincide con el método de destino.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="c7c0b-113">Consulte el ejemplo de código para la sintaxis que debe usar en cada caso.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="c7c0b-114">Los delegados se pueden adjuntar a los valores de función de F # y estáticos o métodos de instancia.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="c7c0b-115">Los valores de función de F # se pueden pasar directamente como argumentos para constructores delegados.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="c7c0b-116">Para un método estático, el delegado se construye utilizando el nombre de la clase y el método.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="c7c0b-117">Para un método de instancia, se proporcionan la instancia de objeto y el método en un argumento.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="c7c0b-118">En ambos casos, el miembro de operador de acceso a (`.`) se utiliza.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="c7c0b-119">El `Invoke` método en el tipo de delegado llama a la función encapsulada.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="c7c0b-120">Además, los delegados se pueden pasar como valores de las funciones haciendo referencia al nombre del método Invoke sin los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="c7c0b-121">El código siguiente muestra la sintaxis para crear delegados que representan varios métodos en una clase.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="c7c0b-122">Dependiendo de si el método es un método estático o un método de instancia y, si tiene argumentos en la tupla o el formulario currificado, la sintaxis para declarar y asignar al delegado es un poco diferente.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="c7c0b-123">El código siguiente muestra algunas de las distintas maneras en que puede trabajar con los delegados.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="c7c0b-124">El resultado del ejemplo de código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="c7c0b-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="c7c0b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7c0b-125">See Also</span></span>
[<span data-ttu-id="c7c0b-126">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="c7c0b-126">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="c7c0b-127">Parámetros y argumentos</span><span class="sxs-lookup"><span data-stu-id="c7c0b-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="c7c0b-128">Eventos</span><span class="sxs-lookup"><span data-stu-id="c7c0b-128">Events</span></span>](members/events.md)
