---
title: Métodos
description: Obtenga información sobre F# cómo un método es una función asociada a un tipo que se usa para exponer e implementar la funcionalidad y el comportamiento de objetos y tipos.
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976643"
---
# <a name="methods"></a><span data-ttu-id="96056-103">Métodos</span><span class="sxs-lookup"><span data-stu-id="96056-103">Methods</span></span>

<span data-ttu-id="96056-104">Un *método* es una función que está asociada a un tipo.</span><span class="sxs-lookup"><span data-stu-id="96056-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="96056-105">En la programación orientada a objetos, los métodos se utilizan para exponer e implementar la funcionalidad y el comportamiento de los objetos y tipos.</span><span class="sxs-lookup"><span data-stu-id="96056-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="96056-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96056-106">Syntax</span></span>

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a><span data-ttu-id="96056-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96056-107">Remarks</span></span>

<span data-ttu-id="96056-108">En la sintaxis anterior, puede ver las distintas formas de declaraciones y definiciones de método.</span><span class="sxs-lookup"><span data-stu-id="96056-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="96056-109">En cuerpos de método más largos, un salto de línea sigue el signo igual (=) y se aplica sangría al cuerpo del método completo.</span><span class="sxs-lookup"><span data-stu-id="96056-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="96056-110">Los atributos se pueden aplicar a cualquier declaración de método.</span><span class="sxs-lookup"><span data-stu-id="96056-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="96056-111">Preceden a la sintaxis de una definición de método y suelen aparecer en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="96056-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="96056-112">Para obtener más información, consulte [Attributes](../attributes.md) (Atributos).</span><span class="sxs-lookup"><span data-stu-id="96056-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="96056-113">Los métodos se pueden marcar como `inline`.</span><span class="sxs-lookup"><span data-stu-id="96056-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="96056-114">Para más información sobre `inline`, vea [Inline Functions](../functions/inline-functions.md) (Funciones insertadas).</span><span class="sxs-lookup"><span data-stu-id="96056-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="96056-115">Los métodos no insertados se pueden usar de forma recursiva dentro del tipo; no es necesario usar explícitamente la palabra clave `rec`.</span><span class="sxs-lookup"><span data-stu-id="96056-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="96056-116">Métodos de instancia</span><span class="sxs-lookup"><span data-stu-id="96056-116">Instance Methods</span></span>

<span data-ttu-id="96056-117">Los métodos de instancia se declaran con la palabra clave `member` y un *identificador automático*, seguido de un punto (.) y el nombre del método y los parámetros.</span><span class="sxs-lookup"><span data-stu-id="96056-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="96056-118">Como es el caso de los enlaces de `let`, la *lista de parámetros* puede ser un patrón.</span><span class="sxs-lookup"><span data-stu-id="96056-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="96056-119">Normalmente, los parámetros de método se delimitan entre paréntesis en una forma de tupla, que es la F# forma en que los métodos aparecen en cuando se crean en otros lenguajes .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="96056-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="96056-120">Sin embargo, también es común la forma currificada (parámetros separados por espacios) y también se admiten otros patrones.</span><span class="sxs-lookup"><span data-stu-id="96056-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="96056-121">En el ejemplo siguiente se muestra la definición y el uso de un método de instancia no abstracta.</span><span class="sxs-lookup"><span data-stu-id="96056-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="96056-122">En los métodos de instancia, no use el identificador propio para tener acceso a los campos definidos mediante el uso de enlaces Let.</span><span class="sxs-lookup"><span data-stu-id="96056-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="96056-123">Use el identificador propio al acceder a otros miembros y propiedades.</span><span class="sxs-lookup"><span data-stu-id="96056-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="96056-124">Métodos estáticos</span><span class="sxs-lookup"><span data-stu-id="96056-124">Static Methods</span></span>

<span data-ttu-id="96056-125">La palabra clave `static` se utiliza para especificar que se puede llamar a un método sin una instancia de y que no está asociado a una instancia de objeto.</span><span class="sxs-lookup"><span data-stu-id="96056-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="96056-126">De lo contrario, los métodos son métodos de instancia.</span><span class="sxs-lookup"><span data-stu-id="96056-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="96056-127">En el ejemplo de la sección siguiente se muestran los campos declarados con la palabra clave `let`, los miembros de propiedad declarados con la palabra clave `member` y un método estático declarado con la palabra clave `static`.</span><span class="sxs-lookup"><span data-stu-id="96056-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="96056-128">En el ejemplo siguiente se muestra la definición y el uso de métodos estáticos.</span><span class="sxs-lookup"><span data-stu-id="96056-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="96056-129">Suponga que estas definiciones de método se encuentran en la clase `SomeType` en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="96056-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="96056-130">Métodos abstractos y virtuales</span><span class="sxs-lookup"><span data-stu-id="96056-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="96056-131">La palabra clave `abstract` indica que un método tiene una ranura de envío virtual y podría no tener una definición en la clase.</span><span class="sxs-lookup"><span data-stu-id="96056-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="96056-132">Una *ranura de envío virtual* es una entrada de una tabla de funciones que se mantiene internamente y que se utiliza en tiempo de ejecución para buscar llamadas a funciones virtuales en un tipo orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="96056-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="96056-133">El mecanismo de distribución virtual es el mecanismo que implementa el *polimorfismo*, una característica importante de la programación orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="96056-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="96056-134">Una clase que tiene al menos un método abstracto sin una definición es una *clase abstracta*, lo que significa que no se puede crear ninguna instancia de esa clase.</span><span class="sxs-lookup"><span data-stu-id="96056-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="96056-135">Para obtener más información sobre las clases abstractas, vea [clases abstractas](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="96056-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="96056-136">Las declaraciones de método abstracto no incluyen un cuerpo de método.</span><span class="sxs-lookup"><span data-stu-id="96056-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="96056-137">En su lugar, el nombre del método va seguido de un signo de dos puntos (:) y una firma de tipo para el método.</span><span class="sxs-lookup"><span data-stu-id="96056-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="96056-138">La signatura de tipo de un método es la misma que la que se muestra en IntelliSense al pausar el puntero del mouse sobre un nombre de método en el editor de Visual Studio Code, excepto sin nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="96056-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="96056-139">El intérprete, FSI. exe, cuando se trabaja de forma interactiva, también muestra las signaturas de tipo.</span><span class="sxs-lookup"><span data-stu-id="96056-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="96056-140">La signatura de tipo de un método se forma enumerando los tipos de los parámetros, seguidos del tipo de valor devuelto, con símbolos de separador adecuados.</span><span class="sxs-lookup"><span data-stu-id="96056-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="96056-141">Los parámetros currificados se separan mediante `->` y los parámetros de tupla se separan mediante `*`.</span><span class="sxs-lookup"><span data-stu-id="96056-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="96056-142">El valor devuelto siempre está separado de los argumentos por un símbolo de `->`.</span><span class="sxs-lookup"><span data-stu-id="96056-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="96056-143">Los paréntesis se pueden usar para agrupar parámetros complejos, como cuando un tipo de función es un parámetro, o para indicar si una tupla se trata como un parámetro único en lugar de como dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="96056-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="96056-144">También puede proporcionar definiciones default de métodos abstractos agregando la definición a la clase y utilizando la palabra clave `default`, tal como se muestra en el bloque de sintaxis de este tema.</span><span class="sxs-lookup"><span data-stu-id="96056-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="96056-145">Un método abstracto que tiene una definición en la misma clase es equivalente a un método virtual en otros lenguajes .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="96056-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="96056-146">Tanto si existe una definición como si no, la palabra clave `abstract` crea una nueva ranura de envío en la tabla de funciones virtuales para la clase.</span><span class="sxs-lookup"><span data-stu-id="96056-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="96056-147">Independientemente de si una clase base implementa sus métodos abstractos, las clases derivadas pueden proporcionar implementaciones de métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="96056-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="96056-148">Para implementar un método abstracto en una clase derivada, defina un método que tenga el mismo nombre y la misma signatura en la clase derivada, excepto use la palabra clave `override` o `default` y proporcione el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="96056-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="96056-149">Las palabras clave `override` y `default` significan exactamente lo mismo.</span><span class="sxs-lookup"><span data-stu-id="96056-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="96056-150">Use `override` si el nuevo método invalida una implementación de clase base; Utilice `default` cuando cree una implementación en la misma clase que la declaración abstracta original.</span><span class="sxs-lookup"><span data-stu-id="96056-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="96056-151">No utilice la palabra clave `abstract` en el método que implementa el método que se declaró Abstract en la clase base.</span><span class="sxs-lookup"><span data-stu-id="96056-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="96056-152">En el ejemplo siguiente se muestra un método abstracto `Rotate` que tiene una implementación predeterminada, que es el equivalente de un método virtual .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="96056-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="96056-153">En el ejemplo siguiente se muestra una clase derivada que reemplaza un método de clase base.</span><span class="sxs-lookup"><span data-stu-id="96056-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="96056-154">En este caso, la invalidación cambia el comportamiento para que el método no hace nada.</span><span class="sxs-lookup"><span data-stu-id="96056-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="96056-155">Métodos sobrecargados</span><span class="sxs-lookup"><span data-stu-id="96056-155">Overloaded Methods</span></span>

<span data-ttu-id="96056-156">Los métodos sobrecargados son métodos que tienen nombres idénticos en un tipo determinado pero que tienen argumentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="96056-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="96056-157">En F#, normalmente se usan argumentos opcionales en lugar de métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="96056-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="96056-158">Sin embargo, los métodos sobrecargados se permiten en el lenguaje, siempre que los argumentos estén en forma de tupla, no en formato currificados.</span><span class="sxs-lookup"><span data-stu-id="96056-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="96056-159">Argumentos opcionales</span><span class="sxs-lookup"><span data-stu-id="96056-159">Optional Arguments</span></span>

<span data-ttu-id="96056-160">A partir F# de 4,1, también puede tener argumentos opcionales con un valor de parámetro predeterminado en los métodos.</span><span class="sxs-lookup"><span data-stu-id="96056-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="96056-161">Esto ayuda a facilitar la interoperabilidad C# con el código.</span><span class="sxs-lookup"><span data-stu-id="96056-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="96056-162">En el ejemplo siguiente se muestra la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="96056-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="96056-163">Tenga en cuenta que el valor que se pasa para `DefaultParameterValue` debe coincidir con el tipo de entrada.</span><span class="sxs-lookup"><span data-stu-id="96056-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="96056-164">En el ejemplo anterior, es un `int`.</span><span class="sxs-lookup"><span data-stu-id="96056-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="96056-165">Si se intenta pasar un valor no entero a `DefaultParameterValue` se produciría un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="96056-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="96056-166">Ejemplo: propiedades y métodos</span><span class="sxs-lookup"><span data-stu-id="96056-166">Example: Properties and Methods</span></span>

<span data-ttu-id="96056-167">El ejemplo siguiente contiene un tipo que tiene ejemplos de campos, funciones privadas, propiedades y un método estático.</span><span class="sxs-lookup"><span data-stu-id="96056-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="96056-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="96056-168">See also</span></span>

- [<span data-ttu-id="96056-169">Miembros</span><span class="sxs-lookup"><span data-stu-id="96056-169">Members</span></span>](index.md)
