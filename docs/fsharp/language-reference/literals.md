---
title: Literales
description: Obtenga información sobre los tipos literales en la F# lenguaje de programación.
ms.date: 06/28/2019
ms.openlocfilehash: 0c9ced0b505817a161ca39c6c9f853f94cedf410
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610155"
---
# <a name="literals"></a><span data-ttu-id="20c88-103">Literales</span><span class="sxs-lookup"><span data-stu-id="20c88-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="20c88-104">Los vínculos de referencia de API en este artículo le llevará a MSDN (por ahora).</span><span class="sxs-lookup"><span data-stu-id="20c88-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="20c88-105">Este tema proporciona una tabla que se muestra cómo especificar el tipo de un literal en F#.</span><span class="sxs-lookup"><span data-stu-id="20c88-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="20c88-106">Tipos literales</span><span class="sxs-lookup"><span data-stu-id="20c88-106">Literal Types</span></span>

<span data-ttu-id="20c88-107">La siguiente tabla muestra los tipos literales en F#.</span><span class="sxs-lookup"><span data-stu-id="20c88-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="20c88-108">Caracteres que representan dígitos en notación hexadecimal no distinguen mayúsculas de minúsculas; caracteres que identifican el tipo distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="20c88-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="20c88-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="20c88-109">Type</span></span>|<span data-ttu-id="20c88-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="20c88-110">Description</span></span>|<span data-ttu-id="20c88-111">Prefijo o sufijo</span><span class="sxs-lookup"><span data-stu-id="20c88-111">Suffix or prefix</span></span>|<span data-ttu-id="20c88-112">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="20c88-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="20c88-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="20c88-113">sbyte</span></span>|<span data-ttu-id="20c88-114">entero de 8 bits con signo</span><span class="sxs-lookup"><span data-stu-id="20c88-114">signed 8-bit integer</span></span>|<span data-ttu-id="20c88-115">y</span><span class="sxs-lookup"><span data-stu-id="20c88-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="20c88-116">byte</span><span class="sxs-lookup"><span data-stu-id="20c88-116">byte</span></span>|<span data-ttu-id="20c88-117">número natural de 8 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="20c88-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="20c88-118">UY</span><span class="sxs-lookup"><span data-stu-id="20c88-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="20c88-119">int16</span><span class="sxs-lookup"><span data-stu-id="20c88-119">int16</span></span>|<span data-ttu-id="20c88-120">entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="20c88-120">signed 16-bit integer</span></span>|<span data-ttu-id="20c88-121">s</span><span class="sxs-lookup"><span data-stu-id="20c88-121">s</span></span>|`86s`|
|<span data-ttu-id="20c88-122">uint16</span><span class="sxs-lookup"><span data-stu-id="20c88-122">uint16</span></span>|<span data-ttu-id="20c88-123">número natural de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="20c88-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="20c88-124">us</span><span class="sxs-lookup"><span data-stu-id="20c88-124">us</span></span>|`86us`|
|<span data-ttu-id="20c88-125">int</span><span class="sxs-lookup"><span data-stu-id="20c88-125">int</span></span><br /><br /><span data-ttu-id="20c88-126">int32</span><span class="sxs-lookup"><span data-stu-id="20c88-126">int32</span></span>|<span data-ttu-id="20c88-127">entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="20c88-127">signed 32-bit integer</span></span>|<span data-ttu-id="20c88-128">l o none</span><span class="sxs-lookup"><span data-stu-id="20c88-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="20c88-129">uint</span><span class="sxs-lookup"><span data-stu-id="20c88-129">uint</span></span><br /><br /><span data-ttu-id="20c88-130">uint32</span><span class="sxs-lookup"><span data-stu-id="20c88-130">uint32</span></span>|<span data-ttu-id="20c88-131">número natural de 32 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="20c88-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="20c88-132">u o ul</span><span class="sxs-lookup"><span data-stu-id="20c88-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="20c88-133">nativeint.</span><span class="sxs-lookup"><span data-stu-id="20c88-133">nativeint</span></span>|<span data-ttu-id="20c88-134">puntero nativo en un número natural con signo</span><span class="sxs-lookup"><span data-stu-id="20c88-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="20c88-135">n</span><span class="sxs-lookup"><span data-stu-id="20c88-135">n</span></span>|`123n`|
|<span data-ttu-id="20c88-136">unativeint.</span><span class="sxs-lookup"><span data-stu-id="20c88-136">unativeint</span></span>|<span data-ttu-id="20c88-137">puntero nativo como un número natural sin signo</span><span class="sxs-lookup"><span data-stu-id="20c88-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="20c88-138">anular</span><span class="sxs-lookup"><span data-stu-id="20c88-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="20c88-139">int64</span><span class="sxs-lookup"><span data-stu-id="20c88-139">int64</span></span>|<span data-ttu-id="20c88-140">entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="20c88-140">signed 64-bit integer</span></span>|<span data-ttu-id="20c88-141">L</span><span class="sxs-lookup"><span data-stu-id="20c88-141">L</span></span>|`86L`|
|<span data-ttu-id="20c88-142">uint64</span><span class="sxs-lookup"><span data-stu-id="20c88-142">uint64</span></span>|<span data-ttu-id="20c88-143">número natural de 64 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="20c88-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="20c88-144">UL</span><span class="sxs-lookup"><span data-stu-id="20c88-144">UL</span></span>|`86UL`|
|<span data-ttu-id="20c88-145">float32 único,</span><span class="sxs-lookup"><span data-stu-id="20c88-145">single, float32</span></span>|<span data-ttu-id="20c88-146">número de punto flotante de 32 bits</span><span class="sxs-lookup"><span data-stu-id="20c88-146">32-bit floating point number</span></span>|<span data-ttu-id="20c88-147">F o f</span><span class="sxs-lookup"><span data-stu-id="20c88-147">F or f</span></span>|<span data-ttu-id="20c88-148">`4.14F` o `4.14f`</span><span class="sxs-lookup"><span data-stu-id="20c88-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="20c88-149">lf</span><span class="sxs-lookup"><span data-stu-id="20c88-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="20c88-150">float; Double</span><span class="sxs-lookup"><span data-stu-id="20c88-150">float; double</span></span>|<span data-ttu-id="20c88-151">número de punto flotante de 64 bits</span><span class="sxs-lookup"><span data-stu-id="20c88-151">64-bit floating point number</span></span>|<span data-ttu-id="20c88-152">ninguna</span><span class="sxs-lookup"><span data-stu-id="20c88-152">none</span></span>|<span data-ttu-id="20c88-153">`4.14` o `2.3E+32` o `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="20c88-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="20c88-154">LF</span><span class="sxs-lookup"><span data-stu-id="20c88-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="20c88-155">bigint</span><span class="sxs-lookup"><span data-stu-id="20c88-155">bigint</span></span>|<span data-ttu-id="20c88-156">entero no limitado a la representación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="20c88-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="20c88-157">I</span><span class="sxs-lookup"><span data-stu-id="20c88-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="20c88-158">decimal</span><span class="sxs-lookup"><span data-stu-id="20c88-158">decimal</span></span>|<span data-ttu-id="20c88-159">número fraccionario representado como un punto fijo o un número racional</span><span class="sxs-lookup"><span data-stu-id="20c88-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="20c88-160">M o m</span><span class="sxs-lookup"><span data-stu-id="20c88-160">M or m</span></span>|<span data-ttu-id="20c88-161">`0.7833M` o `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="20c88-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="20c88-162">Char</span><span class="sxs-lookup"><span data-stu-id="20c88-162">Char</span></span>|<span data-ttu-id="20c88-163">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="20c88-163">Unicode character</span></span>|<span data-ttu-id="20c88-164">ninguna</span><span class="sxs-lookup"><span data-stu-id="20c88-164">none</span></span>|`'a'`|
|<span data-ttu-id="20c88-165">String</span><span class="sxs-lookup"><span data-stu-id="20c88-165">String</span></span>|<span data-ttu-id="20c88-166">Cadena de Unicode</span><span class="sxs-lookup"><span data-stu-id="20c88-166">Unicode string</span></span>|<span data-ttu-id="20c88-167">ninguna</span><span class="sxs-lookup"><span data-stu-id="20c88-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="20c88-168">o</span><span class="sxs-lookup"><span data-stu-id="20c88-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="20c88-169">o</span><span class="sxs-lookup"><span data-stu-id="20c88-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="20c88-170">o</span><span class="sxs-lookup"><span data-stu-id="20c88-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="20c88-171">Vea también [cadenas](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="20c88-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="20c88-172">byte</span><span class="sxs-lookup"><span data-stu-id="20c88-172">byte</span></span>|<span data-ttu-id="20c88-173">Carácter ASCII</span><span class="sxs-lookup"><span data-stu-id="20c88-173">ASCII character</span></span>|<span data-ttu-id="20c88-174">B</span><span class="sxs-lookup"><span data-stu-id="20c88-174">B</span></span>|`'a'B`|
|<span data-ttu-id="20c88-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="20c88-175">byte[]</span></span>|<span data-ttu-id="20c88-176">cadena ASCII</span><span class="sxs-lookup"><span data-stu-id="20c88-176">ASCII string</span></span>|<span data-ttu-id="20c88-177">B</span><span class="sxs-lookup"><span data-stu-id="20c88-177">B</span></span>|`"text"B`|
|<span data-ttu-id="20c88-178">String o byte]</span><span class="sxs-lookup"><span data-stu-id="20c88-178">String or byte[]</span></span>|<span data-ttu-id="20c88-179">literales de cadenas</span><span class="sxs-lookup"><span data-stu-id="20c88-179">verbatim string</span></span>|<span data-ttu-id="20c88-180">prefijo @</span><span class="sxs-lookup"><span data-stu-id="20c88-180">@ prefix</span></span>|<span data-ttu-id="20c88-181">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="20c88-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="20c88-182">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="20c88-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="20c88-183">Literales con nombre</span><span class="sxs-lookup"><span data-stu-id="20c88-183">Named literals</span></span>

<span data-ttu-id="20c88-184">Los valores que están diseñados para ser constantes se pueden marcar con el [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) atributo.</span><span class="sxs-lookup"><span data-stu-id="20c88-184">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="20c88-185">Este atributo tiene el efecto de la causa de un valor que se compile como una constante.</span><span class="sxs-lookup"><span data-stu-id="20c88-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="20c88-186">En las expresiones de coincidencia de patrón, los identificadores que comienzan con caracteres en minúscula se tratan siempre como variables para enlazar, en lugar de como literales, por lo tanto normalmente debe usar mayúsculas iniciales al definir los literales.</span><span class="sxs-lookup"><span data-stu-id="20c88-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="20c88-187">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20c88-187">Remarks</span></span>

<span data-ttu-id="20c88-188">Las cadenas Unicode pueden contener codificaciones explícitas que se pueden especificar mediante el uso de `\u` seguido por un código hexadecimal de 16 bits (0000 - FFFF), o codificaciones UTF-32 que se pueden especificar mediante el uso de `\U` seguido por un código hexadecimal de 32 bits que representa cualquier punto de código Unicode (00000000 - 0010FFFF).</span><span class="sxs-lookup"><span data-stu-id="20c88-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="20c88-189">El uso de otros operadores bit a bit distinto `|||` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="20c88-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="20c88-190">Enteros en otras bases</span><span class="sxs-lookup"><span data-stu-id="20c88-190">Integers in other bases</span></span>

<span data-ttu-id="20c88-191">También pueden especificarse en notación hexadecimal, octal o binario utilizando enteros de 32 bits con signo un `0x`, `0o` o `0b` prefijo respectivamente.</span><span class="sxs-lookup"><span data-stu-id="20c88-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="20c88-192">Caracteres de subrayado en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="20c88-192">Underscores in numeric literals</span></span>

<span data-ttu-id="20c88-193">Puede separar los dígitos con el carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="20c88-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="20c88-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="20c88-194">See also</span></span>

- [<span data-ttu-id="20c88-195">Clase Core.LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="20c88-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
