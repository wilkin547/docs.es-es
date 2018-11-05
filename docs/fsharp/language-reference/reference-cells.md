---
title: Celdas de referencia (F#)
description: Obtenga información sobre cómo las celdas de referencia de F# son ubicaciones de almacenamiento que le permiten crear valores mutables con semántica de referencia.
ms.date: 05/16/2016
ms.openlocfilehash: e2e1a91c62fd76e4992bc5ae11bb672766850718
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "44192279"
---
# <a name="reference-cells"></a><span data-ttu-id="299f9-103">Celdas de referencia</span><span class="sxs-lookup"><span data-stu-id="299f9-103">Reference Cells</span></span>

<span data-ttu-id="299f9-104">*Celdas de referencia* son ubicaciones de almacenamiento que le permiten crear valores mutables con semántica de referencia.</span><span class="sxs-lookup"><span data-stu-id="299f9-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="299f9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="299f9-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="299f9-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="299f9-106">Remarks</span></span>

<span data-ttu-id="299f9-107">Se utiliza el operador `ref` antes de un valor para crear una nueva celda de referencia que encapsula el valor.</span><span class="sxs-lookup"><span data-stu-id="299f9-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="299f9-108">A continuación, se puede cambiar el valor subyacente, porque es mutable.</span><span class="sxs-lookup"><span data-stu-id="299f9-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="299f9-109">Una celda de referencia contiene un valor real; no una mera dirección.</span><span class="sxs-lookup"><span data-stu-id="299f9-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="299f9-110">Al crear una celda de referencia mediante el operador `ref`, se crea una copia del valor subyacente como valor mutable encapsulado.</span><span class="sxs-lookup"><span data-stu-id="299f9-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="299f9-111">Se puede desreferenciar una celda de referencia mediante el operador `!` (bang).</span><span class="sxs-lookup"><span data-stu-id="299f9-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="299f9-112">En el ejemplo de código siguiente se muestran la declaración y el uso de celdas de referencia.</span><span class="sxs-lookup"><span data-stu-id="299f9-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="299f9-113">El resultado es `50`</span><span class="sxs-lookup"><span data-stu-id="299f9-113">The output is `50`.</span></span>

<span data-ttu-id="299f9-114">Las celdas de referencia son instancias del tipo de registro genérico `Ref`, que se declara como sigue.</span><span class="sxs-lookup"><span data-stu-id="299f9-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="299f9-115">El tipo `'a ref` es un sinónimo de `Ref<'a>`.</span><span class="sxs-lookup"><span data-stu-id="299f9-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="299f9-116">Tanto el compilador como IntelliSense en el IDE, muestran el primero para este tipo, pero la definición subyacente es el segundo.</span><span class="sxs-lookup"><span data-stu-id="299f9-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="299f9-117">El operador `ref` crea una nueva celda de referencia.</span><span class="sxs-lookup"><span data-stu-id="299f9-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="299f9-118">El código siguiente es la declaración del operador `ref`.</span><span class="sxs-lookup"><span data-stu-id="299f9-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="299f9-119">En la tabla siguiente se muestran las características que están disponibles en la celda de referencia.</span><span class="sxs-lookup"><span data-stu-id="299f9-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="299f9-120">Operador, miembro o campo</span><span class="sxs-lookup"><span data-stu-id="299f9-120">Operator, member, or field</span></span>|<span data-ttu-id="299f9-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="299f9-121">Description</span></span>|<span data-ttu-id="299f9-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="299f9-122">Type</span></span>|<span data-ttu-id="299f9-123">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="299f9-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="299f9-124">`!` (operador de desreferencia)</span><span class="sxs-lookup"><span data-stu-id="299f9-124">`!` (dereference operator)</span></span>|<span data-ttu-id="299f9-125">Devuelve el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="299f9-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="299f9-126">`:=` (operador de asignación)</span><span class="sxs-lookup"><span data-stu-id="299f9-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="299f9-127">Cambia el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="299f9-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="299f9-128">`ref` (operador)</span><span class="sxs-lookup"><span data-stu-id="299f9-128">`ref` (operator)</span></span>|<span data-ttu-id="299f9-129">Encapsula un valor en una nueva celda de referencia.</span><span class="sxs-lookup"><span data-stu-id="299f9-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="299f9-130">`Value` (propiedad)</span><span class="sxs-lookup"><span data-stu-id="299f9-130">`Value` (property)</span></span>|<span data-ttu-id="299f9-131">Obtiene o establece el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="299f9-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="299f9-132">`contents` (campo de registro)</span><span class="sxs-lookup"><span data-stu-id="299f9-132">`contents` (record field)</span></span>|<span data-ttu-id="299f9-133">Obtiene o establece el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="299f9-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|
<span data-ttu-id="299f9-134">Hay varias maneras de tener acceso al valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="299f9-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="299f9-135">El valor devuelto por el operador de desreferencia (`!`) no es un valor asignable.</span><span class="sxs-lookup"><span data-stu-id="299f9-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="299f9-136">Por consiguiente, si se va a modificar el valor subyacente, se debe utilizar el operador de asignación (`:=`) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="299f9-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="299f9-137">Tanto la propiedad `Value` como el campo `contents` son valores asignables.</span><span class="sxs-lookup"><span data-stu-id="299f9-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="299f9-138">Así pues, se pueden utilizar para obtener acceso al valor subyacente o cambiarlo, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="299f9-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="299f9-139">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="299f9-139">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="299f9-140">El campo `contents` se proporciona por motivos de compatibilidad con otras versiones de ML y generará una advertencia durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="299f9-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="299f9-141">Para deshabilitar la advertencia, utilice la opción `--mlcompatibility` del compilador.</span><span class="sxs-lookup"><span data-stu-id="299f9-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="299f9-142">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="299f9-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="299f9-143">Los programadores de C# deben saber que `ref` en C# no es lo mismo que `ref` en F#.</span><span class="sxs-lookup"><span data-stu-id="299f9-143">C# programmers should know that `ref` in C# is not the same thing as `ref` in F#.</span></span> <span data-ttu-id="299f9-144">Las construcciones de F# equivalente son [zkratka](byrefs.md), que son un concepto diferente de las celdas de referencia.</span><span class="sxs-lookup"><span data-stu-id="299f9-144">The equivalent constructs in F# are [byrefs](byrefs.md), which are a different concept from reference cells.</span></span>

<span data-ttu-id="299f9-145">Los valores marcan como `mutable`se pueden promover automáticamente a `'a ref` si captura una clausura; vea [valores](values/index.md).</span><span class="sxs-lookup"><span data-stu-id="299f9-145">Values marked as `mutable`may be automatically promoted to `'a ref` if captured by a closure; see [Values](values/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="299f9-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="299f9-146">See also</span></span>

- [<span data-ttu-id="299f9-147">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="299f9-147">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="299f9-148">Parámetros y argumentos</span><span class="sxs-lookup"><span data-stu-id="299f9-148">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="299f9-149">Referencia de símbolos y operadores</span><span class="sxs-lookup"><span data-stu-id="299f9-149">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
- [<span data-ttu-id="299f9-150">Valores</span><span class="sxs-lookup"><span data-stu-id="299f9-150">Values</span></span>](values/index.md)
