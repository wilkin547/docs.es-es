---
title: Espacios de nombres (F#)
description: Obtenga información sobre cómo un F# espacio de nombres permite organizar el código en las áreas de funcionalidad relacionada por lo que le permite asociar un nombre a una agrupación de elementos de programa.
ms.date: 12/08/2018
ms.openlocfilehash: ad5cca8947d09d8480bfa418b003c84546edc29b
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169039"
---
# <a name="namespaces"></a><span data-ttu-id="cf354-103">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="cf354-103">Namespaces</span></span>

<span data-ttu-id="cf354-104">Un espacio de nombres permite organizar el código en áreas de funcionalidad relacionada por lo que le permite asociar un nombre a una agrupación de F# elementos del programa.</span><span class="sxs-lookup"><span data-stu-id="cf354-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="cf354-105">Espacios de nombres son elementos de nivel superior normalmente F# archivos.</span><span class="sxs-lookup"><span data-stu-id="cf354-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf354-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf354-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="cf354-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf354-107">Remarks</span></span>

<span data-ttu-id="cf354-108">Si desea colocar el código en un espacio de nombres, la primera declaración en el archivo debe declarar el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="cf354-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="cf354-109">El contenido del archivo completo, a continuación, pasan a formar parte del espacio de nombres, siempre no existe ninguna otra declaración de espacios de nombres más en el archivo.</span><span class="sxs-lookup"><span data-stu-id="cf354-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="cf354-110">Si es así, se considera todo el código hasta la siguiente declaración de espacio de nombres que se encuentra en el primer espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="cf354-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="cf354-111">Los espacios de nombres no pueden contener directamente los valores y funciones.</span><span class="sxs-lookup"><span data-stu-id="cf354-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="cf354-112">En su lugar, los valores y las funciones que deben incluirse en los módulos y los módulos se incluyen en los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="cf354-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="cf354-113">Los espacios de nombres pueden contener tipos de módulos.</span><span class="sxs-lookup"><span data-stu-id="cf354-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="cf354-114">Comentarios de documentación XML se pueden declarar por encima de un espacio de nombres, pero se ignoran.</span><span class="sxs-lookup"><span data-stu-id="cf354-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="cf354-115">También se pueden declarar directivas de compilador por encima de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="cf354-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="cf354-116">Los espacios de nombres se pueden declarar explícitamente con la palabra clave de espacio de nombres, o implícitamente cuando se declara un módulo.</span><span class="sxs-lookup"><span data-stu-id="cf354-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="cf354-117">Para declarar un espacio de nombres explícitamente, utilice la palabra clave de espacio de nombres seguida del nombre de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="cf354-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="cf354-118">El ejemplo siguiente muestra un archivo de código que declara un espacio de nombres `Widgets` con un tipo y un módulo incluido en ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="cf354-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="cf354-119">Si todo el contenido del archivo está en un módulo, también puede declarar espacios de nombres de forma implícita mediante el uso de la `module` palabra clave y proporcionando el nombre de espacio de nombres nuevo en el nombre completo del módulo.</span><span class="sxs-lookup"><span data-stu-id="cf354-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="cf354-120">El ejemplo siguiente muestra un archivo de código que declara un espacio de nombres `Widgets` y un módulo `WidgetsModule`, que contiene una función.</span><span class="sxs-lookup"><span data-stu-id="cf354-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="cf354-121">El código siguiente es equivalente al código anterior, pero el módulo es una declaración de módulo local.</span><span class="sxs-lookup"><span data-stu-id="cf354-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="cf354-122">En ese caso, el espacio de nombres debe aparecer en su propia línea.</span><span class="sxs-lookup"><span data-stu-id="cf354-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="cf354-123">Si se requiere más de un módulo en el mismo archivo en uno o varios espacios de nombres, debe usar las declaraciones de módulo local.</span><span class="sxs-lookup"><span data-stu-id="cf354-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="cf354-124">Cuando utiliza las declaraciones de módulo local, no puede usar el espacio de nombres completo en las declaraciones de módulo.</span><span class="sxs-lookup"><span data-stu-id="cf354-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="cf354-125">El código siguiente muestra un archivo que tiene una declaración de espacio de nombres y dos declaraciones de módulo local.</span><span class="sxs-lookup"><span data-stu-id="cf354-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="cf354-126">En este caso, los módulos se encuentran directamente en el espacio de nombres; No hay ningún módulo creado implícitamente que tiene el mismo nombre que el archivo.</span><span class="sxs-lookup"><span data-stu-id="cf354-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="cf354-127">Cualquier otro código en el archivo, como un `do` enlace, está en el espacio de nombres, pero no en los módulos internos, por lo que necesita calificar los miembros de módulo `widgetFunction` utilizando el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="cf354-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="cf354-128">La salida de este ejemplo es como sigue.</span><span class="sxs-lookup"><span data-stu-id="cf354-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="cf354-129">Para obtener más información, consulte [módulos](modules.md).</span><span class="sxs-lookup"><span data-stu-id="cf354-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="cf354-130">Espacios de nombres anidados</span><span class="sxs-lookup"><span data-stu-id="cf354-130">Nested Namespaces</span></span>

<span data-ttu-id="cf354-131">Cuando se crea un espacio de nombres anidado, debe calificar totalmente.</span><span class="sxs-lookup"><span data-stu-id="cf354-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="cf354-132">En caso contrario, cree un nuevo espacio de nombres de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="cf354-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="cf354-133">Sangría se omite en las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="cf354-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="cf354-134">El ejemplo siguiente muestra cómo declarar un espacio de nombres anidado.</span><span class="sxs-lookup"><span data-stu-id="cf354-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="cf354-135">Espacios de nombres de archivos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="cf354-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="cf354-136">Los espacios de nombres pueden abarcar varios archivos en un solo proyecto o de compilación.</span><span class="sxs-lookup"><span data-stu-id="cf354-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="cf354-137">El término *fragmento de espacio de nombres* describe la parte del espacio de nombres que se incluye en un archivo.</span><span class="sxs-lookup"><span data-stu-id="cf354-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="cf354-138">Los espacios de nombres también pueden abarcar varios ensamblados.</span><span class="sxs-lookup"><span data-stu-id="cf354-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="cf354-139">Por ejemplo, el `System` espacio de nombres incluye todo .NET Framework, que abarca muchos ensamblados y contiene muchos espacios de nombres anidados.</span><span class="sxs-lookup"><span data-stu-id="cf354-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="cf354-140">Namespace global</span><span class="sxs-lookup"><span data-stu-id="cf354-140">Global Namespace</span></span>

<span data-ttu-id="cf354-141">Usar el espacio de nombres predefinido `global` para colocar los nombres en el espacio de nombres de nivel superior. NET.</span><span class="sxs-lookup"><span data-stu-id="cf354-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="cf354-142">También puede usar global para hacer referencia el espacio de nombres .NET nivel superior, por ejemplo, para resolver conflictos de nombres con otros espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="cf354-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="cf354-143">Espacios de nombres recursivos</span><span class="sxs-lookup"><span data-stu-id="cf354-143">Recursive namespaces</span></span>

<span data-ttu-id="cf354-144">También se pueden declarar espacios de nombres como recursivo para permitir todo el código independiente para ser mutuamente recursivas.</span><span class="sxs-lookup"><span data-stu-id="cf354-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="cf354-145">Esto se realiza mediante `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="cf354-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="cf354-146">El uso de `namespace rec` puede aliviar algunas dificultades no se pueda escribir código mutuamente referencial entre los tipos y módulos.</span><span class="sxs-lookup"><span data-stu-id="cf354-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="cf354-147">Este es un ejemplo de esto:</span><span class="sxs-lookup"><span data-stu-id="cf354-147">The following is an example of this:</span></span>

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

<span data-ttu-id="cf354-148">Tenga en cuenta que la excepción `DontSqueezeTheBananaException` y la clase `Banana` ambos hacen referencia entre sí.</span><span class="sxs-lookup"><span data-stu-id="cf354-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="cf354-149">Además, el módulo `BananaHelpers` y la clase `Banana` también hacen referencia entre sí.</span><span class="sxs-lookup"><span data-stu-id="cf354-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="cf354-150">Esto no sería posible expresar en F# si ha quitado el `rec` palabra clave de la `MutualReferences` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="cf354-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="cf354-151">Esta característica también está disponible para su nivel superior [módulos](modules.md).</span><span class="sxs-lookup"><span data-stu-id="cf354-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf354-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf354-152">See also</span></span>

- [<span data-ttu-id="cf354-153">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="cf354-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="cf354-154">Módulos</span><span class="sxs-lookup"><span data-stu-id="cf354-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="cf354-155">F#RFC FS-1009 - permitir tipos mutuamente referenciales y módulos sobre ámbitos más amplios dentro de archivos</span><span class="sxs-lookup"><span data-stu-id="cf354-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
