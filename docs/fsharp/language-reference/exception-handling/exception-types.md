---
title: Tipos de excepción
description: Obtenga información sobre cómo definir y F# usar tipos de excepción.
ms.date: 05/16/2016
ms.openlocfilehash: 8545fab50ff6338d1f1621710a838a200f9ac705
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630316"
---
# <a name="exception-types"></a><span data-ttu-id="0c50c-103">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="0c50c-103">Exception Types</span></span>

<span data-ttu-id="0c50c-104">Existen dos categorías de excepciones en: F#los tipos de excepción de F# .net y los tipos de excepción.</span><span class="sxs-lookup"><span data-stu-id="0c50c-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="0c50c-105">En este tema se describe cómo definir y F# usar tipos de excepciones.</span><span class="sxs-lookup"><span data-stu-id="0c50c-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="0c50c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c50c-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="0c50c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c50c-107">Remarks</span></span>

<span data-ttu-id="0c50c-108">En la sintaxis anterior, *Exception-Type* es el nombre de un nuevo F# tipo de excepción y *argument-Type* representa el tipo de un argumento que se puede proporcionar cuando se produce una excepción de este tipo.</span><span class="sxs-lookup"><span data-stu-id="0c50c-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="0c50c-109">Puede especificar varios argumentos mediante un tipo de tupla para *el tipo de argumento*.</span><span class="sxs-lookup"><span data-stu-id="0c50c-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="0c50c-110">Una definición típica para una F# excepción es similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c50c-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="0c50c-111">Puede generar una excepción de este tipo mediante la `raise` función, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="0c50c-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="0c50c-112">Puede usar un F# tipo de excepción directamente en los filtros de una `try...with` expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c50c-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="0c50c-113">El tipo de excepción que se define con `exception` la palabra F# clave en es un nuevo tipo que hereda `System.Exception`de.</span><span class="sxs-lookup"><span data-stu-id="0c50c-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c50c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c50c-114">See also</span></span>

- [<span data-ttu-id="0c50c-115">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="0c50c-115">Exception Handling</span></span>](index.md)
- <span data-ttu-id="0c50c-116">[Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)</span><span class="sxs-lookup"><span data-stu-id="0c50c-116">[Exceptions: the `raise` Function](the-raise-function.md)</span></span>
- [<span data-ttu-id="0c50c-117">Jerarquía de excepciones</span><span class="sxs-lookup"><span data-stu-id="0c50c-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
