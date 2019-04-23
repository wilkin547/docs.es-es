---
title: Programación orientada a objetos (C#)
ms.date: 07/20/2015
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: a7a3ce1b33d040b337087dfede90b58906c95cbd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59481176"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="d0aab-102">Programación orientada a objetos (C#)</span><span class="sxs-lookup"><span data-stu-id="d0aab-102">Object-Oriented Programming (C#)</span></span>

<span data-ttu-id="d0aab-103">C# proporciona compatibilidad completa para la programación orientada a objetos incluida la encapsulación, la herencia y el polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="d0aab-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

<span data-ttu-id="d0aab-104">La *encapsulación* significa que un grupo de propiedades, métodos y otros miembros relacionados se tratan como una sola unidad u objeto.</span><span class="sxs-lookup"><span data-stu-id="d0aab-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

<span data-ttu-id="d0aab-105">La *herencia* describe la posibilidad de crear nuevas clases basadas en una clase existente.</span><span class="sxs-lookup"><span data-stu-id="d0aab-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

<span data-ttu-id="d0aab-106">El *polimorfismo* significa que puede tener múltiples clases que se pueden usar de manera intercambiable, aunque cada clase implementa las mismas propiedades o los mismos métodos de maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="d0aab-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

<span data-ttu-id="d0aab-107">En esta sección se describen los conceptos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0aab-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="d0aab-108">Clases y objetos</span><span class="sxs-lookup"><span data-stu-id="d0aab-108">Classes and Objects</span></span>](#Classes)

  - [<span data-ttu-id="d0aab-109">Miembros de clases</span><span class="sxs-lookup"><span data-stu-id="d0aab-109">Class Members</span></span>](#Members)

        [Properties and Fields](#Properties)

        [Methods](#Methods)

        [Constructors](#Constructors)

        [Finalizers](#Finalizers)

        [Events](#Events)

        [Nested Classes](#NestedClasses)

  - [<span data-ttu-id="d0aab-110">Modificadores y niveles de acceso</span><span class="sxs-lookup"><span data-stu-id="d0aab-110">Access Modifiers and Access Levels</span></span>](#AccessModifiers)

  - [<span data-ttu-id="d0aab-111">Creación de instancias de las clases</span><span class="sxs-lookup"><span data-stu-id="d0aab-111">Instantiating Classes</span></span>](#InstantiatingClasses)

  - [<span data-ttu-id="d0aab-112">Clases y miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="d0aab-112">Static Classes and Members</span></span>](#Static)

  - [<span data-ttu-id="d0aab-113">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="d0aab-113">Anonymous Types</span></span>](#AnonymousTypes)

- [<span data-ttu-id="d0aab-114">Herencia</span><span class="sxs-lookup"><span data-stu-id="d0aab-114">Inheritance</span></span>](#Inheritance)

  - [<span data-ttu-id="d0aab-115">Reemplazar miembros</span><span class="sxs-lookup"><span data-stu-id="d0aab-115">Overriding Members</span></span>](#Overriding)

- [<span data-ttu-id="d0aab-116">Interfaces</span><span class="sxs-lookup"><span data-stu-id="d0aab-116">Interfaces</span></span>](#Interfaces)

- [<span data-ttu-id="d0aab-117">Genéricos</span><span class="sxs-lookup"><span data-stu-id="d0aab-117">Generics</span></span>](#Generics)

- [<span data-ttu-id="d0aab-118">Delegados</span><span class="sxs-lookup"><span data-stu-id="d0aab-118">Delegates</span></span>](#Delegates)

## <a name="Classes"></a> <span data-ttu-id="d0aab-119">Clases y objetos</span><span class="sxs-lookup"><span data-stu-id="d0aab-119">Classes and Objects</span></span>

<span data-ttu-id="d0aab-120">Los términos *clase* y *objeto* se usan a veces indistintamente pero, en realidad, las clases describen el *tipo* de los objetos, mientras que los objetos son *instancias* de clases que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="d0aab-120">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="d0aab-121">Así, la acción de crear un objeto se denomina *creación de instancias*.</span><span class="sxs-lookup"><span data-stu-id="d0aab-121">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="d0aab-122">Con la analogía de plano, una clase es un plano y un objeto es un edificio construido a partir de ese plano.</span><span class="sxs-lookup"><span data-stu-id="d0aab-122">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="d0aab-123">Para definir una clase:</span><span class="sxs-lookup"><span data-stu-id="d0aab-123">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="d0aab-124">C# también proporciona una versión ligera de las clases denominadas *estructuras*, que resultan útiles cuando es necesario crear una matriz grande de objetos y no quiere usar demasiada memoria para ello.</span><span class="sxs-lookup"><span data-stu-id="d0aab-124">C# also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="d0aab-125">Para definir una estructura:</span><span class="sxs-lookup"><span data-stu-id="d0aab-125">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="d0aab-126">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="d0aab-126">For more information, see:</span></span>

- [<span data-ttu-id="d0aab-127">class</span><span class="sxs-lookup"><span data-stu-id="d0aab-127">class</span></span>](../../../csharp/language-reference/keywords/class.md)

- [<span data-ttu-id="d0aab-128">struct</span><span class="sxs-lookup"><span data-stu-id="d0aab-128">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)

### <a name="Members"></a> <span data-ttu-id="d0aab-129">Miembros de clases</span><span class="sxs-lookup"><span data-stu-id="d0aab-129">Class Members</span></span>

<span data-ttu-id="d0aab-130">Cada clase puede tener distintos *miembros de clase*, entre los que se incluyen las propiedades que describen los datos de clase, los métodos que definen el comportamiento de la clase y los eventos que proporcionan comunicación entre distintos objetos y clases.</span><span class="sxs-lookup"><span data-stu-id="d0aab-130">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="Properties"></a> <span data-ttu-id="d0aab-131">Propiedades y campos</span><span class="sxs-lookup"><span data-stu-id="d0aab-131">Properties and Fields</span></span>

<span data-ttu-id="d0aab-132">Los campos y propiedades representan información que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="d0aab-132">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="d0aab-133">Los campos se parecen a las variables ya que se pueden leer y establecer directamente.</span><span class="sxs-lookup"><span data-stu-id="d0aab-133">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="d0aab-134">Para definir un campo:</span><span class="sxs-lookup"><span data-stu-id="d0aab-134">To define a field:</span></span>

```csharp
class SampleClass
{
    public string sampleField;
}
```

<span data-ttu-id="d0aab-135">Las propiedades tienen procedimientos get y set, que proporcionan un mayor control sobre la forma en que se establecen o devuelven los valores.</span><span class="sxs-lookup"><span data-stu-id="d0aab-135">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="d0aab-136">C# le permite crear un campo privado para almacenar el valor de propiedad o usar las denominadas propiedades de implementación automática que crean este campo en segundo plano automáticamente y proporcionan la lógica básica para los procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="d0aab-136">C# allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="d0aab-137">Para definir una propiedad implementada automáticamente:</span><span class="sxs-lookup"><span data-stu-id="d0aab-137">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="d0aab-138">Si necesita realizar algunas operaciones adicionales para leer y escribir el valor de propiedad, defina un campo para almacenar el valor de propiedad y proporcione la lógica básica para almacenarlo y recuperar lo:</span><span class="sxs-lookup"><span data-stu-id="d0aab-138">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

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

<span data-ttu-id="d0aab-139">La mayoría de las propiedades tienen métodos o procedimientos tanto para establecer como para obtener el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="d0aab-139">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="d0aab-140">Sin embargo, se pueden crear propiedades de solo lectura o solo escritura para restringir su modificación o lectura.</span><span class="sxs-lookup"><span data-stu-id="d0aab-140">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="d0aab-141">En C#, se puede omitir el método de propiedad `get` o `set`.</span><span class="sxs-lookup"><span data-stu-id="d0aab-141">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="d0aab-142">En cambio, las propiedades implementadas automáticamente no pueden ser de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="d0aab-142">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="d0aab-143">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="d0aab-143">For more information, see:</span></span>

- [<span data-ttu-id="d0aab-144">get</span><span class="sxs-lookup"><span data-stu-id="d0aab-144">get</span></span>](../../../csharp/language-reference/keywords/get.md)

- [<span data-ttu-id="d0aab-145">set</span><span class="sxs-lookup"><span data-stu-id="d0aab-145">set</span></span>](../../../csharp/language-reference/keywords/set.md)

#### <a name="Methods"></a> <span data-ttu-id="d0aab-146">Métodos</span><span class="sxs-lookup"><span data-stu-id="d0aab-146">Methods</span></span>

<span data-ttu-id="d0aab-147">Un *método* es una acción que un objeto puede realizar.</span><span class="sxs-lookup"><span data-stu-id="d0aab-147">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="d0aab-148">Para definir un método de una clase:</span><span class="sxs-lookup"><span data-stu-id="d0aab-148">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="d0aab-149">Una clase puede tener varias implementaciones o *sobrecargas* del mismo método que se diferencian en el número de parámetros o de tipos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="d0aab-149">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="d0aab-150">Para sobrecargar un método:</span><span class="sxs-lookup"><span data-stu-id="d0aab-150">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {};
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="d0aab-151">En la mayoría de los casos, un método se declara dentro de una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="d0aab-151">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="d0aab-152">En cambio, C# también admite los *métodos de extensión*, que le permiten agregar métodos a una clase existente fuera de la definición de la clase actual.</span><span class="sxs-lookup"><span data-stu-id="d0aab-152">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="d0aab-153">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="d0aab-153">For more information, see:</span></span>

- [<span data-ttu-id="d0aab-154">Métodos</span><span class="sxs-lookup"><span data-stu-id="d0aab-154">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="d0aab-155">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="d0aab-155">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)

#### <a name="Constructors"></a> <span data-ttu-id="d0aab-156">Constructores</span><span class="sxs-lookup"><span data-stu-id="d0aab-156">Constructors</span></span>

<span data-ttu-id="d0aab-157">Los constructores son métodos de clase que se ejecutan automáticamente cuando se crea un objeto de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="d0aab-157">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="d0aab-158">Normalmente, los constructores inicializan los miembros de datos del nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="d0aab-158">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="d0aab-159">Un constructor solo puede ejecutarse una vez cuando se crea una clase.</span><span class="sxs-lookup"><span data-stu-id="d0aab-159">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="d0aab-160">Además, el código del constructor siempre se ejecuta antes que cualquier otro código en una clase.</span><span class="sxs-lookup"><span data-stu-id="d0aab-160">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="d0aab-161">Sin embargo, puede crear varias sobrecargas del constructor de la misma forma que para cualquier otro método.</span><span class="sxs-lookup"><span data-stu-id="d0aab-161">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="d0aab-162">Para definir un constructor para una clase:</span><span class="sxs-lookup"><span data-stu-id="d0aab-162">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="d0aab-163">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="d0aab-163">For more information, see:</span></span>

<span data-ttu-id="d0aab-164">[Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="d0aab-164">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span></span>

#### <a name="Finalizers"></a> <span data-ttu-id="d0aab-165">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="d0aab-165">Finalizers</span></span>

<span data-ttu-id="d0aab-166">Los finalizadores se usan para destruir instancias de clases.</span><span class="sxs-lookup"><span data-stu-id="d0aab-166">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="d0aab-167">En .NET Framework, el recolector de elementos no utilizados administra automáticamente la asignación y la liberación de memoria para los objetos administrados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0aab-167">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="d0aab-168">En cambio, es posible que aún se necesiten finalizadores para limpiar cualquiera de los recursos no administrados creados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0aab-168">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="d0aab-169">Solo puede haber un finalizador para una clase.</span><span class="sxs-lookup"><span data-stu-id="d0aab-169">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="d0aab-170">Para obtener más información sobre los finalizadores y la recolección de elementos no utilizados en .NET Framework, vea [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="d0aab-170">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="Events"></a> <span data-ttu-id="d0aab-171">Eventos</span><span class="sxs-lookup"><span data-stu-id="d0aab-171">Events</span></span>

<span data-ttu-id="d0aab-172">Cuando ocurre algo interesante, los eventos habilitan una clase u objeto para notificarlo a otras clases u objetos.</span><span class="sxs-lookup"><span data-stu-id="d0aab-172">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="d0aab-173">La clase que envía (o genera) el evento recibe el nombre de *publicador* y las clases que reciben (o controlan) el evento se denominan *suscriptores*.</span><span class="sxs-lookup"><span data-stu-id="d0aab-173">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="d0aab-174">Para obtener más información sobre los eventos y la forma en que se generan y controlan, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="d0aab-174">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="d0aab-175">Para declarar un evento en una clase, use la palabra clave [event](../../../csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="d0aab-175">To declare an event in a class, use the [event](../../../csharp/language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="d0aab-176">Para generar un evento, invoque al delegado de eventos.</span><span class="sxs-lookup"><span data-stu-id="d0aab-176">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="d0aab-177">Para suscribirse a un evento, use el operador `+=`; para anular la suscripción de un evento, use el operador `-=`.</span><span class="sxs-lookup"><span data-stu-id="d0aab-177">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="NestedClasses"></a> <span data-ttu-id="d0aab-178">Clases anidadas</span><span class="sxs-lookup"><span data-stu-id="d0aab-178">Nested Classes</span></span>

<span data-ttu-id="d0aab-179">Una clase definida dentro de otra se denomina *anidada*.</span><span class="sxs-lookup"><span data-stu-id="d0aab-179">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="d0aab-180">De forma predeterminada, una clase anidada es privada.</span><span class="sxs-lookup"><span data-stu-id="d0aab-180">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="d0aab-181">Para crear una instancia de la clase anidada, use el nombre de la clase contenedora seguido de un punto y seguido, a continuación, del nombre de la clase anidada:</span><span class="sxs-lookup"><span data-stu-id="d0aab-181">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="AccessModifiers"></a> <span data-ttu-id="d0aab-182">Modificadores y niveles de acceso</span><span class="sxs-lookup"><span data-stu-id="d0aab-182">Access Modifiers and Access Levels</span></span>

<span data-ttu-id="d0aab-183">Todas las clases y miembros de clase pueden especificar el nivel de acceso que proporcionan a otras clases mediante los *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="d0aab-183">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="d0aab-184">Están disponibles los siguientes modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="d0aab-184">The following access modifiers are available:</span></span>

|<span data-ttu-id="d0aab-185">Modificador de C#</span><span class="sxs-lookup"><span data-stu-id="d0aab-185">C# Modifier</span></span>|<span data-ttu-id="d0aab-186">Definición</span><span class="sxs-lookup"><span data-stu-id="d0aab-186">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="d0aab-187">public</span><span class="sxs-lookup"><span data-stu-id="d0aab-187">public</span></span>](../../../csharp/language-reference/keywords/public.md)|<span data-ttu-id="d0aab-188">Puede obtener acceso al tipo o miembro cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a éste.</span><span class="sxs-lookup"><span data-stu-id="d0aab-188">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="d0aab-189">private</span><span class="sxs-lookup"><span data-stu-id="d0aab-189">private</span></span>](../../../csharp/language-reference/keywords/private.md)|<span data-ttu-id="d0aab-190">Solamente puede obtener acceso al tipo o miembro el código de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="d0aab-190">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="d0aab-191">protected</span><span class="sxs-lookup"><span data-stu-id="d0aab-191">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)|<span data-ttu-id="d0aab-192">Solamente puede obtener acceso al tipo o miembro el código de la misma clase o de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="d0aab-192">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="d0aab-193">internal</span><span class="sxs-lookup"><span data-stu-id="d0aab-193">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)|<span data-ttu-id="d0aab-194">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado, pero no de un ensamblado distinto.</span><span class="sxs-lookup"><span data-stu-id="d0aab-194">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="d0aab-195">protected internal</span><span class="sxs-lookup"><span data-stu-id="d0aab-195">protected internal</span></span>](../../../csharp/language-reference/keywords/protected-internal.md)|<span data-ttu-id="d0aab-196">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado o cualquier clase derivada de otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d0aab-196">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="d0aab-197">private protected</span><span class="sxs-lookup"><span data-stu-id="d0aab-197">private protected</span></span>](../../../csharp/language-reference/keywords/private-protected.md)|<span data-ttu-id="d0aab-198">Un código de la misma clase o de una clase derivada dentro del ensamblado de clase base puede acceder al tipo o miembro en cuestión.</span><span class="sxs-lookup"><span data-stu-id="d0aab-198">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="d0aab-199">Para obtener más información, consulte [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d0aab-199">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>

### <a name="InstantiatingClasses"></a> <span data-ttu-id="d0aab-200">Creación de instancias de las clases</span><span class="sxs-lookup"><span data-stu-id="d0aab-200">Instantiating Classes</span></span>

<span data-ttu-id="d0aab-201">Para crear un objeto, debe crear una o varias instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="d0aab-201">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="d0aab-202">Una vez creadas las instancias de una clase, puede asignar valores a las propiedades y los campos de la instancia, así como invocar métodos de clase.</span><span class="sxs-lookup"><span data-stu-id="d0aab-202">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="d0aab-203">Para asignar valores a las propiedades durante el proceso de creación de instancias de una clase, use los inicializadores de objeto:</span><span class="sxs-lookup"><span data-stu-id="d0aab-203">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="d0aab-204">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="d0aab-204">For more information, see:</span></span>

- [<span data-ttu-id="d0aab-205">new (operador)</span><span class="sxs-lookup"><span data-stu-id="d0aab-205">new Operator</span></span>](../../../csharp/language-reference/keywords/new-operator.md)

- [<span data-ttu-id="d0aab-206">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="d0aab-206">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

### <a name="Static"></a> <span data-ttu-id="d0aab-207">Clases y miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="d0aab-207">Static Classes and Members</span></span>

<span data-ttu-id="d0aab-208">Un miembro estático de la clase es una propiedad, un procedimiento o un campo que comparten todas las instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="d0aab-208">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="d0aab-209">Para definir un miembro estático:</span><span class="sxs-lookup"><span data-stu-id="d0aab-209">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="d0aab-210">Para obtener acceso al miembro estático, use el nombre de la clase sin crear un objeto perteneciente a esta:</span><span class="sxs-lookup"><span data-stu-id="d0aab-210">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="d0aab-211">Las clases estáticas en C# solo tienen miembros estáticos y no se puede crear una instancia de ellas.</span><span class="sxs-lookup"><span data-stu-id="d0aab-211">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="d0aab-212">Además, los miembros estáticos no pueden tener acceso a las propiedades, los campos o los métodos no estáticos.</span><span class="sxs-lookup"><span data-stu-id="d0aab-212">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="d0aab-213">Para obtener más información, vea: [static](../../../csharp/language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="d0aab-213">For more information, see: [static](../../../csharp/language-reference/keywords/static.md).</span></span>

### <a name="AnonymousTypes"></a> <span data-ttu-id="d0aab-214">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="d0aab-214">Anonymous Types</span></span>

<span data-ttu-id="d0aab-215">Los tipos anónimos permiten crear objetos sin escribir una definición de clase para el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d0aab-215">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="d0aab-216">En su lugar, el compilador genera una clase.</span><span class="sxs-lookup"><span data-stu-id="d0aab-216">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="d0aab-217">La clase no tiene ningún nombre que se pueda usar y contiene las propiedades especificadas al declarar el objeto.</span><span class="sxs-lookup"><span data-stu-id="d0aab-217">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="d0aab-218">Para crear una instancia de un tipo anónimo:</span><span class="sxs-lookup"><span data-stu-id="d0aab-218">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="d0aab-219">Para obtener más información, consulte: [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="d0aab-219">For more information, see: [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>

## <a name="Inheritance"></a> <span data-ttu-id="d0aab-220">Herencia</span><span class="sxs-lookup"><span data-stu-id="d0aab-220">Inheritance</span></span>

<span data-ttu-id="d0aab-221">La herencia permite crear una nueva clase que reutiliza, extiende y modifica el comportamiento que se define en otra clase.</span><span class="sxs-lookup"><span data-stu-id="d0aab-221">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="d0aab-222">La clase cuyos miembros se heredan se denomina *clase base* y la clase que hereda esos miembros se denomina *clase derivada*.</span><span class="sxs-lookup"><span data-stu-id="d0aab-222">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="d0aab-223">En cambio, todas las clases de C# heredan implícitamente de la clase <xref:System.Object> que admite la jerarquía de clases .NET y proporciona servicios de bajo nivel a todas las clases.</span><span class="sxs-lookup"><span data-stu-id="d0aab-223">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="d0aab-224">C# no admite la herencia múltiple.</span><span class="sxs-lookup"><span data-stu-id="d0aab-224">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="d0aab-225">Es decir, solo puede especificar una clase base para una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="d0aab-225">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="d0aab-226">Para heredar de una clase base:</span><span class="sxs-lookup"><span data-stu-id="d0aab-226">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="d0aab-227">De forma predeterminada, todas las clases se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="d0aab-227">By default all classes can be inherited.</span></span> <span data-ttu-id="d0aab-228">Sin embargo, puede especificar si una clase no se debe usar como clase base o bien crear una clase que solo se pueda usar como clase base.</span><span class="sxs-lookup"><span data-stu-id="d0aab-228">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="d0aab-229">Para especificar que una clase no se puede usar como clase base:</span><span class="sxs-lookup"><span data-stu-id="d0aab-229">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="d0aab-230">Para especificar que una clase se puede usar solo como clase base y no se pueden crear instancias de esta:</span><span class="sxs-lookup"><span data-stu-id="d0aab-230">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="d0aab-231">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="d0aab-231">For more information, see:</span></span>

- [<span data-ttu-id="d0aab-232">sealed</span><span class="sxs-lookup"><span data-stu-id="d0aab-232">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)

- [<span data-ttu-id="d0aab-233">abstract</span><span class="sxs-lookup"><span data-stu-id="d0aab-233">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)

### <a name="Overriding"></a> <span data-ttu-id="d0aab-234">Reemplazar miembros</span><span class="sxs-lookup"><span data-stu-id="d0aab-234">Overriding Members</span></span>

<span data-ttu-id="d0aab-235">De forma predeterminada, una clase derivada hereda todos los miembros de su clase base.</span><span class="sxs-lookup"><span data-stu-id="d0aab-235">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="d0aab-236">Si desea cambiar el comportamiento del miembro heredado, debe invalidarlo.</span><span class="sxs-lookup"><span data-stu-id="d0aab-236">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="d0aab-237">Es decir, se puede definir una nueva implementación del método, la propiedad o el evento en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="d0aab-237">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="d0aab-238">Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:</span><span class="sxs-lookup"><span data-stu-id="d0aab-238">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="d0aab-239">Modificador de C#</span><span class="sxs-lookup"><span data-stu-id="d0aab-239">C# Modifier</span></span>|<span data-ttu-id="d0aab-240">Definición</span><span class="sxs-lookup"><span data-stu-id="d0aab-240">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="d0aab-241">virtual</span><span class="sxs-lookup"><span data-stu-id="d0aab-241">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="d0aab-242">Permite invalidar un miembro de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="d0aab-242">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="d0aab-243">override</span><span class="sxs-lookup"><span data-stu-id="d0aab-243">override</span></span>](../../../csharp/language-reference/keywords/override.md)|<span data-ttu-id="d0aab-244">Invalida un miembro virtual (invalidable) definido en la clase base.</span><span class="sxs-lookup"><span data-stu-id="d0aab-244">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="d0aab-245">abstract</span><span class="sxs-lookup"><span data-stu-id="d0aab-245">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="d0aab-246">Requiere que se invalide un miembro de clase en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="d0aab-246">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="d0aab-247">new (modificador)</span><span class="sxs-lookup"><span data-stu-id="d0aab-247">new Modifier</span></span>](../../../csharp/language-reference/keywords/new-modifier.md)|<span data-ttu-id="d0aab-248">Oculta un miembro heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="d0aab-248">Hides a member inherited from a base class</span></span>|

## <a name="Interfaces"></a> <span data-ttu-id="d0aab-249">Interfaces</span><span class="sxs-lookup"><span data-stu-id="d0aab-249">Interfaces</span></span>

<span data-ttu-id="d0aab-250">Las interfaces, como las clases, definen un conjunto de propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="d0aab-250">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="d0aab-251">Pero de forma contraria a las clases, las interfaces no proporcionan implementación.</span><span class="sxs-lookup"><span data-stu-id="d0aab-251">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="d0aab-252">Se implementan como clases y se definen como entidades separadas de las clases.</span><span class="sxs-lookup"><span data-stu-id="d0aab-252">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="d0aab-253">Una interfaz representa un contrato, en el cual una clase que implementa una interfaz debe implementar cualquier aspecto de dicha interfaz exactamente como esté definido.</span><span class="sxs-lookup"><span data-stu-id="d0aab-253">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="d0aab-254">Para definir una interfaz:</span><span class="sxs-lookup"><span data-stu-id="d0aab-254">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="d0aab-255">Para implementar una interfaz en una clase:</span><span class="sxs-lookup"><span data-stu-id="d0aab-255">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="d0aab-256">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="d0aab-256">For more information, see:</span></span>

[<span data-ttu-id="d0aab-257">Interfaces</span><span class="sxs-lookup"><span data-stu-id="d0aab-257">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

[<span data-ttu-id="d0aab-258">interface</span><span class="sxs-lookup"><span data-stu-id="d0aab-258">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)

## <a name="Generics"></a> <span data-ttu-id="d0aab-259">Genéricos</span><span class="sxs-lookup"><span data-stu-id="d0aab-259">Generics</span></span>

<span data-ttu-id="d0aab-260">Las clases, las estructuras, las interfaces y los métodos de .NET Framework pueden incluir *parámetros de tipo* que definen los tipos de objetos que estos pueden almacenar o usar.</span><span class="sxs-lookup"><span data-stu-id="d0aab-260">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="d0aab-261">El ejemplo más común de elementos genéricos es una colección, donde se puede especificar el tipo de objetos que se va a almacenar en una colección.</span><span class="sxs-lookup"><span data-stu-id="d0aab-261">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="d0aab-262">Para definir una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="d0aab-262">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="d0aab-263">Para crear una instancia de una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="d0aab-263">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="d0aab-264">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="d0aab-264">For more information, see:</span></span>

- [<span data-ttu-id="d0aab-265">Genéricos</span><span class="sxs-lookup"><span data-stu-id="d0aab-265">Generics</span></span>](~/docs/standard/generics/index.md)

- [<span data-ttu-id="d0aab-266">Genéricos</span><span class="sxs-lookup"><span data-stu-id="d0aab-266">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)

## <a name="Delegates"></a> <span data-ttu-id="d0aab-267">Delegados</span><span class="sxs-lookup"><span data-stu-id="d0aab-267">Delegates</span></span>

<span data-ttu-id="d0aab-268">Un *delegado* es un tipo que define una firma de método y que puede proporcionar una referencia a cualquier método con una firma compatible.</span><span class="sxs-lookup"><span data-stu-id="d0aab-268">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="d0aab-269">Puede invocar (o llamar) al método a través del delegado.</span><span class="sxs-lookup"><span data-stu-id="d0aab-269">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="d0aab-270">Los delegados se utilizan para pasar métodos como argumentos a otros métodos.</span><span class="sxs-lookup"><span data-stu-id="d0aab-270">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="d0aab-271">Los controladores de eventos no son más que métodos que se invocan a través de delegados.</span><span class="sxs-lookup"><span data-stu-id="d0aab-271">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="d0aab-272">Para obtener más información sobre el uso de delegados en el control de eventos, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="d0aab-272">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="d0aab-273">Para crear un delegado:</span><span class="sxs-lookup"><span data-stu-id="d0aab-273">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="d0aab-274">Para crear una referencia a un método que coincida con la firma especificada por el delegado:</span><span class="sxs-lookup"><span data-stu-id="d0aab-274">To create a reference to a method that matches the signature specified by the delegate:</span></span>

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

<span data-ttu-id="d0aab-275">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="d0aab-275">For more information, see:</span></span>

- [<span data-ttu-id="d0aab-276">Delegados</span><span class="sxs-lookup"><span data-stu-id="d0aab-276">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

- [<span data-ttu-id="d0aab-277">delegate</span><span class="sxs-lookup"><span data-stu-id="d0aab-277">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)

## <a name="see-also"></a><span data-ttu-id="d0aab-278">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0aab-278">See also</span></span>

- [<span data-ttu-id="d0aab-279">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d0aab-279">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
