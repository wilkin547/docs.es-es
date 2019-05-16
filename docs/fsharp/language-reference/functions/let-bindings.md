---
title: Enlaces let
description: Aprenda a usar un F# 'let' enlace, que asocia un identificador a un valor o una función.
ms.date: 05/16/2016
ms.openlocfilehash: ac33ee761cd4881f3d82d6680a07f62a1d7e77e5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641887"
---
# <a name="let-bindings"></a><span data-ttu-id="83720-103">Enlaces let</span><span class="sxs-lookup"><span data-stu-id="83720-103">let Bindings</span></span>

<span data-ttu-id="83720-104">Un *enlace* asocia un identificador a un valor o una función.</span><span class="sxs-lookup"><span data-stu-id="83720-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="83720-105">Usa el `let` palabra clave para enlazar un nombre a un valor o una función.</span><span class="sxs-lookup"><span data-stu-id="83720-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="83720-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83720-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="83720-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83720-107">Remarks</span></span>

<span data-ttu-id="83720-108">El `let` palabra clave se usa en expresiones para definir los valores o valores de función para uno o más nombres de enlace.</span><span class="sxs-lookup"><span data-stu-id="83720-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="83720-109">La forma más sencilla de la `let` expresión enlaza un nombre a un valor simple, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="83720-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="83720-110">Si la expresión del identificador de independientes mediante el uso de una nueva línea, debe aplicar sangría a cada línea de la expresión, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="83720-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="83720-111">En lugar de simplemente un nombre, se puede especificar un patrón que contiene los nombres, por ejemplo, una tupla, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="83720-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="83720-112">El *cuerpo de expresión* es la expresión en la que se usan los nombres.</span><span class="sxs-lookup"><span data-stu-id="83720-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="83720-113">La expresión de cuerpo aparece en su propia línea, con una sangría a la línea exactamente con el primer carácter en el `let` palabra clave:</span><span class="sxs-lookup"><span data-stu-id="83720-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="83720-114">Un `let` enlace puede aparecer en el nivel de módulo, en la definición de un tipo de clase o en ámbitos locales, como se muestra en una definición de función.</span><span class="sxs-lookup"><span data-stu-id="83720-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="83720-115">Un `let` enlace en el nivel en un módulo o en un tipo de clase superior no es necesario tener una expresión de cuerpo, pero en otros niveles de ámbito, se requiere la expresión de cuerpo.</span><span class="sxs-lookup"><span data-stu-id="83720-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="83720-116">Los nombres enlazados son utilizables después del punto de definición, pero no en cualquier momento antes de la `let` enlace aparece, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="83720-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="83720-117">Enlaces de función</span><span class="sxs-lookup"><span data-stu-id="83720-117">Function Bindings</span></span>

<span data-ttu-id="83720-118">Enlaces de función siguen las reglas para los enlaces de valor, excepto en que los enlaces de función incluyen el nombre de función y los parámetros, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="83720-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="83720-119">En general, los parámetros son patrones, como un modelo de tupla:</span><span class="sxs-lookup"><span data-stu-id="83720-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="83720-120">Un `let` enlazar la expresión se evalúa como el valor de la última expresión.</span><span class="sxs-lookup"><span data-stu-id="83720-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="83720-121">Por lo tanto, en el ejemplo de código siguiente, el valor de `result` se calcula a partir `100 * function3 (1, 2)`, que se evalúa como `300`.</span><span class="sxs-lookup"><span data-stu-id="83720-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="83720-122">Para obtener más información, vea [Funciones](index.md).</span><span class="sxs-lookup"><span data-stu-id="83720-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="83720-123">Anotaciones de tipo</span><span class="sxs-lookup"><span data-stu-id="83720-123">Type Annotations</span></span>

<span data-ttu-id="83720-124">Puede especificar tipos de parámetros mediante la inclusión de dos puntos (:) seguido por un nombre de tipo, escribir entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="83720-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="83720-125">También puede especificar el tipo de valor devuelto anexando el signo de dos puntos y el tipo después del último parámetro.</span><span class="sxs-lookup"><span data-stu-id="83720-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="83720-126">Las anotaciones de tipo completo de `function1`, con números enteros como tipos de parámetro, sería como sigue.</span><span class="sxs-lookup"><span data-stu-id="83720-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="83720-127">Cuando no hay ningún parámetro de tipo explícito, se usa la inferencia de tipos para determinar los tipos de parámetros de funciones.</span><span class="sxs-lookup"><span data-stu-id="83720-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="83720-128">Esto puede incluir la generalización automática del tipo de un parámetro para ser genérico.</span><span class="sxs-lookup"><span data-stu-id="83720-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="83720-129">Para obtener más información, consulte [generalización automática](../generics/automatic-generalization.md) y [inferencia](../type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="83720-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="83720-130">Enlaces let en clases</span><span class="sxs-lookup"><span data-stu-id="83720-130">let Bindings in Classes</span></span>

<span data-ttu-id="83720-131">Un `let` enlace puede aparecer en un tipo de clase, pero no en una estructura o un tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="83720-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="83720-132">Para utilizar un enlace let en un tipo de clase, la clase debe tener un constructor primario.</span><span class="sxs-lookup"><span data-stu-id="83720-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="83720-133">Los parámetros del constructor deben aparecer después del nombre de tipo en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="83720-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="83720-134">Un `let` enlace en un tipo de clase define los campos privados y los miembros de ese tipo de clase y, junto con `do` formularios de enlaces en el tipo, el código para el constructor principal para el tipo.</span><span class="sxs-lookup"><span data-stu-id="83720-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="83720-135">Los ejemplos de código siguiente muestran una clase `MyClass` con campos privados `field1` y `field2`.</span><span class="sxs-lookup"><span data-stu-id="83720-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="83720-136">Los ámbitos de `field1` y `field2` están limitados al tipo en el que se declaran.</span><span class="sxs-lookup"><span data-stu-id="83720-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="83720-137">Para obtener más información, consulte [ `let` Bindings in Classes](../members/let-bindings-in-classes.md) y [clases](../classes.md).</span><span class="sxs-lookup"><span data-stu-id="83720-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="83720-138">Parámetros de tipo en los enlaces let</span><span class="sxs-lookup"><span data-stu-id="83720-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="83720-139">Un `let` enlace en el nivel de módulo, en un tipo o en una expresión de cálculo puede tener parámetros de tipo explícito.</span><span class="sxs-lookup"><span data-stu-id="83720-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="83720-140">Un enlace let en una expresión, como dentro de una definición de función, no puede tener parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="83720-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="83720-141">Para más información, vea [Genéricos](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="83720-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="83720-142">Atributos en los enlaces let</span><span class="sxs-lookup"><span data-stu-id="83720-142">Attributes on let Bindings</span></span>

<span data-ttu-id="83720-143">Los atributos se pueden aplicar al nivel superior `let` enlaces en un módulo, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="83720-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="83720-144">Ámbito y la accesibilidad de los enlaces Let</span><span class="sxs-lookup"><span data-stu-id="83720-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="83720-145">Se limita a la parte de la que contiene el ámbito de una entidad declarada con un enlace permiten definir el ámbito (por ejemplo, una función, módulo, archivo o clase) después de que aparezca el enlace.</span><span class="sxs-lookup"><span data-stu-id="83720-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="83720-146">Por lo tanto, puede decir que un enlace let introduce un nombre en un ámbito.</span><span class="sxs-lookup"><span data-stu-id="83720-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="83720-147">En un módulo, un valor enlazado a let o una función es accesible a los clientes de un módulo siempre que el módulo sea accesible, puesto que los enlaces let en un módulo se compilan en funciones públicas del módulo.</span><span class="sxs-lookup"><span data-stu-id="83720-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="83720-148">Por el contrario, los enlaces let en una clase son privados para la clase.</span><span class="sxs-lookup"><span data-stu-id="83720-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="83720-149">Normalmente, las funciones de módulos deben calificarse con el nombre del módulo cuando se usa código de cliente.</span><span class="sxs-lookup"><span data-stu-id="83720-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="83720-150">Por ejemplo, si un módulo `Module1` tiene una función `function1`, debería especificar los usuarios `Module1.function1` para hacer referencia a la función.</span><span class="sxs-lookup"><span data-stu-id="83720-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="83720-151">Los usuarios de un módulo pueden usar una declaración de importación para hacer que las funciones dentro de ese módulo disponibles para su uso sin que se está calificado con el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="83720-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="83720-152">En el ejemplo que acabo de mencionar, los usuarios del módulo en ese caso pueden abrir el módulo mediante la apertura de la declaración de importación `Module1` y después hacer referencia a `function1` directamente.</span><span class="sxs-lookup"><span data-stu-id="83720-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

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

<span data-ttu-id="83720-153">Algunos módulos tienen el atributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), lo que significa que las funciones que exponen se deben calificar con el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="83720-153">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="83720-154">Por ejemplo, el F# List (módulo) tiene este atributo.</span><span class="sxs-lookup"><span data-stu-id="83720-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="83720-155">Para obtener más información sobre los módulos y control de acceso, consulte [módulos](../modules.md) y [Control de acceso](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="83720-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="83720-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="83720-156">See also</span></span>

- [<span data-ttu-id="83720-157">Funciones</span><span class="sxs-lookup"><span data-stu-id="83720-157">Functions</span></span>](index.md)
- <span data-ttu-id="83720-158">[`let` Bindings in Classes](../members/let-bindings-in-classes.md) (Enlaces `let` en clases)</span><span class="sxs-lookup"><span data-stu-id="83720-158">[`let` Bindings in Classes](../members/let-bindings-in-classes.md)</span></span>
