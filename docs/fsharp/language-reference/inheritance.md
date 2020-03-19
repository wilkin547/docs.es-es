---
title: Herencia
description: Obtenga información sobre cómo especificar las relaciones de herencia de F- mediante la palabra clave 'inherit'.
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401134"
---
# <a name="inheritance"></a><span data-ttu-id="db1c4-103">Herencia</span><span class="sxs-lookup"><span data-stu-id="db1c4-103">Inheritance</span></span>

<span data-ttu-id="db1c4-104">La herencia se utiliza para modelar la relación "is-a", o subtipando, en la programación orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="db1c4-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="db1c4-105">Especificación de relaciones de herencia</span><span class="sxs-lookup"><span data-stu-id="db1c4-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="db1c4-106">Las relaciones de `inherit` herencia se especifican mediante la palabra clave en una declaración de clase.</span><span class="sxs-lookup"><span data-stu-id="db1c4-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="db1c4-107">La forma sintáctica básica se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="db1c4-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="db1c4-108">Una clase puede tener como máximo una clase base directa.</span><span class="sxs-lookup"><span data-stu-id="db1c4-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="db1c4-109">Si no especifica una clase base `inherit` mediante la palabra clave, `System.Object`la clase hereda implícitamente de .</span><span class="sxs-lookup"><span data-stu-id="db1c4-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="db1c4-110">Miembros heredados</span><span class="sxs-lookup"><span data-stu-id="db1c4-110">Inherited Members</span></span>

<span data-ttu-id="db1c4-111">Si una clase hereda de otra clase, los métodos y miembros de la clase base están disponibles para los usuarios de la clase derivada como si fueran miembros directos de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="db1c4-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="db1c4-112">Cualquier let enlaces y constructor parámetros son privados a una clase y, por lo tanto, no se puede tener acceso desde las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="db1c4-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="db1c4-113">La `base` palabra clave está disponible en clases derivadas y hace referencia a la instancia de clase base.</span><span class="sxs-lookup"><span data-stu-id="db1c4-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="db1c4-114">Se utiliza como el autoidentificador.</span><span class="sxs-lookup"><span data-stu-id="db1c4-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="db1c4-115">Métodos virtuales y modificaciones</span><span class="sxs-lookup"><span data-stu-id="db1c4-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="db1c4-116">Los métodos virtuales (y las propiedades) funcionan de forma algo diferente en F - en comparación con otros lenguajes .NET.</span><span class="sxs-lookup"><span data-stu-id="db1c4-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="db1c4-117">Para declarar un nuevo miembro `abstract` virtual, utilice la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="db1c4-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="db1c4-118">Esto se hace independientemente de si se proporciona una implementación predeterminada para ese método.</span><span class="sxs-lookup"><span data-stu-id="db1c4-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="db1c4-119">Por lo tanto, una definición completa de un método virtual en una clase base sigue este patrón:</span><span class="sxs-lookup"><span data-stu-id="db1c4-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="db1c4-120">Y en una clase derivada, una invalidación de este método virtual sigue este patrón:</span><span class="sxs-lookup"><span data-stu-id="db1c4-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="db1c4-121">Si omite la implementación predeterminada en la clase base, la clase base se convierte en una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="db1c4-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="db1c4-122">En el ejemplo de código siguiente se `function1` muestra la declaración de un nuevo método virtual en una clase base y cómo reemplazarlo en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="db1c4-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="db1c4-123">Constructores y herencia</span><span class="sxs-lookup"><span data-stu-id="db1c4-123">Constructors and Inheritance</span></span>

<span data-ttu-id="db1c4-124">El constructor de la clase base debe llamarse en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="db1c4-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="db1c4-125">Los argumentos del constructor de la clase `inherit` base aparecen en la lista de argumentos de la cláusula.</span><span class="sxs-lookup"><span data-stu-id="db1c4-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="db1c4-126">Los valores que se utilizan deben determinarse a partir de los argumentos proporcionados al constructor de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="db1c4-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="db1c4-127">El código siguiente muestra una clase base y una clase derivada, donde la clase derivada llama al constructor de la clase base en la cláusula inherit:</span><span class="sxs-lookup"><span data-stu-id="db1c4-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="db1c4-128">En el caso de varios constructores, se puede usar el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="db1c4-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="db1c4-129">La primera línea de los constructores `inherit` de clase según lo éstos `val` es la cláusula y los campos aparecen como campos explícitos que se declaran con la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="db1c4-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="db1c4-130">Para obtener más información, consulte [Campos explícitos: `val` La palabra clave](./members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="db1c4-130">For more information, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="db1c4-131">Alternativas a la herencia</span><span class="sxs-lookup"><span data-stu-id="db1c4-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="db1c4-132">En los casos en que se requiere una modificación menor de un tipo, considere la posibilidad de usar una expresión de objeto como alternativa a la herencia.</span><span class="sxs-lookup"><span data-stu-id="db1c4-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="db1c4-133">En el ejemplo siguiente se muestra el uso de una expresión de objeto como alternativa a la creación de un nuevo tipo derivado:</span><span class="sxs-lookup"><span data-stu-id="db1c4-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="db1c4-134">Para obtener más información acerca de las expresiones de objeto, vea [Expresiones de objeto](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="db1c4-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="db1c4-135">Al crear jerarquías de objetos, considere la posibilidad de usar una unión discriminada en lugar de una herencia.</span><span class="sxs-lookup"><span data-stu-id="db1c4-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="db1c4-136">Las uniones discriminadas también pueden modelar un comportamiento variado de diferentes objetos que comparten un tipo general común.</span><span class="sxs-lookup"><span data-stu-id="db1c4-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="db1c4-137">Una sola unión discriminada a menudo puede eliminar la necesidad de un número de clases derivadas que son variaciones menores entre sí.</span><span class="sxs-lookup"><span data-stu-id="db1c4-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="db1c4-138">Para obtener información sobre las uniones discriminadas, consulte [Uniones discriminadas](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="db1c4-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db1c4-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db1c4-139">See also</span></span>

- [<span data-ttu-id="db1c4-140">Expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="db1c4-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="db1c4-141">Referencia del lenguaje f</span><span class="sxs-lookup"><span data-stu-id="db1c4-141">F# Language Reference</span></span>](index.md)
