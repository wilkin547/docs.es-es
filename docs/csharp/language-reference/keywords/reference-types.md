---
title: Tipos de referencia (referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: f99415fc9a2b728917cdf829ffb9e25823a824dd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210911"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="eee05-102">Tipos de referencia (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="eee05-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="eee05-103">Hay dos clases de tipos en C#: tipos de referencia y tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="eee05-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="eee05-104">Las variables de tipos de referencia almacenan referencias en sus datos (objetos), mientras que las variables de tipos de valor contienen directamente los datos.</span><span class="sxs-lookup"><span data-stu-id="eee05-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="eee05-105">Con los tipos de referencia, dos variables pueden hacer referencia al mismo objeto y, por lo tanto, las operaciones en una variable pueden afectar al objeto al que hace referencia la otra variable.</span><span class="sxs-lookup"><span data-stu-id="eee05-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="eee05-106">Con los tipos de valor, cada variable tiene su propia copia de los datos, y no es posible que las operaciones en una variable afecten a la otra (excepto en el caso de las variables de parámetro in, ref y out, consulte el modificador de parámetro [in](in-parameter-modifier.md), [ref](ref.md) y [out](out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="eee05-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="eee05-107">Las palabras clave siguientes se usan para declarar tipos de referencia:</span><span class="sxs-lookup"><span data-stu-id="eee05-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="eee05-108">class</span><span class="sxs-lookup"><span data-stu-id="eee05-108">class</span></span>](class.md)

- [<span data-ttu-id="eee05-109">interface</span><span class="sxs-lookup"><span data-stu-id="eee05-109">interface</span></span>](interface.md)

- [<span data-ttu-id="eee05-110">delegate</span><span class="sxs-lookup"><span data-stu-id="eee05-110">delegate</span></span>](delegate.md)

 <span data-ttu-id="eee05-111">C# también proporciona los siguientes tipos de referencia integrados:</span><span class="sxs-lookup"><span data-stu-id="eee05-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="eee05-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="eee05-112">dynamic</span></span>](dynamic.md)

- [<span data-ttu-id="eee05-113">object</span><span class="sxs-lookup"><span data-stu-id="eee05-113">object</span></span>](object.md)

- [<span data-ttu-id="eee05-114">string</span><span class="sxs-lookup"><span data-stu-id="eee05-114">string</span></span>](string.md)

## <a name="see-also"></a><span data-ttu-id="eee05-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="eee05-115">See also</span></span>

- [<span data-ttu-id="eee05-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="eee05-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="eee05-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="eee05-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="eee05-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="eee05-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="eee05-119">Tipos</span><span class="sxs-lookup"><span data-stu-id="eee05-119">Types</span></span>](types.md)
- [<span data-ttu-id="eee05-120">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="eee05-120">Value Types</span></span>](value-types.md)