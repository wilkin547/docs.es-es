---
title: Herencia (F#)
description: "Obtenga información acerca de cómo especificar relaciones de herencia de F # mediante la palabra clave 'inherit'."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b38ab2f6-7ba7-4839-8eff-e6bd6cfd2b2f
ms.openlocfilehash: 331c8f4e39aacd9d5e55bfbaf584f037e58d36a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="inheritance"></a><span data-ttu-id="bf98f-104">Herencia</span><span class="sxs-lookup"><span data-stu-id="bf98f-104">Inheritance</span></span>

<span data-ttu-id="bf98f-105">Herencia se usa para modelar la relación "es un", o los subtipos en la programación orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="bf98f-105">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>


## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="bf98f-106">Especificar las relaciones de herencia</span><span class="sxs-lookup"><span data-stu-id="bf98f-106">Specifying Inheritance Relationships</span></span>
<span data-ttu-id="bf98f-107">Especificar las relaciones de herencia mediante la `inherit` palabra clave en una declaración de clase.</span><span class="sxs-lookup"><span data-stu-id="bf98f-107">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="bf98f-108">El formato sintáctico básico se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="bf98f-108">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="bf98f-109">Una clase puede tener a lo sumo una clase base directa.</span><span class="sxs-lookup"><span data-stu-id="bf98f-109">A class can have at most one direct base class.</span></span> <span data-ttu-id="bf98f-110">Si no especifica una clase base mediante el uso de la `inherit` (palabra clave), la clase hereda de forma implícita de `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="bf98f-110">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>


## <a name="inherited-members"></a><span data-ttu-id="bf98f-111">Miembros heredados</span><span class="sxs-lookup"><span data-stu-id="bf98f-111">Inherited Members</span></span>
<span data-ttu-id="bf98f-112">Si una clase hereda de otra clase, los métodos y miembros de la clase base están disponibles para los usuarios de la clase derivada como si fueran miembros directos de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="bf98f-112">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="bf98f-113">Todos los enlaces let y parámetros de constructor son privadas para una clase y, por lo tanto, no se pueden tener acceso desde las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="bf98f-113">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="bf98f-114">La palabra clave `base` está disponible en las clases derivadas y hace referencia a la instancia de la clase base.</span><span class="sxs-lookup"><span data-stu-id="bf98f-114">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="bf98f-115">Se utiliza como identificador de la propia.</span><span class="sxs-lookup"><span data-stu-id="bf98f-115">It is used like the self-identifier.</span></span>


## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="bf98f-116">Métodos virtuales y reemplazos</span><span class="sxs-lookup"><span data-stu-id="bf98f-116">Virtual Methods and Overrides</span></span>
<span data-ttu-id="bf98f-117">Métodos virtuales (y las propiedades) funcionan forma ligeramente distinta en F # en comparación con otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="bf98f-117">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="bf98f-118">Para declarar un nuevo miembro virtual, use la `abstract` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="bf98f-118">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="bf98f-119">Para ello, independientemente de si se proporciona una implementación predeterminada para ese método.</span><span class="sxs-lookup"><span data-stu-id="bf98f-119">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="bf98f-120">Por lo tanto, una definición completa de un método virtual en una clase base sigue este patrón:</span><span class="sxs-lookup"><span data-stu-id="bf98f-120">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="bf98f-121">Y en una clase derivada, una invalidación de este método virtual sigue este patrón:</span><span class="sxs-lookup"><span data-stu-id="bf98f-121">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="bf98f-122">Si se omite la implementación predeterminada de la clase base, la clase base se convierte en una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="bf98f-122">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="bf98f-123">En el ejemplo de código siguiente se muestra la declaración de un nuevo método virtual `function1` en una clase base y cómo se reemplaza en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="bf98f-123">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]
    
## <a name="constructors-and-inheritance"></a><span data-ttu-id="bf98f-124">Constructores y herencia</span><span class="sxs-lookup"><span data-stu-id="bf98f-124">Constructors and Inheritance</span></span>
<span data-ttu-id="bf98f-125">El constructor de la clase base debe llamarse en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="bf98f-125">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="bf98f-126">Los argumentos para el constructor de clase base aparecen en la lista de argumentos en la `inherit` cláusula.</span><span class="sxs-lookup"><span data-stu-id="bf98f-126">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="bf98f-127">Los valores que se utilizan deben determinarse de los argumentos proporcionados al constructor de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="bf98f-127">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="bf98f-128">El código siguiente muestra una clase base y una clase derivada, donde la clase derivada llama al constructor de clase base en la cláusula de heredar:</span><span class="sxs-lookup"><span data-stu-id="bf98f-128">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="bf98f-129">En el caso de varios constructores, puede utilizarse el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="bf98f-129">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="bf98f-130">La primera línea de los constructores de clase derivada es el `inherit` cláusula y los campos aparecen como campos explícitos que se declaran con la `val` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="bf98f-130">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="bf98f-131">Para obtener más información, consulte [campos explícitos: el `val` palabra clave](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="bf98f-131">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="bf98f-132">Alternativas a la herencia</span><span class="sxs-lookup"><span data-stu-id="bf98f-132">Alternatives to Inheritance</span></span>
<span data-ttu-id="bf98f-133">En casos donde se requiere una pequeña modificación de un tipo, considere el uso de una expresión de objeto como alternativa a la herencia.</span><span class="sxs-lookup"><span data-stu-id="bf98f-133">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="bf98f-134">En el ejemplo siguiente se muestra el uso de una expresión de objeto como alternativa a la creación de un nuevo tipo derivado:</span><span class="sxs-lookup"><span data-stu-id="bf98f-134">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="bf98f-135">Para obtener más información acerca de las expresiones de objeto, vea [expresiones de objeto](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="bf98f-135">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="bf98f-136">Al crear jerarquías de objetos, considere la posibilidad de usar una unión discriminada en lugar de herencia.</span><span class="sxs-lookup"><span data-stu-id="bf98f-136">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="bf98f-137">Uniones discriminadas también pueden modelar un comportamiento variado de diferentes objetos que comparten un tipo global común.</span><span class="sxs-lookup"><span data-stu-id="bf98f-137">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="bf98f-138">Una sola unión discriminada a menudo puede prescindir del uso de una serie de clases derivadas que son pequeñas variaciones entre sí.</span><span class="sxs-lookup"><span data-stu-id="bf98f-138">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="bf98f-139">Para obtener información sobre las uniones discriminadas, vea [uniones discriminadas](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="bf98f-139">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="bf98f-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf98f-140">See Also</span></span>
[<span data-ttu-id="bf98f-141">Expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="bf98f-141">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="bf98f-142">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="bf98f-142">F# Language Reference</span></span>](index.md)
