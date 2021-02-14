---
description: 'Más información sobre: programación orientada a objetos (Visual Basic)'
title: Programación orientada a objetos
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: af2fbac16bfefc90876bf22bb8c67de162ee6459
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100486802"
---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="9adbb-103">Programación orientada a objetos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9adbb-103">Object-oriented programming (Visual Basic)</span></span>

<span data-ttu-id="9adbb-104">Visual Basic proporciona compatibilidad total con la programación orientada a objetos, incluidos la encapsulación, la herencia y el polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="9adbb-104">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

 <span data-ttu-id="9adbb-105">La *encapsulación* significa que un grupo de propiedades, métodos y otros miembros relacionados se tratan como una sola unidad u objeto.</span><span class="sxs-lookup"><span data-stu-id="9adbb-105">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

 <span data-ttu-id="9adbb-106">La *herencia* describe la posibilidad de crear nuevas clases basadas en una clase existente.</span><span class="sxs-lookup"><span data-stu-id="9adbb-106">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

 <span data-ttu-id="9adbb-107">El *polimorfismo* significa que puede tener múltiples clases que se pueden usar de manera intercambiable, aunque cada clase implementa las mismas propiedades o los mismos métodos de maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="9adbb-107">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

 <span data-ttu-id="9adbb-108">En esta sección se describen los conceptos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9adbb-108">This section describes the following concepts:</span></span>

- [<span data-ttu-id="9adbb-109">Clases y objetos</span><span class="sxs-lookup"><span data-stu-id="9adbb-109">Classes and objects</span></span>](#classes-and-objects)
  - [<span data-ttu-id="9adbb-110">Miembros de clase</span><span class="sxs-lookup"><span data-stu-id="9adbb-110">Class members</span></span>](#class-members)
    - [<span data-ttu-id="9adbb-111">Propiedades y campos</span><span class="sxs-lookup"><span data-stu-id="9adbb-111">Properties and fields</span></span>](#properties-and-fields)
    - [<span data-ttu-id="9adbb-112">Métodos</span><span class="sxs-lookup"><span data-stu-id="9adbb-112">Methods</span></span>](#methods)
    - [<span data-ttu-id="9adbb-113">Constructores</span><span class="sxs-lookup"><span data-stu-id="9adbb-113">Constructors</span></span>](#constructors)
    - [<span data-ttu-id="9adbb-114">Destructores</span><span class="sxs-lookup"><span data-stu-id="9adbb-114">Destructors</span></span>](#destructors)
    - [<span data-ttu-id="9adbb-115">Eventos</span><span class="sxs-lookup"><span data-stu-id="9adbb-115">Events</span></span>](#events)
    - [<span data-ttu-id="9adbb-116">Clases anidadas</span><span class="sxs-lookup"><span data-stu-id="9adbb-116">Nested classes</span></span>](#nested-classes)
  - [<span data-ttu-id="9adbb-117">Modificadores y niveles de acceso</span><span class="sxs-lookup"><span data-stu-id="9adbb-117">Access modifiers and access levels</span></span>](#access-modifiers-and-access-levels)
    - [<span data-ttu-id="9adbb-118">Creación de instancias de clases</span><span class="sxs-lookup"><span data-stu-id="9adbb-118">Instantiating classes</span></span>](#instantiating-classes)
    - [<span data-ttu-id="9adbb-119">Clases y miembros compartidos</span><span class="sxs-lookup"><span data-stu-id="9adbb-119">Shared classes and members</span></span>](#shared-classes-and-members)
    - <span data-ttu-id="9adbb-120">[Tipos anónimos (Guía de programación de C#)](#anonymous-types).</span><span class="sxs-lookup"><span data-stu-id="9adbb-120">[Anonymous types](#anonymous-types)</span></span>
- [<span data-ttu-id="9adbb-121">Herencia</span><span class="sxs-lookup"><span data-stu-id="9adbb-121">Inheritance</span></span>](#inheritance)
  - [<span data-ttu-id="9adbb-122">Reemplazar miembros</span><span class="sxs-lookup"><span data-stu-id="9adbb-122">Overriding members</span></span>](#overriding-members)
- [<span data-ttu-id="9adbb-123">Interfaces</span><span class="sxs-lookup"><span data-stu-id="9adbb-123">Interfaces</span></span>](#interfaces)
- [<span data-ttu-id="9adbb-124">Genéricos</span><span class="sxs-lookup"><span data-stu-id="9adbb-124">Generics</span></span>](#generics)
- [<span data-ttu-id="9adbb-125">Delegados</span><span class="sxs-lookup"><span data-stu-id="9adbb-125">Delegates</span></span>](#delegates)

## <a name="classes-and-objects"></a><span data-ttu-id="9adbb-126">Clases y objetos</span><span class="sxs-lookup"><span data-stu-id="9adbb-126">Classes and objects</span></span>

<span data-ttu-id="9adbb-127">Los términos *clase* y *objeto* se usan a veces indistintamente pero, en realidad, las clases describen el *tipo* de los objetos, mientras que los objetos son *instancias* de clases que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="9adbb-127">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="9adbb-128">Así, la acción de crear un objeto se denomina *creación de instancias*.</span><span class="sxs-lookup"><span data-stu-id="9adbb-128">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="9adbb-129">Con la analogía de plano, una clase es un plano y un objeto es un edificio construido a partir de ese plano.</span><span class="sxs-lookup"><span data-stu-id="9adbb-129">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="9adbb-130">Para definir una clase:</span><span class="sxs-lookup"><span data-stu-id="9adbb-130">To define a class:</span></span>

```vb
Class SampleClass
End Class
```

<span data-ttu-id="9adbb-131">Visual Basic también proporciona una versión ligera de las clases denominadas *estructuras* que son útiles cuando es necesario crear una matriz grande de objetos y no se desea consumir demasiada memoria para ello.</span><span class="sxs-lookup"><span data-stu-id="9adbb-131">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="9adbb-132">Para definir una estructura:</span><span class="sxs-lookup"><span data-stu-id="9adbb-132">To define a structure:</span></span>

```vb
Structure SampleStructure
End Structure
```

<span data-ttu-id="9adbb-133">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="9adbb-133">For more information, see:</span></span>

- [<span data-ttu-id="9adbb-134">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="9adbb-134">Class Statement</span></span>](../../language-reference/statements/class-statement.md)
- [<span data-ttu-id="9adbb-135">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="9adbb-135">Structure Statement</span></span>](../../language-reference/statements/structure-statement.md)

### <a name="class-members"></a><span data-ttu-id="9adbb-136">Miembros de la clase</span><span class="sxs-lookup"><span data-stu-id="9adbb-136">Class members</span></span>

<span data-ttu-id="9adbb-137">Cada clase puede tener distintos *miembros de clase*, entre los que se incluyen las propiedades que describen los datos de clase, los métodos que definen el comportamiento de la clase y los eventos que proporcionan comunicación entre distintos objetos y clases.</span><span class="sxs-lookup"><span data-stu-id="9adbb-137">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="9adbb-138">Propiedades y campos</span><span class="sxs-lookup"><span data-stu-id="9adbb-138">Properties and fields</span></span>

<span data-ttu-id="9adbb-139">Los campos y propiedades representan información que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="9adbb-139">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="9adbb-140">Los campos se parecen a las variables ya que se pueden leer y establecer directamente.</span><span class="sxs-lookup"><span data-stu-id="9adbb-140">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="9adbb-141">Para definir un campo:</span><span class="sxs-lookup"><span data-stu-id="9adbb-141">To define a field:</span></span>

```vb
Class SampleClass
    Public SampleField As String
End Class
```

<span data-ttu-id="9adbb-142">Las propiedades tienen procedimientos get y set, que proporcionan un mayor control sobre la forma en que se establecen o devuelven los valores.</span><span class="sxs-lookup"><span data-stu-id="9adbb-142">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="9adbb-143">Visual Basic permite crear un campo privado para almacenar el valor de propiedad, o bien usar las denominadas propiedades implementadas automáticamente que crean este campo automáticamente en segundo plano y proporcionan la lógica básica para los procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="9adbb-143">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="9adbb-144">Para definir una propiedad implementada automáticamente:</span><span class="sxs-lookup"><span data-stu-id="9adbb-144">To define an auto-implemented property:</span></span>

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

<span data-ttu-id="9adbb-145">Si necesita realizar algunas operaciones adicionales para leer y escribir el valor de propiedad, defina un campo para almacenar el valor de propiedad y proporcione la lógica básica para almacenarlo y recuperar lo:</span><span class="sxs-lookup"><span data-stu-id="9adbb-145">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

<span data-ttu-id="9adbb-146">La mayoría de las propiedades tienen métodos o procedimientos tanto para establecer como para obtener el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="9adbb-146">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="9adbb-147">Sin embargo, se pueden crear propiedades de solo lectura o solo escritura para restringir su modificación o lectura.</span><span class="sxs-lookup"><span data-stu-id="9adbb-147">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="9adbb-148">En Visual Basic se pueden usar las palabras clave `ReadOnly` y `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="9adbb-148">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="9adbb-149">En cambio, las propiedades implementadas automáticamente no pueden ser de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="9adbb-149">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="9adbb-150">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="9adbb-150">For more information, see:</span></span>

- [<span data-ttu-id="9adbb-151">Property Statement</span><span class="sxs-lookup"><span data-stu-id="9adbb-151">Property Statement</span></span>](../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="9adbb-152">Get (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="9adbb-152">Get Statement</span></span>](../../language-reference/statements/get-statement.md)
- [<span data-ttu-id="9adbb-153">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="9adbb-153">Set Statement</span></span>](../../language-reference/statements/set-statement.md)
- [<span data-ttu-id="9adbb-154">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="9adbb-154">ReadOnly</span></span>](../../language-reference/modifiers/readonly.md)
- [<span data-ttu-id="9adbb-155">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="9adbb-155">WriteOnly</span></span>](../../language-reference/modifiers/writeonly.md)

#### <a name="methods"></a><span data-ttu-id="9adbb-156">Métodos</span><span class="sxs-lookup"><span data-stu-id="9adbb-156">Methods</span></span>

 <span data-ttu-id="9adbb-157">Un *método* es una acción que un objeto puede realizar.</span><span class="sxs-lookup"><span data-stu-id="9adbb-157">A *method* is an action that an object can perform.</span></span>

> [!NOTE]
> <span data-ttu-id="9adbb-158">En Visual Basic hay dos formas de crear un método: se usa la instrucción `Sub` si el método no devuelve un valor o bien se usa la instrucción `Function` si el método devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="9adbb-158">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>

<span data-ttu-id="9adbb-159">Para definir un método de una clase:</span><span class="sxs-lookup"><span data-stu-id="9adbb-159">To define a method of a class:</span></span>

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

<span data-ttu-id="9adbb-160">Una clase puede tener varias implementaciones o *sobrecargas* del mismo método que se diferencian en el número de parámetros o de tipos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="9adbb-160">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="9adbb-161">Para sobrecargar un método:</span><span class="sxs-lookup"><span data-stu-id="9adbb-161">To overload a method:</span></span>

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

<span data-ttu-id="9adbb-162">En la mayoría de los casos, un método se declara dentro de una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="9adbb-162">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="9adbb-163">Sin embargo, Visual Basic también admite *métodos de extensión* que permiten agregar métodos a una clase existente fuera de la definición real de la clase.</span><span class="sxs-lookup"><span data-stu-id="9adbb-163">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="9adbb-164">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="9adbb-164">For more information, see:</span></span>

- [<span data-ttu-id="9adbb-165">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="9adbb-165">Function Statement</span></span>](../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="9adbb-166">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="9adbb-166">Sub Statement</span></span>](../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="9adbb-167">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="9adbb-167">Overloads</span></span>](../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="9adbb-168">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="9adbb-168">Extension Methods</span></span>](../language-features/procedures/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="9adbb-169">Constructores</span><span class="sxs-lookup"><span data-stu-id="9adbb-169">Constructors</span></span>

<span data-ttu-id="9adbb-170">Los constructores son métodos de clase que se ejecutan automáticamente cuando se crea un objeto de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="9adbb-170">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="9adbb-171">Normalmente, los constructores inicializan los miembros de datos del nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="9adbb-171">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="9adbb-172">Un constructor solo puede ejecutarse una vez cuando se crea una clase.</span><span class="sxs-lookup"><span data-stu-id="9adbb-172">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="9adbb-173">Además, el código del constructor siempre se ejecuta antes que cualquier otro código en una clase.</span><span class="sxs-lookup"><span data-stu-id="9adbb-173">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="9adbb-174">Sin embargo, puede crear varias sobrecargas del constructor de la misma forma que para cualquier otro método.</span><span class="sxs-lookup"><span data-stu-id="9adbb-174">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="9adbb-175">Para definir un constructor para una clase:</span><span class="sxs-lookup"><span data-stu-id="9adbb-175">To define a constructor for a class:</span></span>

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

<span data-ttu-id="9adbb-176">Para obtener más información, vea: [duración del objeto: cómo se crean y destruyen los objetos](../language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="9adbb-176">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

#### <a name="destructors"></a><span data-ttu-id="9adbb-177">Destructores</span><span class="sxs-lookup"><span data-stu-id="9adbb-177">Destructors</span></span>

<span data-ttu-id="9adbb-178">Los destructores se utilizan para destruir instancias de clases.</span><span class="sxs-lookup"><span data-stu-id="9adbb-178">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="9adbb-179">En .NET Framework, el recolector de elementos no utilizados administra automáticamente la asignación y la liberación de memoria para los objetos administrados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9adbb-179">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="9adbb-180">Sin embargo, es posible que aún se necesiten destructores para limpiar cualquiera de los recursos no administrados creados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9adbb-180">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="9adbb-181">Solo puede haber un destructor para una clase.</span><span class="sxs-lookup"><span data-stu-id="9adbb-181">There can be only one destructor for a class.</span></span>

<span data-ttu-id="9adbb-182">Para obtener más información sobre los destructores y la recolección de elementos no utilizados en .NET Framework, vea [Garbage Collection](../../../standard/garbage-collection/index.md) (Recolección de elementos no utilizados).</span><span class="sxs-lookup"><span data-stu-id="9adbb-182">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="9adbb-183">Events</span><span class="sxs-lookup"><span data-stu-id="9adbb-183">Events</span></span>

<span data-ttu-id="9adbb-184">Cuando ocurre algo interesante, los eventos habilitan una clase u objeto para notificarlo a otras clases u objetos.</span><span class="sxs-lookup"><span data-stu-id="9adbb-184">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="9adbb-185">La clase que envía (o genera) el evento recibe el nombre de *publicador* y las clases que reciben (o controlan) el evento se denominan *suscriptores*.</span><span class="sxs-lookup"><span data-stu-id="9adbb-185">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="9adbb-186">Para obtener más información sobre los eventos y la forma en que se generan y controlan, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="9adbb-186">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="9adbb-187">Para declarar eventos, use la [instrucción de evento](../../language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9adbb-187">To declare events, use the [Event Statement](../../language-reference/statements/event-statement.md).</span></span>

- <span data-ttu-id="9adbb-188">Para generar eventos, use la [instrucción RaiseEvent](../../language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9adbb-188">To raise events, use the [RaiseEvent Statement](../../language-reference/statements/raiseevent-statement.md).</span></span>

- <span data-ttu-id="9adbb-189">Para especificar los controladores de eventos de forma declarativa, use la instrucción [WithEvents](../../language-reference/modifiers/withevents.md) y la cláusula [Handles](../../language-reference/statements/handles-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="9adbb-189">To specify event handlers using a declarative way, use the [WithEvents](../../language-reference/modifiers/withevents.md) statement and the [Handles](../../language-reference/statements/handles-clause.md) clause.</span></span>

- <span data-ttu-id="9adbb-190">Para poder agregar, quitar y cambiar de forma dinámica el controlador de eventos asociado a un evento, utilice la [instrucción AddHandler](../../language-reference/statements/addhandler-statement.md) y la [instrucción RemoveHandler](../../language-reference/statements/removehandler-statement.md) junto con el [operador AddressOf](../../language-reference/operators/addressof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9adbb-190">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../language-reference/operators/addressof-operator.md).</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="9adbb-191">Clases anidadas</span><span class="sxs-lookup"><span data-stu-id="9adbb-191">Nested classes</span></span>

<span data-ttu-id="9adbb-192">Una clase definida dentro de otra se denomina *anidada*.</span><span class="sxs-lookup"><span data-stu-id="9adbb-192">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="9adbb-193">De forma predeterminada, una clase anidada es privada.</span><span class="sxs-lookup"><span data-stu-id="9adbb-193">By default, the nested class is private.</span></span>

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

<span data-ttu-id="9adbb-194">Para crear una instancia de la clase anidada, use el nombre de la clase contenedora seguido de un punto y seguido, a continuación, del nombre de la clase anidada:</span><span class="sxs-lookup"><span data-stu-id="9adbb-194">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="9adbb-195">Modificadores y niveles de acceso</span><span class="sxs-lookup"><span data-stu-id="9adbb-195">Access modifiers and access levels</span></span>

<span data-ttu-id="9adbb-196">Todas las clases y miembros de clase pueden especificar el nivel de acceso que proporcionan a otras clases mediante los *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="9adbb-196">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="9adbb-197">Están disponibles los siguientes modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="9adbb-197">The following access modifiers are available:</span></span>

|<span data-ttu-id="9adbb-198">Modificador de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9adbb-198">Visual Basic Modifier</span></span>|<span data-ttu-id="9adbb-199">Definición</span><span class="sxs-lookup"><span data-stu-id="9adbb-199">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="9adbb-200">Público</span><span class="sxs-lookup"><span data-stu-id="9adbb-200">Public</span></span>](../../language-reference/modifiers/public.md)|<span data-ttu-id="9adbb-201">Puede obtener acceso al tipo o miembro cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a éste.</span><span class="sxs-lookup"><span data-stu-id="9adbb-201">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="9adbb-202">Privado</span><span class="sxs-lookup"><span data-stu-id="9adbb-202">Private</span></span>](../../language-reference/modifiers/private.md)|<span data-ttu-id="9adbb-203">Solamente puede obtener acceso al tipo o miembro el código de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="9adbb-203">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="9adbb-204">Contra</span><span class="sxs-lookup"><span data-stu-id="9adbb-204">Protected</span></span>](../../language-reference/modifiers/protected.md)|<span data-ttu-id="9adbb-205">Solamente puede obtener acceso al tipo o miembro el código de la misma clase o de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="9adbb-205">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="9adbb-206">Friend</span><span class="sxs-lookup"><span data-stu-id="9adbb-206">Friend</span></span>](../../language-reference/modifiers/friend.md)|<span data-ttu-id="9adbb-207">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado, pero no de un ensamblado distinto.</span><span class="sxs-lookup"><span data-stu-id="9adbb-207">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|`Protected Friend`|<span data-ttu-id="9adbb-208">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado o cualquier clase derivada de otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9adbb-208">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|

<span data-ttu-id="9adbb-209">Para obtener más información, consulte [niveles de acceso en Visual Basic](../language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9adbb-209">For more information, see [Access levels in Visual Basic](../language-features/declared-elements/access-levels.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="9adbb-210">Creación de instancias de clases</span><span class="sxs-lookup"><span data-stu-id="9adbb-210">Instantiating classes</span></span>

<span data-ttu-id="9adbb-211">Para crear un objeto, debe crear una o varias instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="9adbb-211">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```vb
Dim sampleObject as New SampleClass()
```

<span data-ttu-id="9adbb-212">Una vez creadas las instancias de una clase, puede asignar valores a las propiedades y los campos de la instancia, así como invocar métodos de clase.</span><span class="sxs-lookup"><span data-stu-id="9adbb-212">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

<span data-ttu-id="9adbb-213">Para asignar valores a las propiedades durante el proceso de creación de instancias de una clase, use los inicializadores de objeto:</span><span class="sxs-lookup"><span data-stu-id="9adbb-213">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="9adbb-214">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="9adbb-214">For more information, see:</span></span>

- [<span data-ttu-id="9adbb-215">New Operator (Nuevo operador)</span><span class="sxs-lookup"><span data-stu-id="9adbb-215">New Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="9adbb-216">Inicializadores de objeto: tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="9adbb-216">Object Initializers: Named and Anonymous Types</span></span>](../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a><span data-ttu-id="9adbb-217">Clases y miembros compartidos</span><span class="sxs-lookup"><span data-stu-id="9adbb-217">Shared classes and members</span></span>

 <span data-ttu-id="9adbb-218">Un miembro compartido de la clase es una propiedad, un procedimiento o un campo que comparten todas las instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="9adbb-218">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

 <span data-ttu-id="9adbb-219">Para definir un miembro compartido:</span><span class="sxs-lookup"><span data-stu-id="9adbb-219">To define a shared member:</span></span>

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 <span data-ttu-id="9adbb-220">Para tener acceso al miembro compartido, use el nombre de la clase sin crear un objeto de esta clase:</span><span class="sxs-lookup"><span data-stu-id="9adbb-220">To access the shared member, use the name of the class without creating an object of this class:</span></span>

```vb
MsgBox(SampleClass.SampleString)
```

 <span data-ttu-id="9adbb-221">Los módulos compartidos de Visual Basic solo tienen miembros compartidos y no se pueden crear instancias de ellos.</span><span class="sxs-lookup"><span data-stu-id="9adbb-221">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="9adbb-222">Los miembros compartidos tampoco pueden tener acceso a propiedades, campos o métodos no compartidos</span><span class="sxs-lookup"><span data-stu-id="9adbb-222">Shared members also cannot access non-shared properties, fields or methods</span></span>

 <span data-ttu-id="9adbb-223">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="9adbb-223">For more information, see:</span></span>

- [<span data-ttu-id="9adbb-224">Compartido</span><span class="sxs-lookup"><span data-stu-id="9adbb-224">Shared</span></span>](../../language-reference/modifiers/shared.md)
- [<span data-ttu-id="9adbb-225">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="9adbb-225">Module Statement</span></span>](../../language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a><span data-ttu-id="9adbb-226">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="9adbb-226">Anonymous types</span></span>

<span data-ttu-id="9adbb-227">Los tipos anónimos permiten crear objetos sin escribir una definición de clase para el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="9adbb-227">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="9adbb-228">En su lugar, el compilador genera una clase.</span><span class="sxs-lookup"><span data-stu-id="9adbb-228">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="9adbb-229">La clase no tiene ningún nombre que se pueda usar y contiene las propiedades especificadas al declarar el objeto.</span><span class="sxs-lookup"><span data-stu-id="9adbb-229">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="9adbb-230">Para crear una instancia de un tipo anónimo:</span><span class="sxs-lookup"><span data-stu-id="9adbb-230">To create an instance of an anonymous type:</span></span>

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="9adbb-231">Para obtener más información, consulte: [Tipos anónimos](../language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="9adbb-231">For more information, see: [Anonymous Types](../language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="9adbb-232">Herencia</span><span class="sxs-lookup"><span data-stu-id="9adbb-232">Inheritance</span></span>

<span data-ttu-id="9adbb-233">La herencia permite crear una nueva clase que reutiliza, extiende y modifica el comportamiento que se define en otra clase.</span><span class="sxs-lookup"><span data-stu-id="9adbb-233">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="9adbb-234">La clase cuyos miembros se heredan se denomina *clase base* y la clase que hereda esos miembros se denomina *clase derivada*.</span><span class="sxs-lookup"><span data-stu-id="9adbb-234">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="9adbb-235">Sin embargo, todas las clases de Visual Basic heredan implícitamente de la <xref:System.Object> clase que admite la jerarquía de clases .net y proporciona servicios de bajo nivel a todas las clases.</span><span class="sxs-lookup"><span data-stu-id="9adbb-235">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="9adbb-236">Visual Basic no admite la herencia múltiple.</span><span class="sxs-lookup"><span data-stu-id="9adbb-236">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="9adbb-237">Es decir, solo puede especificar una clase base para una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="9adbb-237">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="9adbb-238">Para heredar de una clase base:</span><span class="sxs-lookup"><span data-stu-id="9adbb-238">To inherit from a base class:</span></span>

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

<span data-ttu-id="9adbb-239">De forma predeterminada, todas las clases se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="9adbb-239">By default all classes can be inherited.</span></span> <span data-ttu-id="9adbb-240">Sin embargo, puede especificar si una clase no se debe usar como clase base o bien crear una clase que solo se pueda usar como clase base.</span><span class="sxs-lookup"><span data-stu-id="9adbb-240">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="9adbb-241">Para especificar que una clase no se puede usar como clase base:</span><span class="sxs-lookup"><span data-stu-id="9adbb-241">To specify that a class cannot be used as a base class:</span></span>

```vb
NotInheritable Class SampleClass
End Class
```

<span data-ttu-id="9adbb-242">Para especificar que una clase se puede usar solo como clase base y no se pueden crear instancias de esta:</span><span class="sxs-lookup"><span data-stu-id="9adbb-242">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```vb
MustInherit Class BaseClass
End Class
```

<span data-ttu-id="9adbb-243">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="9adbb-243">For more information, see:</span></span>

- [<span data-ttu-id="9adbb-244">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="9adbb-244">Inherits Statement</span></span>](../../language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="9adbb-245">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="9adbb-245">NotInheritable</span></span>](../../language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="9adbb-246">MustInherit</span><span class="sxs-lookup"><span data-stu-id="9adbb-246">MustInherit</span></span>](../../language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a><span data-ttu-id="9adbb-247">Reemplazar miembros</span><span class="sxs-lookup"><span data-stu-id="9adbb-247">Overriding members</span></span>

<span data-ttu-id="9adbb-248">De forma predeterminada, una clase derivada hereda todos los miembros de su clase base.</span><span class="sxs-lookup"><span data-stu-id="9adbb-248">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="9adbb-249">Si desea cambiar el comportamiento del miembro heredado, debe invalidarlo.</span><span class="sxs-lookup"><span data-stu-id="9adbb-249">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="9adbb-250">Es decir, se puede definir una nueva implementación del método, la propiedad o el evento en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="9adbb-250">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="9adbb-251">Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:</span><span class="sxs-lookup"><span data-stu-id="9adbb-251">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="9adbb-252">Modificador de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9adbb-252">Visual Basic Modifier</span></span>|<span data-ttu-id="9adbb-253">Definición</span><span class="sxs-lookup"><span data-stu-id="9adbb-253">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="9adbb-254">Overridable</span><span class="sxs-lookup"><span data-stu-id="9adbb-254">Overridable</span></span>](../../language-reference/modifiers/overridable.md)|<span data-ttu-id="9adbb-255">Permite invalidar un miembro de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="9adbb-255">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="9adbb-256">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="9adbb-256">Overrides</span></span>](../../language-reference/modifiers/overrides.md)|<span data-ttu-id="9adbb-257">Invalida un miembro virtual (invalidable) definido en la clase base.</span><span class="sxs-lookup"><span data-stu-id="9adbb-257">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="9adbb-258">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="9adbb-258">NotOverridable</span></span>](../../language-reference/modifiers/notoverridable.md)|<span data-ttu-id="9adbb-259">Impide que un miembro se invalide en una clase heredera.</span><span class="sxs-lookup"><span data-stu-id="9adbb-259">Prevents a member from being overridden in an inheriting class.</span></span>|
|[<span data-ttu-id="9adbb-260">MustOverride</span><span class="sxs-lookup"><span data-stu-id="9adbb-260">MustOverride</span></span>](../../language-reference/modifiers/mustoverride.md)|<span data-ttu-id="9adbb-261">Requiere que se invalide un miembro de clase en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="9adbb-261">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="9adbb-262">Shadows</span><span class="sxs-lookup"><span data-stu-id="9adbb-262">Shadows</span></span>](../../language-reference/modifiers/shadows.md)|<span data-ttu-id="9adbb-263">Oculta un miembro heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="9adbb-263">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="9adbb-264">Interfaces</span><span class="sxs-lookup"><span data-stu-id="9adbb-264">Interfaces</span></span>

<span data-ttu-id="9adbb-265">Las interfaces, como las clases, definen un conjunto de propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="9adbb-265">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="9adbb-266">Pero de forma contraria a las clases, las interfaces no proporcionan implementación.</span><span class="sxs-lookup"><span data-stu-id="9adbb-266">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="9adbb-267">Se implementan como clases y se definen como entidades separadas de las clases.</span><span class="sxs-lookup"><span data-stu-id="9adbb-267">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="9adbb-268">Una interfaz representa un contrato, en el cual una clase que implementa una interfaz debe implementar cualquier aspecto de dicha interfaz exactamente como esté definido.</span><span class="sxs-lookup"><span data-stu-id="9adbb-268">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="9adbb-269">Para definir una interfaz:</span><span class="sxs-lookup"><span data-stu-id="9adbb-269">To define an interface:</span></span>

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

<span data-ttu-id="9adbb-270">Para implementar una interfaz en una clase:</span><span class="sxs-lookup"><span data-stu-id="9adbb-270">To implement an interface in a class:</span></span>

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

<span data-ttu-id="9adbb-271">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="9adbb-271">For more information, see:</span></span>

- [<span data-ttu-id="9adbb-272">Interfaces</span><span class="sxs-lookup"><span data-stu-id="9adbb-272">Interfaces</span></span>](../language-features/interfaces/index.md)
- [<span data-ttu-id="9adbb-273">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="9adbb-273">Interface Statement</span></span>](../../language-reference/statements/interface-statement.md)
- [<span data-ttu-id="9adbb-274">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="9adbb-274">Implements Statement</span></span>](../../language-reference/statements/implements-statement.md)

## <a name="generics"></a><span data-ttu-id="9adbb-275">Genéricos</span><span class="sxs-lookup"><span data-stu-id="9adbb-275">Generics</span></span>

<span data-ttu-id="9adbb-276">Las clases, las estructuras, las interfaces y los métodos de .NET pueden incluir *parámetros de tipo* que definen los tipos de objetos que pueden almacenar o usar.</span><span class="sxs-lookup"><span data-stu-id="9adbb-276">Classes, structures, interfaces and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="9adbb-277">El ejemplo más común de elementos genéricos es una colección, donde se puede especificar el tipo de objetos que se va a almacenar en una colección.</span><span class="sxs-lookup"><span data-stu-id="9adbb-277">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="9adbb-278">Para definir una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="9adbb-278">To define a generic class:</span></span>

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

<span data-ttu-id="9adbb-279">Para crear una instancia de una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="9adbb-279">To create an instance of a generic class:</span></span>

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

<span data-ttu-id="9adbb-280">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="9adbb-280">For more information, see:</span></span>

- [<span data-ttu-id="9adbb-281">Genéricos</span><span class="sxs-lookup"><span data-stu-id="9adbb-281">Generics</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="9adbb-282">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9adbb-282">Generic Types in Visual Basic</span></span>](../language-features/data-types/generic-types.md)

## <a name="delegates"></a><span data-ttu-id="9adbb-283">Delegados</span><span class="sxs-lookup"><span data-stu-id="9adbb-283">Delegates</span></span>

 <span data-ttu-id="9adbb-284">Un *delegado* es un tipo que define una firma de método y que puede proporcionar una referencia a cualquier método con una firma compatible.</span><span class="sxs-lookup"><span data-stu-id="9adbb-284">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="9adbb-285">Puede invocar (o llamar) al método a través del delegado.</span><span class="sxs-lookup"><span data-stu-id="9adbb-285">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="9adbb-286">Los delegados se utilizan para pasar métodos como argumentos a otros métodos.</span><span class="sxs-lookup"><span data-stu-id="9adbb-286">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="9adbb-287">Los controladores de eventos no son más que métodos que se invocan a través de delegados.</span><span class="sxs-lookup"><span data-stu-id="9adbb-287">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="9adbb-288">Para obtener más información sobre el uso de delegados en el control de eventos, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="9adbb-288">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="9adbb-289">Para crear un delegado:</span><span class="sxs-lookup"><span data-stu-id="9adbb-289">To create a delegate:</span></span>

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

<span data-ttu-id="9adbb-290">Para crear una referencia a un método que coincida con la firma especificada por el delegado:</span><span class="sxs-lookup"><span data-stu-id="9adbb-290">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

<span data-ttu-id="9adbb-291">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="9adbb-291">For more information, see:</span></span>

- [<span data-ttu-id="9adbb-292">Delegados</span><span class="sxs-lookup"><span data-stu-id="9adbb-292">Delegates</span></span>](../language-features/delegates/index.md)
- [<span data-ttu-id="9adbb-293">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="9adbb-293">Delegate Statement</span></span>](../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="9adbb-294">Operador AddressOf</span><span class="sxs-lookup"><span data-stu-id="9adbb-294">AddressOf Operator</span></span>](../../language-reference/operators/addressof-operator.md)

## <a name="see-also"></a><span data-ttu-id="9adbb-295">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9adbb-295">See also</span></span>

- [<span data-ttu-id="9adbb-296">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9adbb-296">Visual Basic Programming Guide</span></span>](../index.md)
