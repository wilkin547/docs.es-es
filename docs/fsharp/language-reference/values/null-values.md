---
title: Valores NULL (F#)
description: "Obtenga información acerca de cómo se usa el valor null en el lenguaje de programación de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 68ebd261-51cf-4582-b2dc-44c84d1c2500
ms.openlocfilehash: 01c14de00eb5efd0952145ffc8aabe69d65a3a48
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="null-values"></a><span data-ttu-id="23f39-104">Valores NULL</span><span class="sxs-lookup"><span data-stu-id="23f39-104">Null Values</span></span>

<span data-ttu-id="23f39-105">Este tema describe cómo se utiliza el valor null en F #.</span><span class="sxs-lookup"><span data-stu-id="23f39-105">This topic describes how the null value is used in F#.</span></span>


## <a name="null-value"></a><span data-ttu-id="23f39-106">Valor null</span><span class="sxs-lookup"><span data-stu-id="23f39-106">Null Value</span></span>
<span data-ttu-id="23f39-107">El valor null no se utiliza normalmente en F # para valores o variables.</span><span class="sxs-lookup"><span data-stu-id="23f39-107">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="23f39-108">Sin embargo, null aparece como valor anormal en determinadas situaciones.</span><span class="sxs-lookup"><span data-stu-id="23f39-108">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="23f39-109">Si se define un tipo de F #, no se permite null como un valor regular a menos que la [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) atributo se aplica al tipo.</span><span class="sxs-lookup"><span data-stu-id="23f39-109">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="23f39-110">Si se define un tipo en otro lenguaje de. NET, null es un valor posible y, si está interoperando con estos tipos, el código de F # podría encontrar valores null.</span><span class="sxs-lookup"><span data-stu-id="23f39-110">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="23f39-111">Para un tipo definido en F # y usar estrictamente en F #, la única manera de crear un valor null directamente con la biblioteca de F # es usar [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) o [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span><span class="sxs-lookup"><span data-stu-id="23f39-111">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="23f39-112">Sin embargo, para un tipo de F # que se utilizan desde otros lenguajes. NET, o si se utiliza ese tipo con una API que no se escribe en F #, como .NET Framework, puede haber valores null.</span><span class="sxs-lookup"><span data-stu-id="23f39-112">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="23f39-113">Puede usar el `option` los tipos de F # cuándo se puede utilizar una variable de referencia con un posible valor null en otro lenguaje. NET.</span><span class="sxs-lookup"><span data-stu-id="23f39-113">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="23f39-114">En lugar de null, con F # `option` tipo, use el valor de la opción `None` si no hay ningún objeto.</span><span class="sxs-lookup"><span data-stu-id="23f39-114">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="23f39-115">Utilice el valor de la opción `Some(obj)` con un objeto `obj` cuando hay un objeto.</span><span class="sxs-lookup"><span data-stu-id="23f39-115">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="23f39-116">Para obtener más información, consulte [opciones](../options.md).</span><span class="sxs-lookup"><span data-stu-id="23f39-116">For more information, see [Options](../options.md).</span></span>

<span data-ttu-id="23f39-117">El `null` palabra clave es una palabra clave válida en el lenguaje F #, y tendrá que usarla cuando se trabaja con la API de .NET Framework u otras API que se escribe en otro lenguaje. NET.</span><span class="sxs-lookup"><span data-stu-id="23f39-117">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="23f39-118">Las dos situaciones en las que podría necesitar un valor null son al llamar a una API de .NET y pasar un valor null como argumento, y cuando interprete el valor devuelto o parámetro de salida de una llamada al método. NET.</span><span class="sxs-lookup"><span data-stu-id="23f39-118">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="23f39-119">Para pasar un valor null a un método. NET, puede utilizar el `null` palabra clave en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="23f39-119">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="23f39-120">En el siguiente ejemplo código se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="23f39-120">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="23f39-121">Para interpretar un valor null que se obtiene de un método. NET, use la coincidencia de patrones, si es posible.</span><span class="sxs-lookup"><span data-stu-id="23f39-121">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="23f39-122">En el ejemplo de código siguiente se muestra cómo utilizar la coincidencia de patrones para interpretar el valor null que se devuelve de `ReadLine` cuando intenta leer después del final de un flujo de entrada.</span><span class="sxs-lookup"><span data-stu-id="23f39-122">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="23f39-123">Valores NULL para los tipos de F # también pueden generarse de otras maneras, como cuando usa `Array.zeroCreate`, que llama `Unchecked.defaultof`.</span><span class="sxs-lookup"><span data-stu-id="23f39-123">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="23f39-124">Debe tener cuidado con este código para mantener encapsulados los valores null.</span><span class="sxs-lookup"><span data-stu-id="23f39-124">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="23f39-125">En una biblioteca diseñada únicamente para F #, no es necesario comprobar si hay valores null en cada función.</span><span class="sxs-lookup"><span data-stu-id="23f39-125">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="23f39-126">Si está escribiendo una biblioteca para que interopere con otros lenguajes. NET, es posible que deba agregar comprueba si hay valores null, los parámetros de entrada y produce un `ArgumentNullException`, tal y como lo hace en el código de C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="23f39-126">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="23f39-127">Puede usar el código siguiente para comprobar si un valor arbitrario es null.</span><span class="sxs-lookup"><span data-stu-id="23f39-127">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="23f39-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="23f39-128">See Also</span></span>
[<span data-ttu-id="23f39-129">Valores</span><span class="sxs-lookup"><span data-stu-id="23f39-129">Values</span></span>](index.md)

[<span data-ttu-id="23f39-130">Expresiones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="23f39-130">Match Expressions</span></span>](../match-expressions.md)
