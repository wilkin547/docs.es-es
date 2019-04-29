---
title: Abreviaturas de tipo
description: Obtenga información sobre F# abreviaturas para asignar un nombre más significativo de un tipo con el fin de facilitar la lectura del código de tipo.
ms.date: 05/16/2016
ms.openlocfilehash: 0deaef789367aad413e5a537bf7164034e1275c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683345"
---
# <a name="type-abbreviations"></a><span data-ttu-id="9008b-103">Abreviaturas de tipo</span><span class="sxs-lookup"><span data-stu-id="9008b-103">Type Abbreviations</span></span>

<span data-ttu-id="9008b-104">Un *abreviatura de tipo* es un alias o nombre alternativo para un tipo.</span><span class="sxs-lookup"><span data-stu-id="9008b-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="9008b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9008b-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="9008b-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9008b-106">Remarks</span></span>

<span data-ttu-id="9008b-107">Puede usar las abreviaturas de tipo para asignar un nombre más significativo, de un tipo con el fin de facilitar la lectura del código.</span><span class="sxs-lookup"><span data-stu-id="9008b-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="9008b-108">También puede usar para crear un nombre fácil de usar para un tipo que en caso contrario, es difícil de escribir. Además, puede usar las abreviaturas de tipo para que sea más fácil cambiar un tipo subyacente sin modificar todo el código que utiliza el tipo.</span><span class="sxs-lookup"><span data-stu-id="9008b-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="9008b-109">La siguiente es una abreviatura de tipo simple.</span><span class="sxs-lookup"><span data-stu-id="9008b-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="9008b-110">Accesibilidad de abreviaturas de tipo de valor predeterminado es `public`.</span><span class="sxs-lookup"><span data-stu-id="9008b-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="9008b-111">Abreviaturas de tipo pueden incluir parámetros genéricos, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9008b-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="9008b-112">En el código anterior, `Transform` es una abreviatura del tipo que representa una función que toma un único argumento de cualquier tipo y que devuelve un valor único de ese mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="9008b-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="9008b-113">Abreviaturas de tipo no se conservan en el código MSIL de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9008b-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="9008b-114">Por lo tanto, cuando se usa un F# ensamblado desde otro lenguaje de .NET Framework, debe usar el nombre de tipo subyacente para una abreviatura de tipo.</span><span class="sxs-lookup"><span data-stu-id="9008b-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="9008b-115">Abreviaturas de tipo también pueden usarse en unidades de medida.</span><span class="sxs-lookup"><span data-stu-id="9008b-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="9008b-116">Para obtener más información, consulte [unidades de medida](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="9008b-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9008b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9008b-117">See also</span></span>

- [<span data-ttu-id="9008b-118">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="9008b-118">F# Language Reference</span></span>](index.md)