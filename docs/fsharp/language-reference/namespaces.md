---
title: Espacios de nombres
description: 'Obtenga información sobre cómo un espacio de nombres de F # le permite organizar el código en áreas de funcionalidad relacionada, permitiéndole adjuntar un nombre a una agrupación de elementos de programa.'
ms.date: 12/08/2018
ms.openlocfilehash: bf71843349434a1ea91c58dbc0477373dbb0c449
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796137"
---
# <a name="namespaces"></a><span data-ttu-id="3b1d8-103">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="3b1d8-103">Namespaces</span></span>

<span data-ttu-id="3b1d8-104">Un espacio de nombres permite organizar el código en áreas de funcionalidad relacionada, ya que permite adjuntar un nombre a una agrupación de elementos de programa de F #.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="3b1d8-105">Los espacios de nombres suelen ser elementos de nivel superior en archivos de F #.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="3b1d8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b1d8-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="3b1d8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b1d8-107">Remarks</span></span>

<span data-ttu-id="3b1d8-108">Si desea colocar el código en un espacio de nombres, la primera declaración del archivo debe declarar el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="3b1d8-109">El contenido de todo el archivo se convierte entonces en parte del espacio de nombres, siempre que no exista otra declaración de espacios de nombres en el archivo.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="3b1d8-110">En ese caso, todo el código hasta la siguiente declaración de espacio de nombres se considera que está dentro del primer espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="3b1d8-111">Los espacios de nombres no pueden contener directamente valores y funciones.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="3b1d8-112">En su lugar, los valores y las funciones deben estar incluidos en los módulos y los módulos se incluyen en los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="3b1d8-113">Los espacios de nombres pueden contener tipos, módulos.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="3b1d8-114">Los comentarios de documento XML se pueden declarar sobre un espacio de nombres, pero se omiten.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="3b1d8-115">Las directivas de compilador también se pueden declarar sobre un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="3b1d8-116">Los espacios de nombres se pueden declarar explícitamente con la palabra clave namespace o implícitamente al declarar un módulo.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="3b1d8-117">Para declarar explícitamente un espacio de nombres, use la palabra clave namespace seguida del nombre del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="3b1d8-118">En el ejemplo siguiente se muestra un archivo de código que declara `Widgets` un espacio de nombres con un tipo y un módulo incluido en dicho espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="3b1d8-119">Si todo el contenido del archivo está en un módulo, también puede declarar espacios de nombres implícitamente mediante la `module` palabra clave y proporcionando el nuevo nombre de espacio de nombres en el nombre completo del módulo.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="3b1d8-120">En el ejemplo siguiente se muestra un archivo de código que declara `Widgets` un espacio de `WidgetsModule`nombres y un módulo, que contiene una función.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="3b1d8-121">El código siguiente es equivalente al código anterior, pero el módulo es una declaración de módulo local.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="3b1d8-122">En ese caso, el espacio de nombres debe aparecer en su propia línea.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="3b1d8-123">Si se necesita más de un módulo en el mismo archivo en uno o varios espacios de nombres, debe usar las declaraciones del módulo local.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="3b1d8-124">Al utilizar las declaraciones del módulo local, no se puede usar el espacio de nombres completo en las declaraciones del módulo.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="3b1d8-125">En el código siguiente se muestra un archivo que tiene una declaración de espacio de nombres y dos declaraciones de módulos locales.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="3b1d8-126">En este caso, los módulos se incluyen directamente en el espacio de nombres; no hay ningún módulo creado implícitamente que tenga el mismo nombre que el archivo.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="3b1d8-127">Cualquier otro código del archivo, como un `do` enlace, está en el espacio de nombres pero no en los módulos internos, por lo que debe calificar el miembro `widgetFunction` del módulo mediante el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="3b1d8-128">La salida de este ejemplo es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="3b1d8-129">Para obtener más información, vea [módulos](modules.md).</span><span class="sxs-lookup"><span data-stu-id="3b1d8-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="3b1d8-130">Espacios de nombres anidados</span><span class="sxs-lookup"><span data-stu-id="3b1d8-130">Nested Namespaces</span></span>

<span data-ttu-id="3b1d8-131">Al crear un espacio de nombres anidado, debe calificarlo por completo.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="3b1d8-132">De lo contrario, se crea un nuevo espacio de nombres de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="3b1d8-133">La sangría se omite en las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="3b1d8-134">En el ejemplo siguiente se muestra cómo declarar un espacio de nombres anidado.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="3b1d8-135">Espacios de nombres en archivos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="3b1d8-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="3b1d8-136">Los espacios de nombres pueden abarcar varios archivos en un único proyecto o compilación.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="3b1d8-137">El término *espacio de nombres* de términos describe la parte de un espacio de nombres que se incluye en un archivo.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="3b1d8-138">Los espacios de nombres también pueden abarcar varios ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="3b1d8-139">Por ejemplo, el `System` espacio de nombres incluye todo el .NET Framework, que abarca muchos ensamblados y contiene muchos espacios de nombres anidados.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="3b1d8-140">Espacio de nombres global</span><span class="sxs-lookup"><span data-stu-id="3b1d8-140">Global Namespace</span></span>

<span data-ttu-id="3b1d8-141">El espacio de nombres `global` predefinido se usa para colocar nombres en el espacio de nombres de nivel superior de .net.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="3b1d8-142">También puede usar global para hacer referencia al espacio de nombres .NET de nivel superior, por ejemplo, para resolver conflictos de nombres con otros espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="3b1d8-143">Espacios de nombres recursivos</span><span class="sxs-lookup"><span data-stu-id="3b1d8-143">Recursive namespaces</span></span>

<span data-ttu-id="3b1d8-144">Los espacios de nombres también se pueden declarar como recursivos para permitir que todo el código contenido sea mutuamente recursivo.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="3b1d8-145">Esto se hace a `namespace rec`través de.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="3b1d8-146">El uso `namespace rec` de puede aliviar algunos problemas al no poder escribir código referencial mutuamente entre tipos y módulos.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="3b1d8-147">El siguiente es un ejemplo de esto:</span><span class="sxs-lookup"><span data-stu-id="3b1d8-147">The following is an example of this:</span></span>

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

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

<span data-ttu-id="3b1d8-148">Tenga en cuenta que `DontSqueezeTheBananaException` la excepción y `Banana` la clase hacen referencia entre sí.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="3b1d8-149">Además, el módulo `BananaHelpers` y la clase `Banana` también hacen referencia entre sí.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="3b1d8-150">No sería posible expresar en F # si se quita la `rec` palabra clave del `MutualReferences` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="3b1d8-151">Esta característica también está disponible para los [módulos](modules.md)de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="3b1d8-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3b1d8-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b1d8-152">See also</span></span>

- [<span data-ttu-id="3b1d8-153">Referencia del lenguaje F #</span><span class="sxs-lookup"><span data-stu-id="3b1d8-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="3b1d8-154">Módulos</span><span class="sxs-lookup"><span data-stu-id="3b1d8-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="3b1d8-155">F # RFC FS-1009: permite tipos y módulos mutuamente referenciables en ámbitos mayores en archivos</span><span class="sxs-lookup"><span data-stu-id="3b1d8-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
