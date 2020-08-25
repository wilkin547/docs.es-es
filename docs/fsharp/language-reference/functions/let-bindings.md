---
title: Enlaces let
description: 'Obtenga información sobre cómo usar un enlace Let de F #, que asocia un identificador con un valor o una función.'
ms.date: 05/16/2016
ms.openlocfilehash: 6f2396f480c5e6c631d0022f4732419ee5b07db6
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812229"
---
# <a name="let-bindings"></a><span data-ttu-id="8d78b-103">Enlaces let</span><span class="sxs-lookup"><span data-stu-id="8d78b-103">let Bindings</span></span>

<span data-ttu-id="8d78b-104">Un *enlace* asocia un identificador con un valor o una función.</span><span class="sxs-lookup"><span data-stu-id="8d78b-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="8d78b-105">La `let` palabra clave se usa para enlazar un nombre a un valor o una función.</span><span class="sxs-lookup"><span data-stu-id="8d78b-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="8d78b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d78b-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="8d78b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d78b-107">Remarks</span></span>

<span data-ttu-id="8d78b-108">La `let` palabra clave se usa en expresiones de enlace para definir valores o valores de función para uno o más nombres.</span><span class="sxs-lookup"><span data-stu-id="8d78b-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="8d78b-109">La forma más sencilla de la `let` expresión enlaza un nombre a un valor simple, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="8d78b-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="8d78b-110">Si separa la expresión del identificador usando una nueva línea, debe aplicar sangría a cada línea de la expresión, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d78b-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="8d78b-111">En lugar de simplemente un nombre, se puede especificar un patrón que contenga nombres, por ejemplo, una tupla, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d78b-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="8d78b-112">El *cuerpo-expresión* es la expresión en la que se usan los nombres.</span><span class="sxs-lookup"><span data-stu-id="8d78b-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="8d78b-113">La expresión de cuerpo aparece en su propia línea, con la sangría que se alinea exactamente con el primer carácter de la `let` palabra clave:</span><span class="sxs-lookup"><span data-stu-id="8d78b-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="8d78b-114">Un `let` enlace puede aparecer en el nivel de módulo, en la definición de un tipo de clase o en ámbitos locales, como en una definición de función.</span><span class="sxs-lookup"><span data-stu-id="8d78b-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="8d78b-115">`let`No es necesario que un enlace en el nivel superior de un módulo o de un tipo de clase tenga una expresión de cuerpo, sino que en otros niveles de ámbito, se requiere la expresión del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8d78b-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="8d78b-116">Los nombres enlazados se pueden usar después del punto de definición, pero no en ningún momento antes de que `let` aparezca el enlace, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d78b-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="8d78b-117">Enlaces de función</span><span class="sxs-lookup"><span data-stu-id="8d78b-117">Function Bindings</span></span>

<span data-ttu-id="8d78b-118">Los enlaces de función siguen las reglas de los enlaces de valor, excepto que los enlaces de función incluyen el nombre de la función y los parámetros, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d78b-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="8d78b-119">En general, los parámetros son patrones, como un patrón de tupla:</span><span class="sxs-lookup"><span data-stu-id="8d78b-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="8d78b-120">Una `let` expresión de enlace se evalúa como el valor de la última expresión.</span><span class="sxs-lookup"><span data-stu-id="8d78b-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="8d78b-121">Por lo tanto, en el ejemplo de código siguiente, el valor de `result` se calcula a partir de `100 * function3 (1, 2)` , que se evalúa como `300` .</span><span class="sxs-lookup"><span data-stu-id="8d78b-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="8d78b-122">Para obtener más información, vea [Funciones](index.md).</span><span class="sxs-lookup"><span data-stu-id="8d78b-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="8d78b-123">Anotaciones de tipo</span><span class="sxs-lookup"><span data-stu-id="8d78b-123">Type Annotations</span></span>

<span data-ttu-id="8d78b-124">Puede especificar los tipos para los parámetros incluyendo dos puntos (:) seguido de un nombre de tipo, todo entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="8d78b-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="8d78b-125">También puede especificar el tipo del valor devuelto anexando los dos puntos y el tipo después del último parámetro.</span><span class="sxs-lookup"><span data-stu-id="8d78b-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="8d78b-126">Las anotaciones de tipo completo para `function1` , con enteros como tipos de parámetro, serían como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="8d78b-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="8d78b-127">Cuando no hay ningún parámetro de tipo explícito, se usa la inferencia de tipos para determinar los tipos de parámetros de las funciones.</span><span class="sxs-lookup"><span data-stu-id="8d78b-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="8d78b-128">Esto puede incluir la generalización automática del tipo de un parámetro para que sea genérico.</span><span class="sxs-lookup"><span data-stu-id="8d78b-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="8d78b-129">Para obtener más información, vea [generalización automática](../generics/automatic-generalization.md) e [inferencia de tipos](../type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="8d78b-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="8d78b-130">Enlaces let en clases</span><span class="sxs-lookup"><span data-stu-id="8d78b-130">let Bindings in Classes</span></span>

<span data-ttu-id="8d78b-131">Un `let` enlace puede aparecer en un tipo de clase, pero no en un tipo de estructura o de registro.</span><span class="sxs-lookup"><span data-stu-id="8d78b-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="8d78b-132">Para usar un enlace Let en un tipo de clase, la clase debe tener un constructor Primary.</span><span class="sxs-lookup"><span data-stu-id="8d78b-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="8d78b-133">Los parámetros de constructor deben aparecer después del nombre de tipo en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="8d78b-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="8d78b-134">Un `let` enlace en un tipo de clase define los campos privados y los miembros de ese tipo de clase y, junto con los `do` enlaces del tipo, crea el código para el constructor principal para el tipo.</span><span class="sxs-lookup"><span data-stu-id="8d78b-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="8d78b-135">En los siguientes ejemplos de código se muestra una clase `MyClass` con campos privados `field1` y `field2` .</span><span class="sxs-lookup"><span data-stu-id="8d78b-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="8d78b-136">Los ámbitos de `field1` y `field2` se limitan al tipo en el que se declaran.</span><span class="sxs-lookup"><span data-stu-id="8d78b-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="8d78b-137">Para obtener más información, vea [ `let` enlaces en clases](../members/let-bindings-in-classes.md) y [clases](../classes.md).</span><span class="sxs-lookup"><span data-stu-id="8d78b-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="8d78b-138">Parámetros de tipo en los enlaces Let</span><span class="sxs-lookup"><span data-stu-id="8d78b-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="8d78b-139">Un `let` enlace en el nivel de módulo, en un tipo o en una expresión de cálculo puede tener parámetros de tipo explícitos.</span><span class="sxs-lookup"><span data-stu-id="8d78b-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="8d78b-140">Un enlace Let en una expresión, como dentro de una definición de función, no puede tener parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="8d78b-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="8d78b-141">Para más información, vea [Genéricos](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="8d78b-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="8d78b-142">Atributos en enlaces Let</span><span class="sxs-lookup"><span data-stu-id="8d78b-142">Attributes on let Bindings</span></span>

<span data-ttu-id="8d78b-143">Los atributos se pueden aplicar a `let` los enlaces de nivel superior de un módulo, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d78b-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="8d78b-144">Ámbito y accesibilidad de los enlaces Let</span><span class="sxs-lookup"><span data-stu-id="8d78b-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="8d78b-145">El ámbito de una entidad declarada con un enlace Let está limitado a la parte del ámbito contenedor (por ejemplo, una función, un módulo, un archivo o una clase) después de que aparezca el enlace.</span><span class="sxs-lookup"><span data-stu-id="8d78b-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="8d78b-146">Por lo tanto, se puede decir que un enlace Let introduce un nombre en un ámbito.</span><span class="sxs-lookup"><span data-stu-id="8d78b-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="8d78b-147">En un módulo, se puede acceder a un valor o función enlazado a los clientes de un módulo siempre que se pueda acceder al módulo, ya que los enlaces Let de un módulo se compilan en funciones públicas del módulo.</span><span class="sxs-lookup"><span data-stu-id="8d78b-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="8d78b-148">Por el contrario, los enlaces Let de una clase son privados para la clase.</span><span class="sxs-lookup"><span data-stu-id="8d78b-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="8d78b-149">Normalmente, las funciones de los módulos deben calificarse con el nombre del módulo cuando se usan en el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="8d78b-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="8d78b-150">Por ejemplo, si un módulo `Module1` tiene una función `function1` , los usuarios especificarán `Module1.function1` que hagan referencia a la función.</span><span class="sxs-lookup"><span data-stu-id="8d78b-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="8d78b-151">Los usuarios de un módulo pueden usar una declaración de importación para hacer que las funciones de ese módulo estén disponibles para su uso sin que el nombre del módulo los califique.</span><span class="sxs-lookup"><span data-stu-id="8d78b-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="8d78b-152">En el ejemplo que se acaba de mencionar, los usuarios del módulo pueden, en ese caso, abrir el módulo mediante la declaración de importación Open `Module1` y, a continuación, hacer referencia `function1` directamente a.</span><span class="sxs-lookup"><span data-stu-id="8d78b-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

<span data-ttu-id="8d78b-153">Algunos módulos tienen el atributo [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html), lo que significa que las funciones que exponen deben calificarse con el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="8d78b-153">Some modules have the attribute [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="8d78b-154">Por ejemplo, el módulo de lista de F # tiene este atributo.</span><span class="sxs-lookup"><span data-stu-id="8d78b-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="8d78b-155">Para obtener más información sobre los módulos y el control de acceso, consulte [módulos](../modules.md) y [Access Control](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="8d78b-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8d78b-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d78b-156">See also</span></span>

- [<span data-ttu-id="8d78b-157">Funciones</span><span class="sxs-lookup"><span data-stu-id="8d78b-157">Functions</span></span>](index.md)
- [<span data-ttu-id="8d78b-158">`let` Enlaces en clases</span><span class="sxs-lookup"><span data-stu-id="8d78b-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
