---
title: Tipos de excepción
description: Obtenga información sobre cómo definir y usar F# tipos de excepción.
ms.date: 05/16/2016
ms.openlocfilehash: ed721dd0dc46a486fafeac2fa4c096800995ccb7
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612834"
---
# <a name="exception-types"></a><span data-ttu-id="215f7-103">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="215f7-103">Exception Types</span></span>

<span data-ttu-id="215f7-104">Existen dos categorías de excepciones en F#: tipos de excepción de .NET y F# tipos de excepción.</span><span class="sxs-lookup"><span data-stu-id="215f7-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="215f7-105">Este tema describe cómo definir y usar F# tipos de excepción.</span><span class="sxs-lookup"><span data-stu-id="215f7-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="215f7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="215f7-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="215f7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="215f7-107">Remarks</span></span>

<span data-ttu-id="215f7-108">En la sintaxis anterior, *tipo de excepción* es el nombre de un nuevo F# tipo de excepción, y *tipos de argumento* representa el tipo de argumento que se puede proporcionar al generar una excepción de este tipo.</span><span class="sxs-lookup"><span data-stu-id="215f7-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="215f7-109">Puede especificar varios argumentos utilizando un tipo de tupla para *tipos de argumento*.</span><span class="sxs-lookup"><span data-stu-id="215f7-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="215f7-110">Una definición típica para un F# excepción es similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="215f7-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="215f7-111">Puede generar una excepción de este tipo mediante el `raise` funcione, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="215f7-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="215f7-112">Puede usar un F# tipo de excepción directamente en los filtros en un `try...with` expresión, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="215f7-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="215f7-113">El tipo de excepción que se define con la `exception` palabra clave en F# es un nuevo tipo que hereda de `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="215f7-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="215f7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="215f7-114">See also</span></span>

- [<span data-ttu-id="215f7-115">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="215f7-115">Exception Handling</span></span>](index.md)
- <span data-ttu-id="215f7-116">[Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)</span><span class="sxs-lookup"><span data-stu-id="215f7-116">[Exceptions: the `raise` Function](the-raise-function.md)</span></span>
- [<span data-ttu-id="215f7-117">Jerarquía de excepciones</span><span class="sxs-lookup"><span data-stu-id="215f7-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)