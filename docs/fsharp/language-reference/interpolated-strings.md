---
title: Cadenas interpoladas
description: 'Obtenga información sobre las cadenas interpoladas, una forma especial de cadena que permite incrustar expresiones de F # directamente dentro de ellas.'
ms.date: 11/12/2020
ms.openlocfilehash: 8c552b44cea7d6c51ec333b6bdd4d407c6f10da7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829692"
---
# <a name="interpolated-strings"></a><span data-ttu-id="7a933-103">Cadenas interpoladas</span><span class="sxs-lookup"><span data-stu-id="7a933-103">Interpolated strings</span></span>

<span data-ttu-id="7a933-104">Las cadenas interpoladas son [cadenas](strings.md) que permiten incrustar expresiones de F # en ellas.</span><span class="sxs-lookup"><span data-stu-id="7a933-104">Interpolated strings are [strings](strings.md) that allow you to embed F# expressions into them.</span></span> <span data-ttu-id="7a933-105">Son útiles en una amplia gama de escenarios en los que el valor de una cadena puede cambiar en función del resultado de un valor o una expresión.</span><span class="sxs-lookup"><span data-stu-id="7a933-105">They are helpful in a wide range of scenarios where the value of a string may change based on the result of a value or expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="7a933-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a933-106">Syntax</span></span>

```fsharp
$"string-text {expr}"
$"string-text %format-specifier{expr}"
$"""string-text {"embedded string literal"}"""
```

## <a name="remarks"></a><span data-ttu-id="7a933-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7a933-107">Remarks</span></span>

<span data-ttu-id="7a933-108">Las cadenas interpoladas permiten escribir código en "huecos" dentro de un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="7a933-108">Interpolated strings let you write code in "holes" inside of a string literal.</span></span> <span data-ttu-id="7a933-109">Este es un ejemplo básico:</span><span class="sxs-lookup"><span data-stu-id="7a933-109">Here's a basic example:</span></span>

```fsharp
let name = "Phillip"
let age = 30
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

<span data-ttu-id="7a933-110">El contenido entre cada `{}` par de llaves puede ser cualquier expresión de F #.</span><span class="sxs-lookup"><span data-stu-id="7a933-110">The contents in between each `{}` brace pair can be any F# expression.</span></span>

<span data-ttu-id="7a933-111">Para escapar un `{}` par de llaves, escriba dos de ellos del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a933-111">To escape a `{}` brace pair, write two of them like so:</span></span>

```fsharp
let str = $"A pair of braces: {{}}"
// "A pair of braces: {}"
```

## <a name="typed-interpolated-strings"></a><span data-ttu-id="7a933-112">Cadenas interpoladas con tipo</span><span class="sxs-lookup"><span data-stu-id="7a933-112">Typed interpolated strings</span></span>

<span data-ttu-id="7a933-113">Las cadenas interpoladas también pueden tener especificadores de formato de F # para exigir la seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="7a933-113">Interpolated strings can also have F# format specifiers to enforce type safety.</span></span>

```fsharp
let name = "Phillip"
let age = 30

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

<span data-ttu-id="7a933-114">En el ejemplo anterior, el código pasa erróneamente el `age` valor donde `name` debería ser y viceversa.</span><span class="sxs-lookup"><span data-stu-id="7a933-114">In the previous example, the code mistakenly passes the `age` value where `name` should be, and vice/versa.</span></span> <span data-ttu-id="7a933-115">Dado que las cadenas interpoladas usan especificadores de formato, se trata de un error de compilación en lugar de un error de tiempo de ejecución sutil.</span><span class="sxs-lookup"><span data-stu-id="7a933-115">Because the interpolated strings use format specifiers, this is a compile error instead of a subtle runtime bug.</span></span>

<span data-ttu-id="7a933-116">Todos los especificadores de formato que se describen en [formato de texto no cifrado](plaintext-formatting.md) son válidos dentro de una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="7a933-116">All format specifiers covered in [plaintext formatting](plaintext-formatting.md) are valid inside of an interpolated string.</span></span>

## <a name="verbatim-interpolated-strings"></a><span data-ttu-id="7a933-117">Cadenas interpoladas textuales</span><span class="sxs-lookup"><span data-stu-id="7a933-117">Verbatim interpolated strings</span></span>

<span data-ttu-id="7a933-118">F # admite cadenas interpoladas textualmente con triples de comillas para que pueda incrustar literales de cadena.</span><span class="sxs-lookup"><span data-stu-id="7a933-118">F# supports verbatim interpolated strings with triple quotes so that you can embed string literals.</span></span>

```fsharp
let age = 30

printfn $"""Name: {"Phillip"}, Age: %d{age}"""
```

## <a name="aligning-expressions-in-interpolated-strings"></a><span data-ttu-id="7a933-119">Alinear expresiones en cadenas interpoladas</span><span class="sxs-lookup"><span data-stu-id="7a933-119">Aligning expressions in interpolated strings</span></span>

<span data-ttu-id="7a933-120">Puede alinear a la izquierda o alinear a la derecha expresiones dentro de cadenas interpoladas con `|` y una especificación de cuántos espacios.</span><span class="sxs-lookup"><span data-stu-id="7a933-120">You can left-align or right-align expressions inside interpolated strings with `|` and a specification of how many spaces.</span></span> <span data-ttu-id="7a933-121">La siguiente cadena interpolada alinea las expresiones izquierda y derecha a la izquierda y a la derecha, respectivamente, por siete espacios.</span><span class="sxs-lookup"><span data-stu-id="7a933-121">The following interpolated string aligns the left and right expressions to the left and right, respectively, by seven spaces.</span></span>

```fsharp
printfn $"""|{"Left",-7}|{"Right",7}|"""
// |Left   |  Right|
```

## <a name="interpolated-strings-and-formattablestring-formatting"></a><span data-ttu-id="7a933-122">Formatos y cadenas interpoladas `FormattableString`</span><span class="sxs-lookup"><span data-stu-id="7a933-122">Interpolated strings and `FormattableString` formatting</span></span>

<span data-ttu-id="7a933-123">También puede aplicar formato que cumpla las reglas de <xref:System.FormattableString> :</span><span class="sxs-lookup"><span data-stu-id="7a933-123">You can also apply formatting that adheres to the rules for <xref:System.FormattableString>:</span></span>

```fsharp
let speedOfLight = 299792.458
printfn $"The speed of light is {speedOfLight:N3} km/s."
// "The speed of light is 299,792.458 km/s."
```

<span data-ttu-id="7a933-124">Además, también se puede comprobar el tipo de una cadena interpolada como <xref:System.FormattableString> a través de una anotación de tipo:</span><span class="sxs-lookup"><span data-stu-id="7a933-124">Additionally, an interpolated string can also be type checked as a <xref:System.FormattableString> via a type annotation:</span></span>

```fsharp
let frmtStr = $"The speed of light is {speedOfLight:N3} km/s." : FormattableString
// Type: FormattableString
// The speed of light is 299,792.458 km/s.
```

<span data-ttu-id="7a933-125">Tenga en cuenta que la anotación de tipo debe estar en la propia expresión de cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="7a933-125">Note that the type annotation must be on the interpolated string expression itself.</span></span> <span data-ttu-id="7a933-126">F # no convierte implícitamente una cadena interpolada en <xref:System.FormattableString> .</span><span class="sxs-lookup"><span data-stu-id="7a933-126">F# does not implicitly convert an interpolated string into a <xref:System.FormattableString>.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a933-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a933-127">See also</span></span>

* [<span data-ttu-id="7a933-128">Cadenas</span><span class="sxs-lookup"><span data-stu-id="7a933-128">Strings</span></span>](strings.md)
