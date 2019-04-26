---
title: Literales
description: Obtenga información sobre los tipos literales en la F# lenguaje de programación.
ms.date: 02/08/2019
ms.openlocfilehash: 28ce34dee3c3c3d4d0cfd4107e8cbc375a23032c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904571"
---
# <a name="literals"></a><span data-ttu-id="e7970-103">Literales</span><span class="sxs-lookup"><span data-stu-id="e7970-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="e7970-104">Los vínculos de referencia de API en este artículo le llevará a MSDN (por ahora).</span><span class="sxs-lookup"><span data-stu-id="e7970-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="e7970-105">Este tema proporciona una tabla que se muestra cómo especificar el tipo de un literal en F#.</span><span class="sxs-lookup"><span data-stu-id="e7970-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="e7970-106">Tipos literales</span><span class="sxs-lookup"><span data-stu-id="e7970-106">Literal Types</span></span>

<span data-ttu-id="e7970-107">La siguiente tabla muestra los tipos literales en F#.</span><span class="sxs-lookup"><span data-stu-id="e7970-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="e7970-108">Caracteres que representan dígitos en notación hexadecimal no distinguen mayúsculas de minúsculas; caracteres que identifican el tipo distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e7970-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="e7970-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="e7970-109">Type</span></span>|<span data-ttu-id="e7970-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7970-110">Description</span></span>|<span data-ttu-id="e7970-111">Prefijo o sufijo</span><span class="sxs-lookup"><span data-stu-id="e7970-111">Suffix or prefix</span></span>|<span data-ttu-id="e7970-112">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e7970-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="e7970-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="e7970-113">sbyte</span></span>|<span data-ttu-id="e7970-114">entero de 8 bits con signo</span><span class="sxs-lookup"><span data-stu-id="e7970-114">signed 8-bit integer</span></span>|<span data-ttu-id="e7970-115">y</span><span class="sxs-lookup"><span data-stu-id="e7970-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="e7970-116">byte</span><span class="sxs-lookup"><span data-stu-id="e7970-116">byte</span></span>|<span data-ttu-id="e7970-117">número natural de 8 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="e7970-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="e7970-118">UY</span><span class="sxs-lookup"><span data-stu-id="e7970-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="e7970-119">int16</span><span class="sxs-lookup"><span data-stu-id="e7970-119">int16</span></span>|<span data-ttu-id="e7970-120">entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="e7970-120">signed 16-bit integer</span></span>|<span data-ttu-id="e7970-121">s</span><span class="sxs-lookup"><span data-stu-id="e7970-121">s</span></span>|`86s`|
|<span data-ttu-id="e7970-122">uint16</span><span class="sxs-lookup"><span data-stu-id="e7970-122">uint16</span></span>|<span data-ttu-id="e7970-123">número natural de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="e7970-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="e7970-124">us</span><span class="sxs-lookup"><span data-stu-id="e7970-124">us</span></span>|`86us`|
|<span data-ttu-id="e7970-125">int</span><span class="sxs-lookup"><span data-stu-id="e7970-125">int</span></span><br /><br /><span data-ttu-id="e7970-126">int32</span><span class="sxs-lookup"><span data-stu-id="e7970-126">int32</span></span>|<span data-ttu-id="e7970-127">entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="e7970-127">signed 32-bit integer</span></span>|<span data-ttu-id="e7970-128">l o none</span><span class="sxs-lookup"><span data-stu-id="e7970-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="e7970-129">uint</span><span class="sxs-lookup"><span data-stu-id="e7970-129">uint</span></span><br /><br /><span data-ttu-id="e7970-130">uint32</span><span class="sxs-lookup"><span data-stu-id="e7970-130">uint32</span></span>|<span data-ttu-id="e7970-131">número natural de 32 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="e7970-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="e7970-132">u o ul</span><span class="sxs-lookup"><span data-stu-id="e7970-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="e7970-133">unativeint.</span><span class="sxs-lookup"><span data-stu-id="e7970-133">unativeint</span></span>|<span data-ttu-id="e7970-134">puntero nativo como un número natural sin signo</span><span class="sxs-lookup"><span data-stu-id="e7970-134">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="e7970-135">anular</span><span class="sxs-lookup"><span data-stu-id="e7970-135">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="e7970-136">int64</span><span class="sxs-lookup"><span data-stu-id="e7970-136">int64</span></span>|<span data-ttu-id="e7970-137">entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="e7970-137">signed 64-bit integer</span></span>|<span data-ttu-id="e7970-138">L</span><span class="sxs-lookup"><span data-stu-id="e7970-138">L</span></span>|`86L`|
|<span data-ttu-id="e7970-139">uint64</span><span class="sxs-lookup"><span data-stu-id="e7970-139">uint64</span></span>|<span data-ttu-id="e7970-140">número natural de 64 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="e7970-140">unsigned 64-bit natural number</span></span>|<span data-ttu-id="e7970-141">UL</span><span class="sxs-lookup"><span data-stu-id="e7970-141">UL</span></span>|`86UL`|
|<span data-ttu-id="e7970-142">float32 único,</span><span class="sxs-lookup"><span data-stu-id="e7970-142">single, float32</span></span>|<span data-ttu-id="e7970-143">número de punto flotante de 32 bits</span><span class="sxs-lookup"><span data-stu-id="e7970-143">32-bit floating point number</span></span>|<span data-ttu-id="e7970-144">F o f</span><span class="sxs-lookup"><span data-stu-id="e7970-144">F or f</span></span>|<span data-ttu-id="e7970-145">`4.14F` o `4.14f`</span><span class="sxs-lookup"><span data-stu-id="e7970-145">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="e7970-146">lf</span><span class="sxs-lookup"><span data-stu-id="e7970-146">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="e7970-147">float; Double</span><span class="sxs-lookup"><span data-stu-id="e7970-147">float; double</span></span>|<span data-ttu-id="e7970-148">número de punto flotante de 64 bits</span><span class="sxs-lookup"><span data-stu-id="e7970-148">64-bit floating point number</span></span>|<span data-ttu-id="e7970-149">ninguna</span><span class="sxs-lookup"><span data-stu-id="e7970-149">none</span></span>|<span data-ttu-id="e7970-150">`4.14` o `2.3E+32` o `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="e7970-150">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="e7970-151">LF</span><span class="sxs-lookup"><span data-stu-id="e7970-151">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="e7970-152">bigint</span><span class="sxs-lookup"><span data-stu-id="e7970-152">bigint</span></span>|<span data-ttu-id="e7970-153">entero no limitado a la representación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="e7970-153">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="e7970-154">I</span><span class="sxs-lookup"><span data-stu-id="e7970-154">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="e7970-155">decimal</span><span class="sxs-lookup"><span data-stu-id="e7970-155">decimal</span></span>|<span data-ttu-id="e7970-156">número fraccionario representado como un punto fijo o un número racional</span><span class="sxs-lookup"><span data-stu-id="e7970-156">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="e7970-157">M o m</span><span class="sxs-lookup"><span data-stu-id="e7970-157">M or m</span></span>|<span data-ttu-id="e7970-158">`0.7833M` o `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="e7970-158">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="e7970-159">Char</span><span class="sxs-lookup"><span data-stu-id="e7970-159">Char</span></span>|<span data-ttu-id="e7970-160">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="e7970-160">Unicode character</span></span>|<span data-ttu-id="e7970-161">ninguna</span><span class="sxs-lookup"><span data-stu-id="e7970-161">none</span></span>|`'a'`|
|<span data-ttu-id="e7970-162">String</span><span class="sxs-lookup"><span data-stu-id="e7970-162">String</span></span>|<span data-ttu-id="e7970-163">Cadena de Unicode</span><span class="sxs-lookup"><span data-stu-id="e7970-163">Unicode string</span></span>|<span data-ttu-id="e7970-164">ninguna</span><span class="sxs-lookup"><span data-stu-id="e7970-164">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="e7970-165">o</span><span class="sxs-lookup"><span data-stu-id="e7970-165">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="e7970-166">o</span><span class="sxs-lookup"><span data-stu-id="e7970-166">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="e7970-167">o</span><span class="sxs-lookup"><span data-stu-id="e7970-167">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="e7970-168">Vea también [cadenas](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="e7970-168">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="e7970-169">byte</span><span class="sxs-lookup"><span data-stu-id="e7970-169">byte</span></span>|<span data-ttu-id="e7970-170">Carácter ASCII</span><span class="sxs-lookup"><span data-stu-id="e7970-170">ASCII character</span></span>|<span data-ttu-id="e7970-171">B</span><span class="sxs-lookup"><span data-stu-id="e7970-171">B</span></span>|`'a'B`|
|<span data-ttu-id="e7970-172">byte[]</span><span class="sxs-lookup"><span data-stu-id="e7970-172">byte[]</span></span>|<span data-ttu-id="e7970-173">cadena ASCII</span><span class="sxs-lookup"><span data-stu-id="e7970-173">ASCII string</span></span>|<span data-ttu-id="e7970-174">B</span><span class="sxs-lookup"><span data-stu-id="e7970-174">B</span></span>|`"text"B`|
|<span data-ttu-id="e7970-175">String o byte]</span><span class="sxs-lookup"><span data-stu-id="e7970-175">String or byte[]</span></span>|<span data-ttu-id="e7970-176">literales de cadenas</span><span class="sxs-lookup"><span data-stu-id="e7970-176">verbatim string</span></span>|<span data-ttu-id="e7970-177">prefijo @</span><span class="sxs-lookup"><span data-stu-id="e7970-177">@ prefix</span></span>|<span data-ttu-id="e7970-178">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="e7970-178">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="e7970-179">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="e7970-179">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="e7970-180">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7970-180">Remarks</span></span>

<span data-ttu-id="e7970-181">Las cadenas Unicode pueden contener codificaciones explícitas que se pueden especificar mediante el uso de `\u` seguido por un código hexadecimal de 16 bits o codificaciones UTF-32 que se pueden especificar mediante el uso de `\U` seguido por un código hexadecimal de 32 bits que representa un Unicode par suplente.</span><span class="sxs-lookup"><span data-stu-id="e7970-181">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="e7970-182">Como de F# 3.1, puede usar el `+` iniciar sesión combinar literales de cadena.</span><span class="sxs-lookup"><span data-stu-id="e7970-182">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="e7970-183">También puede usar el bit a bit o (`|||`) operador para combinar las marcas de enumeración.</span><span class="sxs-lookup"><span data-stu-id="e7970-183">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="e7970-184">Por ejemplo, el código siguiente es legal en F# 3.1:</span><span class="sxs-lookup"><span data-stu-id="e7970-184">For example, the following code is legal in F# 3.1:</span></span>

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

<span data-ttu-id="e7970-185">No se permite el uso de otros operadores bit a bit.</span><span class="sxs-lookup"><span data-stu-id="e7970-185">The use of other bitwise operators isn't allowed.</span></span>

## <a name="named-literals"></a><span data-ttu-id="e7970-186">Literales con nombre</span><span class="sxs-lookup"><span data-stu-id="e7970-186">Named Literals</span></span>

<span data-ttu-id="e7970-187">Los valores que están diseñados para ser constantes se pueden marcar con el [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) atributo.</span><span class="sxs-lookup"><span data-stu-id="e7970-187">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="e7970-188">Este atributo tiene el efecto de la causa de un valor que se compile como una constante.</span><span class="sxs-lookup"><span data-stu-id="e7970-188">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="e7970-189">En las expresiones de coincidencia de patrón, los identificadores que comienzan con caracteres en minúscula se tratan siempre como variables para enlazar, en lugar de como literales, por lo tanto normalmente debe usar mayúsculas iniciales al definir los literales.</span><span class="sxs-lookup"><span data-stu-id="e7970-189">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="e7970-190">Enteros en otras Bases</span><span class="sxs-lookup"><span data-stu-id="e7970-190">Integers In Other Bases</span></span>

<span data-ttu-id="e7970-191">También pueden especificarse en notación hexadecimal, octal o binario utilizando enteros de 32 bits con signo un `0x`, `0o` o `0b` prefijo respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e7970-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="e7970-192">Caracteres de subrayado en literales numéricos</span><span class="sxs-lookup"><span data-stu-id="e7970-192">Underscores in Numeric Literals</span></span>

<span data-ttu-id="e7970-193">A partir de F# 4.1, puede separar los dígitos con el carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="e7970-193">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="e7970-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7970-194">See also</span></span>

- [<span data-ttu-id="e7970-195">Clase Core.LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="e7970-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
