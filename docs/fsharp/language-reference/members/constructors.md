---
title: Constructores (F#)
description: 'Obtenga información sobre cómo definir y utilizar constructores en F # para crear e inicializar objetos de clase y estructura.'
ms.date: 05/16/2016
ms.openlocfilehash: ff2463f890034cce0bbaa85d9a5c93e50427cd03
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43803950"
---
# <a name="constructors"></a><span data-ttu-id="0b244-103">Constructores</span><span class="sxs-lookup"><span data-stu-id="0b244-103">Constructors</span></span>

<span data-ttu-id="0b244-104">Este tema describe cómo definir y usar constructores para crear e inicializar objetos de clase y estructura.</span><span class="sxs-lookup"><span data-stu-id="0b244-104">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="0b244-105">Construcción de objetos de clase</span><span class="sxs-lookup"><span data-stu-id="0b244-105">Construction of Class Objects</span></span>

<span data-ttu-id="0b244-106">Los objetos de tipos de clase tienen constructores.</span><span class="sxs-lookup"><span data-stu-id="0b244-106">Objects of class types have constructors.</span></span> <span data-ttu-id="0b244-107">Hay dos tipos de constructores.</span><span class="sxs-lookup"><span data-stu-id="0b244-107">There are two kinds of constructors.</span></span> <span data-ttu-id="0b244-108">Uno es el constructor principal, cuyos parámetros aparecen entre paréntesis justo después del nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="0b244-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="0b244-109">Especificar otros constructores adicionales opcionales mediante el `new` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="0b244-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="0b244-110">Todos estos constructores adicionales deben llamar al constructor principal.</span><span class="sxs-lookup"><span data-stu-id="0b244-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="0b244-111">El constructor principal contiene `let` y `do` los enlaces que aparecen al principio de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="0b244-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="0b244-112">Un `let` enlace declara campos privados y métodos de la clase; un `do` enlace ejecuta código.</span><span class="sxs-lookup"><span data-stu-id="0b244-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="0b244-113">Para obtener más información acerca de `let` los enlaces en los constructores de clase, vea [ `let` Bindings in Classes](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="0b244-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="0b244-114">Para obtener más información acerca de `do` los enlaces en los constructores, vea [ `do` Bindings in Classes](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="0b244-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="0b244-115">Independientemente de si el constructor que desea llamar es un constructor primario o un constructor adicional, puede crear objetos mediante un `new` expresión, con o sin el elemento opcional `new` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="0b244-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="0b244-116">Inicializar los objetos junto con los argumentos de constructor, ya sea con una lista de los argumentos en orden y separados por comas y entre paréntesis, o mediante el uso de argumentos con nombre y los valores entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="0b244-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="0b244-117">También puede establecer propiedades en un objeto durante la construcción del objeto mediante el uso de los nombres de propiedad y al igual que utiliza la asignación de valores con nombre argumentos de constructor.</span><span class="sxs-lookup"><span data-stu-id="0b244-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="0b244-118">El código siguiente muestra una clase que tiene un constructor y las diversas formas de crear objetos.</span><span class="sxs-lookup"><span data-stu-id="0b244-118">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="0b244-119">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="0b244-119">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="0b244-120">Construcción de estructuras</span><span class="sxs-lookup"><span data-stu-id="0b244-120">Construction of Structures</span></span>

<span data-ttu-id="0b244-121">Las estructuras siguen todas las reglas de clases.</span><span class="sxs-lookup"><span data-stu-id="0b244-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="0b244-122">Por lo tanto, puede tener un constructor primario, y puede proporcionar constructores adicionales mediante `new`.</span><span class="sxs-lookup"><span data-stu-id="0b244-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="0b244-123">Sin embargo, hay una diferencia importante entre las clases y estructuras: las estructuras pueden tener un constructor predeterminado (es decir, uno sin argumentos), incluso si no se define ningún constructor primario.</span><span class="sxs-lookup"><span data-stu-id="0b244-123">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="0b244-124">El constructor predeterminado inicializa todos los campos en el valor predeterminado para ese tipo, normalmente cero o su equivalente.</span><span class="sxs-lookup"><span data-stu-id="0b244-124">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="0b244-125">Los constructores que se definen para las estructuras de deben tener al menos un argumento para que no entren en conflicto con el constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0b244-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="0b244-126">Además, las estructuras tienen a menudo campos que se crean mediante el `val` palabra clave; las clases también pueden tener estos campos.</span><span class="sxs-lookup"><span data-stu-id="0b244-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="0b244-127">Estructuras y clases que tienen campos definidos mediante el `val` palabra clave también se puede inicializar en constructores adicionales mediante el uso de expresiones de registro, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0b244-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="0b244-128">Para obtener más información, consulte [campos explícitos: el `val` palabra clave](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="0b244-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="0b244-129">Ejecutar efectos secundarios en constructores</span><span class="sxs-lookup"><span data-stu-id="0b244-129">Executing Side Effects in Constructors</span></span>

<span data-ttu-id="0b244-130">Un constructor primario en una clase puede ejecutar código en un `do` enlace.</span><span class="sxs-lookup"><span data-stu-id="0b244-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="0b244-131">Sin embargo, ¿qué ocurre si tiene que ejecutar código en un constructor adicional, sin un `do` enlace?</span><span class="sxs-lookup"><span data-stu-id="0b244-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="0b244-132">Para ello, usa el `then` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="0b244-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="0b244-133">Seguir ejecutando los efectos del constructor principal.</span><span class="sxs-lookup"><span data-stu-id="0b244-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="0b244-134">Por lo tanto, el resultado es como sigue.</span><span class="sxs-lookup"><span data-stu-id="0b244-134">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="0b244-135">Autoidentificadores en constructores</span><span class="sxs-lookup"><span data-stu-id="0b244-135">Self Identifiers in Constructors</span></span>

<span data-ttu-id="0b244-136">En otros miembros, proporcione un nombre para el objeto actual en la definición de cada miembro.</span><span class="sxs-lookup"><span data-stu-id="0b244-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="0b244-137">También puede colocar el identificador propio en la primera línea de la definición de clase mediante el uso de la `as` palabra clave inmediatamente después de los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="0b244-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="0b244-138">El ejemplo siguiente muestra esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="0b244-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="0b244-139">En los constructores adicionales, también puede definir un identificador propio colocando el `as` cláusula justo después de los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="0b244-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="0b244-140">El ejemplo siguiente muestra esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="0b244-140">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="0b244-141">Pueden producirse problemas cuando se intenta usar un objeto antes de que está totalmente definida.</span><span class="sxs-lookup"><span data-stu-id="0b244-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="0b244-142">Por lo tanto, usos del identificador propio pueden hacer que el compilador emite una advertencia e inserte comprobaciones adicionales para asegurarse de que no se tiene acceso a los miembros de un objeto antes de que se inicializa el objeto.</span><span class="sxs-lookup"><span data-stu-id="0b244-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="0b244-143">Solo se debe usar el identificador propio en la `do` enlaces del constructor principal o después de la `then` palabra clave en los constructores adicionales.</span><span class="sxs-lookup"><span data-stu-id="0b244-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="0b244-144">El nombre del propio identificador no tiene que ser `this`.</span><span class="sxs-lookup"><span data-stu-id="0b244-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="0b244-145">Puede ser cualquier identificador válido.</span><span class="sxs-lookup"><span data-stu-id="0b244-145">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="0b244-146">Asignar valores a propiedades en la inicialización</span><span class="sxs-lookup"><span data-stu-id="0b244-146">Assigning Values to Properties at Initialization</span></span>

<span data-ttu-id="0b244-147">Puede asignar valores a las propiedades de un objeto de clase en el código de inicialización mediante la anexión de una lista de asignaciones del formulario `property = value` a la lista de argumentos para un constructor.</span><span class="sxs-lookup"><span data-stu-id="0b244-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="0b244-148">Esto se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0b244-148">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="0b244-149">La versión siguiente del código anterior muestra la combinación de argumentos normales, los argumentos opcionales y configuración de propiedades de una llamada de constructor.</span><span class="sxs-lookup"><span data-stu-id="0b244-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="0b244-150">Constructores de clase heredada</span><span class="sxs-lookup"><span data-stu-id="0b244-150">Constructors in inherited class</span></span>

<span data-ttu-id="0b244-151">Al heredar de una clase base que tiene un constructor, debe especificar sus argumentos en la cláusula heredar.</span><span class="sxs-lookup"><span data-stu-id="0b244-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="0b244-152">Para obtener más información, consulte [constructores y herencia](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="0b244-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="0b244-153">Los constructores estáticos o constructores de tipos</span><span class="sxs-lookup"><span data-stu-id="0b244-153">Static Constructors or Type Constructors</span></span>

<span data-ttu-id="0b244-154">Además de especificar el código para crear objetos, estáticos `let` y `do` enlaces se pueden crear tipos de clase que se ejecutan antes de que el tipo en primer lugar se utiliza para realizar la inicialización en el nivel de tipo.</span><span class="sxs-lookup"><span data-stu-id="0b244-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="0b244-155">Para obtener más información, consulte [ `let` Bindings in Classes](let-bindings-in-classes.md) y [ `do` Bindings in Classes](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="0b244-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b244-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b244-156">See also</span></span>

- [<span data-ttu-id="0b244-157">Miembros</span><span class="sxs-lookup"><span data-stu-id="0b244-157">Members</span></span>](index.md)
