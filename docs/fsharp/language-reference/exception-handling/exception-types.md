---
title: Tipos de excepción
description: 'Obtenga información sobre cómo definir y usar los tipos de excepción de F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 8b4ceec31a2d68abbcd025812ffeeefc0c090efb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557234"
---
# <a name="exception-types"></a><span data-ttu-id="36006-103">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="36006-103">Exception Types</span></span>

<span data-ttu-id="36006-104">Hay dos categorías de excepciones en F #: tipos de excepción de .NET y tipos de excepción de F #.</span><span class="sxs-lookup"><span data-stu-id="36006-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="36006-105">En este tema se describe cómo definir y usar los tipos de excepción de F #.</span><span class="sxs-lookup"><span data-stu-id="36006-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="36006-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36006-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="36006-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36006-107">Remarks</span></span>

<span data-ttu-id="36006-108">En la sintaxis anterior, *Exception-Type* es el nombre de un nuevo tipo de excepción de F # y *argument-Type* representa el tipo de un argumento que se puede proporcionar cuando se genera una excepción de este tipo.</span><span class="sxs-lookup"><span data-stu-id="36006-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="36006-109">Puede especificar varios argumentos mediante un tipo de tupla para *el tipo de argumento*.</span><span class="sxs-lookup"><span data-stu-id="36006-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="36006-110">Una definición típica para una excepción de F # es similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="36006-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="36006-111">Puede generar una excepción de este tipo mediante la `raise` función, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="36006-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="36006-112">Puede usar un tipo de excepción de F # directamente en los filtros de una `try...with` expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="36006-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="36006-113">El tipo de excepción que se define con la `exception` palabra clave en F # es un nuevo tipo que hereda de `System.Exception` .</span><span class="sxs-lookup"><span data-stu-id="36006-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="36006-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="36006-114">See also</span></span>

- [<span data-ttu-id="36006-115">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="36006-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="36006-116">Excepciones: la `raise` función</span><span class="sxs-lookup"><span data-stu-id="36006-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="36006-117">Jerarquía de excepciones</span><span class="sxs-lookup"><span data-stu-id="36006-117">Exception Hierarchy</span></span>](../../../standard/exceptions/index.md)
