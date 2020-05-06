---
title: Módulos
description: 'Obtenga información sobre cómo un módulo de F # es una agrupación de código de F #, como valores, tipos y valores de función, en un programa de F #.'
ms.date: 04/24/2017
ms.openlocfilehash: 5f99bbd8069478bf0c7db2800ae545f31926728a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794369"
---
# <a name="modules"></a><span data-ttu-id="56a9d-103">Módulos</span><span class="sxs-lookup"><span data-stu-id="56a9d-103">Modules</span></span>

<span data-ttu-id="56a9d-104">En el contexto del lenguaje F #, un *módulo* es una agrupación de código de f #, como valores, tipos y valores de función, en un programa de f #.</span><span class="sxs-lookup"><span data-stu-id="56a9d-104">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="56a9d-105">Agrupar el código en módulos ayuda a mantener junto el código relacionado y a evitar conflictos de nombres en los programas.</span><span class="sxs-lookup"><span data-stu-id="56a9d-105">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="56a9d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56a9d-106">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="56a9d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56a9d-107">Remarks</span></span>

<span data-ttu-id="56a9d-108">Un módulo de F # es una agrupación de construcciones de código de F #, como tipos, valores, valores de función y `do` código en enlaces.</span><span class="sxs-lookup"><span data-stu-id="56a9d-108">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="56a9d-109">Se implementa como una clase de Common Language Runtime (CLR) que solo tiene miembros estáticos.</span><span class="sxs-lookup"><span data-stu-id="56a9d-109">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="56a9d-110">Hay dos tipos de declaraciones de módulo, dependiendo de si el archivo completo está incluido en el módulo: una declaración de módulo de nivel superior y una declaración de módulo local.</span><span class="sxs-lookup"><span data-stu-id="56a9d-110">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="56a9d-111">Una declaración de módulo de nivel superior incluye el archivo completo en el módulo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-111">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="56a9d-112">Una declaración de módulo de nivel superior solo puede aparecer como la primera declaración de un archivo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-112">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="56a9d-113">En la sintaxis de la declaración de módulo de nivel superior, el *espacio* de nombres completo opcional es la secuencia de nombres de espacios de nombres anidados que contiene el módulo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-113">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="56a9d-114">El espacio de nombres completo no tiene que declararse previamente.</span><span class="sxs-lookup"><span data-stu-id="56a9d-114">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="56a9d-115">No es necesario aplicar sangría a las declaraciones en un módulo de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="56a9d-115">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="56a9d-116">Tiene que aplicar sangría a todas las declaraciones en los módulos locales.</span><span class="sxs-lookup"><span data-stu-id="56a9d-116">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="56a9d-117">En una declaración de módulo local, solo las declaraciones a las que se aplica la sangría en la declaración de módulo forman parte del módulo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-117">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="56a9d-118">Si un archivo de código no comienza con una declaración de módulo de nivel superior o una declaración de espacio de nombres, todo el contenido del archivo, incluidos los módulos locales, pasa a formar parte de un módulo de nivel superior creado implícitamente que tiene el mismo nombre que el archivo, sin la extensión, con la primera letra convertida en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="56a9d-118">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="56a9d-119">Por ejemplo, considere el siguiente archivo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-119">For example, consider the following file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="56a9d-120">Este archivo se compilaría como si estuviera escrito de esta manera:</span><span class="sxs-lookup"><span data-stu-id="56a9d-120">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="56a9d-121">Si tiene varios módulos en un archivo, debe usar una declaración de módulo local para cada módulo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-121">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="56a9d-122">Si se declara un espacio de nombres envolvente, estos módulos forman parte del espacio de nombres envolvente.</span><span class="sxs-lookup"><span data-stu-id="56a9d-122">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="56a9d-123">Si no se declara un espacio de nombres envolvente, los módulos forman parte del módulo de nivel superior creado implícitamente.</span><span class="sxs-lookup"><span data-stu-id="56a9d-123">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="56a9d-124">En el ejemplo de código siguiente se muestra un archivo de código que contiene varios módulos.</span><span class="sxs-lookup"><span data-stu-id="56a9d-124">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="56a9d-125">El compilador crea implícitamente un módulo de nivel `Multiplemodules`superior denominado `MyModule1` y `MyModule2` y se anidan en ese módulo de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="56a9d-125">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="56a9d-126">Si tiene varios archivos en un proyecto o en una única compilación, o si está compilando una biblioteca, debe incluir una declaración de espacio de nombres o una declaración de módulo en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-126">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="56a9d-127">El compilador de F # solo determina implícitamente un nombre de módulo cuando solo hay un archivo en un proyecto o una línea de comandos de compilación, y se crea una aplicación.</span><span class="sxs-lookup"><span data-stu-id="56a9d-127">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="56a9d-128">El *modificador Accessibility* puede ser uno de los siguientes: `public`, `private`,. `internal`</span><span class="sxs-lookup"><span data-stu-id="56a9d-128">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="56a9d-129">Para obtener más información, consulta [Access Control](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="56a9d-129">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="56a9d-130">El valor predeterminado es public.</span><span class="sxs-lookup"><span data-stu-id="56a9d-130">The default is public.</span></span>

## <a name="referencing-code-in-modules"></a><span data-ttu-id="56a9d-131">Referencia al código en módulos</span><span class="sxs-lookup"><span data-stu-id="56a9d-131">Referencing Code in Modules</span></span>

<span data-ttu-id="56a9d-132">Al hacer referencia a funciones, tipos y valores de otro módulo, debe usar un nombre completo o abrir el módulo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-132">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="56a9d-133">Si usa un nombre completo, debe especificar los espacios de nombres, el módulo y el identificador del elemento de programa que desee.</span><span class="sxs-lookup"><span data-stu-id="56a9d-133">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="56a9d-134">Cada parte de la ruta de acceso calificada se separa con un punto (.), como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="56a9d-134">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="56a9d-135">Puede abrir el módulo o uno o varios de los espacios de nombres para simplificar el código.</span><span class="sxs-lookup"><span data-stu-id="56a9d-135">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="56a9d-136">Para obtener más información sobre cómo abrir espacios de nombres y módulos, vea [Import declarations: `open` The keyword](import-declarations-the-open-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="56a9d-136">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="56a9d-137">En el ejemplo de código siguiente se muestra un módulo de nivel superior que contiene todo el código hasta el final del archivo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-137">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="56a9d-138">Para usar este código desde otro archivo en el mismo proyecto, use nombres completos o abra el módulo antes de usar las funciones, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="56a9d-138">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="56a9d-139">Módulos anidados</span><span class="sxs-lookup"><span data-stu-id="56a9d-139">Nested Modules</span></span>

<span data-ttu-id="56a9d-140">Los módulos se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="56a9d-140">Modules can be nested.</span></span> <span data-ttu-id="56a9d-141">Se debe aplicar sangría a los módulos internos en lo que se refiere a las declaraciones de módulos externos para indicar que son módulos internos, no módulos nuevos.</span><span class="sxs-lookup"><span data-stu-id="56a9d-141">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="56a9d-142">Por ejemplo, compare los dos ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="56a9d-142">For example, compare the following two examples.</span></span> <span data-ttu-id="56a9d-143">Module `Z` es un módulo interno en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="56a9d-143">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="56a9d-144">Pero el `Z` módulo es un elemento relacionado `Y` con el módulo en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="56a9d-144">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="56a9d-145">El `Z` módulo también es un módulo relacionado en el código siguiente, ya que no tiene ninguna sangría en lo que se refiere a otras `Y`declaraciones del módulo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-145">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="56a9d-146">Por último, si el módulo externo no tiene ninguna declaración y va seguido inmediatamente de otra declaración de módulo, se supone que la nueva declaración de módulo es un módulo interno, pero el compilador le advierte si la segunda definición de módulo no tiene una sangría más alejada que la primera.</span><span class="sxs-lookup"><span data-stu-id="56a9d-146">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="56a9d-147">Para eliminar la advertencia, aplique una sangría al módulo interno.</span><span class="sxs-lookup"><span data-stu-id="56a9d-147">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="56a9d-148">Si desea que todo el código de un archivo esté en un módulo externo único y desea que los módulos internos, el módulo externo no requiera el signo igual y no se tenga que aplicar sangría a las declaraciones, incluidas las declaraciones de módulo internas, que Irán en el módulo externo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-148">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="56a9d-149">Es necesario aplicar sangría a las declaraciones dentro de las declaraciones del módulo interno.</span><span class="sxs-lookup"><span data-stu-id="56a9d-149">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="56a9d-150">En el código siguiente se muestra este caso.</span><span class="sxs-lookup"><span data-stu-id="56a9d-150">The following code shows this case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="56a9d-151">Módulos recursivos</span><span class="sxs-lookup"><span data-stu-id="56a9d-151">Recursive modules</span></span>

<span data-ttu-id="56a9d-152">F # 4,1 presenta el concepto de módulos que permiten que todo el código contenido sea recursivo.</span><span class="sxs-lookup"><span data-stu-id="56a9d-152">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="56a9d-153">Esto se hace a `module rec`través de.</span><span class="sxs-lookup"><span data-stu-id="56a9d-153">This is done via `module rec`.</span></span>  <span data-ttu-id="56a9d-154">El uso `module rec` de puede aliviar algunos problemas al no poder escribir código referencial mutuamente entre tipos y módulos.</span><span class="sxs-lookup"><span data-stu-id="56a9d-154">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="56a9d-155">El siguiente es un ejemplo de esto:</span><span class="sxs-lookup"><span data-stu-id="56a9d-155">The following is an example of this:</span></span>

```fsharp
module rec RecursiveModule =
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

<span data-ttu-id="56a9d-156">Tenga en cuenta que `DontSqueezeTheBananaException` la excepción y `Banana` la clase hacen referencia entre sí.</span><span class="sxs-lookup"><span data-stu-id="56a9d-156">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="56a9d-157">Además, el módulo `BananaHelpers` y la clase `Banana` también hacen referencia entre sí.</span><span class="sxs-lookup"><span data-stu-id="56a9d-157">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="56a9d-158">Esto no sería posible si se hubiera quitado la `rec` palabra clave del `RecursiveModule` módulo en F #.</span><span class="sxs-lookup"><span data-stu-id="56a9d-158">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="56a9d-159">Esta capacidad también es posible en los [espacios de nombres](namespaces.md) con F # 4,1.</span><span class="sxs-lookup"><span data-stu-id="56a9d-159">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="56a9d-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="56a9d-160">See also</span></span>

- [<span data-ttu-id="56a9d-161">Referencia del lenguaje F #</span><span class="sxs-lookup"><span data-stu-id="56a9d-161">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="56a9d-162">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="56a9d-162">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="56a9d-163">F # RFC FS-1009: permite tipos y módulos mutuamente referenciables en ámbitos mayores en archivos</span><span class="sxs-lookup"><span data-stu-id="56a9d-163">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
