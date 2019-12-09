---
title: Programación orientada a objetos (C#)
ms.date: 07/20/2015
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 1de150f6eb4be893ca1afce6bd16afde5752c986
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711819"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="ca270-102">Programación orientada a objetos (C#)</span><span class="sxs-lookup"><span data-stu-id="ca270-102">Object-Oriented Programming (C#)</span></span>

<span data-ttu-id="ca270-103">C# proporciona compatibilidad completa para la programación orientada a objetos incluida la encapsulación, la herencia y el polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="ca270-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

<span data-ttu-id="ca270-104">La *encapsulación* significa que un grupo de propiedades, métodos y otros miembros relacionados se tratan como una sola unidad u objeto.</span><span class="sxs-lookup"><span data-stu-id="ca270-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

<span data-ttu-id="ca270-105">La *herencia* describe la posibilidad de crear nuevas clases basadas en una clase existente.</span><span class="sxs-lookup"><span data-stu-id="ca270-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

<span data-ttu-id="ca270-106">El *polimorfismo* significa que puede tener múltiples clases que se pueden usar de manera intercambiable, aunque cada clase implementa las mismas propiedades o los mismos métodos de maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="ca270-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

<span data-ttu-id="ca270-107">En esta sección se describen los conceptos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ca270-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="ca270-108">Clases y objetos</span><span class="sxs-lookup"><span data-stu-id="ca270-108">Classes and Objects</span></span>](#Classes)

  - [<span data-ttu-id="ca270-109">Miembros de clases</span><span class="sxs-lookup"><span data-stu-id="ca270-109">Class Members</span></span>](#Members)

    - [<span data-ttu-id="ca270-110">Propiedades y campos</span><span class="sxs-lookup"><span data-stu-id="ca270-110">Properties and Fields</span></span>](#Properties)

    - [<span data-ttu-id="ca270-111">Métodos</span><span class="sxs-lookup"><span data-stu-id="ca270-111">Methods</span></span>](#Methods)

    - [<span data-ttu-id="ca270-112">Constructores</span><span class="sxs-lookup"><span data-stu-id="ca270-112">Constructors</span></span>](#Constructors)

    - [<span data-ttu-id="ca270-113">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="ca270-113">Finalizers</span></span>](#Finalizers)

    - [<span data-ttu-id="ca270-114">Eventos</span><span class="sxs-lookup"><span data-stu-id="ca270-114">Events</span></span>](#Events)

    - [<span data-ttu-id="ca270-115">Clases anidadas</span><span class="sxs-lookup"><span data-stu-id="ca270-115">Nested Classes</span></span>](#NestedClasses)

  - [<span data-ttu-id="ca270-116">Modificadores y niveles de acceso</span><span class="sxs-lookup"><span data-stu-id="ca270-116">Access Modifiers and Access Levels</span></span>](#AccessModifiers)

  - [<span data-ttu-id="ca270-117">Creación de instancias de las clases</span><span class="sxs-lookup"><span data-stu-id="ca270-117">Instantiating Classes</span></span>](#InstantiatingClasses)

  - [<span data-ttu-id="ca270-118">Clases y miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="ca270-118">Static Classes and Members</span></span>](#Static)

  - [<span data-ttu-id="ca270-119">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="ca270-119">Anonymous Types</span></span>](#AnonymousTypes)

- [<span data-ttu-id="ca270-120">Herencia</span><span class="sxs-lookup"><span data-stu-id="ca270-120">Inheritance</span></span>](#Inheritance)

  - [<span data-ttu-id="ca270-121">Reemplazar miembros</span><span class="sxs-lookup"><span data-stu-id="ca270-121">Overriding Members</span></span>](#Overriding)

- [<span data-ttu-id="ca270-122">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ca270-122">Interfaces</span></span>](#Interfaces)

- [<span data-ttu-id="ca270-123">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ca270-123">Generics</span></span>](#Generics)

- [<span data-ttu-id="ca270-124">Delegados</span><span class="sxs-lookup"><span data-stu-id="ca270-124">Delegates</span></span>](#Delegates)

## <a name="Classes"></a> <span data-ttu-id="ca270-125">Clases y objetos</span><span class="sxs-lookup"><span data-stu-id="ca270-125">Classes and Objects</span></span>

<span data-ttu-id="ca270-126">Los términos *clase* y *objeto* se usan a veces indistintamente pero, en realidad, las clases describen el *tipo* de los objetos, mientras que los objetos son *instancias* de clases que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="ca270-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="ca270-127">Así, la acción de crear un objeto se denomina *creación de instancias*.</span><span class="sxs-lookup"><span data-stu-id="ca270-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="ca270-128">Con la analogía de plano, una clase es un plano y un objeto es un edificio construido a partir de ese plano.</span><span class="sxs-lookup"><span data-stu-id="ca270-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="ca270-129">Para definir una clase:</span><span class="sxs-lookup"><span data-stu-id="ca270-129">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="ca270-130">C# también proporciona una versión ligera de las clases denominadas *estructuras*, que resultan útiles cuando es necesario crear una matriz grande de objetos y no quiere usar demasiada memoria para ello.</span><span class="sxs-lookup"><span data-stu-id="ca270-130">C# also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="ca270-131">Para definir una estructura:</span><span class="sxs-lookup"><span data-stu-id="ca270-131">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="ca270-132">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="ca270-132">For more information, see:</span></span>

- [<span data-ttu-id="ca270-133">class</span><span class="sxs-lookup"><span data-stu-id="ca270-133">class</span></span>](../../language-reference/keywords/class.md)

- [<span data-ttu-id="ca270-134">struct</span><span class="sxs-lookup"><span data-stu-id="ca270-134">struct</span></span>](../../language-reference/keywords/struct.md)

### <a name="Members"></a> <span data-ttu-id="ca270-135">Miembros de clases</span><span class="sxs-lookup"><span data-stu-id="ca270-135">Class Members</span></span>

<span data-ttu-id="ca270-136">Cada clase puede tener distintos *miembros de clase*, entre los que se incluyen las propiedades que describen los datos de clase, los métodos que definen el comportamiento de la clase y los eventos que proporcionan comunicación entre distintos objetos y clases.</span><span class="sxs-lookup"><span data-stu-id="ca270-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="Properties"></a> <span data-ttu-id="ca270-137">Propiedades y campos</span><span class="sxs-lookup"><span data-stu-id="ca270-137">Properties and Fields</span></span>

<span data-ttu-id="ca270-138">Los campos y propiedades representan información que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="ca270-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="ca270-139">Los campos se parecen a las variables ya que se pueden leer y establecer directamente.</span><span class="sxs-lookup"><span data-stu-id="ca270-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="ca270-140">Para definir un campo:</span><span class="sxs-lookup"><span data-stu-id="ca270-140">To define a field:</span></span>

```csharp
class SampleClass
{
    public string sampleField;
}
```

<span data-ttu-id="ca270-141">Las propiedades tienen procedimientos get y set, que proporcionan un mayor control sobre la forma en que se establecen o devuelven los valores.</span><span class="sxs-lookup"><span data-stu-id="ca270-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="ca270-142">C# le permite crear un campo privado para almacenar el valor de propiedad o usar las denominadas propiedades de implementación automática que crean este campo en segundo plano automáticamente y proporcionan la lógica básica para los procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ca270-142">C# allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="ca270-143">Para definir una propiedad implementada automáticamente:</span><span class="sxs-lookup"><span data-stu-id="ca270-143">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="ca270-144">Si necesita realizar algunas operaciones adicionales para leer y escribir el valor de propiedad, defina un campo para almacenar el valor de propiedad y proporcione la lógica básica para almacenarlo y recuperar lo:</span><span class="sxs-lookup"><span data-stu-id="ca270-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get { return _sample; }
        // Store the value in the field.
        set { _sample = value; }
    }
}
```

<span data-ttu-id="ca270-145">La mayoría de las propiedades tienen métodos o procedimientos tanto para establecer como para obtener el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ca270-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="ca270-146">Sin embargo, se pueden crear propiedades de solo lectura o solo escritura para restringir su modificación o lectura.</span><span class="sxs-lookup"><span data-stu-id="ca270-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="ca270-147">En C#, se puede omitir el método de propiedad `get` o `set`.</span><span class="sxs-lookup"><span data-stu-id="ca270-147">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="ca270-148">En cambio, las propiedades implementadas automáticamente no pueden ser de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="ca270-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="ca270-149">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="ca270-149">For more information, see:</span></span>

- [<span data-ttu-id="ca270-150">get</span><span class="sxs-lookup"><span data-stu-id="ca270-150">get</span></span>](../../language-reference/keywords/get.md)

- [<span data-ttu-id="ca270-151">set</span><span class="sxs-lookup"><span data-stu-id="ca270-151">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="Methods"></a> <span data-ttu-id="ca270-152">Métodos</span><span class="sxs-lookup"><span data-stu-id="ca270-152">Methods</span></span>

<span data-ttu-id="ca270-153">Un *método* es una acción que un objeto puede realizar.</span><span class="sxs-lookup"><span data-stu-id="ca270-153">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="ca270-154">Para definir un método de una clase:</span><span class="sxs-lookup"><span data-stu-id="ca270-154">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="ca270-155">Una clase puede tener varias implementaciones o *sobrecargas* del mismo método que se diferencian en el número de parámetros o de tipos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="ca270-155">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="ca270-156">Para sobrecargar un método:</span><span class="sxs-lookup"><span data-stu-id="ca270-156">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {}
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="ca270-157">En la mayoría de los casos, un método se declara dentro de una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="ca270-157">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="ca270-158">En cambio, C# también admite los *métodos de extensión*, que le permiten agregar métodos a una clase existente fuera de la definición de la clase actual.</span><span class="sxs-lookup"><span data-stu-id="ca270-158">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="ca270-159">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="ca270-159">For more information, see:</span></span>

- [<span data-ttu-id="ca270-160">Métodos</span><span class="sxs-lookup"><span data-stu-id="ca270-160">Methods</span></span>](../classes-and-structs/methods.md)

- [<span data-ttu-id="ca270-161">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="ca270-161">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="Constructors"></a> <span data-ttu-id="ca270-162">Constructores</span><span class="sxs-lookup"><span data-stu-id="ca270-162">Constructors</span></span>

<span data-ttu-id="ca270-163">Los constructores son métodos de clase que se ejecutan automáticamente cuando se crea un objeto de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="ca270-163">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="ca270-164">Normalmente, los constructores inicializan los miembros de datos del nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="ca270-164">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="ca270-165">Un constructor solo puede ejecutarse una vez cuando se crea una clase.</span><span class="sxs-lookup"><span data-stu-id="ca270-165">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="ca270-166">Además, el código del constructor siempre se ejecuta antes que cualquier otro código en una clase.</span><span class="sxs-lookup"><span data-stu-id="ca270-166">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="ca270-167">Sin embargo, puede crear varias sobrecargas del constructor de la misma forma que para cualquier otro método.</span><span class="sxs-lookup"><span data-stu-id="ca270-167">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="ca270-168">Para definir un constructor para una clase:</span><span class="sxs-lookup"><span data-stu-id="ca270-168">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="ca270-169">Para obtener más información, vea [Constructores](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="ca270-169">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="Finalizers"></a> <span data-ttu-id="ca270-170">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="ca270-170">Finalizers</span></span>

<span data-ttu-id="ca270-171">Los finalizadores se usan para destruir instancias de clases.</span><span class="sxs-lookup"><span data-stu-id="ca270-171">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="ca270-172">En .NET Framework, el recolector de elementos no utilizados administra automáticamente la asignación y la liberación de memoria para los objetos administrados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ca270-172">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="ca270-173">En cambio, es posible que aún se necesiten finalizadores para limpiar cualquiera de los recursos no administrados creados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ca270-173">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="ca270-174">Solo puede haber un finalizador para una clase.</span><span class="sxs-lookup"><span data-stu-id="ca270-174">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="ca270-175">Para obtener más información sobre los finalizadores y la recolección de elementos no utilizados en .NET Framework, vea [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="ca270-175">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="Events"></a> <span data-ttu-id="ca270-176">Eventos</span><span class="sxs-lookup"><span data-stu-id="ca270-176">Events</span></span>

<span data-ttu-id="ca270-177">Cuando ocurre algo interesante, los eventos habilitan una clase u objeto para notificarlo a otras clases u objetos.</span><span class="sxs-lookup"><span data-stu-id="ca270-177">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="ca270-178">La clase que envía (o genera) el evento recibe el nombre de *publicador* y las clases que reciben (o controlan) el evento se denominan *suscriptores*.</span><span class="sxs-lookup"><span data-stu-id="ca270-178">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="ca270-179">Para obtener más información sobre los eventos y la forma en que se generan y controlan, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="ca270-179">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="ca270-180">Para declarar un evento en una clase, use la palabra clave [event](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="ca270-180">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="ca270-181">Para generar un evento, invoque al delegado de eventos.</span><span class="sxs-lookup"><span data-stu-id="ca270-181">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="ca270-182">Para suscribirse a un evento, use el operador `+=`; para anular la suscripción de un evento, use el operador `-=`.</span><span class="sxs-lookup"><span data-stu-id="ca270-182">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="NestedClasses"></a> <span data-ttu-id="ca270-183">Clases anidadas</span><span class="sxs-lookup"><span data-stu-id="ca270-183">Nested Classes</span></span>

<span data-ttu-id="ca270-184">Una clase definida dentro de otra se denomina *anidada*.</span><span class="sxs-lookup"><span data-stu-id="ca270-184">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="ca270-185">De forma predeterminada, una clase anidada es privada.</span><span class="sxs-lookup"><span data-stu-id="ca270-185">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="ca270-186">Para crear una instancia de la clase anidada, use el nombre de la clase contenedora seguido de un punto y seguido, a continuación, del nombre de la clase anidada:</span><span class="sxs-lookup"><span data-stu-id="ca270-186">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="AccessModifiers"></a> <span data-ttu-id="ca270-187">Modificadores y niveles de acceso</span><span class="sxs-lookup"><span data-stu-id="ca270-187">Access Modifiers and Access Levels</span></span>

<span data-ttu-id="ca270-188">Todas las clases y miembros de clase pueden especificar el nivel de acceso que proporcionan a otras clases mediante los *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="ca270-188">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="ca270-189">Están disponibles los siguientes modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="ca270-189">The following access modifiers are available:</span></span>

|<span data-ttu-id="ca270-190">Modificador de C#</span><span class="sxs-lookup"><span data-stu-id="ca270-190">C# Modifier</span></span>|<span data-ttu-id="ca270-191">Definición</span><span class="sxs-lookup"><span data-stu-id="ca270-191">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="ca270-192">public</span><span class="sxs-lookup"><span data-stu-id="ca270-192">public</span></span>](../../language-reference/keywords/public.md)|<span data-ttu-id="ca270-193">Puede obtener acceso al tipo o miembro cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a éste.</span><span class="sxs-lookup"><span data-stu-id="ca270-193">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="ca270-194">private</span><span class="sxs-lookup"><span data-stu-id="ca270-194">private</span></span>](../../language-reference/keywords/private.md)|<span data-ttu-id="ca270-195">Solamente puede obtener acceso al tipo o miembro el código de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="ca270-195">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="ca270-196">protected</span><span class="sxs-lookup"><span data-stu-id="ca270-196">protected</span></span>](../../language-reference/keywords/protected.md)|<span data-ttu-id="ca270-197">Solamente puede obtener acceso al tipo o miembro el código de la misma clase o de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="ca270-197">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="ca270-198">internal</span><span class="sxs-lookup"><span data-stu-id="ca270-198">internal</span></span>](../../language-reference/keywords/internal.md)|<span data-ttu-id="ca270-199">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado, pero no de un ensamblado distinto.</span><span class="sxs-lookup"><span data-stu-id="ca270-199">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="ca270-200">protected internal</span><span class="sxs-lookup"><span data-stu-id="ca270-200">protected internal</span></span>](../../language-reference/keywords/protected-internal.md)|<span data-ttu-id="ca270-201">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado o cualquier clase derivada de otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ca270-201">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="ca270-202">private protected</span><span class="sxs-lookup"><span data-stu-id="ca270-202">private protected</span></span>](../../language-reference/keywords/private-protected.md)|<span data-ttu-id="ca270-203">Un código de la misma clase o de una clase derivada dentro del ensamblado de clase base puede acceder al tipo o miembro en cuestión.</span><span class="sxs-lookup"><span data-stu-id="ca270-203">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="ca270-204">Para obtener más información, consulte [Modificadores de acceso](../classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="ca270-204">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="InstantiatingClasses"></a> <span data-ttu-id="ca270-205">Creación de instancias de las clases</span><span class="sxs-lookup"><span data-stu-id="ca270-205">Instantiating Classes</span></span>

<span data-ttu-id="ca270-206">Para crear un objeto, debe crear una o varias instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="ca270-206">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="ca270-207">Una vez creadas las instancias de una clase, puede asignar valores a las propiedades y los campos de la instancia, así como invocar métodos de clase.</span><span class="sxs-lookup"><span data-stu-id="ca270-207">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="ca270-208">Para asignar valores a las propiedades durante el proceso de creación de instancias de una clase, use los inicializadores de objeto:</span><span class="sxs-lookup"><span data-stu-id="ca270-208">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="ca270-209">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="ca270-209">For more information, see:</span></span>

- [<span data-ttu-id="ca270-210">new (operador)</span><span class="sxs-lookup"><span data-stu-id="ca270-210">new Operator</span></span>](../../language-reference/operators/new-operator.md)

- [<span data-ttu-id="ca270-211">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="ca270-211">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="Static"></a> <span data-ttu-id="ca270-212">Clases y miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="ca270-212">Static Classes and Members</span></span>

<span data-ttu-id="ca270-213">Un miembro estático de la clase es una propiedad, un procedimiento o un campo que comparten todas las instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="ca270-213">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="ca270-214">Para definir un miembro estático:</span><span class="sxs-lookup"><span data-stu-id="ca270-214">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="ca270-215">Para obtener acceso al miembro estático, use el nombre de la clase sin crear un objeto perteneciente a esta:</span><span class="sxs-lookup"><span data-stu-id="ca270-215">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="ca270-216">Las clases estáticas en C# solo tienen miembros estáticos y no se puede crear una instancia de ellas.</span><span class="sxs-lookup"><span data-stu-id="ca270-216">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="ca270-217">Además, los miembros estáticos no pueden tener acceso a las propiedades, los campos o los métodos no estáticos.</span><span class="sxs-lookup"><span data-stu-id="ca270-217">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="ca270-218">Para obtener más información, vea: [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="ca270-218">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="AnonymousTypes"></a> <span data-ttu-id="ca270-219">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="ca270-219">Anonymous Types</span></span>

<span data-ttu-id="ca270-220">Los tipos anónimos permiten crear objetos sin escribir una definición de clase para el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="ca270-220">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="ca270-221">En su lugar, el compilador genera una clase.</span><span class="sxs-lookup"><span data-stu-id="ca270-221">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="ca270-222">La clase no tiene ningún nombre que se pueda usar y contiene las propiedades especificadas al declarar el objeto.</span><span class="sxs-lookup"><span data-stu-id="ca270-222">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="ca270-223">Para crear una instancia de un tipo anónimo:</span><span class="sxs-lookup"><span data-stu-id="ca270-223">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="ca270-224">Para obtener más información, consulte: [Tipos anónimos](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="ca270-224">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="Inheritance"></a> <span data-ttu-id="ca270-225">Herencia</span><span class="sxs-lookup"><span data-stu-id="ca270-225">Inheritance</span></span>

<span data-ttu-id="ca270-226">La herencia permite crear una nueva clase que reutiliza, extiende y modifica el comportamiento que se define en otra clase.</span><span class="sxs-lookup"><span data-stu-id="ca270-226">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="ca270-227">La clase cuyos miembros se heredan se denomina *clase base* y la clase que hereda esos miembros se denomina *clase derivada*.</span><span class="sxs-lookup"><span data-stu-id="ca270-227">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="ca270-228">En cambio, todas las clases de C# heredan implícitamente de la clase <xref:System.Object> que admite la jerarquía de clases .NET y proporciona servicios de bajo nivel a todas las clases.</span><span class="sxs-lookup"><span data-stu-id="ca270-228">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="ca270-229">C# no admite la herencia múltiple.</span><span class="sxs-lookup"><span data-stu-id="ca270-229">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="ca270-230">Es decir, solo puede especificar una clase base para una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="ca270-230">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="ca270-231">Para heredar de una clase base:</span><span class="sxs-lookup"><span data-stu-id="ca270-231">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="ca270-232">De forma predeterminada, todas las clases se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="ca270-232">By default all classes can be inherited.</span></span> <span data-ttu-id="ca270-233">Sin embargo, puede especificar si una clase no se debe usar como clase base o bien crear una clase que solo se pueda usar como clase base.</span><span class="sxs-lookup"><span data-stu-id="ca270-233">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="ca270-234">Para especificar que una clase no se puede usar como clase base:</span><span class="sxs-lookup"><span data-stu-id="ca270-234">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="ca270-235">Para especificar que una clase se puede usar solo como clase base y no se pueden crear instancias de esta:</span><span class="sxs-lookup"><span data-stu-id="ca270-235">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="ca270-236">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="ca270-236">For more information, see:</span></span>

- [<span data-ttu-id="ca270-237">sealed</span><span class="sxs-lookup"><span data-stu-id="ca270-237">sealed</span></span>](../../language-reference/keywords/sealed.md)

- [<span data-ttu-id="ca270-238">abstract</span><span class="sxs-lookup"><span data-stu-id="ca270-238">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="Overriding"></a> <span data-ttu-id="ca270-239">Reemplazar miembros</span><span class="sxs-lookup"><span data-stu-id="ca270-239">Overriding Members</span></span>

<span data-ttu-id="ca270-240">De forma predeterminada, una clase derivada hereda todos los miembros de su clase base.</span><span class="sxs-lookup"><span data-stu-id="ca270-240">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="ca270-241">Si desea cambiar el comportamiento del miembro heredado, debe invalidarlo.</span><span class="sxs-lookup"><span data-stu-id="ca270-241">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="ca270-242">Es decir, se puede definir una nueva implementación del método, la propiedad o el evento en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="ca270-242">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="ca270-243">Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:</span><span class="sxs-lookup"><span data-stu-id="ca270-243">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="ca270-244">Modificador de C#</span><span class="sxs-lookup"><span data-stu-id="ca270-244">C# Modifier</span></span>|<span data-ttu-id="ca270-245">Definición</span><span class="sxs-lookup"><span data-stu-id="ca270-245">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="ca270-246">virtual</span><span class="sxs-lookup"><span data-stu-id="ca270-246">virtual</span></span>](../../language-reference/keywords/virtual.md)|<span data-ttu-id="ca270-247">Permite invalidar un miembro de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="ca270-247">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="ca270-248">override</span><span class="sxs-lookup"><span data-stu-id="ca270-248">override</span></span>](../../language-reference/keywords/override.md)|<span data-ttu-id="ca270-249">Invalida un miembro virtual (invalidable) definido en la clase base.</span><span class="sxs-lookup"><span data-stu-id="ca270-249">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="ca270-250">abstract</span><span class="sxs-lookup"><span data-stu-id="ca270-250">abstract</span></span>](../../language-reference/keywords/abstract.md)|<span data-ttu-id="ca270-251">Requiere que se invalide un miembro de clase en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="ca270-251">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="ca270-252">new (modificador)</span><span class="sxs-lookup"><span data-stu-id="ca270-252">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md)|<span data-ttu-id="ca270-253">Oculta un miembro heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="ca270-253">Hides a member inherited from a base class</span></span>|

## <a name="Interfaces"></a> <span data-ttu-id="ca270-254">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ca270-254">Interfaces</span></span>

<span data-ttu-id="ca270-255">Las interfaces, como las clases, definen un conjunto de propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="ca270-255">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="ca270-256">Pero de forma contraria a las clases, las interfaces no proporcionan implementación.</span><span class="sxs-lookup"><span data-stu-id="ca270-256">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="ca270-257">Se implementan como clases y se definen como entidades separadas de las clases.</span><span class="sxs-lookup"><span data-stu-id="ca270-257">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="ca270-258">Una interfaz representa un contrato, en el cual una clase que implementa una interfaz debe implementar cualquier aspecto de dicha interfaz exactamente como esté definido.</span><span class="sxs-lookup"><span data-stu-id="ca270-258">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="ca270-259">Para definir una interfaz:</span><span class="sxs-lookup"><span data-stu-id="ca270-259">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="ca270-260">Para implementar una interfaz en una clase:</span><span class="sxs-lookup"><span data-stu-id="ca270-260">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="ca270-261">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="ca270-261">For more information, see:</span></span>

[<span data-ttu-id="ca270-262">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ca270-262">Interfaces</span></span>](../interfaces/index.md)

[<span data-ttu-id="ca270-263">interface</span><span class="sxs-lookup"><span data-stu-id="ca270-263">interface</span></span>](../../language-reference/keywords/interface.md)

## <a name="Generics"></a> <span data-ttu-id="ca270-264">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ca270-264">Generics</span></span>

<span data-ttu-id="ca270-265">Las clases, las estructuras, las interfaces y los métodos de .NET Framework pueden incluir *parámetros de tipo* que definen los tipos de objetos que estos pueden almacenar o usar.</span><span class="sxs-lookup"><span data-stu-id="ca270-265">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="ca270-266">El ejemplo más común de elementos genéricos es una colección, donde se puede especificar el tipo de objetos que se va a almacenar en una colección.</span><span class="sxs-lookup"><span data-stu-id="ca270-266">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="ca270-267">Para definir una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="ca270-267">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="ca270-268">Para crear una instancia de una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="ca270-268">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="ca270-269">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="ca270-269">For more information, see:</span></span>

- [<span data-ttu-id="ca270-270">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ca270-270">Generics</span></span>](../../../standard/generics/index.md)

- [<span data-ttu-id="ca270-271">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ca270-271">Generics</span></span>](../generics/index.md)

## <a name="Delegates"></a> <span data-ttu-id="ca270-272">Delegados</span><span class="sxs-lookup"><span data-stu-id="ca270-272">Delegates</span></span>

<span data-ttu-id="ca270-273">Un *delegado* es un tipo que define una firma de método y que puede proporcionar una referencia a cualquier método con una firma compatible.</span><span class="sxs-lookup"><span data-stu-id="ca270-273">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="ca270-274">Puede invocar (o llamar) al método a través del delegado.</span><span class="sxs-lookup"><span data-stu-id="ca270-274">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="ca270-275">Los delegados se utilizan para pasar métodos como argumentos a otros métodos.</span><span class="sxs-lookup"><span data-stu-id="ca270-275">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="ca270-276">Los controladores de eventos no son más que métodos que se invocan a través de delegados.</span><span class="sxs-lookup"><span data-stu-id="ca270-276">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="ca270-277">Para obtener más información sobre el uso de delegados en el control de eventos, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="ca270-277">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="ca270-278">Para crear un delegado:</span><span class="sxs-lookup"><span data-stu-id="ca270-278">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="ca270-279">Para crear una referencia a un método que coincida con la firma especificada por el delegado:</span><span class="sxs-lookup"><span data-stu-id="ca270-279">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void sampleMethod(string message)
    {
        // Add code here.
    }
    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

<span data-ttu-id="ca270-280">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="ca270-280">For more information, see:</span></span>

- [<span data-ttu-id="ca270-281">Delegados</span><span class="sxs-lookup"><span data-stu-id="ca270-281">Delegates</span></span>](../delegates/index.md)

- [<span data-ttu-id="ca270-282">delegate</span><span class="sxs-lookup"><span data-stu-id="ca270-282">delegate</span></span>](../../language-reference/builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="ca270-283">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca270-283">See also</span></span>

- [<span data-ttu-id="ca270-284">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ca270-284">C# Programming Guide</span></span>](../index.md)
