---
title: Programación orientada a objetos (C#)
ms.date: 05/13/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 83140a9dbd16f60f04f50ba18c71099cdd862f15
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226639"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="f54b8-102">Programación orientada a objetos (C#)</span><span class="sxs-lookup"><span data-stu-id="f54b8-102">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="f54b8-103">C# proporciona compatibilidad completa para la programación orientada a objetos incluida la abstracción, la encapsulación, la herencia y el polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="f54b8-103">C# provides full support for object-oriented programming including abstraction, encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="f54b8-104">La *abstracción* significa ocultar los detalles innecesarios de los consumidores de tipos.</span><span class="sxs-lookup"><span data-stu-id="f54b8-104">*Abstraction* means hiding the unnecessary details from type consumers.</span></span>
- <span data-ttu-id="f54b8-105">La *encapsulación* significa que un grupo de propiedades, métodos y otros miembros relacionados se tratan como una sola unidad u objeto.</span><span class="sxs-lookup"><span data-stu-id="f54b8-105">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="f54b8-106">La *herencia* describe la posibilidad de crear nuevas clases basadas en una clase existente.</span><span class="sxs-lookup"><span data-stu-id="f54b8-106">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="f54b8-107">El *polimorfismo* significa que puede tener múltiples clases que se pueden usar de manera intercambiable, aunque cada clase implementa las mismas propiedades o los mismos métodos de maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="f54b8-107">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="f54b8-108">Clases y objetos</span><span class="sxs-lookup"><span data-stu-id="f54b8-108">Classes and objects</span></span>

<span data-ttu-id="f54b8-109">Los términos *clase* y *objeto* describen el *tipo* de los objetos y las *instancias* de las clases, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f54b8-109">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="f54b8-110">Así, la acción de crear un objeto se denomina *creación de instancias*.</span><span class="sxs-lookup"><span data-stu-id="f54b8-110">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="f54b8-111">Con la analogía de plano, una clase es un plano y un objeto es un edificio construido a partir de ese plano.</span><span class="sxs-lookup"><span data-stu-id="f54b8-111">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="f54b8-112">Para definir una clase:</span><span class="sxs-lookup"><span data-stu-id="f54b8-112">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="f54b8-113">En C# también se proporcionan tipos denominados *estructuras* que son útiles cuando no se necesita compatibilidad con la herencia o el polimorfismo.</span><span class="sxs-lookup"><span data-stu-id="f54b8-113">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span> <span data-ttu-id="f54b8-114">Para obtener más información, consulte [Selección entre class y struct](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-114">For more information, see [Choosing between class and struct](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span></span>

<span data-ttu-id="f54b8-115">Para definir una estructura:</span><span class="sxs-lookup"><span data-stu-id="f54b8-115">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="f54b8-116">Para obtener más información, vea los artículos sobre las palabras clave [class](../../language-reference/keywords/class.md) y [struct](../../language-reference/builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-116">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="f54b8-117">Miembros de la clase</span><span class="sxs-lookup"><span data-stu-id="f54b8-117">Class members</span></span>

<span data-ttu-id="f54b8-118">Cada clase puede tener distintos *miembros de clase*, entre los que se incluyen las propiedades que describen los datos de clase, los métodos que definen el comportamiento de la clase y los eventos que proporcionan comunicación entre distintos objetos y clases.</span><span class="sxs-lookup"><span data-stu-id="f54b8-118">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="f54b8-119">Propiedades y campos</span><span class="sxs-lookup"><span data-stu-id="f54b8-119">Properties and fields</span></span>

<span data-ttu-id="f54b8-120">Los campos y propiedades representan información que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="f54b8-120">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="f54b8-121">Los campos se parecen a las variables ya que se pueden leer o establecer directamente, sujetos a los modificadores de acceso aplicables.</span><span class="sxs-lookup"><span data-stu-id="f54b8-121">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="f54b8-122">Para definir un campo al que se pueda acceder desde dentro de las instancias de la clase:</span><span class="sxs-lookup"><span data-stu-id="f54b8-122">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="f54b8-123">Las propiedades tienen descriptores de acceso `get` y `set`, que proporcionan más control sobre la forma en que se establecen o devuelven los valores.</span><span class="sxs-lookup"><span data-stu-id="f54b8-123">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="f54b8-124">C# permite crear un campo privado para almacenar el valor de propiedad o usar propiedades de implementación automática que crean este campo en segundo plano automáticamente y proporcionan la lógica básica para los procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f54b8-124">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="f54b8-125">Para definir una propiedad implementada automáticamente:</span><span class="sxs-lookup"><span data-stu-id="f54b8-125">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="f54b8-126">Si necesita realizar algunas operaciones adicionales para leer y escribir el valor de propiedad, defina un campo para almacenar el valor de propiedad y proporcione la lógica básica para almacenarlo y recuperar lo:</span><span class="sxs-lookup"><span data-stu-id="f54b8-126">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

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

<span data-ttu-id="f54b8-127">La mayoría de las propiedades tienen métodos o procedimientos tanto para establecer como para obtener el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f54b8-127">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="f54b8-128">Sin embargo, se pueden crear propiedades de solo lectura o solo escritura para restringir su modificación o lectura.</span><span class="sxs-lookup"><span data-stu-id="f54b8-128">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="f54b8-129">En C#, se puede omitir el método de propiedad `get` o `set`.</span><span class="sxs-lookup"><span data-stu-id="f54b8-129">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="f54b8-130">Pero las propiedades implementadas automáticamente no pueden ser de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="f54b8-130">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="f54b8-131">Las propiedades implementadas automáticamente de solo lectura se pueden establecer en constructores de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="f54b8-131">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="f54b8-132">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f54b8-132">For more information, see:</span></span>

- [<span data-ttu-id="f54b8-133">get</span><span class="sxs-lookup"><span data-stu-id="f54b8-133">get</span></span>](../../language-reference/keywords/get.md)
- [<span data-ttu-id="f54b8-134">set</span><span class="sxs-lookup"><span data-stu-id="f54b8-134">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="f54b8-135">Métodos</span><span class="sxs-lookup"><span data-stu-id="f54b8-135">Methods</span></span>

<span data-ttu-id="f54b8-136">Un *método* es una acción que un objeto puede realizar.</span><span class="sxs-lookup"><span data-stu-id="f54b8-136">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="f54b8-137">Para definir un método de una clase:</span><span class="sxs-lookup"><span data-stu-id="f54b8-137">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int SampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="f54b8-138">Una clase puede tener varias implementaciones o *sobrecargas* del mismo método que se diferencian en el número de parámetros o de tipos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="f54b8-138">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="f54b8-139">Para sobrecargar un método:</span><span class="sxs-lookup"><span data-stu-id="f54b8-139">To overload a method:</span></span>

```csharp
public int SampleMethod(string sampleParam) { }
public int SampleMethod(int sampleParam) { }
```

<span data-ttu-id="f54b8-140">En la mayoría de los casos, un método se declara dentro de una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="f54b8-140">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="f54b8-141">En cambio, C# también admite los *métodos de extensión*, que le permiten agregar métodos a una clase existente fuera de la definición de la clase actual.</span><span class="sxs-lookup"><span data-stu-id="f54b8-141">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="f54b8-142">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f54b8-142">For more information, see:</span></span>

- [<span data-ttu-id="f54b8-143">Métodos</span><span class="sxs-lookup"><span data-stu-id="f54b8-143">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="f54b8-144">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="f54b8-144">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="f54b8-145">Constructores</span><span class="sxs-lookup"><span data-stu-id="f54b8-145">Constructors</span></span>

<span data-ttu-id="f54b8-146">Los constructores son métodos de clase que se ejecutan automáticamente cuando se crea un objeto de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="f54b8-146">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="f54b8-147">Normalmente, los constructores inicializan los miembros de datos del nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="f54b8-147">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="f54b8-148">Un constructor solo puede ejecutarse una vez cuando se crea una clase.</span><span class="sxs-lookup"><span data-stu-id="f54b8-148">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="f54b8-149">Además, el código del constructor siempre se ejecuta antes que cualquier otro código en una clase.</span><span class="sxs-lookup"><span data-stu-id="f54b8-149">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="f54b8-150">Sin embargo, puede crear varias sobrecargas del constructor de la misma forma que para cualquier otro método.</span><span class="sxs-lookup"><span data-stu-id="f54b8-150">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="f54b8-151">Para definir un constructor para una clase:</span><span class="sxs-lookup"><span data-stu-id="f54b8-151">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="f54b8-152">Para obtener más información, vea [Constructores](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-152">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="f54b8-153">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="f54b8-153">Finalizers</span></span>

<span data-ttu-id="f54b8-154">Los finalizadores se usan para destruir instancias de clases.</span><span class="sxs-lookup"><span data-stu-id="f54b8-154">A finalizer is used to destruct instances of classes.</span></span> <span data-ttu-id="f54b8-155">En .NET, el recolector de elementos no utilizados administra automáticamente la asignación y la liberación de memoria para los objetos administrados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f54b8-155">In .NET, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="f54b8-156">En cambio, es posible que aún se necesiten finalizadores para limpiar cualquiera de los recursos no administrados creados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f54b8-156">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="f54b8-157">Solo puede haber un finalizador para una clase.</span><span class="sxs-lookup"><span data-stu-id="f54b8-157">There can be only one finalizer for a class.</span></span>

<span data-ttu-id="f54b8-158">Para obtener más información sobre los finalizadores y la recolección de elementos no utilizados en .NET, vea [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-158">For more information about finalizers and garbage collection in .NET, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="f54b8-159">Events</span><span class="sxs-lookup"><span data-stu-id="f54b8-159">Events</span></span>

<span data-ttu-id="f54b8-160">Cuando ocurre algo interesante, los eventos habilitan una clase u objeto para notificarlo a otras clases u objetos.</span><span class="sxs-lookup"><span data-stu-id="f54b8-160">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="f54b8-161">La clase que envía (o genera) el evento recibe el nombre de *publicador* y las clases que reciben (o controlan) el evento se denominan *suscriptores*.</span><span class="sxs-lookup"><span data-stu-id="f54b8-161">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="f54b8-162">Para obtener más información sobre los eventos y la forma en que se generan y controlan, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-162">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="f54b8-163">Para declarar un evento en una clase, use la palabra clave [event](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-163">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>
- <span data-ttu-id="f54b8-164">Para generar un evento, invoque al delegado de eventos.</span><span class="sxs-lookup"><span data-stu-id="f54b8-164">To raise an event, invoke the event delegate.</span></span>
- <span data-ttu-id="f54b8-165">Para suscribirse a un evento, use el operador `+=`; para anular la suscripción de un evento, use el operador `-=`.</span><span class="sxs-lookup"><span data-stu-id="f54b8-165">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="f54b8-166">Clases anidadas</span><span class="sxs-lookup"><span data-stu-id="f54b8-166">Nested classes</span></span>

<span data-ttu-id="f54b8-167">Una clase definida dentro de otra se denomina *anidada*.</span><span class="sxs-lookup"><span data-stu-id="f54b8-167">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="f54b8-168">De forma predeterminada, una clase anidada es privada.</span><span class="sxs-lookup"><span data-stu-id="f54b8-168">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="f54b8-169">Para crear una instancia de la clase anidada, use el nombre de la clase contenedora seguido de un punto y seguido, a continuación, del nombre de la clase anidada:</span><span class="sxs-lookup"><span data-stu-id="f54b8-169">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="f54b8-170">Modificadores y niveles de acceso</span><span class="sxs-lookup"><span data-stu-id="f54b8-170">Access modifiers and access levels</span></span>

<span data-ttu-id="f54b8-171">Todas las clases y miembros de clase pueden especificar el nivel de acceso que proporcionan a otras clases mediante los *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="f54b8-171">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="f54b8-172">Están disponibles los siguientes modificadores de acceso:</span><span class="sxs-lookup"><span data-stu-id="f54b8-172">The following access modifiers are available:</span></span>

| <span data-ttu-id="f54b8-173">Modificador de C#</span><span class="sxs-lookup"><span data-stu-id="f54b8-173">C# Modifier</span></span> | <span data-ttu-id="f54b8-174">Definición</span><span class="sxs-lookup"><span data-stu-id="f54b8-174">Definition</span></span> |
|--|--|
| [<span data-ttu-id="f54b8-175">public</span><span class="sxs-lookup"><span data-stu-id="f54b8-175">public</span></span>](../../language-reference/keywords/public.md) | <span data-ttu-id="f54b8-176">Puede obtener acceso al tipo o miembro cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a éste.</span><span class="sxs-lookup"><span data-stu-id="f54b8-176">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span> |
| [<span data-ttu-id="f54b8-177">private</span><span class="sxs-lookup"><span data-stu-id="f54b8-177">private</span></span>](../../language-reference/keywords/private.md) | <span data-ttu-id="f54b8-178">Solamente puede obtener acceso al tipo o miembro el código de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="f54b8-178">The type or member can only be accessed by code in the same class.</span></span> |
| [<span data-ttu-id="f54b8-179">protected</span><span class="sxs-lookup"><span data-stu-id="f54b8-179">protected</span></span>](../../language-reference/keywords/protected.md) | <span data-ttu-id="f54b8-180">Solamente puede obtener acceso al tipo o miembro el código de la misma clase o de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f54b8-180">The type or member can only be accessed by code in the same class or in a derived class.</span></span> |
| [<span data-ttu-id="f54b8-181">internal</span><span class="sxs-lookup"><span data-stu-id="f54b8-181">internal</span></span>](../../language-reference/keywords/internal.md) | <span data-ttu-id="f54b8-182">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado, pero no de un ensamblado distinto.</span><span class="sxs-lookup"><span data-stu-id="f54b8-182">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span> |
| [<span data-ttu-id="f54b8-183">protected internal</span><span class="sxs-lookup"><span data-stu-id="f54b8-183">protected internal</span></span>](../../language-reference/keywords/protected-internal.md) | <span data-ttu-id="f54b8-184">Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado o cualquier clase derivada de otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f54b8-184">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span> |
| [<span data-ttu-id="f54b8-185">private protected</span><span class="sxs-lookup"><span data-stu-id="f54b8-185">private protected</span></span>](../../language-reference/keywords/private-protected.md) | <span data-ttu-id="f54b8-186">Un código de la misma clase o de una clase derivada dentro del ensamblado de clase base puede acceder al tipo o miembro en cuestión.</span><span class="sxs-lookup"><span data-stu-id="f54b8-186">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span> |

<span data-ttu-id="f54b8-187">Para obtener más información, consulte [Modificadores de acceso](../classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-187">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="f54b8-188">Creación de instancias de clases</span><span class="sxs-lookup"><span data-stu-id="f54b8-188">Instantiating classes</span></span>

<span data-ttu-id="f54b8-189">Para crear un objeto, debe crear una o varias instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="f54b8-189">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="f54b8-190">Una vez creadas las instancias de una clase, puede asignar valores a las propiedades y los campos de la instancia, así como invocar métodos de clase.</span><span class="sxs-lookup"><span data-stu-id="f54b8-190">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.SampleMethod();
```

<span data-ttu-id="f54b8-191">Para asignar valores a las propiedades durante el proceso de creación de instancias de una clase, use los inicializadores de objeto:</span><span class="sxs-lookup"><span data-stu-id="f54b8-191">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
var sampleObject = new SampleClass
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="f54b8-192">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f54b8-192">For more information, see:</span></span>

- [<span data-ttu-id="f54b8-193">new (operador)</span><span class="sxs-lookup"><span data-stu-id="f54b8-193">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="f54b8-194">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="f54b8-194">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="f54b8-195">Clases y miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="f54b8-195">Static Classes and Members</span></span>

<span data-ttu-id="f54b8-196">Un miembro estático de la clase es una propiedad, un procedimiento o un campo que comparten todas las instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="f54b8-196">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="f54b8-197">Para definir un miembro estático:</span><span class="sxs-lookup"><span data-stu-id="f54b8-197">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="f54b8-198">Para obtener acceso al miembro estático, use el nombre de la clase sin crear un objeto perteneciente a esta:</span><span class="sxs-lookup"><span data-stu-id="f54b8-198">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="f54b8-199">Las clases estáticas en C# solo tienen miembros estáticos y no se puede crear una instancia de ellas.</span><span class="sxs-lookup"><span data-stu-id="f54b8-199">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="f54b8-200">Además, los miembros estáticos no pueden tener acceso a las propiedades, los campos o los métodos no estáticos.</span><span class="sxs-lookup"><span data-stu-id="f54b8-200">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="f54b8-201">Para obtener más información, vea: [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-201">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="f54b8-202">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="f54b8-202">Anonymous types</span></span>

<span data-ttu-id="f54b8-203">Los tipos anónimos permiten crear objetos sin escribir una definición de clase para el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f54b8-203">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="f54b8-204">En su lugar, el compilador genera una clase.</span><span class="sxs-lookup"><span data-stu-id="f54b8-204">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="f54b8-205">La clase no tiene ningún nombre que se pueda usar y contiene las propiedades especificadas al declarar el objeto.</span><span class="sxs-lookup"><span data-stu-id="f54b8-205">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="f54b8-206">Para crear una instancia de un tipo anónimo:</span><span class="sxs-lookup"><span data-stu-id="f54b8-206">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject = new
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="f54b8-207">Para obtener más información, consulte: [Tipos anónimos](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-207">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="f54b8-208">Herencia</span><span class="sxs-lookup"><span data-stu-id="f54b8-208">Inheritance</span></span>

<span data-ttu-id="f54b8-209">La herencia permite crear una nueva clase que reutiliza, extiende y modifica el comportamiento que se define en otra clase.</span><span class="sxs-lookup"><span data-stu-id="f54b8-209">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="f54b8-210">La clase cuyos miembros se heredan se denomina *clase base* y la clase que hereda esos miembros se denomina *clase derivada*.</span><span class="sxs-lookup"><span data-stu-id="f54b8-210">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="f54b8-211">En cambio, todas las clases de C# heredan implícitamente de la clase <xref:System.Object> que admite la jerarquía de clases .NET y proporciona servicios de bajo nivel a todas las clases.</span><span class="sxs-lookup"><span data-stu-id="f54b8-211">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="f54b8-212">C# no admite la herencia múltiple.</span><span class="sxs-lookup"><span data-stu-id="f54b8-212">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="f54b8-213">Es decir, solo puede especificar una clase base para una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f54b8-213">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="f54b8-214">Para heredar de una clase base:</span><span class="sxs-lookup"><span data-stu-id="f54b8-214">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass { }
```

<span data-ttu-id="f54b8-215">De forma predeterminada, todas las clases se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="f54b8-215">By default all classes can be inherited.</span></span> <span data-ttu-id="f54b8-216">Sin embargo, puede especificar si una clase no se debe usar como clase base o bien crear una clase que solo se pueda usar como clase base.</span><span class="sxs-lookup"><span data-stu-id="f54b8-216">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="f54b8-217">Para especificar que una clase no se puede usar como clase base:</span><span class="sxs-lookup"><span data-stu-id="f54b8-217">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="f54b8-218">Para especificar que una clase se puede usar solo como clase base y no se pueden crear instancias de esta:</span><span class="sxs-lookup"><span data-stu-id="f54b8-218">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="f54b8-219">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f54b8-219">For more information, see:</span></span>

- [<span data-ttu-id="f54b8-220">sealed</span><span class="sxs-lookup"><span data-stu-id="f54b8-220">sealed</span></span>](../../language-reference/keywords/sealed.md)
- [<span data-ttu-id="f54b8-221">abstract</span><span class="sxs-lookup"><span data-stu-id="f54b8-221">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="f54b8-222">Reemplazar miembros</span><span class="sxs-lookup"><span data-stu-id="f54b8-222">Overriding Members</span></span>

<span data-ttu-id="f54b8-223">De forma predeterminada, una clase derivada hereda todos los miembros de su clase base.</span><span class="sxs-lookup"><span data-stu-id="f54b8-223">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="f54b8-224">Si desea cambiar el comportamiento del miembro heredado, debe invalidarlo.</span><span class="sxs-lookup"><span data-stu-id="f54b8-224">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="f54b8-225">Es decir, se puede definir una nueva implementación del método, la propiedad o el evento en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f54b8-225">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="f54b8-226">Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:</span><span class="sxs-lookup"><span data-stu-id="f54b8-226">The following modifiers are used to control how properties and methods are overridden:</span></span>

| <span data-ttu-id="f54b8-227">Modificador de C#</span><span class="sxs-lookup"><span data-stu-id="f54b8-227">C# Modifier</span></span> | <span data-ttu-id="f54b8-228">Definición</span><span class="sxs-lookup"><span data-stu-id="f54b8-228">Definition</span></span> |
|--|--|
| [<span data-ttu-id="f54b8-229">virtual</span><span class="sxs-lookup"><span data-stu-id="f54b8-229">virtual</span></span>](../../language-reference/keywords/virtual.md) | <span data-ttu-id="f54b8-230">Permite invalidar un miembro de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f54b8-230">Allows a class member to be overridden in a derived class.</span></span> |
| [<span data-ttu-id="f54b8-231">override</span><span class="sxs-lookup"><span data-stu-id="f54b8-231">override</span></span>](../../language-reference/keywords/override.md) | <span data-ttu-id="f54b8-232">Invalida un miembro virtual (invalidable) definido en la clase base.</span><span class="sxs-lookup"><span data-stu-id="f54b8-232">Overrides a virtual (overridable) member defined in the base class.</span></span> |
| [<span data-ttu-id="f54b8-233">abstract</span><span class="sxs-lookup"><span data-stu-id="f54b8-233">abstract</span></span>](../../language-reference/keywords/abstract.md) | <span data-ttu-id="f54b8-234">Requiere que se invalide un miembro de clase en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f54b8-234">Requires that a class member to be overridden in the derived class.</span></span> |
| [<span data-ttu-id="f54b8-235">new (modificador)</span><span class="sxs-lookup"><span data-stu-id="f54b8-235">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md) | <span data-ttu-id="f54b8-236">Oculta un miembro heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="f54b8-236">Hides a member inherited from a base class</span></span> |

## <a name="interfaces"></a><span data-ttu-id="f54b8-237">Interfaces</span><span class="sxs-lookup"><span data-stu-id="f54b8-237">Interfaces</span></span>

<span data-ttu-id="f54b8-238">Las interfaces, como las clases, definen un conjunto de propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="f54b8-238">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="f54b8-239">Pero de forma contraria a las clases, las interfaces no proporcionan implementación.</span><span class="sxs-lookup"><span data-stu-id="f54b8-239">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="f54b8-240">Se implementan como clases y se definen como entidades separadas de las clases.</span><span class="sxs-lookup"><span data-stu-id="f54b8-240">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="f54b8-241">Una interfaz representa un contrato, en el cual una clase que implementa una interfaz debe implementar cualquier aspecto de dicha interfaz exactamente como esté definido.</span><span class="sxs-lookup"><span data-stu-id="f54b8-241">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="f54b8-242">Para definir una interfaz:</span><span class="sxs-lookup"><span data-stu-id="f54b8-242">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void DoSomething();
}
```

<span data-ttu-id="f54b8-243">Para implementar una interfaz en una clase:</span><span class="sxs-lookup"><span data-stu-id="f54b8-243">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.DoSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="f54b8-244">Para obtener más información, vea el artículo de la guía de programación sobre [interfaces](../interfaces/index.md) y el artículo de la referencia del lenguaje sobre la palabra clave [interface](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-244">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="f54b8-245">Genéricos</span><span class="sxs-lookup"><span data-stu-id="f54b8-245">Generics</span></span>

<span data-ttu-id="f54b8-246">Las clases, las estructuras, las interfaces y los métodos de .NET pueden incluir *parámetros de tipo* que definen los tipos de objetos que estos pueden almacenar o usar.</span><span class="sxs-lookup"><span data-stu-id="f54b8-246">Classes, structures, interfaces, and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="f54b8-247">El ejemplo más común de elementos genéricos es una colección, donde se puede especificar el tipo de objetos que se va a almacenar en una colección.</span><span class="sxs-lookup"><span data-stu-id="f54b8-247">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="f54b8-248">Para definir una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="f54b8-248">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="f54b8-249">Para crear una instancia de una clase genérica:</span><span class="sxs-lookup"><span data-stu-id="f54b8-249">To create an instance of a generic class:</span></span>

```csharp
var sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="f54b8-250">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f54b8-250">For more information, see:</span></span>

- [<span data-ttu-id="f54b8-251">Elementos genéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="f54b8-251">Generics in .NET</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="f54b8-252">Aspectos genéricos: Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f54b8-252">Generics - C# Programming Guide</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="f54b8-253">Delegados</span><span class="sxs-lookup"><span data-stu-id="f54b8-253">Delegates</span></span>

<span data-ttu-id="f54b8-254">Un *delegado* es un tipo que define una firma de método y que puede proporcionar una referencia a cualquier método con una firma compatible.</span><span class="sxs-lookup"><span data-stu-id="f54b8-254">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="f54b8-255">Puede invocar (o llamar) al método a través del delegado.</span><span class="sxs-lookup"><span data-stu-id="f54b8-255">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="f54b8-256">Los delegados se utilizan para pasar métodos como argumentos a otros métodos.</span><span class="sxs-lookup"><span data-stu-id="f54b8-256">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="f54b8-257">Los controladores de eventos no son más que métodos que se invocan a través de delegados.</span><span class="sxs-lookup"><span data-stu-id="f54b8-257">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="f54b8-258">Para obtener más información sobre el uso de delegados en el control de eventos, vea [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-258">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="f54b8-259">Para crear un delegado:</span><span class="sxs-lookup"><span data-stu-id="f54b8-259">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="f54b8-260">Para crear una referencia a un método que coincida con la firma especificada por el delegado:</span><span class="sxs-lookup"><span data-stu-id="f54b8-260">To create a reference to a method that matches the signature specified by the delegate:</span></span>

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

<span data-ttu-id="f54b8-261">Para obtener más información, vea el artículo de la guía de programación sobre [Delegados](../delegates/index.md) y el artículo de la referencia del lenguaje sobre la palabra clave [delegate](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="f54b8-261">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="f54b8-262">Vea también</span><span class="sxs-lookup"><span data-stu-id="f54b8-262">See also</span></span>

- [<span data-ttu-id="f54b8-263">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f54b8-263">C# Programming Guide</span></span>](../index.md)
