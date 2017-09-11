---
title: 'Enumeraciones de C#: un paseo por el lenguaje C#'
description: "Obtenga información sobre enumeraciones, constantes con nombre discretas en C#"
keywords: . NET, csharp
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 77d315dd87d9cab32605de415674d146eb9115fa
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
    
# <a name="enums"></a><span data-ttu-id="10026-104">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="10026-104">Enums</span></span>

<span data-ttu-id="10026-105">Un ***tipo de enumeración*** es un tipo de valor distinto con un conjunto de constantes con nombre.</span><span class="sxs-lookup"><span data-stu-id="10026-105">An ***enum type*** is a distinct value type with a set of named constants.</span></span> <span data-ttu-id="10026-106">Las enumeraciones se definen cuando se necesita fijar un tipo que pueda tener un conjunto de valores discretos.</span><span class="sxs-lookup"><span data-stu-id="10026-106">You define enums when you need to define a type that can have a set of discrete values.</span></span> <span data-ttu-id="10026-107">Usan uno de los tipos de valor integral como almacenamiento subyacente.</span><span class="sxs-lookup"><span data-stu-id="10026-107">They use one of the integral value types as their underlying storage.</span></span> <span data-ttu-id="10026-108">Proporcionan significado semántico a los valores discretos.</span><span class="sxs-lookup"><span data-stu-id="10026-108">They provide semantic meaning to the discrete values.</span></span>

<span data-ttu-id="10026-109">En el ejemplo siguiente se declara y usa un tipo `enum` denominado `Color` con tres valores constantes, `Red`, `Green` y `Blue`.</span><span class="sxs-lookup"><span data-stu-id="10026-109">The following example declares and uses an `enum` type named `Color` with three constant values, `Red`, `Green`, and `Blue`.</span></span>

<span data-ttu-id="10026-110">[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]</span><span class="sxs-lookup"><span data-stu-id="10026-110">[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]</span></span>

<span data-ttu-id="10026-111">A cada tipo `enum` le corresponde un tipo entero conocido como el ***tipo subyacente*** del tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="10026-111">Each `enum` type has a corresponding integral type called the ***underlying type*** of the `enum` type.</span></span> <span data-ttu-id="10026-112">Un tipo `enum` que no declara explícitamente un tipo subyacente tiene un tipo subyacente de `int`.</span><span class="sxs-lookup"><span data-stu-id="10026-112">An `enum` type that does not explicitly declare an underlying type has an underlying type of `int`.</span></span> <span data-ttu-id="10026-113">El formato de almacenamiento de un tipo `enum` y el intervalo de valores posibles se determinan por el tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="10026-113">An `enum` type’s storage format and range of possible values are determined by its underlying type.</span></span> <span data-ttu-id="10026-114">El conjunto de valores que un tipo `enum` puede asumir no está limitado por sus miembros `enum`.</span><span class="sxs-lookup"><span data-stu-id="10026-114">The set of values that an `enum` type can take on is not limited by its `enum` members.</span></span> <span data-ttu-id="10026-115">En concreto, cualquier valor del tipo subyacente de un tipo `enum` puede convertirse en el tipo `enum` y es un valor válido distinto de ese tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="10026-115">In particular, any value of the underlying type of an `enum` can be cast to the `enum` type and is a distinct valid value of that `enum` type.</span></span>

<span data-ttu-id="10026-116">En el ejemplo siguiente se declara un tipo `enum` denominado `Alignment` con un tipo subyacente de `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="10026-116">The following example declares an `enum` type named `Alignment` with an underlying type of `sbyte`.</span></span>

<span data-ttu-id="10026-117">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]</span><span class="sxs-lookup"><span data-stu-id="10026-117">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]</span></span>

<span data-ttu-id="10026-118">Como se muestra en el ejemplo anterior, una declaración de miembro `enum` puede incluir una expresión constante que especifica el valor del miembro.</span><span class="sxs-lookup"><span data-stu-id="10026-118">As shown by the previous example, an `enum` member declaration can include a constant expression that specifies the value of the member.</span></span> <span data-ttu-id="10026-119">El valor constante para cada miembro `enum` debe estar en el intervalo del tipo subyacente de `enum`.</span><span class="sxs-lookup"><span data-stu-id="10026-119">The constant value for each `enum` member must be in the range of the underlying type of the `enum`.</span></span> <span data-ttu-id="10026-120">Cuando una declaración de miembro `enum` no especifica explícitamente un valor, al miembro se le asigna el valor cero (si es el primer miembro en el tipo `enum`) o el valor del miembro textualmente anterior `enum` más uno.</span><span class="sxs-lookup"><span data-stu-id="10026-120">When an `enum` member declaration does not explicitly specify a value, the member is given the value zero (if it is the first member in the `enum` type) or the value of the textually preceding `enum` member plus one.</span></span>

<span data-ttu-id="10026-121">Los valores `Enum` se pueden convertir a valores integrales y viceversa, usando las conversiones de tipo.</span><span class="sxs-lookup"><span data-stu-id="10026-121">`Enum` values can be converted to integral values and vice versa using type casts.</span></span> <span data-ttu-id="10026-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="10026-122">For example:</span></span>

<span data-ttu-id="10026-123">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]</span><span class="sxs-lookup"><span data-stu-id="10026-123">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]</span></span>

<span data-ttu-id="10026-124">El valor predeterminado de cualquier tipo `enum` es el valor integral cero convertido al tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="10026-124">The default value of any `enum` type is the integral value zero converted to the `enum` type.</span></span> <span data-ttu-id="10026-125">En los casos donde las variables se inicializan automáticamente en un valor predeterminado, este es el valor que se le asigna a las variables de tipos `enum`.</span><span class="sxs-lookup"><span data-stu-id="10026-125">In cases where variables are automatically initialized to a default value, this is the value given to variables of `enum` types.</span></span> <span data-ttu-id="10026-126">Para que el valor predeterminado de un tipo `enum` esté fácilmente disponible, el literal `0` se convierte implícitamente a cualquier tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="10026-126">In order for the default value of an `enum` type to be easily available, the literal `0` implicitly converts to any `enum` type.</span></span> <span data-ttu-id="10026-127">Por tanto, el siguiente código es válido.</span><span class="sxs-lookup"><span data-stu-id="10026-127">Thus, the following is permitted.</span></span>

<span data-ttu-id="10026-128">[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]</span><span class="sxs-lookup"><span data-stu-id="10026-128">[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="10026-129">[Anterior](interfaces.md)
[Siguiente](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="10026-129">[Previous](interfaces.md)
[Next](delegates.md)</span></span>

