---
title: Literales
description: 'Obtenga información sobre los tipos literales en el lenguaje de programación F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 15f73db3c36f7c60ab1eeba96c63a28ebc6d7f01
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559159"
---
# <a name="literals"></a><span data-ttu-id="47502-103">Literales</span><span class="sxs-lookup"><span data-stu-id="47502-103">Literals</span></span>

<span data-ttu-id="47502-104">En este artículo se proporciona una tabla que muestra cómo especificar el tipo de un literal en F #.</span><span class="sxs-lookup"><span data-stu-id="47502-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="47502-105">Tipos literales</span><span class="sxs-lookup"><span data-stu-id="47502-105">Literal types</span></span>

<span data-ttu-id="47502-106">En la tabla siguiente se muestran los tipos literales de F #.</span><span class="sxs-lookup"><span data-stu-id="47502-106">The following table shows the literal types in F#.</span></span> <span data-ttu-id="47502-107">Los caracteres que representan dígitos en notación hexadecimal no distinguen mayúsculas de minúsculas; los caracteres que identifican el tipo distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="47502-107">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="47502-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="47502-108">Type</span></span>|<span data-ttu-id="47502-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="47502-109">Description</span></span>|<span data-ttu-id="47502-110">Sufijo o prefijo</span><span class="sxs-lookup"><span data-stu-id="47502-110">Suffix or prefix</span></span>|<span data-ttu-id="47502-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="47502-111">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="47502-112">sbyte</span><span class="sxs-lookup"><span data-stu-id="47502-112">sbyte</span></span>|<span data-ttu-id="47502-113">entero de 8 bits con signo</span><span class="sxs-lookup"><span data-stu-id="47502-113">signed 8-bit integer</span></span>|<span data-ttu-id="47502-114">y</span><span class="sxs-lookup"><span data-stu-id="47502-114">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="47502-115">byte</span><span class="sxs-lookup"><span data-stu-id="47502-115">byte</span></span>|<span data-ttu-id="47502-116">número natural de 8 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="47502-116">unsigned 8-bit natural number</span></span>|<span data-ttu-id="47502-117">uy</span><span class="sxs-lookup"><span data-stu-id="47502-117">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="47502-118">int16</span><span class="sxs-lookup"><span data-stu-id="47502-118">int16</span></span>|<span data-ttu-id="47502-119">entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="47502-119">signed 16-bit integer</span></span>|<span data-ttu-id="47502-120">s</span><span class="sxs-lookup"><span data-stu-id="47502-120">s</span></span>|`86s`|
|<span data-ttu-id="47502-121">uint16</span><span class="sxs-lookup"><span data-stu-id="47502-121">uint16</span></span>|<span data-ttu-id="47502-122">número natural de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="47502-122">unsigned 16-bit natural number</span></span>|<span data-ttu-id="47502-123">americana</span><span class="sxs-lookup"><span data-stu-id="47502-123">us</span></span>|`86us`|
|<span data-ttu-id="47502-124">int</span><span class="sxs-lookup"><span data-stu-id="47502-124">int</span></span><br /><br /><span data-ttu-id="47502-125">int32</span><span class="sxs-lookup"><span data-stu-id="47502-125">int32</span></span>|<span data-ttu-id="47502-126">entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="47502-126">signed 32-bit integer</span></span>|<span data-ttu-id="47502-127">l o ninguno</span><span class="sxs-lookup"><span data-stu-id="47502-127">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="47502-128">uint</span><span class="sxs-lookup"><span data-stu-id="47502-128">uint</span></span><br /><br /><span data-ttu-id="47502-129">uint32</span><span class="sxs-lookup"><span data-stu-id="47502-129">uint32</span></span>|<span data-ttu-id="47502-130">unsigned 32-número natural de bits</span><span class="sxs-lookup"><span data-stu-id="47502-130">unsigned 32-bit natural number</span></span>|<span data-ttu-id="47502-131">u o UL</span><span class="sxs-lookup"><span data-stu-id="47502-131">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="47502-132">nativeint</span><span class="sxs-lookup"><span data-stu-id="47502-132">nativeint</span></span>|<span data-ttu-id="47502-133">puntero nativo a un número natural con signo</span><span class="sxs-lookup"><span data-stu-id="47502-133">native pointer to a signed natural number</span></span>|<span data-ttu-id="47502-134">n</span><span class="sxs-lookup"><span data-stu-id="47502-134">n</span></span>|`123n`|
|<span data-ttu-id="47502-135">unativeint</span><span class="sxs-lookup"><span data-stu-id="47502-135">unativeint</span></span>|<span data-ttu-id="47502-136">puntero nativo como un número natural sin signo</span><span class="sxs-lookup"><span data-stu-id="47502-136">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="47502-137">CEPE</span><span class="sxs-lookup"><span data-stu-id="47502-137">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="47502-138">int64</span><span class="sxs-lookup"><span data-stu-id="47502-138">int64</span></span>|<span data-ttu-id="47502-139">entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="47502-139">signed 64-bit integer</span></span>|<span data-ttu-id="47502-140">L</span><span class="sxs-lookup"><span data-stu-id="47502-140">L</span></span>|`86L`|
|<span data-ttu-id="47502-141">uint64</span><span class="sxs-lookup"><span data-stu-id="47502-141">uint64</span></span>|<span data-ttu-id="47502-142">unsigned 64-número natural de bits</span><span class="sxs-lookup"><span data-stu-id="47502-142">unsigned 64-bit natural number</span></span>|<span data-ttu-id="47502-143">UL</span><span class="sxs-lookup"><span data-stu-id="47502-143">UL</span></span>|`86UL`|
|<span data-ttu-id="47502-144">single, float32</span><span class="sxs-lookup"><span data-stu-id="47502-144">single, float32</span></span>|<span data-ttu-id="47502-145">número de punto flotante de 32 bits</span><span class="sxs-lookup"><span data-stu-id="47502-145">32-bit floating point number</span></span>|<span data-ttu-id="47502-146">F o f</span><span class="sxs-lookup"><span data-stu-id="47502-146">F or f</span></span>|<span data-ttu-id="47502-147">`4.14F` o `4.14f`</span><span class="sxs-lookup"><span data-stu-id="47502-147">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="47502-148">LF</span><span class="sxs-lookup"><span data-stu-id="47502-148">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="47502-149">flot hace</span><span class="sxs-lookup"><span data-stu-id="47502-149">float; double</span></span>|<span data-ttu-id="47502-150">número de punto flotante de 64 bits</span><span class="sxs-lookup"><span data-stu-id="47502-150">64-bit floating point number</span></span>|<span data-ttu-id="47502-151">ninguno</span><span class="sxs-lookup"><span data-stu-id="47502-151">none</span></span>|<span data-ttu-id="47502-152">`4.14`, `2.3E+32` o `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="47502-152">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="47502-153">LF</span><span class="sxs-lookup"><span data-stu-id="47502-153">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="47502-154">bigint</span><span class="sxs-lookup"><span data-stu-id="47502-154">bigint</span></span>|<span data-ttu-id="47502-155">entero no limitado a la representación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="47502-155">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="47502-156">I</span><span class="sxs-lookup"><span data-stu-id="47502-156">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="47502-157">Decimal</span><span class="sxs-lookup"><span data-stu-id="47502-157">decimal</span></span>|<span data-ttu-id="47502-158">número fraccionario representado como un número de punto o racional fijo</span><span class="sxs-lookup"><span data-stu-id="47502-158">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="47502-159">M o m</span><span class="sxs-lookup"><span data-stu-id="47502-159">M or m</span></span>|<span data-ttu-id="47502-160">`0.7833M` o `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="47502-160">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="47502-161">Char</span><span class="sxs-lookup"><span data-stu-id="47502-161">Char</span></span>|<span data-ttu-id="47502-162">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="47502-162">Unicode character</span></span>|<span data-ttu-id="47502-163">ninguno</span><span class="sxs-lookup"><span data-stu-id="47502-163">none</span></span>|<span data-ttu-id="47502-164">`'a'` o `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="47502-164">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="47502-165">String</span><span class="sxs-lookup"><span data-stu-id="47502-165">String</span></span>|<span data-ttu-id="47502-166">Cadena de Unicode</span><span class="sxs-lookup"><span data-stu-id="47502-166">Unicode string</span></span>|<span data-ttu-id="47502-167">ninguno</span><span class="sxs-lookup"><span data-stu-id="47502-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="47502-168">or</span><span class="sxs-lookup"><span data-stu-id="47502-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="47502-169">or</span><span class="sxs-lookup"><span data-stu-id="47502-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="47502-170">or</span><span class="sxs-lookup"><span data-stu-id="47502-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="47502-171">Vea también [cadenas](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="47502-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="47502-172">byte</span><span class="sxs-lookup"><span data-stu-id="47502-172">byte</span></span>|<span data-ttu-id="47502-173">Carácter ASCII</span><span class="sxs-lookup"><span data-stu-id="47502-173">ASCII character</span></span>|<span data-ttu-id="47502-174">B</span><span class="sxs-lookup"><span data-stu-id="47502-174">B</span></span>|`'a'B`|
|<span data-ttu-id="47502-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="47502-175">byte[]</span></span>|<span data-ttu-id="47502-176">Cadena ASCII</span><span class="sxs-lookup"><span data-stu-id="47502-176">ASCII string</span></span>|<span data-ttu-id="47502-177">B</span><span class="sxs-lookup"><span data-stu-id="47502-177">B</span></span>|`"text"B`|
|<span data-ttu-id="47502-178">Cadena o Byte []</span><span class="sxs-lookup"><span data-stu-id="47502-178">String or byte[]</span></span>|<span data-ttu-id="47502-179">cadena textual</span><span class="sxs-lookup"><span data-stu-id="47502-179">verbatim string</span></span>|<span data-ttu-id="47502-180">@ prefix</span><span class="sxs-lookup"><span data-stu-id="47502-180">@ prefix</span></span>|<span data-ttu-id="47502-181">`@"\\server\share"` Unicode</span><span class="sxs-lookup"><span data-stu-id="47502-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="47502-182">`@"\\server\share"B` ASCII</span><span class="sxs-lookup"><span data-stu-id="47502-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="47502-183">Literales con nombre</span><span class="sxs-lookup"><span data-stu-id="47502-183">Named literals</span></span>

<span data-ttu-id="47502-184">Los valores que están diseñados para ser constantes se pueden marcar con el atributo [literal](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) .</span><span class="sxs-lookup"><span data-stu-id="47502-184">Values that are intended to be constants can be marked with the [Literal](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) attribute.</span></span> <span data-ttu-id="47502-185">Este atributo tiene el efecto de hacer que un valor se compile como una constante.</span><span class="sxs-lookup"><span data-stu-id="47502-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="47502-186">En las expresiones de coincidencia de patrones, los identificadores que comienzan con caracteres en minúsculas siempre se tratan como variables que se van a enlazar, en lugar de como literales, por lo que generalmente debe usar mayúsculas iniciales al definir los literales.</span><span class="sxs-lookup"><span data-stu-id="47502-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="47502-187">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47502-187">Remarks</span></span>

<span data-ttu-id="47502-188">Las cadenas Unicode pueden contener codificaciones explícitas que puede especificar mediante `\u` el uso seguido de una codificación de código hexadecimal de 16 bits (0000-ffff) o UTF-32 que puede especificar mediante `\U` un código hexadecimal de 32 bits que representa cualquier punto de código Unicode (00000000-0010FFFF).</span><span class="sxs-lookup"><span data-stu-id="47502-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="47502-189">No se permite el uso de otros operadores bit a bit distintos de `|||` .</span><span class="sxs-lookup"><span data-stu-id="47502-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="47502-190">Enteros en otras bases</span><span class="sxs-lookup"><span data-stu-id="47502-190">Integers in other bases</span></span>

<span data-ttu-id="47502-191">Los enteros de 32 bits con signo también se pueden especificar en hexadecimal, octal o binario mediante `0x` un `0o` `0b` prefijo, o respectivamente.</span><span class="sxs-lookup"><span data-stu-id="47502-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="47502-192">Caracteres de subrayado en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="47502-192">Underscores in numeric literals</span></span>

<span data-ttu-id="47502-193">Puede separar los dígitos con el carácter de subrayado ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="47502-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```
