---
title: Literales
description: Obtenga información sobre los tipos literales F# en el lenguaje de programación.
ms.date: 06/28/2019
ms.openlocfilehash: 9792a24ac28eb402e35e78574cd6a2bf9526734d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041041"
---
# <a name="literals"></a><span data-ttu-id="17c40-103">Literales</span><span class="sxs-lookup"><span data-stu-id="17c40-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="17c40-104">Los vínculos de referencia de la API de este artículo le llevarán a MSDN (por ahora).</span><span class="sxs-lookup"><span data-stu-id="17c40-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="17c40-105">En este tema se proporciona una tabla que muestra cómo especificar el tipo de un literal F#en.</span><span class="sxs-lookup"><span data-stu-id="17c40-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="17c40-106">Tipos literales</span><span class="sxs-lookup"><span data-stu-id="17c40-106">Literal Types</span></span>

<span data-ttu-id="17c40-107">En la tabla siguiente se muestran los tipos F#literales en.</span><span class="sxs-lookup"><span data-stu-id="17c40-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="17c40-108">Los caracteres que representan dígitos en notación hexadecimal no distinguen mayúsculas de minúsculas; los caracteres que identifican el tipo distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="17c40-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="17c40-109">Type</span><span class="sxs-lookup"><span data-stu-id="17c40-109">Type</span></span>|<span data-ttu-id="17c40-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="17c40-110">Description</span></span>|<span data-ttu-id="17c40-111">Sufijo o prefijo</span><span class="sxs-lookup"><span data-stu-id="17c40-111">Suffix or prefix</span></span>|<span data-ttu-id="17c40-112">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="17c40-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="17c40-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="17c40-113">sbyte</span></span>|<span data-ttu-id="17c40-114">entero de 8 bits con signo</span><span class="sxs-lookup"><span data-stu-id="17c40-114">signed 8-bit integer</span></span>|<span data-ttu-id="17c40-115">s</span><span class="sxs-lookup"><span data-stu-id="17c40-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="17c40-116">byte</span><span class="sxs-lookup"><span data-stu-id="17c40-116">byte</span></span>|<span data-ttu-id="17c40-117">número natural de 8 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="17c40-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="17c40-118">uy</span><span class="sxs-lookup"><span data-stu-id="17c40-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="17c40-119">int16</span><span class="sxs-lookup"><span data-stu-id="17c40-119">int16</span></span>|<span data-ttu-id="17c40-120">entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="17c40-120">signed 16-bit integer</span></span>|<span data-ttu-id="17c40-121">s</span><span class="sxs-lookup"><span data-stu-id="17c40-121">s</span></span>|`86s`|
|<span data-ttu-id="17c40-122">uint16</span><span class="sxs-lookup"><span data-stu-id="17c40-122">uint16</span></span>|<span data-ttu-id="17c40-123">número natural de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="17c40-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="17c40-124">us</span><span class="sxs-lookup"><span data-stu-id="17c40-124">us</span></span>|`86us`|
|<span data-ttu-id="17c40-125">int</span><span class="sxs-lookup"><span data-stu-id="17c40-125">int</span></span><br /><br /><span data-ttu-id="17c40-126">int32</span><span class="sxs-lookup"><span data-stu-id="17c40-126">int32</span></span>|<span data-ttu-id="17c40-127">entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="17c40-127">signed 32-bit integer</span></span>|<span data-ttu-id="17c40-128">l o ninguno</span><span class="sxs-lookup"><span data-stu-id="17c40-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="17c40-129">uint</span><span class="sxs-lookup"><span data-stu-id="17c40-129">uint</span></span><br /><br /><span data-ttu-id="17c40-130">uint32</span><span class="sxs-lookup"><span data-stu-id="17c40-130">uint32</span></span>|<span data-ttu-id="17c40-131">unsigned 32-número natural de bits</span><span class="sxs-lookup"><span data-stu-id="17c40-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="17c40-132">u o UL</span><span class="sxs-lookup"><span data-stu-id="17c40-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="17c40-133">nativeint (</span><span class="sxs-lookup"><span data-stu-id="17c40-133">nativeint</span></span>|<span data-ttu-id="17c40-134">puntero nativo a un número natural con signo</span><span class="sxs-lookup"><span data-stu-id="17c40-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="17c40-135">n</span><span class="sxs-lookup"><span data-stu-id="17c40-135">n</span></span>|`123n`|
|<span data-ttu-id="17c40-136">unativeint (</span><span class="sxs-lookup"><span data-stu-id="17c40-136">unativeint</span></span>|<span data-ttu-id="17c40-137">puntero nativo como un número natural sin signo</span><span class="sxs-lookup"><span data-stu-id="17c40-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="17c40-138">CEPE</span><span class="sxs-lookup"><span data-stu-id="17c40-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="17c40-139">int64</span><span class="sxs-lookup"><span data-stu-id="17c40-139">int64</span></span>|<span data-ttu-id="17c40-140">entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="17c40-140">signed 64-bit integer</span></span>|<span data-ttu-id="17c40-141">L</span><span class="sxs-lookup"><span data-stu-id="17c40-141">L</span></span>|`86L`|
|<span data-ttu-id="17c40-142">uint64</span><span class="sxs-lookup"><span data-stu-id="17c40-142">uint64</span></span>|<span data-ttu-id="17c40-143">unsigned 64-número natural de bits</span><span class="sxs-lookup"><span data-stu-id="17c40-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="17c40-144">UL</span><span class="sxs-lookup"><span data-stu-id="17c40-144">UL</span></span>|`86UL`|
|<span data-ttu-id="17c40-145">single, float32</span><span class="sxs-lookup"><span data-stu-id="17c40-145">single, float32</span></span>|<span data-ttu-id="17c40-146">número de punto flotante de 32 bits</span><span class="sxs-lookup"><span data-stu-id="17c40-146">32-bit floating point number</span></span>|<span data-ttu-id="17c40-147">F o f</span><span class="sxs-lookup"><span data-stu-id="17c40-147">F or f</span></span>|<span data-ttu-id="17c40-148">`4.14F` o `4.14f`</span><span class="sxs-lookup"><span data-stu-id="17c40-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="17c40-149">LF</span><span class="sxs-lookup"><span data-stu-id="17c40-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="17c40-150">flot hace</span><span class="sxs-lookup"><span data-stu-id="17c40-150">float; double</span></span>|<span data-ttu-id="17c40-151">número de punto flotante de 64 bits</span><span class="sxs-lookup"><span data-stu-id="17c40-151">64-bit floating point number</span></span>|<span data-ttu-id="17c40-152">ninguna</span><span class="sxs-lookup"><span data-stu-id="17c40-152">none</span></span>|<span data-ttu-id="17c40-153">`4.14` o `2.3E+32` o `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="17c40-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="17c40-154">LF</span><span class="sxs-lookup"><span data-stu-id="17c40-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="17c40-155">bigint</span><span class="sxs-lookup"><span data-stu-id="17c40-155">bigint</span></span>|<span data-ttu-id="17c40-156">entero no limitado a la representación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="17c40-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="17c40-157">I</span><span class="sxs-lookup"><span data-stu-id="17c40-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="17c40-158">decimal</span><span class="sxs-lookup"><span data-stu-id="17c40-158">decimal</span></span>|<span data-ttu-id="17c40-159">número fraccionario representado como un número de punto o racional fijo</span><span class="sxs-lookup"><span data-stu-id="17c40-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="17c40-160">M o m</span><span class="sxs-lookup"><span data-stu-id="17c40-160">M or m</span></span>|<span data-ttu-id="17c40-161">`0.7833M` o `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="17c40-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="17c40-162">Char</span><span class="sxs-lookup"><span data-stu-id="17c40-162">Char</span></span>|<span data-ttu-id="17c40-163">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="17c40-163">Unicode character</span></span>|<span data-ttu-id="17c40-164">ninguna</span><span class="sxs-lookup"><span data-stu-id="17c40-164">none</span></span>|<span data-ttu-id="17c40-165">`'a'` o `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="17c40-165">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="17c40-166">String</span><span class="sxs-lookup"><span data-stu-id="17c40-166">String</span></span>|<span data-ttu-id="17c40-167">Cadena de Unicode</span><span class="sxs-lookup"><span data-stu-id="17c40-167">Unicode string</span></span>|<span data-ttu-id="17c40-168">ninguna</span><span class="sxs-lookup"><span data-stu-id="17c40-168">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="17c40-169">o</span><span class="sxs-lookup"><span data-stu-id="17c40-169">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="17c40-170">o</span><span class="sxs-lookup"><span data-stu-id="17c40-170">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="17c40-171">o</span><span class="sxs-lookup"><span data-stu-id="17c40-171">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="17c40-172">Vea también [cadenas](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="17c40-172">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="17c40-173">byte</span><span class="sxs-lookup"><span data-stu-id="17c40-173">byte</span></span>|<span data-ttu-id="17c40-174">Carácter ASCII</span><span class="sxs-lookup"><span data-stu-id="17c40-174">ASCII character</span></span>|<span data-ttu-id="17c40-175">B</span><span class="sxs-lookup"><span data-stu-id="17c40-175">B</span></span>|`'a'B`|
|<span data-ttu-id="17c40-176">byte[]</span><span class="sxs-lookup"><span data-stu-id="17c40-176">byte[]</span></span>|<span data-ttu-id="17c40-177">cadena ASCII</span><span class="sxs-lookup"><span data-stu-id="17c40-177">ASCII string</span></span>|<span data-ttu-id="17c40-178">B</span><span class="sxs-lookup"><span data-stu-id="17c40-178">B</span></span>|`"text"B`|
|<span data-ttu-id="17c40-179">Cadena o Byte []</span><span class="sxs-lookup"><span data-stu-id="17c40-179">String or byte[]</span></span>|<span data-ttu-id="17c40-180">cadena textual</span><span class="sxs-lookup"><span data-stu-id="17c40-180">verbatim string</span></span>|<span data-ttu-id="17c40-181">@ prefix</span><span class="sxs-lookup"><span data-stu-id="17c40-181">@ prefix</span></span>|<span data-ttu-id="17c40-182">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="17c40-182">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="17c40-183">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="17c40-183">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="17c40-184">Literales con nombre</span><span class="sxs-lookup"><span data-stu-id="17c40-184">Named literals</span></span>

<span data-ttu-id="17c40-185">Los valores que están diseñados para ser constantes se pueden marcar con el atributo [literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) .</span><span class="sxs-lookup"><span data-stu-id="17c40-185">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="17c40-186">Este atributo tiene el efecto de hacer que un valor se compile como una constante.</span><span class="sxs-lookup"><span data-stu-id="17c40-186">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="17c40-187">En las expresiones de coincidencia de patrones, los identificadores que comienzan con caracteres en minúsculas siempre se tratan como variables que se van a enlazar, en lugar de como literales, por lo que generalmente debe usar mayúsculas iniciales al definir los literales.</span><span class="sxs-lookup"><span data-stu-id="17c40-187">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a><span data-ttu-id="17c40-188">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17c40-188">Remarks</span></span>

<span data-ttu-id="17c40-189">Las cadenas Unicode pueden contener codificaciones explícitas que puede especificar mediante `\u` seguido de una codificación de código hexadecimal de 16 bits (0000-FFFF) o UTF-32 que puede especificar mediante `\U` seguido de un código hexadecimal de 32 bits que representa cualquier Unicode. punto de código (00000000-0010FFFF).</span><span class="sxs-lookup"><span data-stu-id="17c40-189">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="17c40-190">No se permite el uso de otros operadores bit a bit distintos de `|||`.</span><span class="sxs-lookup"><span data-stu-id="17c40-190">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="17c40-191">Enteros en otras bases</span><span class="sxs-lookup"><span data-stu-id="17c40-191">Integers in other bases</span></span>

<span data-ttu-id="17c40-192">Los enteros de 32 bits con signo también se pueden especificar en formato hexadecimal, octal o binario mediante un prefijo `0x`, `0o` o `0b` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="17c40-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="17c40-193">Caracteres de subrayado en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="17c40-193">Underscores in numeric literals</span></span>

<span data-ttu-id="17c40-194">Puede separar los dígitos con el carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="17c40-194">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="17c40-195">Vea también</span><span class="sxs-lookup"><span data-stu-id="17c40-195">See also</span></span>

- [<span data-ttu-id="17c40-196">Clase Core. Literalattribute (</span><span class="sxs-lookup"><span data-stu-id="17c40-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
