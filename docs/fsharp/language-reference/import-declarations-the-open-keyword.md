---
title: 'Declaraciones de importación: palabra clave open'
description: Obtenga información sobre las declaraciones de importación de F y cómo especifican un módulo o espacio de nombres a cuyos elementos puede hacer referencia sin usar un nombre completo.
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021531"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="197db-103">Declaraciones de importación: la palabra clave `open`</span><span class="sxs-lookup"><span data-stu-id="197db-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="197db-104">Los vínculos de la referencia de API de este artículo le llevarán a MSDN.</span><span class="sxs-lookup"><span data-stu-id="197db-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="197db-105">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="197db-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="197db-106">Una declaración de *importación* especifica un módulo o espacio de nombres cuyos elementos se pueden hacer referencia sin usar un nombre completo.</span><span class="sxs-lookup"><span data-stu-id="197db-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="197db-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="197db-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="197db-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="197db-108">Remarks</span></span>

<span data-ttu-id="197db-109">Hacer referencia a código mediante el espacio de nombres completo o la ruta de acceso del módulo cada vez puede crear código que sea difícil de escribir, leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="197db-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="197db-110">En su lugar, `open` puede usar la palabra clave para módulos y espacios de nombres usados con frecuencia para que al hacer referencia a un miembro de ese módulo o espacio de nombres, pueda usar la forma abreviada del nombre en lugar del nombre completo.</span><span class="sxs-lookup"><span data-stu-id="197db-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="197db-111">Esta palabra clave `using` es similar a `using namespace` la palabra clave `Imports` en C- , en Visual C+ y en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="197db-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="197db-112">El módulo o espacio de nombres proporcionado debe estar en el mismo proyecto o en un proyecto o ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="197db-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="197db-113">Si no es así, puede agregar una referencia `-reference` al proyecto o utilizar la `-r`opción de línea de comandos (o su abreviatura).</span><span class="sxs-lookup"><span data-stu-id="197db-113">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="197db-114">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="197db-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="197db-115">La declaración de importación hace que los nombres estén disponibles en el código que sigue a la declaración, hasta el final del espacio de nombres, módulo o archivo envolvente.</span><span class="sxs-lookup"><span data-stu-id="197db-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="197db-116">Cuando se utilizan varias declaraciones de importación, deben aparecer en líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="197db-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="197db-117">El código siguiente muestra `open` el uso de la palabra clave para simplificar el código.</span><span class="sxs-lookup"><span data-stu-id="197db-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="197db-118">El compilador de F no emite un error o una advertencia cuando se producen ambiguedades cuando se produce el mismo nombre en más de un módulo abierto o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="197db-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="197db-119">Cuando se producen ambiguedades, F- da preferencia al módulo o espacio de nombres abierto más recientemente.</span><span class="sxs-lookup"><span data-stu-id="197db-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="197db-120">Por ejemplo, en el `empty` `Seq.empty`código siguiente, significa , aunque `empty` se encuentra en los `List` módulos y. `Seq`</span><span class="sxs-lookup"><span data-stu-id="197db-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="197db-121">Por lo tanto, tenga cuidado al `List` abrir `Seq` módulos o espacios de nombres como o que contienen miembros que tienen nombres idénticos; en su lugar, considere el uso de los nombres calificados.</span><span class="sxs-lookup"><span data-stu-id="197db-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="197db-122">Debe evitar cualquier situación en la que el código dependa del orden de las declaraciones de importación.</span><span class="sxs-lookup"><span data-stu-id="197db-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="197db-123">Espacios de nombres abiertos por defecto</span><span class="sxs-lookup"><span data-stu-id="197db-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="197db-124">Algunos espacios de nombres se usan con tanta frecuencia en el código de F que se abren implícitamente sin necesidad de una declaración de importación explícita.</span><span class="sxs-lookup"><span data-stu-id="197db-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="197db-125">En la tabla siguiente se muestran los espacios de nombres que están abiertos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="197db-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="197db-126">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="197db-126">Namespace</span></span>|<span data-ttu-id="197db-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="197db-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="197db-128">Contiene definiciones de tipos básicas de `int` F `float`para tipos integrados, como y .</span><span class="sxs-lookup"><span data-stu-id="197db-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="197db-129">Contiene operaciones aritméticas básicas como `+` y `*`.</span><span class="sxs-lookup"><span data-stu-id="197db-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="197db-130">Contiene clases de colección inmutables como `List` y `Array`.</span><span class="sxs-lookup"><span data-stu-id="197db-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="197db-131">Contiene tipos para construcciones de control como la evaluación diferida y flujos de trabajo asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="197db-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="197db-132">Contiene funciones para E/S `printf` con formato, como la función.</span><span class="sxs-lookup"><span data-stu-id="197db-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="197db-133">Atributo AutoOpen</span><span class="sxs-lookup"><span data-stu-id="197db-133">AutoOpen Attribute</span></span>

<span data-ttu-id="197db-134">Puede aplicar `AutoOpen` el atributo a un ensamblado si desea abrir automáticamente un espacio de nombres o módulo cuando se hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="197db-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="197db-135">También puede aplicar `AutoOpen` el atributo a un módulo para abrir automáticamente ese módulo cuando se abre el módulo primario o el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="197db-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="197db-136">Para obtener más información, vea [Core.AutoOpenAttribute (Clase)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="197db-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="197db-137">Atributo RequireQualifiedAccess</span><span class="sxs-lookup"><span data-stu-id="197db-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="197db-138">Algunos módulos, registros o `RequireQualifiedAccess` tipos de unión pueden especificar el atributo.</span><span class="sxs-lookup"><span data-stu-id="197db-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="197db-139">Al hacer referencia a elementos de esos módulos, registros o uniones, debe usar un nombre completo independientemente de si incluye una declaración de importación.</span><span class="sxs-lookup"><span data-stu-id="197db-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="197db-140">Si utiliza este atributo estratégicamente en tipos que definen nombres de uso común, ayuda a evitar colisiones de nombres y, por lo tanto, hace que el código sea más resistente a los cambios en las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="197db-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="197db-141">Para obtener más información, vea [Core.RequireQualifiedAccessAttribute (Clase)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="197db-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="197db-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="197db-142">See also</span></span>

- [<span data-ttu-id="197db-143">Referencia del lenguaje f</span><span class="sxs-lookup"><span data-stu-id="197db-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="197db-144">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="197db-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="197db-145">Módulos</span><span class="sxs-lookup"><span data-stu-id="197db-145">Modules</span></span>](modules.md)
