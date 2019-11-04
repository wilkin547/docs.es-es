---
title: 'Tipos de referencia: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 61b9f8096e1b2093b1ea5589f4336618cd189c34
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422458"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="76f7d-102">Tipos de referencia (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="76f7d-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="76f7d-103">Hay dos clases de tipos en C#: tipos de referencia y tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="76f7d-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="76f7d-104">Las variables de tipos de referencia almacenan referencias en sus datos (objetos), mientras que las variables de tipos de valor contienen directamente los datos.</span><span class="sxs-lookup"><span data-stu-id="76f7d-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="76f7d-105">Con los tipos de referencia, dos variables pueden hacer referencia al mismo objeto y, por lo tanto, las operaciones en una variable pueden afectar al objeto al que hace referencia la otra variable.</span><span class="sxs-lookup"><span data-stu-id="76f7d-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="76f7d-106">Con los tipos de valor, cada variable tiene su propia copia de los datos, y no es posible que las operaciones en una variable afecten a la otra (excepto en el caso de las variables de parámetro in, ref y out, consulte el modificador de parámetro [in](in-parameter-modifier.md), [ref](ref.md) y [out](out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="76f7d-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="76f7d-107">Las palabras clave siguientes se usan para declarar tipos de referencia:</span><span class="sxs-lookup"><span data-stu-id="76f7d-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="76f7d-108">class</span><span class="sxs-lookup"><span data-stu-id="76f7d-108">class</span></span>](class.md)

- [<span data-ttu-id="76f7d-109">interface</span><span class="sxs-lookup"><span data-stu-id="76f7d-109">interface</span></span>](interface.md)

- [<span data-ttu-id="76f7d-110">delegate</span><span class="sxs-lookup"><span data-stu-id="76f7d-110">delegate</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="76f7d-111">C# también proporciona los siguientes tipos de referencia integrados:</span><span class="sxs-lookup"><span data-stu-id="76f7d-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="76f7d-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="76f7d-112">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="76f7d-113">object</span><span class="sxs-lookup"><span data-stu-id="76f7d-113">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="76f7d-114">string</span><span class="sxs-lookup"><span data-stu-id="76f7d-114">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="76f7d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="76f7d-115">See also</span></span>

- [<span data-ttu-id="76f7d-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="76f7d-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="76f7d-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="76f7d-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="76f7d-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="76f7d-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="76f7d-119">Tipos</span><span class="sxs-lookup"><span data-stu-id="76f7d-119">Types</span></span>](/dotnet/csharp/language-reference/keywords)
- [<span data-ttu-id="76f7d-120">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="76f7d-120">Value Types</span></span>](value-types.md)
