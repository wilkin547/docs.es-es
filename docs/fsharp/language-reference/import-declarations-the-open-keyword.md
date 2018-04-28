---
title: 'Declaraciones de importación: la palabra clave open (F#)'
description: 'Obtenga información sobre las declaraciones de importación de F # y cómo especifican un módulo o espacio de nombres cuyos elementos puede hacer referencia sin usar un nombre completo.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: ddbc1086e2adbe8dae408f4d39fd5af888d7fd5e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="9550a-103">Declaraciones de importación: La `open` (palabra clave)</span><span class="sxs-lookup"><span data-stu-id="9550a-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
<span data-ttu-id="9550a-104">Los vínculos de la referencia de API de este artículo le llevarán a MSDN.</span><span class="sxs-lookup"><span data-stu-id="9550a-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="9550a-105">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="9550a-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="9550a-106">Un *Importar declaración* especifica un módulo o espacio de nombres cuyos elementos puede hacer referencia sin usar un nombre completo.</span><span class="sxs-lookup"><span data-stu-id="9550a-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>


## <a name="syntax"></a><span data-ttu-id="9550a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9550a-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="9550a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9550a-108">Remarks</span></span>
<span data-ttu-id="9550a-109">Hacer referencia al código mediante el uso de la ruta de acceso de espacio de nombres o módulo completo cada vez puede crear código que es difícil de escribir, leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="9550a-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="9550a-110">En su lugar, puede usar el `open` palabra clave para los módulos y espacios de nombres para que cuando se hace referencia a un miembro de ese módulo o espacio de nombres, puede utilizar la forma abreviada del nombre en lugar del nombre completo se usen con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="9550a-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="9550a-111">Esta palabra clave es similar a la `using` palabra clave en C#, `using namespace` en Visual C++, y `Imports` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9550a-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="9550a-112">El módulo o espacio de nombres proporcionado debe ser en el mismo proyecto o en un proyecto de referencia o un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9550a-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="9550a-113">Si no es así, puede agregar una referencia al proyecto, o usar el `-reference` comando`-`opción de línea (o su abreviatura, `-r`).</span><span class="sxs-lookup"><span data-stu-id="9550a-113">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="9550a-114">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9550a-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="9550a-115">La declaración de importación hace que los nombres disponibles en el código que sigue a la declaración, hasta el final del espacio de nombres, módulo o archivo envolvente.</span><span class="sxs-lookup"><span data-stu-id="9550a-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="9550a-116">Cuando se utilizan varias declaraciones de importación, deben aparecer en líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="9550a-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="9550a-117">El código siguiente muestra el uso de la `open` palabra clave para simplificar el código.</span><span class="sxs-lookup"><span data-stu-id="9550a-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="9550a-118">El compilador de F # no emite un error o una advertencia cuando las ambigüedades se producen cuando se produce el mismo nombre en más de un espacio de nombres o módulo abierta.</span><span class="sxs-lookup"><span data-stu-id="9550a-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="9550a-119">Cuando se producen las ambigüedades, F # da preferencia al módulo o espacio de nombres abiertos más recientemente.</span><span class="sxs-lookup"><span data-stu-id="9550a-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="9550a-120">Por ejemplo, en el código siguiente, `empty` significa `Seq.empty`, aunque `empty` se encuentra tanto en el `List` y `Seq` módulos.</span><span class="sxs-lookup"><span data-stu-id="9550a-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="9550a-121">Por lo tanto, tenga cuidado al abrir módulos o espacios de nombres como `List` o `Seq` que contienen miembros que tienen nombres idénticos; en su lugar, considere el uso de los nombres completos.</span><span class="sxs-lookup"><span data-stu-id="9550a-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="9550a-122">Debe evitar cualquier situación en la que el código es dependa del orden de las declaraciones de importación.</span><span class="sxs-lookup"><span data-stu-id="9550a-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>


## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="9550a-123">Espacios de nombres que estén abiertos de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="9550a-123">Namespaces That Are Open by Default</span></span>
<span data-ttu-id="9550a-124">Algunos espacios de nombres se utilizan con tanta frecuencia en que se abren implícitamente sin la necesidad de una declaración de importación explícita del código de F #.</span><span class="sxs-lookup"><span data-stu-id="9550a-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="9550a-125">En la tabla siguiente muestra los espacios de nombres que se abre de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9550a-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="9550a-126">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="9550a-126">Namespace</span></span>|<span data-ttu-id="9550a-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="9550a-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="9550a-128">Contiene básicas definiciones de tipo F # para los tipos integrados como `int` y `float`.</span><span class="sxs-lookup"><span data-stu-id="9550a-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="9550a-129">Contiene operaciones aritméticas básicas como `+` y `*`.</span><span class="sxs-lookup"><span data-stu-id="9550a-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="9550a-130">Contiene clases de colección inmutables como `List` y `Array`.</span><span class="sxs-lookup"><span data-stu-id="9550a-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="9550a-131">Contiene tipos para estructuras de control como la evaluación diferida y los flujos de trabajo asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="9550a-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="9550a-132">Contiene funciones de E/S con formato, como el `printf` función.</span><span class="sxs-lookup"><span data-stu-id="9550a-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="9550a-133">AutoOpen (atributo)</span><span class="sxs-lookup"><span data-stu-id="9550a-133">AutoOpen Attribute</span></span>
<span data-ttu-id="9550a-134">Puede aplicar el `AutoOpen` atributo a un ensamblado si desea abrir automáticamente un espacio de nombres o módulo cuando se hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9550a-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="9550a-135">También puede aplicar el `AutoOpen` atributo a un módulo de ese módulo se abra automáticamente al abre el módulo primario o el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="9550a-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="9550a-136">Para obtener más información, consulte [Core.AutoOpenAttribute clase](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="9550a-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>


## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="9550a-137">RequireQualifiedAccess (atributo)</span><span class="sxs-lookup"><span data-stu-id="9550a-137">RequireQualifiedAccess Attribute</span></span>
<span data-ttu-id="9550a-138">Algunos módulos, registros o tipos de unión pueden especificar el `RequireQualifiedAccess` atributo.</span><span class="sxs-lookup"><span data-stu-id="9550a-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="9550a-139">Cuando se hace referencia a elementos de esos módulos, registros o uniones, debe usar un nombre completo sin tener en cuenta si incluye una declaración de importación.</span><span class="sxs-lookup"><span data-stu-id="9550a-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="9550a-140">Si usa este atributo de forma estratégica en tipos que definen normalmente los nombres utilizan, para ayudar a evitar conflictos de nombres y, por tanto, asegúrese de código más resistente a los cambios en las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="9550a-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="9550a-141">Para obtener más información, consulte [Core.RequireQualifiedAccessAttribute clase](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="9550a-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>


## <a name="see-also"></a><span data-ttu-id="9550a-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="9550a-142">See Also</span></span>
[<span data-ttu-id="9550a-143"># Referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="9550a-143"># Language Reference</span></span>](index.md)

[<span data-ttu-id="9550a-144">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="9550a-144">Namespaces</span></span>](namespaces.md)

[<span data-ttu-id="9550a-145">Módulos</span><span class="sxs-lookup"><span data-stu-id="9550a-145">Modules</span></span>](modules.md)

