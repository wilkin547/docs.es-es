---
title: Literales
description: 'Obtenga información sobre los tipos literales en el lenguaje de programación F #.'
ms.date: 06/28/2019
ms.openlocfilehash: 98d609a1cf0beb00c0dd4d45ea343aaa2280b62e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855028"
---
# <a name="literals"></a><span data-ttu-id="b0845-103">Literales</span><span class="sxs-lookup"><span data-stu-id="b0845-103">Literals</span></span>

<span data-ttu-id="b0845-104">En este artículo se proporciona una tabla que muestra cómo especificar el tipo de un literal en F #.</span><span class="sxs-lookup"><span data-stu-id="b0845-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

> [!NOTE]
> <span data-ttu-id="b0845-105">La referencia de la API de docs.microsoft.com para F # no está completa.</span><span class="sxs-lookup"><span data-stu-id="b0845-105">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="b0845-106">Si encuentra vínculos rotos, consulte la [documentación de la biblioteca básica de F #](https://fsharp.github.io/fsharp-core-docs/) .</span><span class="sxs-lookup"><span data-stu-id="b0845-106">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

## <a name="literal-types"></a><span data-ttu-id="b0845-107">Tipos literales</span><span class="sxs-lookup"><span data-stu-id="b0845-107">Literal types</span></span>

<span data-ttu-id="b0845-108">En la tabla siguiente se muestran los tipos literales de F #.</span><span class="sxs-lookup"><span data-stu-id="b0845-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="b0845-109">Los caracteres que representan dígitos en notación hexadecimal no distinguen mayúsculas de minúsculas; los caracteres que identifican el tipo distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b0845-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="b0845-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="b0845-110">Type</span></span>|<span data-ttu-id="b0845-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0845-111">Description</span></span>|<span data-ttu-id="b0845-112">Sufijo o prefijo</span><span class="sxs-lookup"><span data-stu-id="b0845-112">Suffix or prefix</span></span>|<span data-ttu-id="b0845-113">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b0845-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="b0845-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="b0845-114">sbyte</span></span>|<span data-ttu-id="b0845-115">entero de 8 bits con signo</span><span class="sxs-lookup"><span data-stu-id="b0845-115">signed 8-bit integer</span></span>|<span data-ttu-id="b0845-116">y</span><span class="sxs-lookup"><span data-stu-id="b0845-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="b0845-117">byte</span><span class="sxs-lookup"><span data-stu-id="b0845-117">byte</span></span>|<span data-ttu-id="b0845-118">número natural de 8 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="b0845-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="b0845-119">uy</span><span class="sxs-lookup"><span data-stu-id="b0845-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="b0845-120">int16</span><span class="sxs-lookup"><span data-stu-id="b0845-120">int16</span></span>|<span data-ttu-id="b0845-121">entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="b0845-121">signed 16-bit integer</span></span>|<span data-ttu-id="b0845-122">s</span><span class="sxs-lookup"><span data-stu-id="b0845-122">s</span></span>|`86s`|
|<span data-ttu-id="b0845-123">uint16</span><span class="sxs-lookup"><span data-stu-id="b0845-123">uint16</span></span>|<span data-ttu-id="b0845-124">número natural de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="b0845-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="b0845-125">americana</span><span class="sxs-lookup"><span data-stu-id="b0845-125">us</span></span>|`86us`|
|<span data-ttu-id="b0845-126">int</span><span class="sxs-lookup"><span data-stu-id="b0845-126">int</span></span><br /><br /><span data-ttu-id="b0845-127">int32</span><span class="sxs-lookup"><span data-stu-id="b0845-127">int32</span></span>|<span data-ttu-id="b0845-128">entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="b0845-128">signed 32-bit integer</span></span>|<span data-ttu-id="b0845-129">l o ninguno</span><span class="sxs-lookup"><span data-stu-id="b0845-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="b0845-130">uint</span><span class="sxs-lookup"><span data-stu-id="b0845-130">uint</span></span><br /><br /><span data-ttu-id="b0845-131">uint32</span><span class="sxs-lookup"><span data-stu-id="b0845-131">uint32</span></span>|<span data-ttu-id="b0845-132">unsigned 32-número natural de bits</span><span class="sxs-lookup"><span data-stu-id="b0845-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="b0845-133">u o UL</span><span class="sxs-lookup"><span data-stu-id="b0845-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="b0845-134">nativeint</span><span class="sxs-lookup"><span data-stu-id="b0845-134">nativeint</span></span>|<span data-ttu-id="b0845-135">puntero nativo a un número natural con signo</span><span class="sxs-lookup"><span data-stu-id="b0845-135">native pointer to a signed natural number</span></span>|<span data-ttu-id="b0845-136">n</span><span class="sxs-lookup"><span data-stu-id="b0845-136">n</span></span>|`123n`|
|<span data-ttu-id="b0845-137">unativeint</span><span class="sxs-lookup"><span data-stu-id="b0845-137">unativeint</span></span>|<span data-ttu-id="b0845-138">puntero nativo como un número natural sin signo</span><span class="sxs-lookup"><span data-stu-id="b0845-138">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="b0845-139">CEPE</span><span class="sxs-lookup"><span data-stu-id="b0845-139">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="b0845-140">int64</span><span class="sxs-lookup"><span data-stu-id="b0845-140">int64</span></span>|<span data-ttu-id="b0845-141">entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="b0845-141">signed 64-bit integer</span></span>|<span data-ttu-id="b0845-142">L</span><span class="sxs-lookup"><span data-stu-id="b0845-142">L</span></span>|`86L`|
|<span data-ttu-id="b0845-143">uint64</span><span class="sxs-lookup"><span data-stu-id="b0845-143">uint64</span></span>|<span data-ttu-id="b0845-144">unsigned 64-número natural de bits</span><span class="sxs-lookup"><span data-stu-id="b0845-144">unsigned 64-bit natural number</span></span>|<span data-ttu-id="b0845-145">UL</span><span class="sxs-lookup"><span data-stu-id="b0845-145">UL</span></span>|`86UL`|
|<span data-ttu-id="b0845-146">single, float32</span><span class="sxs-lookup"><span data-stu-id="b0845-146">single, float32</span></span>|<span data-ttu-id="b0845-147">número de punto flotante de 32 bits</span><span class="sxs-lookup"><span data-stu-id="b0845-147">32-bit floating point number</span></span>|<span data-ttu-id="b0845-148">F o f</span><span class="sxs-lookup"><span data-stu-id="b0845-148">F or f</span></span>|<span data-ttu-id="b0845-149">`4.14F` o `4.14f`</span><span class="sxs-lookup"><span data-stu-id="b0845-149">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="b0845-150">LF</span><span class="sxs-lookup"><span data-stu-id="b0845-150">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="b0845-151">flot hace</span><span class="sxs-lookup"><span data-stu-id="b0845-151">float; double</span></span>|<span data-ttu-id="b0845-152">número de punto flotante de 64 bits</span><span class="sxs-lookup"><span data-stu-id="b0845-152">64-bit floating point number</span></span>|<span data-ttu-id="b0845-153">ninguno</span><span class="sxs-lookup"><span data-stu-id="b0845-153">none</span></span>|<span data-ttu-id="b0845-154">`4.14`, `2.3E+32` o `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="b0845-154">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="b0845-155">LF</span><span class="sxs-lookup"><span data-stu-id="b0845-155">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="b0845-156">bigint</span><span class="sxs-lookup"><span data-stu-id="b0845-156">bigint</span></span>|<span data-ttu-id="b0845-157">entero no limitado a la representación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="b0845-157">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="b0845-158">I</span><span class="sxs-lookup"><span data-stu-id="b0845-158">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="b0845-159">Decimal</span><span class="sxs-lookup"><span data-stu-id="b0845-159">decimal</span></span>|<span data-ttu-id="b0845-160">número fraccionario representado como un número de punto o racional fijo</span><span class="sxs-lookup"><span data-stu-id="b0845-160">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="b0845-161">M o m</span><span class="sxs-lookup"><span data-stu-id="b0845-161">M or m</span></span>|<span data-ttu-id="b0845-162">`0.7833M` o `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="b0845-162">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="b0845-163">Char</span><span class="sxs-lookup"><span data-stu-id="b0845-163">Char</span></span>|<span data-ttu-id="b0845-164">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="b0845-164">Unicode character</span></span>|<span data-ttu-id="b0845-165">ninguno</span><span class="sxs-lookup"><span data-stu-id="b0845-165">none</span></span>|<span data-ttu-id="b0845-166">`'a'` o `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="b0845-166">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="b0845-167">String</span><span class="sxs-lookup"><span data-stu-id="b0845-167">String</span></span>|<span data-ttu-id="b0845-168">Cadena de Unicode</span><span class="sxs-lookup"><span data-stu-id="b0845-168">Unicode string</span></span>|<span data-ttu-id="b0845-169">ninguno</span><span class="sxs-lookup"><span data-stu-id="b0845-169">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="b0845-170">or</span><span class="sxs-lookup"><span data-stu-id="b0845-170">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="b0845-171">or</span><span class="sxs-lookup"><span data-stu-id="b0845-171">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="b0845-172">or</span><span class="sxs-lookup"><span data-stu-id="b0845-172">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="b0845-173">Vea también [cadenas](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="b0845-173">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="b0845-174">byte</span><span class="sxs-lookup"><span data-stu-id="b0845-174">byte</span></span>|<span data-ttu-id="b0845-175">Carácter ASCII</span><span class="sxs-lookup"><span data-stu-id="b0845-175">ASCII character</span></span>|<span data-ttu-id="b0845-176">B</span><span class="sxs-lookup"><span data-stu-id="b0845-176">B</span></span>|`'a'B`|
|<span data-ttu-id="b0845-177">byte[]</span><span class="sxs-lookup"><span data-stu-id="b0845-177">byte[]</span></span>|<span data-ttu-id="b0845-178">Cadena ASCII</span><span class="sxs-lookup"><span data-stu-id="b0845-178">ASCII string</span></span>|<span data-ttu-id="b0845-179">B</span><span class="sxs-lookup"><span data-stu-id="b0845-179">B</span></span>|`"text"B`|
|<span data-ttu-id="b0845-180">Cadena o Byte []</span><span class="sxs-lookup"><span data-stu-id="b0845-180">String or byte[]</span></span>|<span data-ttu-id="b0845-181">cadena textual</span><span class="sxs-lookup"><span data-stu-id="b0845-181">verbatim string</span></span>|<span data-ttu-id="b0845-182">@ prefix</span><span class="sxs-lookup"><span data-stu-id="b0845-182">@ prefix</span></span>|<span data-ttu-id="b0845-183">`@"\\server\share"`Unicode</span><span class="sxs-lookup"><span data-stu-id="b0845-183">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="b0845-184">`@"\\server\share"B`ASCII</span><span class="sxs-lookup"><span data-stu-id="b0845-184">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="b0845-185">Literales con nombre</span><span class="sxs-lookup"><span data-stu-id="b0845-185">Named literals</span></span>

<span data-ttu-id="b0845-186">Los valores que están diseñados para ser constantes se pueden marcar con el atributo [literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) .</span><span class="sxs-lookup"><span data-stu-id="b0845-186">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="b0845-187">Este atributo tiene el efecto de hacer que un valor se compile como una constante.</span><span class="sxs-lookup"><span data-stu-id="b0845-187">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="b0845-188">En las expresiones de coincidencia de patrones, los identificadores que comienzan con caracteres en minúsculas siempre se tratan como variables que se van a enlazar, en lugar de como literales, por lo que generalmente debe usar mayúsculas iniciales al definir los literales.</span><span class="sxs-lookup"><span data-stu-id="b0845-188">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="b0845-189">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b0845-189">Remarks</span></span>

<span data-ttu-id="b0845-190">Las cadenas Unicode pueden contener codificaciones explícitas que puede especificar mediante `\u` el uso seguido de una codificación de código hexadecimal de 16 bits (0000-ffff) o UTF-32 que puede especificar mediante `\U` un código hexadecimal de 32 bits que representa cualquier punto de código Unicode (00000000-0010FFFF).</span><span class="sxs-lookup"><span data-stu-id="b0845-190">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="b0845-191">No se permite el uso de otros operadores bit a bit distintos de `|||` .</span><span class="sxs-lookup"><span data-stu-id="b0845-191">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="b0845-192">Enteros en otras bases</span><span class="sxs-lookup"><span data-stu-id="b0845-192">Integers in other bases</span></span>

<span data-ttu-id="b0845-193">Los enteros de 32 bits con signo también se pueden especificar en hexadecimal, octal o binario mediante `0x` un `0o` `0b` prefijo, o respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b0845-193">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="b0845-194">Caracteres de subrayado en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="b0845-194">Underscores in numeric literals</span></span>

<span data-ttu-id="b0845-195">Puede separar los dígitos con el carácter de subrayado ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="b0845-195">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="b0845-196">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0845-196">See also</span></span>

- [<span data-ttu-id="b0845-197">Clase Core. Literalattribute (</span><span class="sxs-lookup"><span data-stu-id="b0845-197">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
