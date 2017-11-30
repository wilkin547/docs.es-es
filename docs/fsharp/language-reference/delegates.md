---
title: Delegados (F#)
description: "Obtenga información acerca de cómo trabajar con los delegados de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 719948a3-83ba-4618-82d6-a22945c3f4b0
ms.openlocfilehash: c929a342ab4c5098062417691a99cee3b007d2d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="delegates"></a><span data-ttu-id="13cda-104">Delegados</span><span class="sxs-lookup"><span data-stu-id="13cda-104">Delegates</span></span>

<span data-ttu-id="13cda-105">Un delegado representa una llamada de función como un objeto.</span><span class="sxs-lookup"><span data-stu-id="13cda-105">A delegate represents a function call as an object.</span></span> <span data-ttu-id="13cda-106">En F #, normalmente debe utilizar valores de función para representar las funciones como valores de primera clase; Sin embargo, los delegados se utilizan en .NET Framework y por lo que son necesarios al interoperar con las API que espera.</span><span class="sxs-lookup"><span data-stu-id="13cda-106">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="13cda-107">También puede usar al crear bibliotecas diseñadas para usan en otros lenguajes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="13cda-107">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>


## <a name="syntax"></a><span data-ttu-id="13cda-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13cda-108">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="13cda-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13cda-109">Remarks</span></span>
<span data-ttu-id="13cda-110">En la sintaxis anterior, `type1` representa el tipo de argumento o los tipos y `type2` representa el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="13cda-110">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="13cda-111">Los tipos de argumentos que se representan mediante `type1` se currifican automáticamente.</span><span class="sxs-lookup"><span data-stu-id="13cda-111">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="13cda-112">Esto sugiere para este tipo que se utiliza una forma de tupla si los argumentos de la función de destino se currificadas y una tupla entre paréntesis para los argumentos que ya están en el formulario de la tupla.</span><span class="sxs-lookup"><span data-stu-id="13cda-112">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="13cda-113">La currificación automática quita un conjunto de paréntesis, si deja un argumento de tupla que coincide con el método de destino.</span><span class="sxs-lookup"><span data-stu-id="13cda-113">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="13cda-114">Consulte el ejemplo de código para la sintaxis que debe usar en cada caso.</span><span class="sxs-lookup"><span data-stu-id="13cda-114">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="13cda-115">Los delegados se pueden adjuntar a los valores de función de F # y estáticos o métodos de instancia.</span><span class="sxs-lookup"><span data-stu-id="13cda-115">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="13cda-116">Los valores de función de F # se pueden pasar directamente como argumentos para constructores delegados.</span><span class="sxs-lookup"><span data-stu-id="13cda-116">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="13cda-117">Para un método estático, el delegado se construye utilizando el nombre de la clase y el método.</span><span class="sxs-lookup"><span data-stu-id="13cda-117">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="13cda-118">Para un método de instancia, se proporcionan la instancia de objeto y el método en un argumento.</span><span class="sxs-lookup"><span data-stu-id="13cda-118">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="13cda-119">En ambos casos, el miembro de operador de acceso a (`.`) se utiliza.</span><span class="sxs-lookup"><span data-stu-id="13cda-119">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="13cda-120">El `Invoke` método en el tipo de delegado llama a la función encapsulada.</span><span class="sxs-lookup"><span data-stu-id="13cda-120">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="13cda-121">Además, los delegados se pueden pasar como valores de las funciones haciendo referencia al nombre del método Invoke sin los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="13cda-121">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="13cda-122">El código siguiente muestra la sintaxis para crear delegados que representan varios métodos en una clase.</span><span class="sxs-lookup"><span data-stu-id="13cda-122">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="13cda-123">Dependiendo de si el método es un método estático o un método de instancia y, si tiene argumentos en la tupla o el formulario currificado, la sintaxis para declarar y asignar al delegado es un poco diferente.</span><span class="sxs-lookup"><span data-stu-id="13cda-123">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="13cda-124">El código siguiente muestra algunas de las distintas maneras en que puede trabajar con los delegados.</span><span class="sxs-lookup"><span data-stu-id="13cda-124">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="13cda-125">El resultado del ejemplo de código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="13cda-125">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="13cda-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="13cda-126">See Also</span></span>
[<span data-ttu-id="13cda-127">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="13cda-127">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="13cda-128">Parámetros y argumentos</span><span class="sxs-lookup"><span data-stu-id="13cda-128">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="13cda-129">Eventos</span><span class="sxs-lookup"><span data-stu-id="13cda-129">Events</span></span>](members/events.md)
