---
title: "Tipos de excepción (F#)"
description: "Obtenga información acerca de cómo definir y utilizar tipos de excepción de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e850205a-b8da-459e-8f6d-cb3510f8f173
ms.openlocfilehash: a0864218841396c0ebdf26c7585e0e5bb778f83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="exception-types"></a><span data-ttu-id="9bdac-104">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="9bdac-104">Exception Types</span></span>

<span data-ttu-id="9bdac-105">Existen dos categorías de excepciones en F #: tipos de excepción de .NET y los tipos de excepción de F #.</span><span class="sxs-lookup"><span data-stu-id="9bdac-105">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="9bdac-106">En este tema se describe cómo definir y utilizar tipos de excepción de F #.</span><span class="sxs-lookup"><span data-stu-id="9bdac-106">This topic describes how to define and use F# exception types.</span></span>


## <a name="syntax"></a><span data-ttu-id="9bdac-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9bdac-107">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="9bdac-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9bdac-108">Remarks</span></span>
<span data-ttu-id="9bdac-109">En la sintaxis anterior, *tipo de excepción* es el nombre de un nuevo tipo F # excepción, y *tipos de argumento* representa el tipo de argumento que se pueden proporcionar cuando se inicia una excepción de este tipo.</span><span class="sxs-lookup"><span data-stu-id="9bdac-109">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="9bdac-110">Puede especificar varios argumentos utilizando un tipo de tupla para *tipos de argumento*.</span><span class="sxs-lookup"><span data-stu-id="9bdac-110">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="9bdac-111">Una definición típica para una excepción de F # es similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="9bdac-111">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="9bdac-112">También puede generar una excepción de este tipo mediante el `raise` funcione, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="9bdac-112">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="9bdac-113">Puede usar un tipo de excepción de F # directamente en los filtros de un `try...with` expresión, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9bdac-113">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="9bdac-114">El tipo de excepción que se define con el `exception` palabra clave en F # es un nuevo tipo que hereda de `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="9bdac-114">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>


## <a name="see-also"></a><span data-ttu-id="9bdac-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bdac-115">See Also</span></span>
[<span data-ttu-id="9bdac-116">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="9bdac-116">Exception Handling</span></span>](index.md)

<span data-ttu-id="9bdac-117">[Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)</span><span class="sxs-lookup"><span data-stu-id="9bdac-117">[Exceptions: the `raise` Function](the-raise-function.md)</span></span>

[<span data-ttu-id="9bdac-118">Jerarquía de excepciones</span><span class="sxs-lookup"><span data-stu-id="9bdac-118">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
