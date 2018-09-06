---
title: Delegados (F#)
description: 'Obtenga información sobre cómo trabajar con delegados en F #.'
ms.date: 05/16/2016
ms.openlocfilehash: be58997dffe8fcd949bbc2d47d86ffccc157d43e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43801543"
---
# <a name="delegates"></a><span data-ttu-id="f1db9-103">Delegados</span><span class="sxs-lookup"><span data-stu-id="f1db9-103">Delegates</span></span>

<span data-ttu-id="f1db9-104">Un delegado representa una llamada de función como un objeto.</span><span class="sxs-lookup"><span data-stu-id="f1db9-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="f1db9-105">En F #, normalmente debe usar los valores de función para representar funciones como valores de primera clase; Sin embargo, los delegados se usan en .NET Framework y por lo que son necesarios al interactuar con las API que esperan.</span><span class="sxs-lookup"><span data-stu-id="f1db9-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="f1db9-106">También puede usar al crear bibliotecas diseñadas para utilizan desde otros lenguajes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f1db9-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1db9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1db9-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="f1db9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1db9-108">Remarks</span></span>

<span data-ttu-id="f1db9-109">En la sintaxis anterior, `type1` representa el tipo de argumento o los tipos y `type2` representa el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f1db9-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="f1db9-110">Los tipos de argumento que se representan mediante `type1` se currifican automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f1db9-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="f1db9-111">Esto sugiere que, para este tipo que se utiliza una forma de tupla si están currificados los argumentos de la función de destino y una tupla entre paréntesis para los argumentos que ya están en forma de tupla.</span><span class="sxs-lookup"><span data-stu-id="f1db9-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="f1db9-112">La currificación automática quita un conjunto de paréntesis, dejando un argumento de tupla que coincide con el método de destino.</span><span class="sxs-lookup"><span data-stu-id="f1db9-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="f1db9-113">Consulte el ejemplo de código para la sintaxis que debe usar en cada caso.</span><span class="sxs-lookup"><span data-stu-id="f1db9-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="f1db9-114">Los delegados se pueden adjuntar a los valores de función de F # y estáticos o métodos de instancia.</span><span class="sxs-lookup"><span data-stu-id="f1db9-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="f1db9-115">Los valores de función de F # se pueden pasar directamente como argumentos para delegar constructores.</span><span class="sxs-lookup"><span data-stu-id="f1db9-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="f1db9-116">Para un método estático, el delegado se construye utilizando el nombre de la clase y el método.</span><span class="sxs-lookup"><span data-stu-id="f1db9-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="f1db9-117">Para un método de instancia, debe proporcionar la instancia de objeto y el método en un argumento.</span><span class="sxs-lookup"><span data-stu-id="f1db9-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="f1db9-118">En ambos casos, el miembro de operador de acceso a (`.`) se utiliza.</span><span class="sxs-lookup"><span data-stu-id="f1db9-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="f1db9-119">El `Invoke` método en el tipo de delegado llama a la función encapsulada.</span><span class="sxs-lookup"><span data-stu-id="f1db9-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="f1db9-120">Además, los delegados se pueden pasar como valores de función indicando el nombre del método Invoke sin paréntesis.</span><span class="sxs-lookup"><span data-stu-id="f1db9-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="f1db9-121">El código siguiente muestra la sintaxis para crear delegados que representan varios métodos en una clase.</span><span class="sxs-lookup"><span data-stu-id="f1db9-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="f1db9-122">Dependiendo de si el método es un método estático o un método de instancia y, si tiene argumentos en forma de tupla o currificada, la sintaxis para declarar y asignar al delegado es un poco diferente.</span><span class="sxs-lookup"><span data-stu-id="f1db9-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="f1db9-123">El código siguiente muestra algunas de las distintas formas en que puede trabajar con delegados.</span><span class="sxs-lookup"><span data-stu-id="f1db9-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="f1db9-124">La salida de ejemplo de código anterior es como sigue.</span><span class="sxs-lookup"><span data-stu-id="f1db9-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="f1db9-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1db9-125">See also</span></span>

- [<span data-ttu-id="f1db9-126">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="f1db9-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f1db9-127">Parámetros y argumentos</span><span class="sxs-lookup"><span data-stu-id="f1db9-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="f1db9-128">Eventos</span><span class="sxs-lookup"><span data-stu-id="f1db9-128">Events</span></span>](members/events.md)
