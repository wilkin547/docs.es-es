---
title: Sintaxis detallada (F#)
description: 'Obtenga información acerca de la diferencia entre la sintaxis ligera y detallado en el lenguaje de programación de F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: fd040a66a789bc6717fd14e6a9f28274c9e3542b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="verbose-syntax"></a><span data-ttu-id="a4114-103">Sintaxis detallada</span><span class="sxs-lookup"><span data-stu-id="a4114-103">Verbose Syntax</span></span>

<span data-ttu-id="a4114-104">Hay dos formas de sintaxis disponibles para muchas construcciones del lenguaje F #: *sintaxis detallada* y *sintaxis ligera*.</span><span class="sxs-lookup"><span data-stu-id="a4114-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="a4114-105">La sintaxis detallada no se utiliza normalmente, pero tiene la ventaja de ser menos sensible a la sangría.</span><span class="sxs-lookup"><span data-stu-id="a4114-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="a4114-106">La sintaxis ligera es más corta y utiliza la sangría para señalar el principio y final de las construcciones, en lugar de como palabras clave adicionales `begin`, `end`, `in`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="a4114-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="a4114-107">La sintaxis predeterminada es la sintaxis ligera.</span><span class="sxs-lookup"><span data-stu-id="a4114-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="a4114-108">Este tema describe la sintaxis para las construcciones de F # cuando no está habilitada la sintaxis ligera.</span><span class="sxs-lookup"><span data-stu-id="a4114-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="a4114-109">Sintaxis detallada siempre está habilitada, de modo que aunque se habilite la sintaxis ligera, todavía puede utilizar la sintaxis detallada para algunas construcciones.</span><span class="sxs-lookup"><span data-stu-id="a4114-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="a4114-110">Sintaxis ligera se pueden deshabilitar mediante la `#light "off"` directiva.</span><span class="sxs-lookup"><span data-stu-id="a4114-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>


## <a name="table-of-constructs"></a><span data-ttu-id="a4114-111">Tabla de construcciones.</span><span class="sxs-lookup"><span data-stu-id="a4114-111">Table of Constructs</span></span>
<span data-ttu-id="a4114-112">En la tabla siguiente muestra la sintaxis ligera y detallada para construcciones del lenguaje F # en contextos donde hay una diferencia entre las dos formas.</span><span class="sxs-lookup"><span data-stu-id="a4114-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="a4114-113">En esta tabla, están entre corchetes angulares (&lt;&gt;) encerrar los elementos de sintaxis proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a4114-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="a4114-114">Consulte la documentación de cada construcción de lenguaje para obtener más información acerca de la sintaxis utilizada dentro de estas construcciones.</span><span class="sxs-lookup"><span data-stu-id="a4114-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>



<table>
<tr>
<th><span data-ttu-id="a4114-115">Construcción de lenguaje</span><span class="sxs-lookup"><span data-stu-id="a4114-115">Language construct</span></span></th>
<th><span data-ttu-id="a4114-116">Sintaxis ligera</span><span class="sxs-lookup"><span data-stu-id="a4114-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="a4114-117">Sintaxis detallada</span><span class="sxs-lookup"><span data-stu-id="a4114-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="a4114-118">expresiones compuestas</span><span class="sxs-lookup"><span data-stu-id="a4114-118">compound expressions</span></span>
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


<span data-ttu-id="a4114-119">anidada `let` enlaces</span><span class="sxs-lookup"><span data-stu-id="a4114-119">nested `let` bindings</span></span>

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
<span data-ttu-id="a4114-120">bloque de código</span><span class="sxs-lookup"><span data-stu-id="a4114-120">code block</span></span>
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
<tr><td><span data-ttu-id="a4114-121">record</span><span class="sxs-lookup"><span data-stu-id="a4114-121">record</span></span>
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
<tr><td><span data-ttu-id="a4114-122">clase</span><span class="sxs-lookup"><span data-stu-id="a4114-122">class</span></span>
</td><td><span data-ttu-id="a4114-123">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="a4114-123">
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
<tr><td><span data-ttu-id="a4114-124">estructura</span><span class="sxs-lookup"><span data-stu-id="a4114-124">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="a4114-125">unión discriminada</span><span class="sxs-lookup"><span data-stu-id="a4114-125">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="a4114-126">interfaz</span><span class="sxs-lookup"><span data-stu-id="a4114-126">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="a4114-127">expresión de objeto</span><span class="sxs-lookup"><span data-stu-id="a4114-127">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="a4114-128">implementación de interfaces</span><span class="sxs-lookup"><span data-stu-id="a4114-128">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="a4114-129">extensión de tipo</span><span class="sxs-lookup"><span data-stu-id="a4114-129">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="a4114-130">module</span><span class="sxs-lookup"><span data-stu-id="a4114-130">module</span></span></td><td>

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



## <a name="see-also"></a><span data-ttu-id="a4114-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4114-131">See Also</span></span>
[<span data-ttu-id="a4114-132">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="a4114-132">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="a4114-133">Directivas de compilador</span><span class="sxs-lookup"><span data-stu-id="a4114-133">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="a4114-134">Instrucciones de formato de código</span><span class="sxs-lookup"><span data-stu-id="a4114-134">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
