---
title: Clases abstractas (F#)
description: "Obtenga información acerca de clases abstractas de F #, lo cual dejar a algunos o todos los miembros no implementados y representa la funcionalidad común de un conjunto diverso de tipos de objeto."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 209bcca70318db59506011b1f2bb74a09bf3814a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="abstract-classes"></a><span data-ttu-id="2d3b6-104">Clases abstractas</span><span class="sxs-lookup"><span data-stu-id="2d3b6-104">Abstract Classes</span></span>

<span data-ttu-id="2d3b6-105">*Clases abstractas* son clases que dejan algunos o todos los miembros sin implementar para que las clases derivadas pueden proporcionar implementaciones.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-105">*Abstract classes* are classes that leave some or all members unimplemented, so that implementations can be provided by derived classes.</span></span>

## <a name="syntax"></a><span data-ttu-id="2d3b6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d3b6-106">Syntax</span></span>

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a><span data-ttu-id="2d3b6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d3b6-107">Remarks</span></span>
<span data-ttu-id="2d3b6-108">En la programación orientada a objetos, una clase abstracta sirve como clase base de una jerarquía y representa la funcionalidad común de un conjunto diverso de tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-108">In object-oriented programming, an abstract class is used as a base class of a hierarchy, and represents common functionality of a diverse set of object types.</span></span> <span data-ttu-id="2d3b6-109">Como el nombre "abstract" implica, clases abstractas a menudo no corresponden directamente a entidades concretas en el dominio del problema.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-109">As the name "abstract" implies, abstract classes often do not correspond directly onto concrete entities in the problem domain.</span></span> <span data-ttu-id="2d3b6-110">Sin embargo, representan lo que muchas entidades concretas diferentes tienen en común.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-110">However, they do represent what many different concrete entities have in common.</span></span>

<span data-ttu-id="2d3b6-111">Las clases abstractas deben tener el `AbstractClass` atributo.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-111">Abstract classes must have the `AbstractClass` attribute.</span></span> <span data-ttu-id="2d3b6-112">Puede haber miembros implementados y.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-112">They can have implemented and unimplemented members.</span></span> <span data-ttu-id="2d3b6-113">El uso del término *abstracta* cuando se aplica a una clase es el mismo que en otros lenguajes. NET; sin embargo, el uso del término *abstracta* cuando se aplica a los métodos (y propiedades) es un poco diferente en F # de su usar en otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-113">The use of the term *abstract* when applied to a class is the same as in other .NET languages; however, the use of the term *abstract* when applied to methods (and properties) is a little different in F# from its use in other .NET languages.</span></span> <span data-ttu-id="2d3b6-114">En F #, cuando un método está marcado con el `abstract` (palabra clave), esto indica que un miembro tiene una entrada, conocida como un *entrada de distribución virtual*, en la tabla interna de funciones virtuales de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-114">In F#, when a method is marked with the `abstract` keyword, this indicates that a member has an entry, known as a *virtual dispatch slot*, in the internal table of virtual functions for that type.</span></span> <span data-ttu-id="2d3b6-115">En otras palabras, el método es virtual, aunque la `virtual` no se utiliza la palabra clave en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-115">In other words, the method is virtual, although the `virtual` keyword is not used in the F# language.</span></span> <span data-ttu-id="2d3b6-116">La palabra clave `abstract` se utiliza en los métodos virtuales, independientemente de si se implementa el método.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-116">The keyword `abstract` is used on virtual methods regardless of whether the method is implemented.</span></span> <span data-ttu-id="2d3b6-117">La declaración de una ranura de distribución virtual es independiente de la definición de un método para esa ranura de envío.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-117">The declaration of a virtual dispatch slot is separate from the definition of a method for that dispatch slot.</span></span> <span data-ttu-id="2d3b6-118">Por lo tanto, el equivalente de F # de una declaración de método virtual y la definición en otro lenguaje de .NET es una combinación de una declaración de método abstracto y una definición independiente, con cualquiera el `default` palabra clave o el `override` (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="2d3b6-118">Therefore, the F# equivalent of a virtual method declaration and definition in another .NET language is a combination of both an abstract method declaration and a separate definition, with either the `default` keyword or the `override` keyword.</span></span> <span data-ttu-id="2d3b6-119">Para obtener más información y ejemplos, vea [métodos](members/methods.md).</span><span class="sxs-lookup"><span data-stu-id="2d3b6-119">For more information and examples, see [Methods](members/methods.md).</span></span>

<span data-ttu-id="2d3b6-120">Una clase se considera abstracta únicamente si hay métodos abstractos que se han declarado pero no definido.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-120">A class is considered abstract only if there are abstract methods that are declared but not defined.</span></span> <span data-ttu-id="2d3b6-121">Por lo tanto, las clases que tienen métodos abstractos no son necesariamente clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-121">Therefore, classes that have abstract methods are not necessarily abstract classes.</span></span> <span data-ttu-id="2d3b6-122">A menos que una clase tiene un indefinido métodos abstractos, no utilice la **AbstractClass** atributo.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-122">Unless a class has undefined abstract methods, do not use the **AbstractClass** attribute.</span></span>

<span data-ttu-id="2d3b6-123">En la sintaxis anterior, *modificador de accesibilidad* puede ser `public`, `private` o `internal`.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-123">In the previous syntax, *accessibility-modifier* can be `public`, `private` or `internal`.</span></span> <span data-ttu-id="2d3b6-124">Para más información, vea [Access Control](access-control.md) (Control de acceso).</span><span class="sxs-lookup"><span data-stu-id="2d3b6-124">For more information, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="2d3b6-125">Como ocurre con otros tipos, las clases abstractas pueden tener una clase base y una o varias interfaces base.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-125">As with other types, abstract classes can have a base class and one or more base interfaces.</span></span> <span data-ttu-id="2d3b6-126">Cada clase base o interfaz aparece en una línea independiente junto con el `inherit` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-126">Each base class or interface appears on a separate line together with the `inherit` keyword.</span></span>

<span data-ttu-id="2d3b6-127">La definición de tipo de una clase abstracta puede contener miembros totalmente definidos, pero también puede contener a miembros abstractos.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-127">The type definition of an abstract class can contain fully defined members, but it can also contain abstract members.</span></span> <span data-ttu-id="2d3b6-128">La sintaxis de miembros abstractos se muestran por separado en la sintaxis anterior.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-128">The syntax for abstract members is shown separately in the previous syntax.</span></span> <span data-ttu-id="2d3b6-129">En esta sintaxis, la *signatura de tipo* de un miembro es una lista que contiene los tipos de parámetros en orden y los tipos de valor devueltos, separada por `->` tokens o `*` tokens según corresponda para currificadas y tupla parámetros.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-129">In this syntax, the *type signature* of a member is a list that contains the parameter types in order and the return types, separated by `->` tokens and/or `*` tokens as appropriate for curried and tupled parameters.</span></span> <span data-ttu-id="2d3b6-130">La sintaxis de las signaturas de tipo de miembro abstracto es el mismo que el se usa en los archivos de firma y se muestra en IntelliSense en el Editor de código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-130">The syntax for abstract member type signatures is the same as that used in signature files and that shown by IntelliSense in the Visual Studio Code Editor.</span></span>

<span data-ttu-id="2d3b6-131">El código siguiente muestra una clase abstracta forma, que tiene dos clases derivadas de no abstracta, cuadrado y un círculo.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-131">The following code illustrates an abstract class Shape, which has two non-abstract derived classes, Square and Circle.</span></span> <span data-ttu-id="2d3b6-132">En el ejemplo se muestra cómo utilizar propiedades, métodos y clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-132">The example shows how to use abstract classes, methods, and properties.</span></span> <span data-ttu-id="2d3b6-133">En el ejemplo, la forma de clase abstracta representa los elementos comunes de las entidades concretas circle y square.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-133">In the example, the abstract class Shape represents the common elements of the concrete entities circle and square.</span></span> <span data-ttu-id="2d3b6-134">Las características comunes de todas las formas (en un sistema de coordenadas bidimensional) se abstraen en la clase Shape: la posición en la cuadrícula, un ángulo de giro y las propiedades de área y el perímetro.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-134">The common features of all shapes (in a two-dimensional coordinate system) are abstracted out into the Shape class: the position on the grid, an angle of rotation, and the area and perimeter properties.</span></span> <span data-ttu-id="2d3b6-135">Estos pueden ser invalidados, salvo la posición, el comportamiento de los cuales no se pueden cambiar las formas individuales.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-135">These can be overridden, except for position, the behavior of which individual shapes cannot change.</span></span>

<span data-ttu-id="2d3b6-136">Puede invalidar el método de rotación, como en la clase Circle, que es invariable rotación dada su simetría.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-136">The rotation method can be overridden, as in the Circle class, which is rotation invariant because of its symmetry.</span></span> <span data-ttu-id="2d3b6-137">Por lo que en la clase de círculo, el método de rotación se reemplaza por un método que no hace nada.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-137">So in the Circle class, the rotation method is replaced by a method that does nothing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

<span data-ttu-id="2d3b6-138">**Salida:**</span><span class="sxs-lookup"><span data-stu-id="2d3b6-138">**Output:**</span></span>

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a><span data-ttu-id="2d3b6-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d3b6-139">See Also</span></span>
[<span data-ttu-id="2d3b6-140">Clases</span><span class="sxs-lookup"><span data-stu-id="2d3b6-140">Classes</span></span>](classes.md)

[<span data-ttu-id="2d3b6-141">Miembros</span><span class="sxs-lookup"><span data-stu-id="2d3b6-141">Members</span></span>](members/index.md)

[<span data-ttu-id="2d3b6-142">Métodos</span><span class="sxs-lookup"><span data-stu-id="2d3b6-142">Methods</span></span>](members/methods.md)

[<span data-ttu-id="2d3b6-143">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2d3b6-143">Properties</span></span>](members/Properties.md)
