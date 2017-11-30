---
title: Sintaxis detallada (F#)
description: "Obtenga información acerca de la diferencia entre la sintaxis ligera y detallado en el lenguaje de programación de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0a6792b3-b312-4453-a025-21d9760eee5d
ms.openlocfilehash: 2cef359a879897825733a3186be97b38896f5953
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="verbose-syntax"></a><span data-ttu-id="57437-104">Sintaxis detallada</span><span class="sxs-lookup"><span data-stu-id="57437-104">Verbose Syntax</span></span>

<span data-ttu-id="57437-105">Hay dos formas de sintaxis disponibles para muchas construcciones del lenguaje F #: *sintaxis detallada* y *sintaxis ligera*.</span><span class="sxs-lookup"><span data-stu-id="57437-105">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="57437-106">La sintaxis detallada no se utiliza normalmente, pero tiene la ventaja de ser menos sensible a la sangría.</span><span class="sxs-lookup"><span data-stu-id="57437-106">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="57437-107">La sintaxis ligera es más corta y utiliza la sangría para señalar el principio y final de las construcciones, en lugar de como palabras clave adicionales `begin`, `end`, `in`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="57437-107">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="57437-108">La sintaxis predeterminada es la sintaxis ligera.</span><span class="sxs-lookup"><span data-stu-id="57437-108">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="57437-109">Este tema describe la sintaxis para las construcciones de F # cuando no está habilitada la sintaxis ligera.</span><span class="sxs-lookup"><span data-stu-id="57437-109">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="57437-110">Sintaxis detallada siempre está habilitada, de modo que aunque se habilite la sintaxis ligera, todavía puede utilizar la sintaxis detallada para algunas construcciones.</span><span class="sxs-lookup"><span data-stu-id="57437-110">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="57437-111">Sintaxis ligera se pueden deshabilitar mediante la `#light "off"` directiva.</span><span class="sxs-lookup"><span data-stu-id="57437-111">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>


## <a name="table-of-constructs"></a><span data-ttu-id="57437-112">Tabla de construcciones.</span><span class="sxs-lookup"><span data-stu-id="57437-112">Table of Constructs</span></span>
<span data-ttu-id="57437-113">En la tabla siguiente muestra la sintaxis ligera y detallada para construcciones del lenguaje F # en contextos donde hay una diferencia entre las dos formas.</span><span class="sxs-lookup"><span data-stu-id="57437-113">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="57437-114">En esta tabla, están entre corchetes angulares (&lt;&gt;) encerrar los elementos de sintaxis proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="57437-114">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="57437-115">Consulte la documentación de cada construcción de lenguaje para obtener más información acerca de la sintaxis utilizada dentro de estas construcciones.</span><span class="sxs-lookup"><span data-stu-id="57437-115">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>



<table>
<tr>
<th><span data-ttu-id="57437-116">Construcción de lenguaje</span><span class="sxs-lookup"><span data-stu-id="57437-116">Language construct</span></span></th>
<th><span data-ttu-id="57437-117">Sintaxis ligera</span><span class="sxs-lookup"><span data-stu-id="57437-117">Lightweight syntax</span></span></th>
<th><span data-ttu-id="57437-118">Sintaxis detallada</span><span class="sxs-lookup"><span data-stu-id="57437-118">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="57437-119">expresiones compuestas</span><span class="sxs-lookup"><span data-stu-id="57437-119">compound expressions</span></span>
</td>
<td>

```xml
<expression1>
<expression2>
```
</td><td>

```
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>


<span data-ttu-id="57437-120">anidada `let` enlaces</span><span class="sxs-lookup"><span data-stu-id="57437-120">nested `let` bindings</span></span>

</td><td>
```
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
<span data-ttu-id="57437-121">bloque de código</span><span class="sxs-lookup"><span data-stu-id="57437-121">code block</span></span>
</td><td>

```
(
    <expression1>
    <expression2>
)
```

</td><td>

```
begin
    <expression1>;
    <expression2>;
end
```
</td>
</tr>
<tr><td>
`for...do`
</td><td>

```
for counter = start to finish do
    ...
```

</td><td>

```
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```
while <condition> do
    ...
```

</td><td>

```
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```
for var in start .. finish do
    ...
```

</td><td>

```
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```
do
    ...
```

</td><td>

```
do
    ...
in
```

</td>
</tr>
<tr><td><span data-ttu-id="57437-122">record</span><span class="sxs-lookup"><span data-stu-id="57437-122">record</span></span>
</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="57437-123">clase</span><span class="sxs-lookup"><span data-stu-id="57437-123">class</span></span>
</td><td><span data-ttu-id="57437-124">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="57437-124">
```
type <class-name>(<params>) = ... ```

</span></span></td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td><span data-ttu-id="57437-125">estructura</span><span class="sxs-lookup"><span data-stu-id="57437-125">structure</span></span></td><td>

```
[<StructAttribute>]
type <structure-name> =
    ...
```
</td><td>

```
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="57437-126">unión discriminada</span><span class="sxs-lookup"><span data-stu-id="57437-126">discriminated union</span></span></td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```
</td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end    
```

</td>
</tr>
<tr><td><span data-ttu-id="57437-127">interfaz</span><span class="sxs-lookup"><span data-stu-id="57437-127">interface</span></span></td><td>

```
type <interface-name> =
    ...
```
</td><td>

```
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="57437-128">expresión de objeto</span><span class="sxs-lookup"><span data-stu-id="57437-128">object expression</span></span></td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td><span data-ttu-id="57437-129">implementación de interfaces</span><span class="sxs-lookup"><span data-stu-id="57437-129">interface implementation</span></span></td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="57437-130">extensión de tipo</span><span class="sxs-lookup"><span data-stu-id="57437-130">type extension</span></span></td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="57437-131">module</span><span class="sxs-lookup"><span data-stu-id="57437-131">module</span></span></td><td>

```
module <module-name> =
    ...
```

</td><td>

```
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>



## <a name="see-also"></a><span data-ttu-id="57437-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="57437-132">See Also</span></span>
[<span data-ttu-id="57437-133">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="57437-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="57437-134">Directivas de compilador</span><span class="sxs-lookup"><span data-stu-id="57437-134">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="57437-135">Instrucciones de formato de código</span><span class="sxs-lookup"><span data-stu-id="57437-135">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
