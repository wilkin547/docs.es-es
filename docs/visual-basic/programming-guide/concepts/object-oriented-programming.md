---
title: Programación orientada a objetos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: e8936eb9031ef68ea333835d8433e1ba1a45990f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655972"
---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="f62df-102">Programación orientada a objetos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f62df-102">Object-Oriented Programming (Visual Basic)</span></span>
<span data-ttu-id="f62df-103">Visual Basic proporciona compatibilidad completa para la programación orientada a objetos, incluidos la encapsulación, la herencia y el polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="f62df-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>  
  
 <span data-ttu-id="f62df-104">La *encapsulación* significa que un grupo de propiedades, métodos y otros miembros relacionados se tratan como una sola unidad u objeto.</span><span class="sxs-lookup"><span data-stu-id="f62df-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>  
  
 <span data-ttu-id="f62df-105">La *herencia* describe la posibilidad de crear nuevas clases basadas en una clase existente.</span><span class="sxs-lookup"><span data-stu-id="f62df-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>  
  
 <span data-ttu-id="f62df-106">El *polimorfismo* significa que puede tener múltiples clases que se pueden usar de manera intercambiable, aunque cada clase implementa las mismas propiedades o los mismos métodos de maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="f62df-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>  
  
 <span data-ttu-id="f62df-107">En esta sección se describen los conceptos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f62df-107">This section describes the following concepts:</span></span>  
  
-   [<span data-ttu-id="f62df-108">Clases y objetos</span><span class="sxs-lookup"><span data-stu-id="f62df-108">Classes and objects</span></span>](#classes-and-objects)  
  
    -   [<span data-ttu-id="f62df-109">Miembros de clases</span><span class="sxs-lookup"><span data-stu-id="f62df-109">Class members</span></span>](#members)  
  
         [<span data-ttu-id="f62df-110">Los campos y propiedades</span><span class="sxs-lookup"><span data-stu-id="f62df-110">Properties and fields</span></span>](#properties-and-fields)  
  
         [<span data-ttu-id="f62df-111">Métodos</span><span class="sxs-lookup"><span data-stu-id="f62df-111">Methods</span></span>](#methods)  
  
         [<span data-ttu-id="f62df-112">Constructores</span><span class="sxs-lookup"><span data-stu-id="f62df-112">Constructors</span></span>](#constructors)  
  
         [<span data-ttu-id="f62df-113">Destructores</span><span class="sxs-lookup"><span data-stu-id="f62df-113">Destructors</span></span>](#destructors)  
  
         [<span data-ttu-id="f62df-114">Eventos</span><span class="sxs-lookup"><span data-stu-id="f62df-114">Events</span></span>](#events)  
  
         [<span data-ttu-id="f62df-115">Clases anidadas</span><span class="sxs-lookup"><span data-stu-id="f62df-115">Nested classes</span></span>](#nested-classes)  
  
    -   [<span data-ttu-id="f62df-116">Modificadores de acceso y niveles de acceso</span><span class="sxs-lookup"><span data-stu-id="f62df-116">Access modifiers and access levels</span></span>](#access-modifiers-and-access-levels)  
  
    -   [<span data-ttu-id="f62df-117">Crear instancias de clases</span><span class="sxs-lookup"><span data-stu-id="f62df-117">Instantiating classes</span></span>](#instantiating-classes)  
  
    -   [<span data-ttu-id="f62df-118">Los miembros y clases compartidas</span><span class="sxs-lookup"><span data-stu-id="f62df-118">Shared classes and members</span></span>](#shared-classes-and-members)  
  
    -   <span data-ttu-id="f62df-119">[Anonymous Types](#anonymous-types) (Tipos anónimos [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="f62df-119">[Anonymous types](#anonymous-types)</span></span>  
  
-   [<span data-ttu-id="f62df-120">Herencia</span><span class="sxs-lookup"><span data-stu-id="f62df-120">Inheritance</span></span>](#inheritance)  
  
    -   [<span data-ttu-id="f62df-121">Reemplazar miembros</span><span class="sxs-lookup"><span data-stu-id="f62df-121">Overriding members</span></span>](#overriding-members)  
  
-   [<span data-ttu-id="f62df-122">Interfaces</span><span class="sxs-lookup"><span data-stu-id="f62df-122">Interfaces</span></span>](#interfaces)  
  
-   [<span data-ttu-id="f62df-123">Genéricos</span><span class="sxs-lookup"><span data-stu-id="f62df-123">Generics</span></span>](#generics)  
  
-   [<span data-ttu-id="f62df-124">Delegados</span><span class="sxs-lookup"><span data-stu-id="f62df-124">Delegates</span></span>](#delegates)  
  
## <a name="classes-and-objects"></a><span data-ttu-id="f62df-125">Clases y objetos</span><span class="sxs-lookup"><span data-stu-id="f62df-125">Classes and objects</span></span>  
<span data-ttu-id="f62df-126">Los términos *clase* y *objeto* se usan a veces indistintamente pero, en realidad, las clases describen el *tipo* de los objetos, mientras que los objetos son *instancias* de clases que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="f62df-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="f62df-127">Así, la acción de crear un objeto se denomina *creación de instancias*.</span><span class="sxs-lookup"><span data-stu-id="f62df-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="f62df-128">Con la analogía de plano, una clase es un plano y un objeto es un edificio construido a partir de ese plano.</span><span class="sxs-lookup"><span data-stu-id="f62df-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="f62df-129">Para definir una clase:</span><span class="sxs-lookup"><span data-stu-id="f62df-129">To define a class:</span></span>

```vb  
Class SampleClass
End Class
```

<span data-ttu-id="f62df-130">Visual Basic también proporciona una versión ligera de las clases denominadas *estructuras* que son útiles cuando necesite crear una matriz grande de objetos y desea consumir demasiada memoria para que.</span><span class="sxs-lookup"><span data-stu-id="f62df-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="f62df-131">Para definir una estructura:</span><span class="sxs-lookup"><span data-stu-id="f62df-131">To define a structure:</span></span>  

```vb
Structure SampleStructure
End Structure
```

<span data-ttu-id="f62df-132">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f62df-132">For more information, see:</span></span>

- [<span data-ttu-id="f62df-133">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-133">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)

- [<span data-ttu-id="f62df-134">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

### <a name="class-members"></a><span data-ttu-id="f62df-135">Miembros de la clase</span><span class="sxs-lookup"><span data-stu-id="f62df-135">Class members</span></span>
<span data-ttu-id="f62df-136">Cada clase puede tener distintos *miembros de clase*, entre los que se incluyen las propiedades que describen los datos de clase, los métodos que definen el comportamiento de la clase y los eventos que proporcionan comunicación entre distintos objetos y clases.</span><span class="sxs-lookup"><span data-stu-id="f62df-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="f62df-137">Los campos y propiedades</span><span class="sxs-lookup"><span data-stu-id="f62df-137">Properties and fields</span></span>
<span data-ttu-id="f62df-138">Los campos y propiedades representan información que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="f62df-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="f62df-139">Los campos se parecen a las variables ya que se pueden leer y establecer directamente.</span><span class="sxs-lookup"><span data-stu-id="f62df-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="f62df-140">Para definir un campo:</span><span class="sxs-lookup"><span data-stu-id="f62df-140">To define a field:</span></span>

```vb
Class SampleClass
    Public SampleField As String
End Class
```

<span data-ttu-id="f62df-141">Las propiedades tienen procedimientos get y set, que proporcionan un mayor control sobre la forma en que se establecen o devuelven los valores.</span><span class="sxs-lookup"><span data-stu-id="f62df-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="f62df-142">Visual Basic permite crear un campo privado para almacenar el valor de propiedad o usar las denominadas propiedades implementadas automáticamente que crean este campo en segundo plano automáticamente y proporcionan la lógica básica para los procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f62df-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="f62df-143">Para definir una propiedad implementada automáticamente:</span><span class="sxs-lookup"><span data-stu-id="f62df-143">To define an auto-implemented property:</span></span>

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

<span data-ttu-id="f62df-144">Si necesita realizar algunas operaciones adicionales para leer y escribir el valor de propiedad, defina un campo para almacenar el valor de propiedad y proporcione la lógica básica para almacenarlo y recuperar lo:</span><span class="sxs-lookup"><span data-stu-id="f62df-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

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

<span data-ttu-id="f62df-145">La mayoría de las propiedades tienen métodos o procedimientos tanto para establecer como para obtener el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f62df-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="f62df-146">Sin embargo, se pueden crear propiedades de solo lectura o solo escritura para restringir su modificación o lectura.</span><span class="sxs-lookup"><span data-stu-id="f62df-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="f62df-147">En Visual Basic se pueden usar las palabras clave `ReadOnly` y `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="f62df-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="f62df-148">En cambio, las propiedades implementadas automáticamente no pueden ser de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="f62df-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="f62df-149">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f62df-149">For more information, see:</span></span>
  
-   [<span data-ttu-id="f62df-150">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-150">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="f62df-151">Get (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-151">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
  
-   [<span data-ttu-id="f62df-152">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-152">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
  
-   [<span data-ttu-id="f62df-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="f62df-153">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
  
-   [<span data-ttu-id="f62df-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="f62df-154">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)  
  
#### <a name="methods"></a><span data-ttu-id="f62df-155">Métodos</span><span class="sxs-lookup"><span data-stu-id="f62df-155">Methods</span></span>  
 <span data-ttu-id="f62df-156">Un *método* es una acción que un objeto puede realizar.</span><span class="sxs-lookup"><span data-stu-id="f62df-156">A *method* is an action that an object can perform.</span></span>  

> [!NOTE]
>  <span data-ttu-id="f62df-157">En Visual Basic hay dos formas de crear un método: se usa la instrucción `Sub` si el método no devuelve un valor o bien se usa la instrucción `Function` si el método devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="f62df-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>

<span data-ttu-id="f62df-158">Para definir un método de una clase:</span><span class="sxs-lookup"><span data-stu-id="f62df-158">To define a method of a class:</span></span>

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

<span data-ttu-id="f62df-159">Una clase puede tener varias implementaciones o *sobrecargas* del mismo método que se diferencian en el número de parámetros o de tipos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f62df-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="f62df-160">Para sobrecargar un método:</span><span class="sxs-lookup"><span data-stu-id="f62df-160">To overload a method:</span></span>

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

<span data-ttu-id="f62df-161">En la mayoría de los casos, un método se declara dentro de una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="f62df-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="f62df-162">Sin embargo, Visual Basic también admite *métodos de extensión* que le permiten agregar métodos a una clase existente fuera de la definición de la clase.</span><span class="sxs-lookup"><span data-stu-id="f62df-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="f62df-163">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f62df-163">For more information, see:</span></span>

- [<span data-ttu-id="f62df-164">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-164">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  

- [<span data-ttu-id="f62df-165">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-165">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  

- [<span data-ttu-id="f62df-166">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="f62df-166">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  

- [<span data-ttu-id="f62df-167">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="f62df-167">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  

#### <a name="constructors"></a><span data-ttu-id="f62df-168">Constructores</span><span class="sxs-lookup"><span data-stu-id="f62df-168">Constructors</span></span>  
<span data-ttu-id="f62df-169">Los constructores son métodos de clase que se ejecutan automáticamente cuando se crea un objeto de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="f62df-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="f62df-170">Normalmente, los constructores inicializan los miembros de datos del nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="f62df-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="f62df-171">Un constructor solo puede ejecutarse una vez cuando se crea una clase.</span><span class="sxs-lookup"><span data-stu-id="f62df-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="f62df-172">Además, el código del constructor siempre se ejecuta antes que cualquier otro código en una clase.</span><span class="sxs-lookup"><span data-stu-id="f62df-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="f62df-173">Sin embargo, puede crear varias sobrecargas del constructor de la misma forma que para cualquier otro método.</span><span class="sxs-lookup"><span data-stu-id="f62df-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="f62df-174">Para definir un constructor para una clase:</span><span class="sxs-lookup"><span data-stu-id="f62df-174">To define a constructor for a class:</span></span>

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class 
```

<span data-ttu-id="f62df-175">Para obtener más información, consulte: [duración de los objetos: cómo los objetos son crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="f62df-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

#### <a name="destructors"></a><span data-ttu-id="f62df-176">Destructores</span><span class="sxs-lookup"><span data-stu-id="f62df-176">Destructors</span></span>
<span data-ttu-id="f62df-177">Los destructores se utilizan para destruir instancias de clases.</span><span class="sxs-lookup"><span data-stu-id="f62df-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="f62df-178">En .NET Framework, el recolector de elementos no utilizados administra automáticamente la asignación y la liberación de memoria para los objetos administrados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f62df-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="f62df-179">Sin embargo, es posible que aún se necesiten destructores para limpiar cualquiera de los recursos no administrados creados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f62df-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="f62df-180">Solo puede haber un destructor para una clase.</span><span class="sxs-lookup"><span data-stu-id="f62df-180">There can be only one destructor for a class.</span></span>

<span data-ttu-id="f62df-181">Para obtener más información sobre los destructores y la recolección de elementos no utilizados en .NET Framework, vea [Garbage Collection](../../../standard/garbage-collection/index.md) (Recolección de elementos no utilizados).</span><span class="sxs-lookup"><span data-stu-id="f62df-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="f62df-182">Eventos</span><span class="sxs-lookup"><span data-stu-id="f62df-182">Events</span></span>
<span data-ttu-id="f62df-183">Cuando ocurre algo interesante, los eventos habilitan una clase u objeto para notificarlo a otras clases u objetos.</span><span class="sxs-lookup"><span data-stu-id="f62df-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="f62df-184">La clase que envía (o genera) el evento recibe el nombre de *publicador* y las clases que reciben (o controlan) el evento se denominan *suscriptores*.</span><span class="sxs-lookup"><span data-stu-id="f62df-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="f62df-185">Para obtener más información sobre los eventos y la forma en que se generan y controlan, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f62df-185">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="f62df-186">Para declarar eventos, use la [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f62df-186">To declare events, use the [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>

- <span data-ttu-id="f62df-187">Para provocar eventos, utilice la [RaiseEvent (instrucción)](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f62df-187">To raise events, use the [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>

- <span data-ttu-id="f62df-188">Para especificar controladores de eventos mediante una manera declarativa, use la [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) instrucción y la [controla](../../../visual-basic/language-reference/statements/handles-clause.md) cláusula.</span><span class="sxs-lookup"><span data-stu-id="f62df-188">To specify event handlers using a declarative way, use the [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) statement and the [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span>

- <span data-ttu-id="f62df-189">Para poder agregar, quitar y cambiar el controlador de eventos asociado a un evento de forma dinámica, utilice el [AddHandler (instrucción)](../../../visual-basic/language-reference/statements/addhandler-statement.md) y [RemoveHandler (instrucción)](../../../visual-basic/language-reference/statements/removehandler-statement.md) junto con el [AddressOf Operador](../../../visual-basic/language-reference/operators/addressof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f62df-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="f62df-190">Clases anidadas</span><span class="sxs-lookup"><span data-stu-id="f62df-190">Nested classes</span></span>  
<span data-ttu-id="f62df-191">Una clase definida dentro de otra se denomina *anidada*.</span><span class="sxs-lookup"><span data-stu-id="f62df-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="f62df-192">De forma predeterminada, una clase anidada es privada.</span><span class="sxs-lookup"><span data-stu-id="f62df-192">By default, the nested class is private.</span></span>

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

<span data-ttu-id="f62df-193">Para crear una instancia de la clase anidada, use el nombre de la clase contenedora seguido de un punto y seguido, a continuación, del nombre de la clase anidada:</span><span class="sxs-lookup"><span data-stu-id="f62df-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="f62df-194">Modificadores de acceso y niveles de acceso</span><span class="sxs-lookup"><span data-stu-id="f62df-194">Access modifiers and access levels</span></span>  
<span data-ttu-id="f62df-195">Todas las clases y miembros de clase pueden especificar el nivel de acceso que proporcionan a otras clases mediante los *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="f62df-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="f62df-196">Están disponibles los siguientes modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="f62df-196">The following access modifiers are available:</span></span>

|<span data-ttu-id="f62df-197">Modificador de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f62df-197">Visual Basic Modifier</span></span>|<span data-ttu-id="f62df-198">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="f62df-198">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="f62df-199">Public</span><span class="sxs-lookup"><span data-stu-id="f62df-199">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)|<span data-ttu-id="f62df-200">Puede obtener acceso al tipo o miembro cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a éste.</span><span class="sxs-lookup"><span data-stu-id="f62df-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="f62df-201">Private</span><span class="sxs-lookup"><span data-stu-id="f62df-201">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)|<span data-ttu-id="f62df-202">Solamente puede obtener acceso al tipo o miembro el código de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="f62df-202">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="f62df-203">Protected</span><span class="sxs-lookup"><span data-stu-id="f62df-203">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)|<span data-ttu-id="f62df-204">Solamente puede obtener acceso al tipo o miembro el código de la misma clase o de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f62df-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="f62df-205">Friend</span><span class="sxs-lookup"><span data-stu-id="f62df-205">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)|<span data-ttu-id="f62df-206">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado, pero no de un ensamblado distinto.</span><span class="sxs-lookup"><span data-stu-id="f62df-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|`Protected Friend`|<span data-ttu-id="f62df-207">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado o cualquier clase derivada de otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f62df-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|

<span data-ttu-id="f62df-208">Para obtener más información, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f62df-208">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="f62df-209">Crear instancias de clases</span><span class="sxs-lookup"><span data-stu-id="f62df-209">Instantiating classes</span></span>  
<span data-ttu-id="f62df-210">Para crear un objeto, debe crear una o varias instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="f62df-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```vb
Dim sampleObject as New SampleClass()
```

<span data-ttu-id="f62df-211">Una vez creadas las instancias de una clase, puede asignar valores a las propiedades y los campos de la instancia, así como invocar métodos de clase.</span><span class="sxs-lookup"><span data-stu-id="f62df-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

<span data-ttu-id="f62df-212">Para asignar valores a las propiedades durante el proceso de creación de instancias de una clase, use los inicializadores de objeto:</span><span class="sxs-lookup"><span data-stu-id="f62df-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="f62df-213">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f62df-213">For more information, see:</span></span>

- [<span data-ttu-id="f62df-214">New (operador)</span><span class="sxs-lookup"><span data-stu-id="f62df-214">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)

- [<span data-ttu-id="f62df-215">Inicializadores de objeto: Tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="f62df-215">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

###  <a name="Static"></a> <span data-ttu-id="f62df-216">Clases compartidas y miembros</span><span class="sxs-lookup"><span data-stu-id="f62df-216">Shared Classes and Members</span></span>  
 <span data-ttu-id="f62df-217">Un miembro de la clase compartido es una propiedad, un procedimiento o un campo que comparten todas las instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="f62df-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>  
  
 <span data-ttu-id="f62df-218">Para definir a un miembro compartido:</span><span class="sxs-lookup"><span data-stu-id="f62df-218">To define a shared member:</span></span>  
  
```vb  
Class SampleClass  
    Public Shared SampleString As String = "Sample String"  
End Class  
```  
  
 <span data-ttu-id="f62df-219">Para obtener acceso al miembro compartido, utilice el nombre de la clase sin crear un objeto de esta clase:</span><span class="sxs-lookup"><span data-stu-id="f62df-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>  
  
```vb  
MsgBox(SampleClass.SampleString)  
```  
  
 <span data-ttu-id="f62df-220">Módulos compartidos en Visual Basic compartieron a solo miembros y no se pueden crear instancias.</span><span class="sxs-lookup"><span data-stu-id="f62df-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="f62df-221">Miembros compartidos no pueden tener acceso a propiedades no compartidos, campos o métodos</span><span class="sxs-lookup"><span data-stu-id="f62df-221">Shared members also cannot access non-shared properties, fields or methods</span></span>  
  
 <span data-ttu-id="f62df-222">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f62df-222">For more information, see:</span></span>  
  
-   [<span data-ttu-id="f62df-223">Shared</span><span class="sxs-lookup"><span data-stu-id="f62df-223">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
  
-   [<span data-ttu-id="f62df-224">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-224">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
### <a name="anonymous-types"></a><span data-ttu-id="f62df-225">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="f62df-225">Anonymous types</span></span>  
<span data-ttu-id="f62df-226">Los tipos anónimos permiten crear objetos sin escribir una definición de clase para el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f62df-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="f62df-227">En su lugar, el compilador genera una clase.</span><span class="sxs-lookup"><span data-stu-id="f62df-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="f62df-228">La clase no tiene ningún nombre que se pueda usar y contiene las propiedades especificadas al declarar el objeto.</span><span class="sxs-lookup"><span data-stu-id="f62df-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="f62df-229">Para crear una instancia de un tipo anónimo:</span><span class="sxs-lookup"><span data-stu-id="f62df-229">To create an instance of an anonymous type:</span></span>

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="f62df-230">Para obtener más información, vea: [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="f62df-230">For more information, see: [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="f62df-231">Herencia</span><span class="sxs-lookup"><span data-stu-id="f62df-231">Inheritance</span></span>
<span data-ttu-id="f62df-232">La herencia permite crear una nueva clase que reutiliza, extiende y modifica el comportamiento que se define en otra clase.</span><span class="sxs-lookup"><span data-stu-id="f62df-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="f62df-233">La clase cuyos miembros se heredan se denomina *clase base* y la clase que hereda esos miembros se denomina *clase derivada*.</span><span class="sxs-lookup"><span data-stu-id="f62df-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="f62df-234">Sin embargo, todas las clases en Visual Basic heredan implícitamente de la <xref:System.Object> clase que admite la jerarquía de clases de .NET y proporciona servicios de bajo nivel a todas las clases.</span><span class="sxs-lookup"><span data-stu-id="f62df-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
>  <span data-ttu-id="f62df-235">Visual Basic no admite la herencia múltiple.</span><span class="sxs-lookup"><span data-stu-id="f62df-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="f62df-236">Es decir, solo puede especificar una clase base para una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f62df-236">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="f62df-237">Para heredar de una clase base:</span><span class="sxs-lookup"><span data-stu-id="f62df-237">To inherit from a base class:</span></span>

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

<span data-ttu-id="f62df-238">De forma predeterminada, todas las clases se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="f62df-238">By default all classes can be inherited.</span></span> <span data-ttu-id="f62df-239">Sin embargo, puede especificar si una clase no se debe usar como clase base o bien crear una clase que solo se pueda usar como clase base.</span><span class="sxs-lookup"><span data-stu-id="f62df-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="f62df-240">Para especificar que una clase no se puede usar como clase base:</span><span class="sxs-lookup"><span data-stu-id="f62df-240">To specify that a class cannot be used as a base class:</span></span>

```vb
NotInheritable Class SampleClass
End Class
```

<span data-ttu-id="f62df-241">Para especificar que una clase se puede usar solo como clase base y no se pueden crear instancias de esta:</span><span class="sxs-lookup"><span data-stu-id="f62df-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```vb
MustInherit Class BaseClass
End Class
```

<span data-ttu-id="f62df-242">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f62df-242">For more information, see:</span></span>

- [<span data-ttu-id="f62df-243">Inherits (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-243">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)

- [<span data-ttu-id="f62df-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="f62df-244">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)

- [<span data-ttu-id="f62df-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="f62df-245">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a><span data-ttu-id="f62df-246">Reemplazar miembros</span><span class="sxs-lookup"><span data-stu-id="f62df-246">Overriding members</span></span>
<span data-ttu-id="f62df-247">De forma predeterminada, una clase derivada hereda todos los miembros de su clase base.</span><span class="sxs-lookup"><span data-stu-id="f62df-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="f62df-248">Si desea cambiar el comportamiento del miembro heredado, debe invalidarlo.</span><span class="sxs-lookup"><span data-stu-id="f62df-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="f62df-249">Es decir, se puede definir una nueva implementación del método, la propiedad o el evento en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f62df-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="f62df-250">Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:</span><span class="sxs-lookup"><span data-stu-id="f62df-250">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="f62df-251">Modificador de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f62df-251">Visual Basic Modifier</span></span>|<span data-ttu-id="f62df-252">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="f62df-252">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="f62df-253">Overridable</span><span class="sxs-lookup"><span data-stu-id="f62df-253">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)|<span data-ttu-id="f62df-254">Permite invalidar un miembro de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f62df-254">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="f62df-255">Overrides</span><span class="sxs-lookup"><span data-stu-id="f62df-255">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)|<span data-ttu-id="f62df-256">Invalida un miembro virtual (invalidable) definido en la clase base.</span><span class="sxs-lookup"><span data-stu-id="f62df-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="f62df-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="f62df-257">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)|<span data-ttu-id="f62df-258">Impide que un miembro se invalide en una clase heredera.</span><span class="sxs-lookup"><span data-stu-id="f62df-258">Prevents a member from being overridden in an inheriting class.</span></span>|
|[<span data-ttu-id="f62df-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="f62df-259">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)|<span data-ttu-id="f62df-260">Requiere que se invalide un miembro de clase en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f62df-260">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="f62df-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="f62df-261">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)|<span data-ttu-id="f62df-262">Oculta un miembro heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="f62df-262">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="f62df-263">Interfaces</span><span class="sxs-lookup"><span data-stu-id="f62df-263">Interfaces</span></span>
<span data-ttu-id="f62df-264">Las interfaces, como las clases, definen un conjunto de propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="f62df-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="f62df-265">Pero de forma contraria a las clases, las interfaces no proporcionan implementación.</span><span class="sxs-lookup"><span data-stu-id="f62df-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="f62df-266">Se implementan como clases y se definen como entidades separadas de las clases.</span><span class="sxs-lookup"><span data-stu-id="f62df-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="f62df-267">Una interfaz representa un contrato, en el cual una clase que implementa una interfaz debe implementar cualquier aspecto de dicha interfaz exactamente como esté definido.</span><span class="sxs-lookup"><span data-stu-id="f62df-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="f62df-268">Para definir una interfaz:</span><span class="sxs-lookup"><span data-stu-id="f62df-268">To define an interface:</span></span>

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

<span data-ttu-id="f62df-269">Para implementar una interfaz en una clase:</span><span class="sxs-lookup"><span data-stu-id="f62df-269">To implement an interface in a class:</span></span>

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

<span data-ttu-id="f62df-270">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f62df-270">For more information, see:</span></span>

- [<span data-ttu-id="f62df-271">Interfaces</span><span class="sxs-lookup"><span data-stu-id="f62df-271">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  

- [<span data-ttu-id="f62df-272">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-272">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  

- [<span data-ttu-id="f62df-273">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-273">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  

## <a name="generics"></a><span data-ttu-id="f62df-274">Genéricos</span><span class="sxs-lookup"><span data-stu-id="f62df-274">Generics</span></span>
<span data-ttu-id="f62df-275">Pueden incluir las clases, estructuras, interfaces y métodos de .NET *parámetros de tipo* que definen los tipos de objetos que pueden almacenar o usar.</span><span class="sxs-lookup"><span data-stu-id="f62df-275">Classes, structures, interfaces and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="f62df-276">El ejemplo más común de elementos genéricos es una colección, donde se puede especificar el tipo de objetos que se va a almacenar en una colección.</span><span class="sxs-lookup"><span data-stu-id="f62df-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>  

<span data-ttu-id="f62df-277">Para definir una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="f62df-277">To define a generic class:</span></span>

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

<span data-ttu-id="f62df-278">Para crear una instancia de una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="f62df-278">To create an instance of a generic class:</span></span>

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

<span data-ttu-id="f62df-279">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f62df-279">For more information, see:</span></span>

- [<span data-ttu-id="f62df-280">Genéricos</span><span class="sxs-lookup"><span data-stu-id="f62df-280">Generics</span></span>](~/docs/standard/generics/index.md)

- [<span data-ttu-id="f62df-281">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f62df-281">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

## <a name="delegates"></a><span data-ttu-id="f62df-282">Delegados</span><span class="sxs-lookup"><span data-stu-id="f62df-282">Delegates</span></span>
 <span data-ttu-id="f62df-283">Un *delegado* es un tipo que define una firma de método y que puede proporcionar una referencia a cualquier método con una firma compatible.</span><span class="sxs-lookup"><span data-stu-id="f62df-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="f62df-284">Puede invocar (o llamar) al método a través del delegado.</span><span class="sxs-lookup"><span data-stu-id="f62df-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="f62df-285">Los delegados se utilizan para pasar métodos como argumentos a otros métodos.</span><span class="sxs-lookup"><span data-stu-id="f62df-285">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
>  <span data-ttu-id="f62df-286">Los controladores de eventos no son más que métodos que se invocan a través de delegados.</span><span class="sxs-lookup"><span data-stu-id="f62df-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="f62df-287">Para obtener más información sobre el uso de delegados en el control de eventos, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f62df-287">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="f62df-288">Para crear un delegado:</span><span class="sxs-lookup"><span data-stu-id="f62df-288">To create a delegate:</span></span>

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

<span data-ttu-id="f62df-289">Para crear una referencia a un método que coincida con la firma especificada por el delegado:</span><span class="sxs-lookup"><span data-stu-id="f62df-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>

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

<span data-ttu-id="f62df-290">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f62df-290">For more information, see:</span></span>

- [<span data-ttu-id="f62df-291">Delegados</span><span class="sxs-lookup"><span data-stu-id="f62df-291">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)

- [<span data-ttu-id="f62df-292">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f62df-292">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [<span data-ttu-id="f62df-293">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="f62df-293">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)

## <a name="see-also"></a><span data-ttu-id="f62df-294">Vea también</span><span class="sxs-lookup"><span data-stu-id="f62df-294">See also</span></span>
 [<span data-ttu-id="f62df-295">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f62df-295">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
