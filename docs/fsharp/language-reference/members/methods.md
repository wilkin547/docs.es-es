---
title: Métodos (F#)
description: 'Obtenga información sobre cómo un método de F # es una función asociada a un tipo que se utilizan para exponer e implementar la funcionalidad y el comportamiento de objetos y tipos.'
ms.date: 05/16/2016
ms.openlocfilehash: 02d5a7d22d1ce79a06e15462637c373b33623f61
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253213"
---
# <a name="methods"></a><span data-ttu-id="8f63e-103">Métodos</span><span class="sxs-lookup"><span data-stu-id="8f63e-103">Methods</span></span>

<span data-ttu-id="8f63e-104">Un *método* es una función que está asociada a un tipo.</span><span class="sxs-lookup"><span data-stu-id="8f63e-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="8f63e-105">En la programación orientada a objetos, métodos se usan para exponer e implementar la funcionalidad y el comportamiento de objetos y tipos.</span><span class="sxs-lookup"><span data-stu-id="8f63e-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f63e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f63e-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="8f63e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f63e-107">Remarks</span></span>

<span data-ttu-id="8f63e-108">En la sintaxis anterior, puede ver las distintas formas de definiciones y declaraciones de método.</span><span class="sxs-lookup"><span data-stu-id="8f63e-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="8f63e-109">En los cuerpos de método más largo, un salto de línea detrás del signo igual (=) y se aplica sangría al cuerpo del método completo.</span><span class="sxs-lookup"><span data-stu-id="8f63e-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="8f63e-110">Atributos pueden aplicarse a cualquier declaración de método.</span><span class="sxs-lookup"><span data-stu-id="8f63e-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="8f63e-111">Que preceden a la sintaxis para una definición de método y normalmente se muestran en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="8f63e-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="8f63e-112">Para obtener más información, consulte [Attributes](../attributes.md) (Atributos).</span><span class="sxs-lookup"><span data-stu-id="8f63e-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="8f63e-113">Se pueden marcar métodos `inline`.</span><span class="sxs-lookup"><span data-stu-id="8f63e-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="8f63e-114">Para más información sobre `inline`, vea [Inline Functions](../functions/inline-functions.md) (Funciones insertadas).</span><span class="sxs-lookup"><span data-stu-id="8f63e-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="8f63e-115">Métodos de en línea no se pueden utilizar de forma recursiva dentro del tipo; no es necesario utilizar explícitamente el `rec` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="8f63e-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="8f63e-116">Métodos de instancia</span><span class="sxs-lookup"><span data-stu-id="8f63e-116">Instance Methods</span></span>

<span data-ttu-id="8f63e-117">Los métodos de instancia se declaran con la `member` palabra clave y un *self-identifier*, seguido de un punto (.) y el nombre del método y los parámetros.</span><span class="sxs-lookup"><span data-stu-id="8f63e-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="8f63e-118">Como es el caso de `let` enlaces, el *lista de parámetros* puede ser un modelo.</span><span class="sxs-lookup"><span data-stu-id="8f63e-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="8f63e-119">Normalmente, debe encerrarlo entre método aparecen los parámetros entre paréntesis en forma de tupla, que es de los métodos de manera F # cuando se crean en otros lenguajes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f63e-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="8f63e-120">Sin embargo, también es común currificada (parámetros separados por espacios) y se admiten otros patrones también.</span><span class="sxs-lookup"><span data-stu-id="8f63e-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="8f63e-121">El ejemplo siguiente muestra la definición y uso de un método de instancia no abstracto.</span><span class="sxs-lookup"><span data-stu-id="8f63e-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="8f63e-122">Dentro de los métodos de instancia, no use el identificador propio para obtener acceso a los campos definidos mediante enlaces.</span><span class="sxs-lookup"><span data-stu-id="8f63e-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="8f63e-123">Use el identificador propio al obtener acceso a otros miembros y propiedades.</span><span class="sxs-lookup"><span data-stu-id="8f63e-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="8f63e-124">Métodos estáticos</span><span class="sxs-lookup"><span data-stu-id="8f63e-124">Static Methods</span></span>

<span data-ttu-id="8f63e-125">La palabra clave `static` se utiliza para especificar que un método se pueda llamar sin una instancia y no está asociado a una instancia de objeto.</span><span class="sxs-lookup"><span data-stu-id="8f63e-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="8f63e-126">En caso contrario, los métodos son métodos de instancia.</span><span class="sxs-lookup"><span data-stu-id="8f63e-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="8f63e-127">El ejemplo de la sección siguiente muestra los campos declarados con el `let` palabra clave, los miembros de la propiedad se declaran con el `member` palabra clave y un método estático que se declara con el `static` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="8f63e-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="8f63e-128">El ejemplo siguiente muestra la definición y uso de métodos estáticos.</span><span class="sxs-lookup"><span data-stu-id="8f63e-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="8f63e-129">Se supone que estas definiciones de método están en el `SomeType` clase en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="8f63e-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="8f63e-130">Métodos abstractos y virtuales</span><span class="sxs-lookup"><span data-stu-id="8f63e-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="8f63e-131">La palabra clave `abstract` indica que un método tiene una ranura de la distribución virtual y que no dispongan de una definición de la clase.</span><span class="sxs-lookup"><span data-stu-id="8f63e-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="8f63e-132">Un *ranura distribución virtual* es una entrada en una tabla de funciones mantenida internamente que se usa en tiempo de ejecución para buscar la función virtual llamadas en un tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="8f63e-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="8f63e-133">El mecanismo de distribución virtual es el mecanismo que implementa *polimorfismo*, una característica importante de la programación orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="8f63e-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="8f63e-134">Es una clase que tiene al menos un método abstracto sin una definición de un *clase abstracta*, lo que significa que no se puede crear ninguna instancia de esa clase.</span><span class="sxs-lookup"><span data-stu-id="8f63e-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="8f63e-135">Para obtener más información sobre las clases abstractas, vea [clases abstractas](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="8f63e-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="8f63e-136">Las declaraciones de método abstracto no incluyen un cuerpo de método.</span><span class="sxs-lookup"><span data-stu-id="8f63e-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="8f63e-137">En su lugar, el nombre del método es seguido por dos puntos (:) y una signatura de tipo para el método.</span><span class="sxs-lookup"><span data-stu-id="8f63e-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="8f63e-138">La signatura de tipo de un método es el mismo que muestra IntelliSense cuando sitúe el puntero del mouse sobre un nombre de método en el Editor de código de Visual Studio, excepto sin los nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="8f63e-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="8f63e-139">Las signaturas de tipo también se muestran el intérprete, fsi.exe, cuando se trabaja de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="8f63e-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="8f63e-140">La signatura de tipo de un método está formada por enumerando los tipos de los parámetros, seguidos por el tipo de valor devuelto, con símbolos de separador adecuado.</span><span class="sxs-lookup"><span data-stu-id="8f63e-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="8f63e-141">Parámetros currificados están separados por `->` y parámetros de tupla se separan mediante `*`.</span><span class="sxs-lookup"><span data-stu-id="8f63e-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="8f63e-142">El valor devuelto siempre se separa de los argumentos mediante un `->` símbolos.</span><span class="sxs-lookup"><span data-stu-id="8f63e-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="8f63e-143">Pueden usarse paréntesis para agrupar parámetros complejos, por ejemplo, cuando un tipo de función es un parámetro, o para indicar cuándo una tupla se trata como un único parámetro en lugar de dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="8f63e-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="8f63e-144">También puedes usar los métodos abstractos definiciones default agregando la definición de la clase y usando el `default` palabra clave, como se muestra en el bloque de sintaxis en este tema.</span><span class="sxs-lookup"><span data-stu-id="8f63e-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="8f63e-145">Un método abstracto que tiene una definición de la misma clase es equivalente a un método virtual en otros lenguajes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f63e-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="8f63e-146">Si existe o no una definición, la `abstract` palabra clave crea una nueva ranura de envío en la tabla de funciones virtuales para la clase.</span><span class="sxs-lookup"><span data-stu-id="8f63e-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="8f63e-147">Independientemente de si una clase base implementa sus métodos abstractos, las clases derivadas pueden proporcionar implementaciones de métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="8f63e-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="8f63e-148">Para implementar un método abstracto en una clase derivada, defina un método que tiene el mismo nombre y la firma de la clase derivada, excepto que use el `override` o `default` palabra clave y proporcione el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="8f63e-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="8f63e-149">Las palabras clave `override` y `default` exactamente el mismo significado.</span><span class="sxs-lookup"><span data-stu-id="8f63e-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="8f63e-150">Usar `override` si el nuevo método reemplaza una implementación de la clase base; use `default` al crear una implementación en la misma clase que la declaración abstracta original.</span><span class="sxs-lookup"><span data-stu-id="8f63e-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="8f63e-151">No utilice el `abstract` palabra clave en el método que implementa el método que se ha declarado como abstracto en la clase base.</span><span class="sxs-lookup"><span data-stu-id="8f63e-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="8f63e-152">El ejemplo siguiente muestra un método abstracto `Rotate` que tiene una implementación de forma predeterminada, el equivalente de un método virtual de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f63e-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="8f63e-153">El ejemplo siguiente muestra una clase derivada que reemplaza un método de clase base.</span><span class="sxs-lookup"><span data-stu-id="8f63e-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="8f63e-154">En este caso, la invalidación cambia el comportamiento para que el método no hace nada.</span><span class="sxs-lookup"><span data-stu-id="8f63e-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="8f63e-155">Métodos sobrecargados</span><span class="sxs-lookup"><span data-stu-id="8f63e-155">Overloaded Methods</span></span>

<span data-ttu-id="8f63e-156">Métodos sobrecargados son métodos que tienen nombres idénticos en un tipo determinado, pero que tienen diferentes argumentos.</span><span class="sxs-lookup"><span data-stu-id="8f63e-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="8f63e-157">En F #, los argumentos opcionales se suelen usar en lugar de métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="8f63e-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="8f63e-158">Sin embargo, se permiten métodos sobrecargados en el lenguaje, siempre que los argumentos son en forma de tupla, no currificada.</span><span class="sxs-lookup"><span data-stu-id="8f63e-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="8f63e-159">Argumentos opcionales</span><span class="sxs-lookup"><span data-stu-id="8f63e-159">Optional Arguments</span></span>

<span data-ttu-id="8f63e-160">A partir de F # 4.1, también puede tener argumentos opcionales con valor de parámetro predeterminado en métodos.</span><span class="sxs-lookup"><span data-stu-id="8f63e-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="8f63e-161">Esto sirve para ayudar a facilitar la interoperación con código C#.</span><span class="sxs-lookup"><span data-stu-id="8f63e-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="8f63e-162">El ejemplo siguiente muestra la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8f63e-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="8f63e-163">Tenga en cuenta que el valor pasado para `DefaultParameterValue` debe coincidir con el tipo de entrada.</span><span class="sxs-lookup"><span data-stu-id="8f63e-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="8f63e-164">En el ejemplo anterior, es un `int`.</span><span class="sxs-lookup"><span data-stu-id="8f63e-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="8f63e-165">Intenta pasar un valor no entero `DefaultParameterValue` daría lugar a un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="8f63e-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="8f63e-166">Ejemplo: Propiedades y métodos</span><span class="sxs-lookup"><span data-stu-id="8f63e-166">Example: Properties and Methods</span></span>

<span data-ttu-id="8f63e-167">En el siguiente ejemplo contiene un tipo que contiene algunos ejemplos de campos, funciones privadas, propiedades y un método estático.</span><span class="sxs-lookup"><span data-stu-id="8f63e-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="8f63e-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f63e-168">See also</span></span>

- [<span data-ttu-id="8f63e-169">Miembros</span><span class="sxs-lookup"><span data-stu-id="8f63e-169">Members</span></span>](index.md)
