---
title: Literales (F#)
description: "Obtenga información acerca de los tipos literales en el lenguaje de programación de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4b1d6e9d-f933-4cd4-966d-d643152c27e4
ms.openlocfilehash: 6bb1f233b6846e226c4e73aee00b8cf77735fe2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="literals"></a><span data-ttu-id="381de-104">Literales</span><span class="sxs-lookup"><span data-stu-id="381de-104">Literals</span></span>

> [!NOTE]
<span data-ttu-id="381de-105">Los vínculos de referencia de API en este artículo le llevará a MSDN (por ahora).</span><span class="sxs-lookup"><span data-stu-id="381de-105">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="381de-106">En este tema se proporciona una tabla que muestra cómo especificar el tipo de un literal en F #.</span><span class="sxs-lookup"><span data-stu-id="381de-106">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="381de-107">Tipos literales</span><span class="sxs-lookup"><span data-stu-id="381de-107">Literal Types</span></span>
<span data-ttu-id="381de-108">La tabla siguiente muestran los tipos literales en F #.</span><span class="sxs-lookup"><span data-stu-id="381de-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="381de-109">Los caracteres que representan dígitos en notación hexadecimal no distinguen entre mayúsculas y minúsculas; caracteres que identifican el tipo distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="381de-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="381de-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="381de-110">Type</span></span>|<span data-ttu-id="381de-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="381de-111">Description</span></span>|<span data-ttu-id="381de-112">Prefijo o sufijo</span><span class="sxs-lookup"><span data-stu-id="381de-112">Suffix or prefix</span></span>|<span data-ttu-id="381de-113">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="381de-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="381de-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="381de-114">sbyte</span></span>|<span data-ttu-id="381de-115">Entero de 8 bits con signo</span><span class="sxs-lookup"><span data-stu-id="381de-115">signed 8-bit integer</span></span>|<span data-ttu-id="381de-116">y</span><span class="sxs-lookup"><span data-stu-id="381de-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="381de-117">byte</span><span class="sxs-lookup"><span data-stu-id="381de-117">byte</span></span>|<span data-ttu-id="381de-118">número natural de 8 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="381de-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="381de-119">UY</span><span class="sxs-lookup"><span data-stu-id="381de-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="381de-120">int16</span><span class="sxs-lookup"><span data-stu-id="381de-120">int16</span></span>|<span data-ttu-id="381de-121">Entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="381de-121">signed 16-bit integer</span></span>|<span data-ttu-id="381de-122">s</span><span class="sxs-lookup"><span data-stu-id="381de-122">s</span></span>|`86s`|
|<span data-ttu-id="381de-123">uint16</span><span class="sxs-lookup"><span data-stu-id="381de-123">uint16</span></span>|<span data-ttu-id="381de-124">número de natural de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="381de-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="381de-125">us</span><span class="sxs-lookup"><span data-stu-id="381de-125">us</span></span>|`86us`|
|<span data-ttu-id="381de-126">int</span><span class="sxs-lookup"><span data-stu-id="381de-126">int</span></span><br /><br /><span data-ttu-id="381de-127">int32</span><span class="sxs-lookup"><span data-stu-id="381de-127">int32</span></span>|<span data-ttu-id="381de-128">Entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="381de-128">signed 32-bit integer</span></span>|<span data-ttu-id="381de-129">l o ninguno</span><span class="sxs-lookup"><span data-stu-id="381de-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="381de-130">uint</span><span class="sxs-lookup"><span data-stu-id="381de-130">uint</span></span><br /><br /><span data-ttu-id="381de-131">uint32</span><span class="sxs-lookup"><span data-stu-id="381de-131">uint32</span></span>|<span data-ttu-id="381de-132">número de natural de 32 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="381de-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="381de-133">u o ul</span><span class="sxs-lookup"><span data-stu-id="381de-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="381de-134">unativeint</span><span class="sxs-lookup"><span data-stu-id="381de-134">unativeint</span></span>|<span data-ttu-id="381de-135">puntero nativo como un número natural sin signo</span><span class="sxs-lookup"><span data-stu-id="381de-135">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="381de-136">anular</span><span class="sxs-lookup"><span data-stu-id="381de-136">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="381de-137">int64</span><span class="sxs-lookup"><span data-stu-id="381de-137">int64</span></span>|<span data-ttu-id="381de-138">Entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="381de-138">signed 64-bit integer</span></span>|<span data-ttu-id="381de-139">L</span><span class="sxs-lookup"><span data-stu-id="381de-139">L</span></span>|`86L`|
|<span data-ttu-id="381de-140">uint64</span><span class="sxs-lookup"><span data-stu-id="381de-140">uint64</span></span>|<span data-ttu-id="381de-141">número de natural de 64 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="381de-141">unsigned 64-bit natural number</span></span>|<span data-ttu-id="381de-142">UL</span><span class="sxs-lookup"><span data-stu-id="381de-142">UL</span></span>|`86UL`|
|<span data-ttu-id="381de-143">float32 único,</span><span class="sxs-lookup"><span data-stu-id="381de-143">single, float32</span></span>|<span data-ttu-id="381de-144">número de punto flotante de 32 bits</span><span class="sxs-lookup"><span data-stu-id="381de-144">32-bit floating point number</span></span>|<span data-ttu-id="381de-145">F o f</span><span class="sxs-lookup"><span data-stu-id="381de-145">F or f</span></span>|<span data-ttu-id="381de-146">`4.14F` o `4.14f`</span><span class="sxs-lookup"><span data-stu-id="381de-146">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="381de-147">LF</span><span class="sxs-lookup"><span data-stu-id="381de-147">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="381de-148">float; doble</span><span class="sxs-lookup"><span data-stu-id="381de-148">float; double</span></span>|<span data-ttu-id="381de-149">número de punto flotante de 64 bits</span><span class="sxs-lookup"><span data-stu-id="381de-149">64-bit floating point number</span></span>|<span data-ttu-id="381de-150">ninguna</span><span class="sxs-lookup"><span data-stu-id="381de-150">none</span></span>|<span data-ttu-id="381de-151">`4.14`o `2.3E+32` o`2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="381de-151">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="381de-152">LF</span><span class="sxs-lookup"><span data-stu-id="381de-152">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="381de-153">bigint</span><span class="sxs-lookup"><span data-stu-id="381de-153">bigint</span></span>|<span data-ttu-id="381de-154">entero no limitado a la representación en forma de 64 bits</span><span class="sxs-lookup"><span data-stu-id="381de-154">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="381de-155">I</span><span class="sxs-lookup"><span data-stu-id="381de-155">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="381de-156">decimal</span><span class="sxs-lookup"><span data-stu-id="381de-156">decimal</span></span>|<span data-ttu-id="381de-157">número fraccionario representado como un punto fijo o un número racional</span><span class="sxs-lookup"><span data-stu-id="381de-157">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="381de-158">M o m</span><span class="sxs-lookup"><span data-stu-id="381de-158">M or m</span></span>|<span data-ttu-id="381de-159">`0.7833M` o `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="381de-159">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="381de-160">Char</span><span class="sxs-lookup"><span data-stu-id="381de-160">Char</span></span>|<span data-ttu-id="381de-161">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="381de-161">Unicode character</span></span>|<span data-ttu-id="381de-162">ninguna</span><span class="sxs-lookup"><span data-stu-id="381de-162">none</span></span>|`'a'`|
|<span data-ttu-id="381de-163">Cadena</span><span class="sxs-lookup"><span data-stu-id="381de-163">String</span></span>|<span data-ttu-id="381de-164">Cadena de Unicode</span><span class="sxs-lookup"><span data-stu-id="381de-164">Unicode string</span></span>|<span data-ttu-id="381de-165">ninguna</span><span class="sxs-lookup"><span data-stu-id="381de-165">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="381de-166">o</span><span class="sxs-lookup"><span data-stu-id="381de-166">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="381de-167">o</span><span class="sxs-lookup"><span data-stu-id="381de-167">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="381de-168">o</span><span class="sxs-lookup"><span data-stu-id="381de-168">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="381de-169">Vea también [cadenas](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="381de-169">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="381de-170">byte</span><span class="sxs-lookup"><span data-stu-id="381de-170">byte</span></span>|<span data-ttu-id="381de-171">Carácter ASCII</span><span class="sxs-lookup"><span data-stu-id="381de-171">ASCII character</span></span>|<span data-ttu-id="381de-172">B</span><span class="sxs-lookup"><span data-stu-id="381de-172">B</span></span>|`'a'B`|
|<span data-ttu-id="381de-173">byte[]</span><span class="sxs-lookup"><span data-stu-id="381de-173">byte[]</span></span>|<span data-ttu-id="381de-174">cadena ASCII</span><span class="sxs-lookup"><span data-stu-id="381de-174">ASCII string</span></span>|<span data-ttu-id="381de-175">B</span><span class="sxs-lookup"><span data-stu-id="381de-175">B</span></span>|`"text"B`|
|<span data-ttu-id="381de-176">String o byte]</span><span class="sxs-lookup"><span data-stu-id="381de-176">String or byte[]</span></span>|<span data-ttu-id="381de-177">literales de cadenas</span><span class="sxs-lookup"><span data-stu-id="381de-177">verbatim string</span></span>|<span data-ttu-id="381de-178">prefijo @</span><span class="sxs-lookup"><span data-stu-id="381de-178">@ prefix</span></span>|<span data-ttu-id="381de-179">`@"\\server\share"`(Unicode)</span><span class="sxs-lookup"><span data-stu-id="381de-179">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="381de-180">`@"\\server\share"B`(ASCII)</span><span class="sxs-lookup"><span data-stu-id="381de-180">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="381de-181">Comentarios</span><span class="sxs-lookup"><span data-stu-id="381de-181">Remarks</span></span>
<span data-ttu-id="381de-182">Las cadenas Unicode pueden contener codificaciones explícitas, que se pueden especificar mediante `\u` seguido por un código hexadecimal de 16 bits o codificaciones UTF-32 se pueden especificar mediante `\U` seguido por un código hexadecimal de 32 bits que representa un Unicode par suplente.</span><span class="sxs-lookup"><span data-stu-id="381de-182">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="381de-183">A partir de F # 3.1, puede usar el `+` iniciar sesión combinar los literales de cadena.</span><span class="sxs-lookup"><span data-stu-id="381de-183">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="381de-184">También puede usar el bit a bit o (`|||`) operador para combinar marcadores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="381de-184">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="381de-185">Por ejemplo, el código siguiente es legal en F # 3.1:</span><span class="sxs-lookup"><span data-stu-id="381de-185">For example, the following code is legal in F# 3.1:</span></span>

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

<span data-ttu-id="381de-186">No se permite el uso de otros operadores bit a bit.</span><span class="sxs-lookup"><span data-stu-id="381de-186">The use of other bitwise operators isn't allowed.</span></span>


## <a name="named-literals"></a><span data-ttu-id="381de-187">Literales con nombre</span><span class="sxs-lookup"><span data-stu-id="381de-187">Named Literals</span></span>
<span data-ttu-id="381de-188">Valores que están diseñados para ser constantes se pueden marcar con el [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) atributo.</span><span class="sxs-lookup"><span data-stu-id="381de-188">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="381de-189">Este atributo tiene el efecto de lograr que un valor se compile como una constante.</span><span class="sxs-lookup"><span data-stu-id="381de-189">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="381de-190">En expresiones de coincidencia de patrones, los identificadores que comiencen por caracteres en minúsculas siempre se tratan como variables a enlazar, en lugar de como literales, por lo que normalmente debe usar mayúsculas iniciales al definir literales.</span><span class="sxs-lookup"><span data-stu-id="381de-190">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="381de-191">Enteros en otras bases de datos</span><span class="sxs-lookup"><span data-stu-id="381de-191">Integers In Other Bases</span></span>

<span data-ttu-id="381de-192">Los enteros de 32 bits con signo también pueden especificarse en notación hexadecimal, octal o binario con un `0x`, `0o` o `0b` prefijo respectivamente.</span><span class="sxs-lookup"><span data-stu-id="381de-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="381de-193">Carácter de subrayado en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="381de-193">Underscores in Numeric Literals</span></span>

<span data-ttu-id="381de-194">A partir de F # 4.1, puede separar los dígitos con el carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="381de-194">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="381de-195">Vea también</span><span class="sxs-lookup"><span data-stu-id="381de-195">See Also</span></span>

[<span data-ttu-id="381de-196">Core.LiteralAttribute (clase)</span><span class="sxs-lookup"><span data-stu-id="381de-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
