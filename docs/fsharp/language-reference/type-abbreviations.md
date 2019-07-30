---
title: Abreviaturas de tipo
description: Obtenga información F# sobre las abreviaturas de tipo para asignar un nombre más significativo a un tipo con el fin de facilitar la lectura del código.
ms.date: 05/16/2016
ms.openlocfilehash: 339b22a675e3f1ad8a3da207053e611942b55a22
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630216"
---
# <a name="type-abbreviations"></a><span data-ttu-id="9da5b-103">Abreviaturas de tipo</span><span class="sxs-lookup"><span data-stu-id="9da5b-103">Type Abbreviations</span></span>

<span data-ttu-id="9da5b-104">Una *abreviatura de tipo* es un alias o un nombre alternativo para un tipo.</span><span class="sxs-lookup"><span data-stu-id="9da5b-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="9da5b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9da5b-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="9da5b-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9da5b-106">Remarks</span></span>

<span data-ttu-id="9da5b-107">Puede usar las abreviaturas de tipo para asignar un nombre más significativo a un tipo, con el fin de facilitar la lectura del código.</span><span class="sxs-lookup"><span data-stu-id="9da5b-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="9da5b-108">También puede usarlos para crear un nombre fácil de usar para un tipo que, de otro modo, es engorroso de escribir. Además, puede usar las abreviaturas de tipo para facilitar la modificación de un tipo subyacente sin cambiar todo el código que usa el tipo.</span><span class="sxs-lookup"><span data-stu-id="9da5b-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="9da5b-109">La siguiente es una abreviatura de tipo simple.</span><span class="sxs-lookup"><span data-stu-id="9da5b-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="9da5b-110">La accesibilidad de las abreviaturas de tipo `public`tiene como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9da5b-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="9da5b-111">Las abreviaturas de tipo pueden incluir parámetros genéricos, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9da5b-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="9da5b-112">En el código anterior, `Transform` es una abreviatura de tipo que representa una función que toma un solo argumento de cualquier tipo y que devuelve un valor único del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="9da5b-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="9da5b-113">Las abreviaturas de tipo no se conservan en el código MSIL de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9da5b-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="9da5b-114">Por lo tanto, cuando se F# usa un ensamblado de otro lenguaje .NET Framework, se debe usar el nombre de tipo subyacente para una abreviatura de tipo.</span><span class="sxs-lookup"><span data-stu-id="9da5b-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="9da5b-115">Las abreviaturas de tipo también se pueden usar en unidades de medida.</span><span class="sxs-lookup"><span data-stu-id="9da5b-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="9da5b-116">Para obtener más información, consulte [unidades de medida](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="9da5b-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9da5b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9da5b-117">See also</span></span>

- [<span data-ttu-id="9da5b-118">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="9da5b-118">F# Language Reference</span></span>](index.md)
