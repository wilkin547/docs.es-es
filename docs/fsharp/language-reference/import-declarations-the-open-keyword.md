---
title: 'Declaraciones de importación: palabra clave open'
description: 'Obtenga información sobre las declaraciones de importación de F # y cómo especifican un módulo o un espacio de nombres a cuyos elementos puede hacer referencia sin usar un nombre completo.'
ms.date: 08/15/2020
ms.openlocfilehash: 6420df071f86159c44606c2710331d5f587023cc
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557612"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="42671-103">Declaraciones de importación: `open` palabra clave</span><span class="sxs-lookup"><span data-stu-id="42671-103">Import declarations: The `open` keyword</span></span>

<span data-ttu-id="42671-104">Una *declaración de importación* especifica un módulo o un espacio de nombres a cuyos elementos se puede hacer referencia sin usar un nombre completo.</span><span class="sxs-lookup"><span data-stu-id="42671-104">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="42671-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42671-105">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="42671-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="42671-106">Remarks</span></span>

<span data-ttu-id="42671-107">La referencia al código mediante el espacio de nombres completo o la ruta de acceso del módulo cada vez puede crear código que es difícil de escribir, leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="42671-107">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="42671-108">En su lugar, puede usar la `open` palabra clave para los módulos y espacios de nombres que se usan con frecuencia, de modo que cuando se haga referencia a un miembro de ese módulo o espacio de nombres, se pueda usar la forma abreviada del nombre en lugar del nombre completo.</span><span class="sxs-lookup"><span data-stu-id="42671-108">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="42671-109">Esta palabra clave es similar a la `using` palabra clave en C#, `using namespace` en Visual C++ y `Imports` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="42671-109">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="42671-110">El módulo o espacio de nombres proporcionado debe estar en el mismo proyecto o en un proyecto o ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="42671-110">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="42671-111">Si no es así, puede Agregar una referencia al proyecto o usar la `-reference` opción de línea de comandos (o su abreviatura `-r` ).</span><span class="sxs-lookup"><span data-stu-id="42671-111">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="42671-112">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="42671-112">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="42671-113">La declaración de importación hace que los nombres estén disponibles en el código que sigue a la declaración, hasta el final del espacio de nombres, módulo o archivo envolvente.</span><span class="sxs-lookup"><span data-stu-id="42671-113">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="42671-114">Cuando se usan varias declaraciones de importación, deben aparecer en líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="42671-114">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="42671-115">En el código siguiente se muestra el uso de la `open` palabra clave para simplificar el código.</span><span class="sxs-lookup"><span data-stu-id="42671-115">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="42671-116">El compilador de F # no emite un error o advertencia cuando se producen ambigüedades cuando se produce el mismo nombre en más de un módulo o espacio de nombres abierto.</span><span class="sxs-lookup"><span data-stu-id="42671-116">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="42671-117">Cuando se producen ambigüedades, F # da preferencia al módulo o espacio de nombres abierto más recientemente.</span><span class="sxs-lookup"><span data-stu-id="42671-117">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="42671-118">Por ejemplo, en el código siguiente, `empty` significa `Seq.empty` que, aunque `empty` se encuentre en los `List` módulos y `Seq` .</span><span class="sxs-lookup"><span data-stu-id="42671-118">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="42671-119">Por lo tanto, tenga cuidado al abrir módulos o espacios de nombres como `List` o `Seq` que contengan miembros que tengan nombres idénticos; en su lugar, considere la posibilidad de usar los nombres completos.</span><span class="sxs-lookup"><span data-stu-id="42671-119">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="42671-120">Debe evitar cualquier situación en la que el código dependa del orden de las declaraciones de importación.</span><span class="sxs-lookup"><span data-stu-id="42671-120">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="42671-121">Espacios de nombres que están abiertos de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="42671-121">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="42671-122">Algunos espacios de nombres se usan con frecuencia en código de F # y se abren de forma implícita sin necesidad de una declaración de importación explícita.</span><span class="sxs-lookup"><span data-stu-id="42671-122">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="42671-123">En la tabla siguiente se muestran los espacios de nombres que están abiertos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="42671-123">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="42671-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="42671-124">Namespace</span></span>|<span data-ttu-id="42671-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="42671-125">Description</span></span>|
|---------|-----------|
|`FSharp.Core`|<span data-ttu-id="42671-126">Contiene definiciones de tipos de F # básicas para tipos integrados como `int` y `float` .</span><span class="sxs-lookup"><span data-stu-id="42671-126">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`FSharp.Core.Operators`|<span data-ttu-id="42671-127">Contiene operaciones aritméticas básicas como `+` y `*` .</span><span class="sxs-lookup"><span data-stu-id="42671-127">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`FSharp.Collections`|<span data-ttu-id="42671-128">Contiene clases de colección inmutables como `List` y `Array` .</span><span class="sxs-lookup"><span data-stu-id="42671-128">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`FSharp.Control`|<span data-ttu-id="42671-129">Contiene los tipos para las construcciones de control, como la evaluación diferida y los flujos de trabajo asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="42671-129">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`FSharp.Text`|<span data-ttu-id="42671-130">Contiene funciones para la e/s con formato, como la `printf` función.</span><span class="sxs-lookup"><span data-stu-id="42671-130">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="42671-131">Atributo AutoOpen</span><span class="sxs-lookup"><span data-stu-id="42671-131">AutoOpen Attribute</span></span>

<span data-ttu-id="42671-132">Puede aplicar el `AutoOpen` atributo a un ensamblado si desea abrir automáticamente un espacio de nombres o módulo cuando se hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="42671-132">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="42671-133">También puede aplicar el `AutoOpen` atributo a un módulo para abrir automáticamente ese módulo cuando se abre el espacio de nombres o el módulo primario.</span><span class="sxs-lookup"><span data-stu-id="42671-133">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="42671-134">Para obtener más información, vea [autoopenattribute (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-autoopenattribute.html).</span><span class="sxs-lookup"><span data-stu-id="42671-134">For more information, see [AutoOpenAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-autoopenattribute.html).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="42671-135">Atributo RequireQualifiedAccess</span><span class="sxs-lookup"><span data-stu-id="42671-135">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="42671-136">Algunos módulos, registros o tipos de Unión pueden especificar el `RequireQualifiedAccess` atributo.</span><span class="sxs-lookup"><span data-stu-id="42671-136">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="42671-137">Cuando se hace referencia a elementos de dichos módulos, registros o uniones, se debe usar un nombre completo independientemente de si se incluye una declaración de importación.</span><span class="sxs-lookup"><span data-stu-id="42671-137">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="42671-138">Si usa este atributo de forma estratégica en los tipos que definen nombres usados comúnmente, ayuda a evitar colisiones de nombres y, por tanto, hace que el código sea más resistente a los cambios en las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="42671-138">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="42671-139">Para obtener más información, vea [requirequalifiedaccessattribute (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html).</span><span class="sxs-lookup"><span data-stu-id="42671-139">For more information, see [RequireQualifiedAccessAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="42671-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="42671-140">See also</span></span>

- [<span data-ttu-id="42671-141">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="42671-141">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="42671-142">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="42671-142">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="42671-143">Módulos</span><span class="sxs-lookup"><span data-stu-id="42671-143">Modules</span></span>](modules.md)
