---
description: '#error: Referencia de C#'
title: '#error: Referencia de C#'
ms.date: 08/24/2020
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 76325901c5e39f340545b186a0aa9546cd853ff8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138103"
---
# <a name="error-c-reference"></a><span data-ttu-id="335ff-103">#error (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="335ff-103">#error (C# Reference)</span></span>

<span data-ttu-id="335ff-104">`#error` permite generar un error [CS1029](../compiler-messages/cs1029.md) definido por el usuario desde una ubicación específica en el código.</span><span class="sxs-lookup"><span data-stu-id="335ff-104">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="335ff-105">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="335ff-105">For example:</span></span>

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> <span data-ttu-id="335ff-106">El compilador trata `#error version` de forma especial e informa de un error del compilador, CS8304, con un mensaje que contiene las versiones que se usan del compilador y del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="335ff-106">The compiler treats `#error version` in a special way and reports a compiler error, CS8304, with a message containing the used compiler and language versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="335ff-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="335ff-107">Remarks</span></span>

<span data-ttu-id="335ff-108">Un uso común de `#error` es en una directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="335ff-108">A common use of `#error` is in a conditional directive.</span></span>

<span data-ttu-id="335ff-109">También es posible generar una advertencia definida por el usuario con [#warning](./preprocessor-warning.md).</span><span class="sxs-lookup"><span data-stu-id="335ff-109">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>

## <a name="example"></a><span data-ttu-id="335ff-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="335ff-110">Example</span></span>

```csharp
// preprocessor_error.cs
// CS1029 expected
#define DEBUG
class MainClass
{
    static void Main()
    {
#if DEBUG
#error DEBUG is defined
#endif
    }
}
```

## <a name="see-also"></a><span data-ttu-id="335ff-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="335ff-111">See also</span></span>

- [<span data-ttu-id="335ff-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="335ff-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="335ff-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="335ff-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="335ff-114">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="335ff-114">C# Preprocessor Directives</span></span>](./index.md)
