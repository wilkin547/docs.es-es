---
title: Programación orientada a objetos (C#)
ms.date: 05/13/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 541d1a2581a3241f35fc8478040c007b6581e3b2
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396688"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="fc437-102">Programación orientada a objetos (C#)</span><span class="sxs-lookup"><span data-stu-id="fc437-102">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="fc437-103">C# proporciona compatibilidad completa para la programación orientada a objetos incluida la encapsulación, la herencia y el polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="fc437-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="fc437-104">La *encapsulación* significa que un grupo de propiedades, métodos y otros miembros relacionados se tratan como una sola unidad u objeto.</span><span class="sxs-lookup"><span data-stu-id="fc437-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="fc437-105">La *herencia* describe la posibilidad de crear nuevas clases basadas en una clase existente.</span><span class="sxs-lookup"><span data-stu-id="fc437-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="fc437-106">El *polimorfismo* significa que puede tener múltiples clases que se pueden usar de manera intercambiable, aunque cada clase implementa las mismas propiedades o los mismos métodos de maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="fc437-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="fc437-107">Clases y objetos</span><span class="sxs-lookup"><span data-stu-id="fc437-107">Classes and objects</span></span>

<span data-ttu-id="fc437-108">Los términos *clase* y *objeto* describen el *tipo* de los objetos y las *instancias* de las clases, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="fc437-108">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="fc437-109">Así, la acción de crear un objeto se denomina *creación de instancias*.</span><span class="sxs-lookup"><span data-stu-id="fc437-109">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="fc437-110">Con la analogía de plano, una clase es un plano y un objeto es un edificio construido a partir de ese plano.</span><span class="sxs-lookup"><span data-stu-id="fc437-110">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="fc437-111">Para definir una clase:</span><span class="sxs-lookup"><span data-stu-id="fc437-111">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="fc437-112">En C# también se proporcionan tipos denominados *estructuras* que son útiles cuando no se necesita compatibilidad con la herencia o el polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="fc437-112">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span>

<span data-ttu-id="fc437-113">Para definir una estructura:</span><span class="sxs-lookup"><span data-stu-id="fc437-113">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="fc437-114">Para obtener más información, vea los artículos sobre las palabras clave [class](../../language-reference/keywords/class.md) y [struct](../../language-reference/builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="fc437-114">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="fc437-115">Miembros de la clase</span><span class="sxs-lookup"><span data-stu-id="fc437-115">Class members</span></span>

<span data-ttu-id="fc437-116">Cada clase puede tener distintos *miembros de clase*, entre los que se incluyen las propiedades que describen los datos de clase, los métodos que definen el comportamiento de la clase y los eventos que proporcionan comunicación entre distintos objetos y clases.</span><span class="sxs-lookup"><span data-stu-id="fc437-116">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="fc437-117">Propiedades y campos</span><span class="sxs-lookup"><span data-stu-id="fc437-117">Properties and fields</span></span>

<span data-ttu-id="fc437-118">Los campos y propiedades representan información que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="fc437-118">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="fc437-119">Los campos se parecen a las variables ya que se pueden leer o establecer directamente, sujetos a los modificadores de acceso aplicables.</span><span class="sxs-lookup"><span data-stu-id="fc437-119">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="fc437-120">Para definir un campo al que se pueda acceder desde dentro de las instancias de la clase:</span><span class="sxs-lookup"><span data-stu-id="fc437-120">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="fc437-121">Las propiedades tienen descriptores de acceso `get` y `set`, que proporcionan más control sobre la forma en que se establecen o devuelven los valores.</span><span class="sxs-lookup"><span data-stu-id="fc437-121">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="fc437-122">C# permite crear un campo privado para almacenar el valor de propiedad o usar propiedades de implementación automática que crean este campo en segundo plano automáticamente y proporcionan la lógica básica para los procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="fc437-122">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="fc437-123">Para definir una propiedad implementada automáticamente:</span><span class="sxs-lookup"><span data-stu-id="fc437-123">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="fc437-124">Si necesita realizar algunas operaciones adicionales para leer y escribir el valor de propiedad, defina un campo para almacenar el valor de propiedad y proporcione la lógica básica para almacenarlo y recuperar lo:</span><span class="sxs-lookup"><span data-stu-id="fc437-124">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get => _sample;
        // Store the value in the field.
        set =>  _sample = value;
    }
}
```

<span data-ttu-id="fc437-125">La mayoría de las propiedades tienen métodos o procedimientos tanto para establecer como para obtener el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="fc437-125">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="fc437-126">Sin embargo, se pueden crear propiedades de solo lectura o solo escritura para restringir su modificación o lectura.</span><span class="sxs-lookup"><span data-stu-id="fc437-126">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="fc437-127">En C#, se puede omitir el método de propiedad `get` o `set`.</span><span class="sxs-lookup"><span data-stu-id="fc437-127">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="fc437-128">Pero las propiedades implementadas automáticamente no pueden ser de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="fc437-128">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="fc437-129">Las propiedades implementadas automáticamente de solo lectura se pueden establecer en constructores de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="fc437-129">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="fc437-130">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="fc437-130">For more information, see:</span></span>

- [<span data-ttu-id="fc437-131">get</span><span class="sxs-lookup"><span data-stu-id="fc437-131">get</span></span>](../../language-reference/keywords/get.md)
- [<span data-ttu-id="fc437-132">set</span><span class="sxs-lookup"><span data-stu-id="fc437-132">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="fc437-133">Métodos</span><span class="sxs-lookup"><span data-stu-id="fc437-133">Methods</span></span>

<span data-ttu-id="fc437-134">Un *método* es una acción que un objeto puede realizar.</span><span class="sxs-lookup"><span data-stu-id="fc437-134">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="fc437-135">Para definir un método de una clase:</span><span class="sxs-lookup"><span data-stu-id="fc437-135">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int SampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="fc437-136">Una clase puede tener varias implementaciones o *sobrecargas* del mismo método que se diferencian en el número de parámetros o de tipos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="fc437-136">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="fc437-137">Para sobrecargar un método:</span><span class="sxs-lookup"><span data-stu-id="fc437-137">To overload a method:</span></span>

```csharp
public int SampleMethod(string sampleParam) { }
public int SampleMethod(int sampleParam) { }
```

<span data-ttu-id="fc437-138">En la mayoría de los casos, un método se declara dentro de una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="fc437-138">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="fc437-139">En cambio, C# también admite los *métodos de extensión*, que le permiten agregar métodos a una clase existente fuera de la definición de la clase actual.</span><span class="sxs-lookup"><span data-stu-id="fc437-139">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="fc437-140">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="fc437-140">For more information, see:</span></span>

- [<span data-ttu-id="fc437-141">Métodos</span><span class="sxs-lookup"><span data-stu-id="fc437-141">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="fc437-142">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="fc437-142">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="fc437-143">Constructores</span><span class="sxs-lookup"><span data-stu-id="fc437-143">Constructors</span></span>

<span data-ttu-id="fc437-144">Los constructores son métodos de clase que se ejecutan automáticamente cuando se crea un objeto de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="fc437-144">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="fc437-145">Normalmente, los constructores inicializan los miembros de datos del nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="fc437-145">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="fc437-146">Un constructor solo puede ejecutarse una vez cuando se crea una clase.</span><span class="sxs-lookup"><span data-stu-id="fc437-146">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="fc437-147">Además, el código del constructor siempre se ejecuta antes que cualquier otro código en una clase.</span><span class="sxs-lookup"><span data-stu-id="fc437-147">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="fc437-148">Sin embargo, puede crear varias sobrecargas del constructor de la misma forma que para cualquier otro método.</span><span class="sxs-lookup"><span data-stu-id="fc437-148">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="fc437-149">Para definir un constructor para una clase:</span><span class="sxs-lookup"><span data-stu-id="fc437-149">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="fc437-150">Para obtener más información, vea [Constructores](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="fc437-150">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="fc437-151">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="fc437-151">Finalizers</span></span>

<span data-ttu-id="fc437-152">Los finalizadores se usan para destruir instancias de clases.</span><span class="sxs-lookup"><span data-stu-id="fc437-152">A finalizer is used to destruct instances of classes.</span></span> <span data-ttu-id="fc437-153">En .NET Framework, el recolector de elementos no utilizados administra automáticamente la asignación y la liberación de memoria para los objetos administrados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc437-153">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="fc437-154">En cambio, es posible que aún se necesiten finalizadores para limpiar cualquiera de los recursos no administrados creados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc437-154">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="fc437-155">Solo puede haber un finalizador para una clase.</span><span class="sxs-lookup"><span data-stu-id="fc437-155">There can be only one finalizer for a class.</span></span>

<span data-ttu-id="fc437-156">Para obtener más información sobre los finalizadores y la recolección de elementos no utilizados en .NET Framework, vea [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="fc437-156">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="fc437-157">Events</span><span class="sxs-lookup"><span data-stu-id="fc437-157">Events</span></span>

<span data-ttu-id="fc437-158">Cuando ocurre algo interesante, los eventos habilitan una clase u objeto para notificarlo a otras clases u objetos.</span><span class="sxs-lookup"><span data-stu-id="fc437-158">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="fc437-159">La clase que envía (o genera) el evento recibe el nombre de *publicador* y las clases que reciben (o controlan) el evento se denominan *suscriptores*.</span><span class="sxs-lookup"><span data-stu-id="fc437-159">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="fc437-160">Para obtener más información sobre los eventos y la forma en que se generan y controlan, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="fc437-160">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="fc437-161">Para declarar un evento en una clase, use la palabra clave [event](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="fc437-161">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>
- <span data-ttu-id="fc437-162">Para generar un evento, invoque al delegado de eventos.</span><span class="sxs-lookup"><span data-stu-id="fc437-162">To raise an event, invoke the event delegate.</span></span>
- <span data-ttu-id="fc437-163">Para suscribirse a un evento, use el operador `+=`; para anular la suscripción de un evento, use el operador `-=`.</span><span class="sxs-lookup"><span data-stu-id="fc437-163">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="fc437-164">Clases anidadas</span><span class="sxs-lookup"><span data-stu-id="fc437-164">Nested classes</span></span>

<span data-ttu-id="fc437-165">Una clase definida dentro de otra se denomina *anidada*.</span><span class="sxs-lookup"><span data-stu-id="fc437-165">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="fc437-166">De forma predeterminada, una clase anidada es privada.</span><span class="sxs-lookup"><span data-stu-id="fc437-166">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="fc437-167">Para crear una instancia de la clase anidada, use el nombre de la clase contenedora seguido de un punto y seguido, a continuación, del nombre de la clase anidada:</span><span class="sxs-lookup"><span data-stu-id="fc437-167">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="fc437-168">Modificadores y niveles de acceso</span><span class="sxs-lookup"><span data-stu-id="fc437-168">Access modifiers and access levels</span></span>

<span data-ttu-id="fc437-169">Todas las clases y miembros de clase pueden especificar el nivel de acceso que proporcionan a otras clases mediante los *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="fc437-169">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="fc437-170">Están disponibles los siguientes modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="fc437-170">The following access modifiers are available:</span></span>

| <span data-ttu-id="fc437-171">Modificador de C#</span><span class="sxs-lookup"><span data-stu-id="fc437-171">C# Modifier</span></span> | <span data-ttu-id="fc437-172">Definición</span><span class="sxs-lookup"><span data-stu-id="fc437-172">Definition</span></span> |
|--|--|
| [<span data-ttu-id="fc437-173">public</span><span class="sxs-lookup"><span data-stu-id="fc437-173">public</span></span>](../../language-reference/keywords/public.md) | <span data-ttu-id="fc437-174">Puede obtener acceso al tipo o miembro cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a éste.</span><span class="sxs-lookup"><span data-stu-id="fc437-174">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span> |
| [<span data-ttu-id="fc437-175">private</span><span class="sxs-lookup"><span data-stu-id="fc437-175">private</span></span>](../../language-reference/keywords/private.md) | <span data-ttu-id="fc437-176">Solamente puede obtener acceso al tipo o miembro el código de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="fc437-176">The type or member can only be accessed by code in the same class.</span></span> |
| [<span data-ttu-id="fc437-177">protected</span><span class="sxs-lookup"><span data-stu-id="fc437-177">protected</span></span>](../../language-reference/keywords/protected.md) | <span data-ttu-id="fc437-178">Solamente puede obtener acceso al tipo o miembro el código de la misma clase o de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="fc437-178">The type or member can only be accessed by code in the same class or in a derived class.</span></span> |
| [<span data-ttu-id="fc437-179">internal</span><span class="sxs-lookup"><span data-stu-id="fc437-179">internal</span></span>](../../language-reference/keywords/internal.md) | <span data-ttu-id="fc437-180">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado, pero no de un ensamblado distinto.</span><span class="sxs-lookup"><span data-stu-id="fc437-180">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span> |
| [<span data-ttu-id="fc437-181">protected internal</span><span class="sxs-lookup"><span data-stu-id="fc437-181">protected internal</span></span>](../../language-reference/keywords/protected-internal.md) | <span data-ttu-id="fc437-182">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado o cualquier clase derivada de otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fc437-182">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span> |
| [<span data-ttu-id="fc437-183">private protected</span><span class="sxs-lookup"><span data-stu-id="fc437-183">private protected</span></span>](../../language-reference/keywords/private-protected.md) | <span data-ttu-id="fc437-184">Un código de la misma clase o de una clase derivada dentro del ensamblado de clase base puede acceder al tipo o miembro en cuestión.</span><span class="sxs-lookup"><span data-stu-id="fc437-184">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span> |

<span data-ttu-id="fc437-185">Para obtener más información, consulte [Modificadores de acceso](../classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="fc437-185">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="fc437-186">Creación de instancias de clases</span><span class="sxs-lookup"><span data-stu-id="fc437-186">Instantiating classes</span></span>

<span data-ttu-id="fc437-187">Para crear un objeto, debe crear una o varias instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="fc437-187">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="fc437-188">Una vez creadas las instancias de una clase, puede asignar valores a las propiedades y los campos de la instancia, así como invocar métodos de clase.</span><span class="sxs-lookup"><span data-stu-id="fc437-188">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.SampleMethod();
```

<span data-ttu-id="fc437-189">Para asignar valores a las propiedades durante el proceso de creación de instancias de una clase, use los inicializadores de objeto:</span><span class="sxs-lookup"><span data-stu-id="fc437-189">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
var sampleObject = new SampleClass
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="fc437-190">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="fc437-190">For more information, see:</span></span>

- [<span data-ttu-id="fc437-191">new (operador)</span><span class="sxs-lookup"><span data-stu-id="fc437-191">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="fc437-192">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="fc437-192">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="fc437-193">Clases y miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="fc437-193">Static Classes and Members</span></span>

<span data-ttu-id="fc437-194">Un miembro estático de la clase es una propiedad, un procedimiento o un campo que comparten todas las instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="fc437-194">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="fc437-195">Para definir un miembro estático:</span><span class="sxs-lookup"><span data-stu-id="fc437-195">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="fc437-196">Para obtener acceso al miembro estático, use el nombre de la clase sin crear un objeto perteneciente a esta:</span><span class="sxs-lookup"><span data-stu-id="fc437-196">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="fc437-197">Las clases estáticas en C# solo tienen miembros estáticos y no se puede crear una instancia de ellas.</span><span class="sxs-lookup"><span data-stu-id="fc437-197">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="fc437-198">Además, los miembros estáticos no pueden tener acceso a las propiedades, los campos o los métodos no estáticos.</span><span class="sxs-lookup"><span data-stu-id="fc437-198">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="fc437-199">Para obtener más información, vea: [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="fc437-199">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="fc437-200">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="fc437-200">Anonymous types</span></span>

<span data-ttu-id="fc437-201">Los tipos anónimos permiten crear objetos sin escribir una definición de clase para el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="fc437-201">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="fc437-202">En su lugar, el compilador genera una clase.</span><span class="sxs-lookup"><span data-stu-id="fc437-202">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="fc437-203">La clase no tiene ningún nombre que se pueda usar y contiene las propiedades especificadas al declarar el objeto.</span><span class="sxs-lookup"><span data-stu-id="fc437-203">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="fc437-204">Para crear una instancia de un tipo anónimo:</span><span class="sxs-lookup"><span data-stu-id="fc437-204">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject = new
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="fc437-205">Para obtener más información, consulte: [Tipos anónimos](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="fc437-205">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="fc437-206">Herencia</span><span class="sxs-lookup"><span data-stu-id="fc437-206">Inheritance</span></span>

<span data-ttu-id="fc437-207">La herencia permite crear una nueva clase que reutiliza, extiende y modifica el comportamiento que se define en otra clase.</span><span class="sxs-lookup"><span data-stu-id="fc437-207">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="fc437-208">La clase cuyos miembros se heredan se denomina *clase base* y la clase que hereda esos miembros se denomina *clase derivada*.</span><span class="sxs-lookup"><span data-stu-id="fc437-208">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="fc437-209">En cambio, todas las clases de C# heredan implícitamente de la clase <xref:System.Object> que admite la jerarquía de clases .NET y proporciona servicios de bajo nivel a todas las clases.</span><span class="sxs-lookup"><span data-stu-id="fc437-209">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="fc437-210">C# no admite la herencia múltiple.</span><span class="sxs-lookup"><span data-stu-id="fc437-210">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="fc437-211">Es decir, solo puede especificar una clase base para una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="fc437-211">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="fc437-212">Para heredar de una clase base:</span><span class="sxs-lookup"><span data-stu-id="fc437-212">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass { }
```

<span data-ttu-id="fc437-213">De forma predeterminada, todas las clases se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="fc437-213">By default all classes can be inherited.</span></span> <span data-ttu-id="fc437-214">Sin embargo, puede especificar si una clase no se debe usar como clase base o bien crear una clase que solo se pueda usar como clase base.</span><span class="sxs-lookup"><span data-stu-id="fc437-214">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="fc437-215">Para especificar que una clase no se puede usar como clase base:</span><span class="sxs-lookup"><span data-stu-id="fc437-215">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="fc437-216">Para especificar que una clase se puede usar solo como clase base y no se pueden crear instancias de esta:</span><span class="sxs-lookup"><span data-stu-id="fc437-216">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="fc437-217">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="fc437-217">For more information, see:</span></span>

- [<span data-ttu-id="fc437-218">sealed</span><span class="sxs-lookup"><span data-stu-id="fc437-218">sealed</span></span>](../../language-reference/keywords/sealed.md)
- [<span data-ttu-id="fc437-219">abstract</span><span class="sxs-lookup"><span data-stu-id="fc437-219">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="fc437-220">Reemplazar miembros</span><span class="sxs-lookup"><span data-stu-id="fc437-220">Overriding Members</span></span>

<span data-ttu-id="fc437-221">De forma predeterminada, una clase derivada hereda todos los miembros de su clase base.</span><span class="sxs-lookup"><span data-stu-id="fc437-221">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="fc437-222">Si desea cambiar el comportamiento del miembro heredado, debe invalidarlo.</span><span class="sxs-lookup"><span data-stu-id="fc437-222">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="fc437-223">Es decir, se puede definir una nueva implementación del método, la propiedad o el evento en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="fc437-223">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="fc437-224">Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:</span><span class="sxs-lookup"><span data-stu-id="fc437-224">The following modifiers are used to control how properties and methods are overridden:</span></span>

| <span data-ttu-id="fc437-225">Modificador de C#</span><span class="sxs-lookup"><span data-stu-id="fc437-225">C# Modifier</span></span> | <span data-ttu-id="fc437-226">Definición</span><span class="sxs-lookup"><span data-stu-id="fc437-226">Definition</span></span> |
|--|--|
| [<span data-ttu-id="fc437-227">virtual</span><span class="sxs-lookup"><span data-stu-id="fc437-227">virtual</span></span>](../../language-reference/keywords/virtual.md) | <span data-ttu-id="fc437-228">Permite invalidar un miembro de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="fc437-228">Allows a class member to be overridden in a derived class.</span></span> |
| [<span data-ttu-id="fc437-229">override</span><span class="sxs-lookup"><span data-stu-id="fc437-229">override</span></span>](../../language-reference/keywords/override.md) | <span data-ttu-id="fc437-230">Invalida un miembro virtual (invalidable) definido en la clase base.</span><span class="sxs-lookup"><span data-stu-id="fc437-230">Overrides a virtual (overridable) member defined in the base class.</span></span> |
| [<span data-ttu-id="fc437-231">abstract</span><span class="sxs-lookup"><span data-stu-id="fc437-231">abstract</span></span>](../../language-reference/keywords/abstract.md) | <span data-ttu-id="fc437-232">Requiere que se invalide un miembro de clase en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="fc437-232">Requires that a class member to be overridden in the derived class.</span></span> |
| [<span data-ttu-id="fc437-233">new (modificador)</span><span class="sxs-lookup"><span data-stu-id="fc437-233">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md) | <span data-ttu-id="fc437-234">Oculta un miembro heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="fc437-234">Hides a member inherited from a base class</span></span> |

## <a name="interfaces"></a><span data-ttu-id="fc437-235">Interfaces</span><span class="sxs-lookup"><span data-stu-id="fc437-235">Interfaces</span></span>

<span data-ttu-id="fc437-236">Las interfaces, como las clases, definen un conjunto de propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="fc437-236">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="fc437-237">Pero de forma contraria a las clases, las interfaces no proporcionan implementación.</span><span class="sxs-lookup"><span data-stu-id="fc437-237">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="fc437-238">Se implementan como clases y se definen como entidades separadas de las clases.</span><span class="sxs-lookup"><span data-stu-id="fc437-238">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="fc437-239">Una interfaz representa un contrato, en el cual una clase que implementa una interfaz debe implementar cualquier aspecto de dicha interfaz exactamente como esté definido.</span><span class="sxs-lookup"><span data-stu-id="fc437-239">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="fc437-240">Para definir una interfaz:</span><span class="sxs-lookup"><span data-stu-id="fc437-240">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void DoSomething();
}
```

<span data-ttu-id="fc437-241">Para implementar una interfaz en una clase:</span><span class="sxs-lookup"><span data-stu-id="fc437-241">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.DoSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="fc437-242">Para obtener más información, vea el artículo de la guía de programación sobre [interfaces](../interfaces/index.md) y el artículo de la referencia del lenguaje sobre la palabra clave [interface](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="fc437-242">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="fc437-243">Genéricos</span><span class="sxs-lookup"><span data-stu-id="fc437-243">Generics</span></span>

<span data-ttu-id="fc437-244">Las clases, las estructuras, las interfaces y los métodos de .NET Framework pueden incluir *parámetros de tipo* que definen los tipos de objetos que estos pueden almacenar o usar.</span><span class="sxs-lookup"><span data-stu-id="fc437-244">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="fc437-245">El ejemplo más común de elementos genéricos es una colección, donde se puede especificar el tipo de objetos que se va a almacenar en una colección.</span><span class="sxs-lookup"><span data-stu-id="fc437-245">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="fc437-246">Para definir una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="fc437-246">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="fc437-247">Para crear una instancia de una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="fc437-247">To create an instance of a generic class:</span></span>

```csharp
var sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="fc437-248">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="fc437-248">For more information, see:</span></span>

- [<span data-ttu-id="fc437-249">Elementos genéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="fc437-249">Generics in .NET</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="fc437-250">Aspectos genéricos: Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fc437-250">Generics - C# Programming Guide</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="fc437-251">Delegados</span><span class="sxs-lookup"><span data-stu-id="fc437-251">Delegates</span></span>

<span data-ttu-id="fc437-252">Un *delegado* es un tipo que define una firma de método y que puede proporcionar una referencia a cualquier método con una firma compatible.</span><span class="sxs-lookup"><span data-stu-id="fc437-252">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="fc437-253">Puede invocar (o llamar) al método a través del delegado.</span><span class="sxs-lookup"><span data-stu-id="fc437-253">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="fc437-254">Los delegados se utilizan para pasar métodos como argumentos a otros métodos.</span><span class="sxs-lookup"><span data-stu-id="fc437-254">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="fc437-255">Los controladores de eventos no son más que métodos que se invocan a través de delegados.</span><span class="sxs-lookup"><span data-stu-id="fc437-255">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="fc437-256">Para obtener más información sobre el uso de delegados en el control de eventos, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="fc437-256">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="fc437-257">Para crear un delegado:</span><span class="sxs-lookup"><span data-stu-id="fc437-257">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="fc437-258">Para crear una referencia a un método que coincida con la firma especificada por el delegado:</span><span class="sxs-lookup"><span data-stu-id="fc437-258">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void SampleMethod(string message)
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

<span data-ttu-id="fc437-259">Para obtener más información, vea el artículo de la guía de programación sobre [Delegados](../delegates/index.md) y el artículo de la referencia del lenguaje sobre la palabra clave [delegate](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="fc437-259">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc437-260">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc437-260">See also</span></span>

- [<span data-ttu-id="fc437-261">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fc437-261">C# Programming Guide</span></span>](../index.md)
