---
title: Clases abstractas (F#)
description: 'Obtenga información acerca de clases abstractas de F #, lo cual dejar a algunos o todos los miembros no implementados y representa la funcionalidad común de un conjunto diverso de tipos de objeto.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 0d7ca996de89c44a5cfb9197c1b515741a2303df
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="abstract-classes"></a><span data-ttu-id="2971c-103">Clases abstractas</span><span class="sxs-lookup"><span data-stu-id="2971c-103">Abstract Classes</span></span>

<span data-ttu-id="2971c-104">*Clases abstractas* son clases que dejan algunos o todos los miembros sin implementar para que las clases derivadas pueden proporcionar implementaciones.</span><span class="sxs-lookup"><span data-stu-id="2971c-104">*Abstract classes* are classes that leave some or all members unimplemented, so that implementations can be provided by derived classes.</span></span>

## <a name="syntax"></a><span data-ttu-id="2971c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2971c-105">Syntax</span></span>

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a><span data-ttu-id="2971c-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2971c-106">Remarks</span></span>
<span data-ttu-id="2971c-107">En la programación orientada a objetos, una clase abstracta sirve como clase base de una jerarquía y representa la funcionalidad común de un conjunto diverso de tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="2971c-107">In object-oriented programming, an abstract class is used as a base class of a hierarchy, and represents common functionality of a diverse set of object types.</span></span> <span data-ttu-id="2971c-108">Como el nombre "abstract" implica, clases abstractas a menudo no corresponden directamente a entidades concretas en el dominio del problema.</span><span class="sxs-lookup"><span data-stu-id="2971c-108">As the name "abstract" implies, abstract classes often do not correspond directly onto concrete entities in the problem domain.</span></span> <span data-ttu-id="2971c-109">Sin embargo, representan lo que muchas entidades concretas diferentes tienen en común.</span><span class="sxs-lookup"><span data-stu-id="2971c-109">However, they do represent what many different concrete entities have in common.</span></span>

<span data-ttu-id="2971c-110">Las clases abstractas deben tener el `AbstractClass` atributo.</span><span class="sxs-lookup"><span data-stu-id="2971c-110">Abstract classes must have the `AbstractClass` attribute.</span></span> <span data-ttu-id="2971c-111">Puede haber miembros implementados y.</span><span class="sxs-lookup"><span data-stu-id="2971c-111">They can have implemented and unimplemented members.</span></span> <span data-ttu-id="2971c-112">El uso del término *abstracta* cuando se aplica a una clase es el mismo que en otros lenguajes. NET; sin embargo, el uso del término *abstracta* cuando se aplica a los métodos (y propiedades) es un poco diferente en F # de su usar en otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="2971c-112">The use of the term *abstract* when applied to a class is the same as in other .NET languages; however, the use of the term *abstract* when applied to methods (and properties) is a little different in F# from its use in other .NET languages.</span></span> <span data-ttu-id="2971c-113">En F #, cuando un método está marcado con el `abstract` (palabra clave), esto indica que un miembro tiene una entrada, conocida como un *entrada de distribución virtual*, en la tabla interna de funciones virtuales de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="2971c-113">In F#, when a method is marked with the `abstract` keyword, this indicates that a member has an entry, known as a *virtual dispatch slot*, in the internal table of virtual functions for that type.</span></span> <span data-ttu-id="2971c-114">En otras palabras, el método es virtual, aunque la `virtual` no se utiliza la palabra clave en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="2971c-114">In other words, the method is virtual, although the `virtual` keyword is not used in the F# language.</span></span> <span data-ttu-id="2971c-115">La palabra clave `abstract` se utiliza en los métodos virtuales, independientemente de si se implementa el método.</span><span class="sxs-lookup"><span data-stu-id="2971c-115">The keyword `abstract` is used on virtual methods regardless of whether the method is implemented.</span></span> <span data-ttu-id="2971c-116">La declaración de una ranura de distribución virtual es independiente de la definición de un método para esa ranura de envío.</span><span class="sxs-lookup"><span data-stu-id="2971c-116">The declaration of a virtual dispatch slot is separate from the definition of a method for that dispatch slot.</span></span> <span data-ttu-id="2971c-117">Por lo tanto, el equivalente de F # de una declaración de método virtual y la definición en otro lenguaje de .NET es una combinación de una declaración de método abstracto y una definición independiente, con cualquiera el `default` palabra clave o el `override` (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="2971c-117">Therefore, the F# equivalent of a virtual method declaration and definition in another .NET language is a combination of both an abstract method declaration and a separate definition, with either the `default` keyword or the `override` keyword.</span></span> <span data-ttu-id="2971c-118">Para obtener más información y ejemplos, vea [métodos](members/methods.md).</span><span class="sxs-lookup"><span data-stu-id="2971c-118">For more information and examples, see [Methods](members/methods.md).</span></span>

<span data-ttu-id="2971c-119">Una clase se considera abstracta únicamente si hay métodos abstractos que se han declarado pero no definido.</span><span class="sxs-lookup"><span data-stu-id="2971c-119">A class is considered abstract only if there are abstract methods that are declared but not defined.</span></span> <span data-ttu-id="2971c-120">Por lo tanto, las clases que tienen métodos abstractos no son necesariamente clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="2971c-120">Therefore, classes that have abstract methods are not necessarily abstract classes.</span></span> <span data-ttu-id="2971c-121">A menos que una clase tiene un indefinido métodos abstractos, no utilice la **AbstractClass** atributo.</span><span class="sxs-lookup"><span data-stu-id="2971c-121">Unless a class has undefined abstract methods, do not use the **AbstractClass** attribute.</span></span>

<span data-ttu-id="2971c-122">En la sintaxis anterior, *modificador de accesibilidad* puede ser `public`, `private` o `internal`.</span><span class="sxs-lookup"><span data-stu-id="2971c-122">In the previous syntax, *accessibility-modifier* can be `public`, `private` or `internal`.</span></span> <span data-ttu-id="2971c-123">Para más información, vea [Access Control](access-control.md) (Control de acceso).</span><span class="sxs-lookup"><span data-stu-id="2971c-123">For more information, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="2971c-124">Como ocurre con otros tipos, las clases abstractas pueden tener una clase base y una o varias interfaces base.</span><span class="sxs-lookup"><span data-stu-id="2971c-124">As with other types, abstract classes can have a base class and one or more base interfaces.</span></span> <span data-ttu-id="2971c-125">Cada clase base o interfaz aparece en una línea independiente junto con el `inherit` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="2971c-125">Each base class or interface appears on a separate line together with the `inherit` keyword.</span></span>

<span data-ttu-id="2971c-126">La definición de tipo de una clase abstracta puede contener miembros totalmente definidos, pero también puede contener a miembros abstractos.</span><span class="sxs-lookup"><span data-stu-id="2971c-126">The type definition of an abstract class can contain fully defined members, but it can also contain abstract members.</span></span> <span data-ttu-id="2971c-127">La sintaxis de miembros abstractos se muestran por separado en la sintaxis anterior.</span><span class="sxs-lookup"><span data-stu-id="2971c-127">The syntax for abstract members is shown separately in the previous syntax.</span></span> <span data-ttu-id="2971c-128">En esta sintaxis, la *signatura de tipo* de un miembro es una lista que contiene los tipos de parámetros en orden y los tipos de valor devueltos, separada por `->` tokens o `*` tokens según corresponda para currificadas y tupla parámetros.</span><span class="sxs-lookup"><span data-stu-id="2971c-128">In this syntax, the *type signature* of a member is a list that contains the parameter types in order and the return types, separated by `->` tokens and/or `*` tokens as appropriate for curried and tupled parameters.</span></span> <span data-ttu-id="2971c-129">La sintaxis de las signaturas de tipo de miembro abstracto es el mismo que el se usa en los archivos de firma y se muestra en IntelliSense en el Editor de código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2971c-129">The syntax for abstract member type signatures is the same as that used in signature files and that shown by IntelliSense in the Visual Studio Code Editor.</span></span>

<span data-ttu-id="2971c-130">El código siguiente muestra una clase abstracta forma, que tiene dos clases derivadas de no abstracta, cuadrado y un círculo.</span><span class="sxs-lookup"><span data-stu-id="2971c-130">The following code illustrates an abstract class Shape, which has two non-abstract derived classes, Square and Circle.</span></span> <span data-ttu-id="2971c-131">En el ejemplo se muestra cómo utilizar propiedades, métodos y clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="2971c-131">The example shows how to use abstract classes, methods, and properties.</span></span> <span data-ttu-id="2971c-132">En el ejemplo, la forma de clase abstracta representa los elementos comunes de las entidades concretas circle y square.</span><span class="sxs-lookup"><span data-stu-id="2971c-132">In the example, the abstract class Shape represents the common elements of the concrete entities circle and square.</span></span> <span data-ttu-id="2971c-133">Las características comunes de todas las formas (en un sistema de coordenadas bidimensional) se abstraen en la clase Shape: la posición en la cuadrícula, un ángulo de giro y las propiedades de área y el perímetro.</span><span class="sxs-lookup"><span data-stu-id="2971c-133">The common features of all shapes (in a two-dimensional coordinate system) are abstracted out into the Shape class: the position on the grid, an angle of rotation, and the area and perimeter properties.</span></span> <span data-ttu-id="2971c-134">Estos pueden ser invalidados, salvo la posición, el comportamiento de los cuales no se pueden cambiar las formas individuales.</span><span class="sxs-lookup"><span data-stu-id="2971c-134">These can be overridden, except for position, the behavior of which individual shapes cannot change.</span></span>

<span data-ttu-id="2971c-135">Puede invalidar el método de rotación, como en la clase Circle, que es invariable rotación dada su simetría.</span><span class="sxs-lookup"><span data-stu-id="2971c-135">The rotation method can be overridden, as in the Circle class, which is rotation invariant because of its symmetry.</span></span> <span data-ttu-id="2971c-136">Por lo que en la clase de círculo, el método de rotación se reemplaza por un método que no hace nada.</span><span class="sxs-lookup"><span data-stu-id="2971c-136">So in the Circle class, the rotation method is replaced by a method that does nothing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

<span data-ttu-id="2971c-137">**Salida:**</span><span class="sxs-lookup"><span data-stu-id="2971c-137">**Output:**</span></span>

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a><span data-ttu-id="2971c-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="2971c-138">See Also</span></span>
[<span data-ttu-id="2971c-139">Clases</span><span class="sxs-lookup"><span data-stu-id="2971c-139">Classes</span></span>](classes.md)

[<span data-ttu-id="2971c-140">Miembros</span><span class="sxs-lookup"><span data-stu-id="2971c-140">Members</span></span>](members/index.md)

[<span data-ttu-id="2971c-141">Métodos</span><span class="sxs-lookup"><span data-stu-id="2971c-141">Methods</span></span>](members/methods.md)

[<span data-ttu-id="2971c-142">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2971c-142">Properties</span></span>](members/Properties.md)
