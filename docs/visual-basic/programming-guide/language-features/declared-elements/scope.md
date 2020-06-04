---
title: Ámbito
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 1bee904996257474b7457b2aefb1f17d250933cb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410739"
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="19581-102">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19581-102">Scope in Visual Basic</span></span>

<span data-ttu-id="19581-103">El *ámbito* de un elemento declarado es el conjunto de todo el código que puede hacer referencia a él sin calificar su nombre o ponerlo a disposición a través de una [instrucción Imports (espacio de nombres de .net y tipo)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="19581-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="19581-104">Un elemento puede tener el ámbito en uno de los siguientes niveles:</span><span class="sxs-lookup"><span data-stu-id="19581-104">An element can have scope at one of the following levels:</span></span>

|<span data-ttu-id="19581-105">Nivel</span><span class="sxs-lookup"><span data-stu-id="19581-105">Level</span></span>|<span data-ttu-id="19581-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="19581-106">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="19581-107">Ámbito de bloque</span><span class="sxs-lookup"><span data-stu-id="19581-107">Block scope</span></span>|<span data-ttu-id="19581-108">Solo está disponible en el bloque de código en el que se declara</span><span class="sxs-lookup"><span data-stu-id="19581-108">Available only within the code block in which it is declared</span></span>|
|<span data-ttu-id="19581-109">Ámbito del procedimiento</span><span class="sxs-lookup"><span data-stu-id="19581-109">Procedure scope</span></span>|<span data-ttu-id="19581-110">Disponible para todo el código del procedimiento en el que se declara</span><span class="sxs-lookup"><span data-stu-id="19581-110">Available to all code within the procedure in which it is declared</span></span>|
|<span data-ttu-id="19581-111">Ámbito del módulo</span><span class="sxs-lookup"><span data-stu-id="19581-111">Module scope</span></span>|<span data-ttu-id="19581-112">Disponible para todo el código del módulo, la clase o la estructura en la que se declara</span><span class="sxs-lookup"><span data-stu-id="19581-112">Available to all code within the module, class, or structure in which it is declared</span></span>|
|<span data-ttu-id="19581-113">Ámbito de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="19581-113">Namespace scope</span></span>|<span data-ttu-id="19581-114">Disponible para todo el código del espacio de nombres en el que se declara</span><span class="sxs-lookup"><span data-stu-id="19581-114">Available to all code in the namespace in which it is declared</span></span>|

<span data-ttu-id="19581-115">Estos niveles de progreso del ámbito van desde el más estrecho (bloque) hasta el más ancho (espacio de nombres), donde el *ámbito más estrecho* significa el conjunto más pequeño de código que puede hacer referencia al elemento sin calificación.</span><span class="sxs-lookup"><span data-stu-id="19581-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="19581-116">Para obtener más información, vea "niveles de ámbito" en esta página.</span><span class="sxs-lookup"><span data-stu-id="19581-116">For more information, see "Levels of Scope" on this page.</span></span>

## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="19581-117">Especificar el ámbito y definir variables</span><span class="sxs-lookup"><span data-stu-id="19581-117">Specifying Scope and Defining Variables</span></span>

<span data-ttu-id="19581-118">El ámbito de un elemento se especifica cuando se declara.</span><span class="sxs-lookup"><span data-stu-id="19581-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="19581-119">El ámbito puede depender de los siguientes factores:</span><span class="sxs-lookup"><span data-stu-id="19581-119">The scope can depend on the following factors:</span></span>

- <span data-ttu-id="19581-120">Región (bloque, procedimiento, módulo, clase o estructura) en la que se declara el elemento.</span><span class="sxs-lookup"><span data-stu-id="19581-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>

- <span data-ttu-id="19581-121">Espacio de nombres que contiene la declaración del elemento.</span><span class="sxs-lookup"><span data-stu-id="19581-121">The namespace containing the element's declaration</span></span>

- <span data-ttu-id="19581-122">Nivel de acceso que se declara para el elemento.</span><span class="sxs-lookup"><span data-stu-id="19581-122">The access level you declare for the element</span></span>

<span data-ttu-id="19581-123">Tenga cuidado al definir variables con el mismo nombre pero con un ámbito diferente, ya que esto puede provocar resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="19581-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="19581-124">Para obtener más información, consulta [References to Declared Elements](references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="19581-124">For more information, see [References to Declared Elements](references-to-declared-elements.md).</span></span>

## <a name="levels-of-scope"></a><span data-ttu-id="19581-125">Niveles de ámbito</span><span class="sxs-lookup"><span data-stu-id="19581-125">Levels of Scope</span></span>

<span data-ttu-id="19581-126">Un elemento de programación está disponible en toda la región en la que se declara.</span><span class="sxs-lookup"><span data-stu-id="19581-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="19581-127">Todo el código de la misma región puede hacer referencia al elemento sin calificar su nombre.</span><span class="sxs-lookup"><span data-stu-id="19581-127">All code in the same region can refer to the element without qualifying its name.</span></span>

### <a name="block-scope"></a><span data-ttu-id="19581-128">Ámbito de bloque</span><span class="sxs-lookup"><span data-stu-id="19581-128">Block Scope</span></span>

<span data-ttu-id="19581-129">Un bloque es un conjunto de instrucciones incluidas en las instrucciones de declaración de inicio y finalización, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="19581-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>

- <span data-ttu-id="19581-130">`Do` y `Loop`</span><span class="sxs-lookup"><span data-stu-id="19581-130">`Do` and `Loop`</span></span>

- <span data-ttu-id="19581-131">`For`[ `Each` ] y`Next`</span><span class="sxs-lookup"><span data-stu-id="19581-131">`For` [`Each`] and `Next`</span></span>

- <span data-ttu-id="19581-132">`If` y `End If`</span><span class="sxs-lookup"><span data-stu-id="19581-132">`If` and `End If`</span></span>

- <span data-ttu-id="19581-133">`Select` y `End Select`</span><span class="sxs-lookup"><span data-stu-id="19581-133">`Select` and `End Select`</span></span>

- <span data-ttu-id="19581-134">`SyncLock` y `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="19581-134">`SyncLock` and `End SyncLock`</span></span>

- <span data-ttu-id="19581-135">`Try` y `End Try`</span><span class="sxs-lookup"><span data-stu-id="19581-135">`Try` and `End Try`</span></span>

- <span data-ttu-id="19581-136">`While` y `End While`</span><span class="sxs-lookup"><span data-stu-id="19581-136">`While` and `End While`</span></span>

- <span data-ttu-id="19581-137">`With` y `End With`</span><span class="sxs-lookup"><span data-stu-id="19581-137">`With` and `End With`</span></span>

<span data-ttu-id="19581-138">Si declara una variable dentro de un bloque, solo podrá usarla dentro de ese bloque.</span><span class="sxs-lookup"><span data-stu-id="19581-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="19581-139">En el ejemplo siguiente, el ámbito de la variable de entero `cube` es el bloque entre `If` y `End If` , y ya no se puede hacer referencia a `cube` cuando la ejecución pasa fuera del bloque.</span><span class="sxs-lookup"><span data-stu-id="19581-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>

```vb
If n < 1291 Then
    Dim cube As Integer
    cube = n ^ 3
End If
```

> [!NOTE]
> <span data-ttu-id="19581-140">Incluso si el ámbito de una variable está limitado a un bloque, su duración sigue siendo la del procedimiento completo.</span><span class="sxs-lookup"><span data-stu-id="19581-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="19581-141">Si especifica el bloque más de una vez durante el procedimiento, cada variable de bloque conserva su valor anterior.</span><span class="sxs-lookup"><span data-stu-id="19581-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="19581-142">Para evitar resultados inesperados en este caso, es aconsejable inicializar las variables de bloque al principio del bloque.</span><span class="sxs-lookup"><span data-stu-id="19581-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>

### <a name="procedure-scope"></a><span data-ttu-id="19581-143">Ámbito del procedimiento</span><span class="sxs-lookup"><span data-stu-id="19581-143">Procedure Scope</span></span>

<span data-ttu-id="19581-144">Un elemento declarado dentro de un procedimiento no está disponible fuera de ese procedimiento.</span><span class="sxs-lookup"><span data-stu-id="19581-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="19581-145">Solo el procedimiento que contiene la declaración puede utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="19581-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="19581-146">Las variables de este nivel también se conocen como *variables locales*.</span><span class="sxs-lookup"><span data-stu-id="19581-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="19581-147">Se declaran con la [instrucción Dim](../../../language-reference/statements/dim-statement.md), con o sin la palabra clave [static](../../../language-reference/modifiers/static.md) .</span><span class="sxs-lookup"><span data-stu-id="19581-147">You declare them with the [Dim Statement](../../../language-reference/statements/dim-statement.md), with or without the [Static](../../../language-reference/modifiers/static.md) keyword.</span></span>

<span data-ttu-id="19581-148">El procedimiento y el ámbito de bloque están estrechamente relacionados.</span><span class="sxs-lookup"><span data-stu-id="19581-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="19581-149">Si declara una variable dentro de un procedimiento pero fuera de un bloque dentro de ese procedimiento, puede considerar que la variable tiene ámbito de bloque, donde el bloque es el procedimiento completo.</span><span class="sxs-lookup"><span data-stu-id="19581-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="19581-150">Todos los elementos locales, incluso si son `Static` variables, son privados para el procedimiento en el que aparecen.</span><span class="sxs-lookup"><span data-stu-id="19581-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="19581-151">No se puede declarar ningún elemento mediante la palabra clave [Public](../../../language-reference/modifiers/public.md) dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="19581-151">You cannot declare any element using the [Public](../../../language-reference/modifiers/public.md) keyword within a procedure.</span></span>

### <a name="module-scope"></a><span data-ttu-id="19581-152">Ámbito del módulo</span><span class="sxs-lookup"><span data-stu-id="19581-152">Module Scope</span></span>

<span data-ttu-id="19581-153">Para mayor comodidad, el *nivel de módulo* de un solo término se aplica igualmente a los módulos, las clases y las estructuras.</span><span class="sxs-lookup"><span data-stu-id="19581-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="19581-154">Puede declarar elementos en este nivel colocando la instrucción de declaración fuera de cualquier procedimiento o bloque, pero dentro del módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="19581-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>

<span data-ttu-id="19581-155">Al crear una declaración en el nivel de módulo, el nivel de acceso que elija determina el ámbito.</span><span class="sxs-lookup"><span data-stu-id="19581-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="19581-156">El espacio de nombres que contiene el módulo, la clase o la estructura también afecta al ámbito.</span><span class="sxs-lookup"><span data-stu-id="19581-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>

<span data-ttu-id="19581-157">Los elementos para los que declara el nivel de acceso [privado](../../../language-reference/modifiers/private.md) están disponibles para todos los procedimientos de ese módulo, pero no para cualquier código de otro módulo.</span><span class="sxs-lookup"><span data-stu-id="19581-157">Elements for which you declare [Private](../../../language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="19581-158">La `Dim` instrucción en el nivel de módulo tiene como valor predeterminado `Private` si no se usa ninguna palabra clave de nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="19581-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="19581-159">Sin embargo, puede hacer que el ámbito y el nivel de acceso sean más obvios mediante el uso de la `Private` palabra clave en la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="19581-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>

<span data-ttu-id="19581-160">En el ejemplo siguiente, todos los procedimientos definidos en el módulo pueden hacer referencia a la variable de cadena `strMsg` .</span><span class="sxs-lookup"><span data-stu-id="19581-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="19581-161">Cuando se llama al segundo procedimiento, se muestra el contenido de la variable de cadena `strMsg` en un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="19581-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>

```vb
' Put the following declaration at module level (not in any procedure).
Private strMsg As String
' Put the following Sub procedure in the same module.
Sub initializePrivateVariable()
    strMsg = "This variable cannot be used outside this module."
End Sub
' Put the following Sub procedure in the same module.
Sub usePrivateVariable()
    MsgBox(strMsg)
End Sub
```

### <a name="namespace-scope"></a><span data-ttu-id="19581-162">Ámbito de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="19581-162">Namespace Scope</span></span>

<span data-ttu-id="19581-163">Si declara un elemento en el nivel de módulo mediante la palabra clave [Friend](../../../language-reference/modifiers/friend.md) o [Public](../../../language-reference/modifiers/public.md) , estará disponible para todos los procedimientos en todo el espacio de nombres en el que se declara el elemento.</span><span class="sxs-lookup"><span data-stu-id="19581-163">If you declare an element at module level using the [Friend](../../../language-reference/modifiers/friend.md) or [Public](../../../language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="19581-164">Con la siguiente modificación en el ejemplo anterior, el código puede hacer referencia a la variable de cadena `strMsg` en cualquier lugar del espacio de nombres de su declaración.</span><span class="sxs-lookup"><span data-stu-id="19581-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>

```vb
' Include this declaration at module level (not inside any procedure).
Public strMsg As String
```

<span data-ttu-id="19581-165">El ámbito de espacio de nombres incluye espacios de nombres anidados.</span><span class="sxs-lookup"><span data-stu-id="19581-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="19581-166">Un elemento disponible desde dentro de un espacio de nombres también está disponible en cualquier espacio de nombres anidado dentro de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="19581-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>

<span data-ttu-id="19581-167">Si el proyecto no contiene ninguna [instrucción de espacio de nombres](../../../language-reference/statements/namespace-statement.md), todo el proyecto se encuentra en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="19581-167">If your project does not contain any [Namespace Statement](../../../language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="19581-168">En este caso, el ámbito del espacio de nombres se puede considerar como ámbito del proyecto.</span><span class="sxs-lookup"><span data-stu-id="19581-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="19581-169">`Public`los elementos de un módulo, clase o estructura también están disponibles para cualquier proyecto que haga referencia a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="19581-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>

## <a name="choice-of-scope"></a><span data-ttu-id="19581-170">Elección del ámbito</span><span class="sxs-lookup"><span data-stu-id="19581-170">Choice of Scope</span></span>

<span data-ttu-id="19581-171">Al declarar una variable, debe tener en cuenta los siguientes puntos al elegir su ámbito.</span><span class="sxs-lookup"><span data-stu-id="19581-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>

### <a name="advantages-of-local-variables"></a><span data-ttu-id="19581-172">Ventajas de las variables locales</span><span class="sxs-lookup"><span data-stu-id="19581-172">Advantages of Local Variables</span></span>

<span data-ttu-id="19581-173">Las variables locales son una buena opción para cualquier tipo de cálculo temporal, por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="19581-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>

- <span data-ttu-id="19581-174">**Prevención de conflictos de nombres.**</span><span class="sxs-lookup"><span data-stu-id="19581-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="19581-175">Los nombres de las variables locales no son susceptibles de conflictos.</span><span class="sxs-lookup"><span data-stu-id="19581-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="19581-176">Por ejemplo, puede crear varios procedimientos diferentes que contengan una variable denominada `intTemp` .</span><span class="sxs-lookup"><span data-stu-id="19581-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="19581-177">Siempre y cuando cada uno `intTemp` de ellos se declare como una variable local, cada procedimiento solo reconoce su propia versión de `intTemp` .</span><span class="sxs-lookup"><span data-stu-id="19581-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="19581-178">Cualquier procedimiento puede modificar el valor en su local `intTemp` sin afectar a `intTemp` las variables de otros procedimientos.</span><span class="sxs-lookup"><span data-stu-id="19581-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>

- <span data-ttu-id="19581-179">**Consumo de memoria.**</span><span class="sxs-lookup"><span data-stu-id="19581-179">**Memory Consumption.**</span></span> <span data-ttu-id="19581-180">Las variables locales consumen memoria solo mientras su procedimiento se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="19581-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="19581-181">La memoria se libera cuando el procedimiento vuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="19581-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="19581-182">Por el contrario, las variables [compartidas](../../../language-reference/modifiers/shared.md) y [estáticas](../../../language-reference/modifiers/static.md) consumen recursos de memoria hasta que la aplicación deja de ejecutarse, por lo que debe usarlas solo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="19581-182">By contrast, [Shared](../../../language-reference/modifiers/shared.md) and [Static](../../../language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="19581-183">*Las variables de instancia* consumen memoria mientras su instancia sigue existiendo, lo que hace que sean menos eficientes que las variables locales, pero que pueden ser más eficaces que `Shared` o `Static` variables.</span><span class="sxs-lookup"><span data-stu-id="19581-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>

### <a name="minimizing-scope"></a><span data-ttu-id="19581-184">Minimizar el ámbito</span><span class="sxs-lookup"><span data-stu-id="19581-184">Minimizing Scope</span></span>

<span data-ttu-id="19581-185">En general, al declarar cualquier variable o constante, es una buena práctica de programación conseguir que el ámbito sea lo más estrecho posible (el ámbito de bloque es el más estrecho).</span><span class="sxs-lookup"><span data-stu-id="19581-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="19581-186">Esto ayuda a conservar la memoria y minimiza las posibilidades de que el código hace referencia erróneamente a la variable equivocada.</span><span class="sxs-lookup"><span data-stu-id="19581-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="19581-187">Del mismo modo, debe declarar una variable para que sea [estática](../../../language-reference/modifiers/static.md) solo cuando sea necesario conservar su valor entre las llamadas a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="19581-187">Similarly, you should declare a variable to be [Static](../../../language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="19581-188">Consulte también</span><span class="sxs-lookup"><span data-stu-id="19581-188">See also</span></span>

- [<span data-ttu-id="19581-189">Características de los elementos declarados</span><span class="sxs-lookup"><span data-stu-id="19581-189">Declared Element Characteristics</span></span>](declared-element-characteristics.md)
- [<span data-ttu-id="19581-190">Procedimiento para controlar el ámbito de una variable</span><span class="sxs-lookup"><span data-stu-id="19581-190">How to: Control the Scope of a Variable</span></span>](how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="19581-191">Período de duración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19581-191">Lifetime in Visual Basic</span></span>](lifetime.md)
- [<span data-ttu-id="19581-192">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19581-192">Access levels in Visual Basic</span></span>](access-levels.md)
- [<span data-ttu-id="19581-193">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="19581-193">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="19581-194">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="19581-194">Variable Declaration</span></span>](../variables/variable-declaration.md)
