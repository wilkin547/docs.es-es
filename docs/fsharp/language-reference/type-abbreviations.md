---
title: Abreviaturas de tipo (F#)
description: 'Obtenga información acerca de abreviaturas de tipo de F # para proporcionar un nombre más descriptivo a un tipo con el fin de facilitar la lectura del código.'
ms.date: 05/16/2016
ms.openlocfilehash: e222caa41a20a64071c94cffea6ea7b2bec8eb22
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2018
---
# <a name="type-abbreviations"></a><span data-ttu-id="ef79f-103">Abreviaturas de tipo</span><span class="sxs-lookup"><span data-stu-id="ef79f-103">Type Abbreviations</span></span>

<span data-ttu-id="ef79f-104">A *abreviatura de tipo* es un alias o nombre alternativo para un tipo.</span><span class="sxs-lookup"><span data-stu-id="ef79f-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="ef79f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef79f-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="ef79f-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef79f-106">Remarks</span></span>
<span data-ttu-id="ef79f-107">Puede utilizar las abreviaturas de tipo para asignar un nombre más significativo, de un tipo con el fin de facilitar la lectura del código.</span><span class="sxs-lookup"><span data-stu-id="ef79f-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="ef79f-108">También puede usar para crear un nombre fácil de usar para un tipo que en caso contrario, es difícil de escribir. Además, puede utilizar las abreviaturas de tipo para que sea más fácil cambiar un tipo subyacente sin modificar todo el código que utiliza el tipo.</span><span class="sxs-lookup"><span data-stu-id="ef79f-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="ef79f-109">La siguiente es una abreviatura de tipo simple.</span><span class="sxs-lookup"><span data-stu-id="ef79f-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="ef79f-110">Accesibilidad de abreviaturas de tipo de valor predeterminado es `public`.</span><span class="sxs-lookup"><span data-stu-id="ef79f-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="ef79f-111">Abreviaturas de tipo pueden incluir parámetros genéricos, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef79f-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="ef79f-112">En el código anterior, `Transform` es una abreviatura de tipo que representa una función que toma un único argumento de cualquier tipo y que devuelve un valor único de dicho tipo.</span><span class="sxs-lookup"><span data-stu-id="ef79f-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="ef79f-113">Abreviaturas de tipo no se conservan en el código de MSIL de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ef79f-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="ef79f-114">Por lo tanto, cuando se usa un ensamblado de F # desde otro lenguaje de .NET Framework, debe utilizar el nombre del tipo subyacente de una abreviatura de tipo.</span><span class="sxs-lookup"><span data-stu-id="ef79f-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="ef79f-115">Abreviaturas de tipo también pueden utilizarse en las unidades de medida.</span><span class="sxs-lookup"><span data-stu-id="ef79f-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="ef79f-116">Para obtener más información, consulte [unidades de medida](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="ef79f-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="ef79f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef79f-117">See Also</span></span>
[<span data-ttu-id="ef79f-118">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="ef79f-118">F# Language Reference</span></span>](index.md)

