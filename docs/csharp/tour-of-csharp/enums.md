---
title: 'Enumeraciones de C#: un paseo por el lenguaje C#'
description: Obtenga información sobre enumeraciones, constantes con nombre discretas en C#
ms.date: 08/10/2016
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.openlocfilehash: d55462f0360b6896c398d581918a9c17a87583be
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126659"
---
# <a name="enums"></a><span data-ttu-id="b310b-103">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="b310b-103">Enums</span></span>

<span data-ttu-id="b310b-104">Un ***tipo de enumeración*** es un tipo de valor distinto con un conjunto de constantes con nombre.</span><span class="sxs-lookup"><span data-stu-id="b310b-104">An ***enum type*** is a distinct value type with a set of named constants.</span></span> <span data-ttu-id="b310b-105">Las enumeraciones se definen cuando se necesita fijar un tipo que pueda tener un conjunto de valores discretos.</span><span class="sxs-lookup"><span data-stu-id="b310b-105">You define enums when you need to define a type that can have a set of discrete values.</span></span> <span data-ttu-id="b310b-106">Usan uno de los tipos de valor integral como almacenamiento subyacente.</span><span class="sxs-lookup"><span data-stu-id="b310b-106">They use one of the integral value types as their underlying storage.</span></span> <span data-ttu-id="b310b-107">Proporcionan significado semántico a los valores discretos.</span><span class="sxs-lookup"><span data-stu-id="b310b-107">They provide semantic meaning to the discrete values.</span></span>

<span data-ttu-id="b310b-108">En el ejemplo siguiente se declara y usa un tipo `enum` denominado `Color` con tres valores constantes, `Red`, `Green` y `Blue`.</span><span class="sxs-lookup"><span data-stu-id="b310b-108">The following example declares and uses an `enum` type named `Color` with three constant values, `Red`, `Green`, and `Blue`.</span></span>

[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]

<span data-ttu-id="b310b-109">A cada tipo `enum` le corresponde un tipo entero conocido como el ***tipo subyacente*** del tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="b310b-109">Each `enum` type has a corresponding integral type called the ***underlying type*** of the `enum` type.</span></span> <span data-ttu-id="b310b-110">Un tipo `enum` que no declara explícitamente un tipo subyacente tiene un tipo subyacente de `int`.</span><span class="sxs-lookup"><span data-stu-id="b310b-110">An `enum` type that does not explicitly declare an underlying type has an underlying type of `int`.</span></span> <span data-ttu-id="b310b-111">El formato de almacenamiento de un tipo `enum` y el intervalo de valores posibles se determinan por el tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="b310b-111">An `enum` type’s storage format and range of possible values are determined by its underlying type.</span></span> <span data-ttu-id="b310b-112">El conjunto de valores que un tipo `enum` puede asumir no está limitado por sus miembros `enum`.</span><span class="sxs-lookup"><span data-stu-id="b310b-112">The set of values that an `enum` type can take on is not limited by its `enum` members.</span></span> <span data-ttu-id="b310b-113">En concreto, cualquier valor del tipo subyacente de un tipo `enum` puede convertirse en el tipo `enum` y es un valor válido distinto de ese tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="b310b-113">In particular, any value of the underlying type of an `enum` can be cast to the `enum` type and is a distinct valid value of that `enum` type.</span></span>

<span data-ttu-id="b310b-114">En el ejemplo siguiente se declara un tipo `enum` denominado `Alignment` con un tipo subyacente de `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="b310b-114">The following example declares an `enum` type named `Alignment` with an underlying type of `sbyte`.</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]

<span data-ttu-id="b310b-115">Como se muestra en el ejemplo anterior, una declaración de miembro `enum` puede incluir una expresión constante que especifica el valor del miembro.</span><span class="sxs-lookup"><span data-stu-id="b310b-115">As shown by the previous example, an `enum` member declaration can include a constant expression that specifies the value of the member.</span></span> <span data-ttu-id="b310b-116">El valor constante para cada miembro `enum` debe estar en el intervalo del tipo subyacente de `enum`.</span><span class="sxs-lookup"><span data-stu-id="b310b-116">The constant value for each `enum` member must be in the range of the underlying type of the `enum`.</span></span> <span data-ttu-id="b310b-117">Cuando una declaración de miembro `enum` no especifica explícitamente un valor, al miembro se le asigna el valor cero (si es el primer miembro en el tipo `enum`) o el valor del miembro textualmente anterior `enum` más uno.</span><span class="sxs-lookup"><span data-stu-id="b310b-117">When an `enum` member declaration does not explicitly specify a value, the member is given the value zero (if it is the first member in the `enum` type) or the value of the textually preceding `enum` member plus one.</span></span>

<span data-ttu-id="b310b-118">Los valores `Enum` se pueden convertir a valores integrales y viceversa, usando las conversiones de tipo.</span><span class="sxs-lookup"><span data-stu-id="b310b-118">`Enum` values can be converted to integral values and vice versa using type casts.</span></span> <span data-ttu-id="b310b-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b310b-119">For example:</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]

<span data-ttu-id="b310b-120">El valor predeterminado de cualquier tipo `enum` es el valor integral cero convertido al tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="b310b-120">The default value of any `enum` type is the integral value zero converted to the `enum` type.</span></span> <span data-ttu-id="b310b-121">En los casos donde las variables se inicializan automáticamente en un valor predeterminado, este es el valor que se le asigna a las variables de tipos `enum`.</span><span class="sxs-lookup"><span data-stu-id="b310b-121">In cases where variables are automatically initialized to a default value, this is the value given to variables of `enum` types.</span></span> <span data-ttu-id="b310b-122">Para que el valor predeterminado de un tipo `enum` esté fácilmente disponible, el literal `0` se convierte implícitamente a cualquier tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="b310b-122">In order for the default value of an `enum` type to be easily available, the literal `0` implicitly converts to any `enum` type.</span></span> <span data-ttu-id="b310b-123">Por tanto, el siguiente código es válido.</span><span class="sxs-lookup"><span data-stu-id="b310b-123">Thus, the following is permitted.</span></span>

[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]

>[!div class="step-by-step"]
><span data-ttu-id="b310b-124">[Anterior](interfaces.md)
>[Siguiente](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="b310b-124">[Previous](interfaces.md)
[Next](delegates.md)</span></span>