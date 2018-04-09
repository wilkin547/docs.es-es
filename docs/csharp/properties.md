---
title: Propiedades
description: Obtenga información sobre las propiedades de C#, que incluyen características para la validación, valores calculados, evaluación diferida y notificaciones de cambio de propiedad.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 04/03/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 6950d25a-bba1-4744-b7c7-a3cc90438c55
ms.openlocfilehash: 2a25919048f94211b1696ac8c8471a14ce6e15c5
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="properties"></a><span data-ttu-id="86c04-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="86c04-104">Properties</span></span>

<span data-ttu-id="86c04-105">Las propiedades son ciudadanos de primera clase en C#.</span><span class="sxs-lookup"><span data-stu-id="86c04-105">Properties are first class citizens in C#.</span></span> <span data-ttu-id="86c04-106">El lenguaje define la sintaxis que permite a los desarrolladores escribir código que exprese con precisión su intención de diseño.</span><span class="sxs-lookup"><span data-stu-id="86c04-106">The language defines syntax that enables developers to write code that accurately expresses their design intent.</span></span>

<span data-ttu-id="86c04-107">Las propiedades se comportan como campos cuando se obtiene acceso a ellas.</span><span class="sxs-lookup"><span data-stu-id="86c04-107">Properties behave like fields when they are accessed.</span></span>
<span data-ttu-id="86c04-108">Pero, a diferencia de los campos, las propiedades se implementan con descriptores de acceso que definen las instrucciones que se ejecutan cuando se tiene acceso a una propiedad o se asigna.</span><span class="sxs-lookup"><span data-stu-id="86c04-108">However, unlike fields, properties are implemented with accessors that define the statements executed when a property is accessed or assigned.</span></span>

## <a name="property-syntax"></a><span data-ttu-id="86c04-109">Sintaxis de propiedades</span><span class="sxs-lookup"><span data-stu-id="86c04-109">Property Syntax</span></span>

<span data-ttu-id="86c04-110">La sintaxis para propiedades es una extensión natural de los campos.</span><span class="sxs-lookup"><span data-stu-id="86c04-110">The syntax for properties is a natural extension to fields.</span></span> <span data-ttu-id="86c04-111">Un campo define una ubicación de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="86c04-111">A field defines a storage location:</span></span>

```csharp
public class Person
{
    public string FirstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="86c04-112">Una definición de propiedad contiene las declaraciones para un descriptor de acceso `get` y `set` que recupera y asigna el valor de esa propiedad:</span><span class="sxs-lookup"><span data-stu-id="86c04-112">A property definition contains declarations for a `get` and `set` accessor that retrieves and assigns the value of that property:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="86c04-113">La sintaxis anterior es la sintaxis *de propiedades automáticas*.</span><span class="sxs-lookup"><span data-stu-id="86c04-113">The syntax shown above is the *auto property* syntax.</span></span> <span data-ttu-id="86c04-114">El compilador genera la ubicación de almacenamiento para el campo que respalda a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="86c04-114">The compiler generates the storage location for the field that backs up the property.</span></span> <span data-ttu-id="86c04-115">El compilador también implementa el cuerpo de los descriptores de acceso `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="86c04-115">The compiler also implements the body of the `get` and `set` accessors.</span></span>

<span data-ttu-id="86c04-116">A veces, necesita inicializar una propiedad en un valor distinto del predeterminado para su tipo.</span><span class="sxs-lookup"><span data-stu-id="86c04-116">Sometimes, you need to initialize a property to a value other than the default for its type.</span></span>  <span data-ttu-id="86c04-117">C# permite esto estableciendo un valor después de la llave de cierre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="86c04-117">C# enables that by setting a value after the closing brace for the property.</span></span> <span data-ttu-id="86c04-118">Puede que prefiera que el valor inicial para la propiedad `FirstName` sea la cadena vacía en lugar de `null`.</span><span class="sxs-lookup"><span data-stu-id="86c04-118">You may prefer the initial value for the `FirstName` property to be the empty string rather than `null`.</span></span> <span data-ttu-id="86c04-119">Debe especificarlo como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="86c04-119">You would specify that as shown below:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; } = string.Empty;

    // remaining implementation removed from listing
}
```

<span data-ttu-id="86c04-120">Esto es más útil para las propiedades de solo lectura, como verá posteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="86c04-120">This is most useful for read-only properties, as you'll see later in this topic.</span></span>

<span data-ttu-id="86c04-121">También puede definir su propio almacenamiento, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="86c04-121">You can also define the storage yourself, as shown below:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get { return firstName; }
        set { firstName = value; }
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="86c04-122">Cuando una implementación de propiedad es una expresión única, puede usar *miembros con forma de expresión* para el captador o establecedor:</span><span class="sxs-lookup"><span data-stu-id="86c04-122">When a property implementation is a single expression, you can use *expression-bodied members* for the getter or setter:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get => firstName;
        set => firstName = value;
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="86c04-123">Esta sintaxis simplificada se usará cuando sea necesario en todo el tema.</span><span class="sxs-lookup"><span data-stu-id="86c04-123">This simplified syntax will be used where applicable throughout this topic.</span></span>

<span data-ttu-id="86c04-124">La definición de propiedad anterior es una propiedad de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="86c04-124">The property definition shown above is a read-write property.</span></span> <span data-ttu-id="86c04-125">Observe la palabra clave `value` en el descriptor de acceso set.</span><span class="sxs-lookup"><span data-stu-id="86c04-125">Notice the keyword `value` in the set accessor.</span></span> <span data-ttu-id="86c04-126">El descriptor de acceso `set` siempre tiene un único parámetro denominado `value`.</span><span class="sxs-lookup"><span data-stu-id="86c04-126">The `set` accessor always has a single parameter named `value`.</span></span> <span data-ttu-id="86c04-127">El descriptor de acceso `get` tiene que devolver un valor que se pueda convertir al tipo de la propiedad (`string` en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="86c04-127">The `get` accessor must return a value that is convertible to the type of the property (`string` in this example).</span></span>
 
<span data-ttu-id="86c04-128">Estos son los conceptos básicos de la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="86c04-128">That's the basics of the syntax.</span></span> <span data-ttu-id="86c04-129">Hay muchas variantes distintas que admiten diversos lenguajes de diseño diferentes.</span><span class="sxs-lookup"><span data-stu-id="86c04-129">There are many different variations that support a variety of different design idioms.</span></span> <span data-ttu-id="86c04-130">Vamos a explorarlos y a aprender las opciones de sintaxis de cada uno.</span><span class="sxs-lookup"><span data-stu-id="86c04-130">Let's explore those, and learn the syntax options for each.</span></span>

## <a name="scenarios"></a><span data-ttu-id="86c04-131">Escenarios</span><span class="sxs-lookup"><span data-stu-id="86c04-131">Scenarios</span></span>

<span data-ttu-id="86c04-132">Los ejemplos anteriores mostraron uno de los casos más simples de definición de propiedad: una propiedad de lectura y escritura sin validación.</span><span class="sxs-lookup"><span data-stu-id="86c04-132">The examples above showed one of the simplest cases of property definition: a read-write property with no validation.</span></span> <span data-ttu-id="86c04-133">Al escribir el código que quiere en los descriptores de acceso `get` y `set`, puede crear muchos escenarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="86c04-133">By writing the code you want in the `get` and `set` accessors, you can create many different scenarios.</span></span>

### <a name="validation"></a><span data-ttu-id="86c04-134">Validación</span><span class="sxs-lookup"><span data-stu-id="86c04-134">Validation</span></span>

<span data-ttu-id="86c04-135">Puede escribir código en el descriptor de acceso `set` para asegurarse de que los valores representados por una propiedad siempre son válidos.</span><span class="sxs-lookup"><span data-stu-id="86c04-135">You can write code in the `set` accessor to ensure that the values represented by a property are always valid.</span></span> <span data-ttu-id="86c04-136">Por ejemplo, suponga que una regla para la clase `Person` es que el nombre no puede estar en blanco ni tener espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="86c04-136">For example, suppose one rule for the `Person` class is that the name cannot be blank, or whitespace.</span></span> <span data-ttu-id="86c04-137">Se escribiría de esta forma:</span><span class="sxs-lookup"><span data-stu-id="86c04-137">You would write that as follows:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get => firstName;
        set
        {
            if (string.IsNullOrWhiteSpace(value))
                throw new ArgumentException("First name must not be blank");
            firstName = value;
        }
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="86c04-138">El ejemplo anterior aplica la regla de que el nombre no debe estar en blanco ni tener espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="86c04-138">The example above enforces the rule that the first name must not be blank, or whitespace.</span></span> <span data-ttu-id="86c04-139">Si un desarrollador escribe:</span><span class="sxs-lookup"><span data-stu-id="86c04-139">If a developer writes</span></span>

```csharp
hero.FirstName = "";
```

<span data-ttu-id="86c04-140">Esa asignación produce una excepción `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="86c04-140">That assignment throws an `ArgumentException`.</span></span> <span data-ttu-id="86c04-141">Dado que un descriptor de acceso set de propiedad debe tener un tipo de valor devuelto void, los errores se notifican en el descriptor de acceso set iniciando una excepción.</span><span class="sxs-lookup"><span data-stu-id="86c04-141">Because a property set accessor must have a void return type, you report errors in the set accessor by throwing an exception.</span></span>

<span data-ttu-id="86c04-142">Es un caso sencillo de validación.</span><span class="sxs-lookup"><span data-stu-id="86c04-142">That is a simple case of validation.</span></span> <span data-ttu-id="86c04-143">Se puede extender esta misma sintaxis para todo lo que se necesite en el escenario.</span><span class="sxs-lookup"><span data-stu-id="86c04-143">You can extend this same syntax to anything needed in your scenario.</span></span> <span data-ttu-id="86c04-144">Se pueden comprobar las relaciones entre las diferentes propiedades o validar con respecto a cualquier condición externa.</span><span class="sxs-lookup"><span data-stu-id="86c04-144">You can check the relationships between different properties, or validate against any external conditions.</span></span> <span data-ttu-id="86c04-145">Todas las instrucciones de C# válidas son válidas en un descriptor de acceso de propiedad.</span><span class="sxs-lookup"><span data-stu-id="86c04-145">Any valid C# statements are valid in a property accessor.</span></span>

### <a name="read-only"></a><span data-ttu-id="86c04-146">De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="86c04-146">Read-only</span></span>

<span data-ttu-id="86c04-147">Hasta ahora, todas las definiciones de propiedad que se vieron son propiedades de lectura y escritura con descriptores de acceso públicos.</span><span class="sxs-lookup"><span data-stu-id="86c04-147">Up to this point, all the property definitions you have seen are read/write properties with public accessors.</span></span> <span data-ttu-id="86c04-148">No es la única accesibilidad válida para las propiedades.</span><span class="sxs-lookup"><span data-stu-id="86c04-148">That's not the only valid accessibility for properties.</span></span>
<span data-ttu-id="86c04-149">Se pueden crear propiedades de solo lectura, o proporcionar accesibilidad diferente a los descriptores de acceso set y get.</span><span class="sxs-lookup"><span data-stu-id="86c04-149">You can create read-only properties, or give different accessibility to the set and get accessors.</span></span> <span data-ttu-id="86c04-150">Suponga que su clase `Person` solo debe habilitar el cambio del valor de la propiedad `FirstName` desde otros métodos de esa clase.</span><span class="sxs-lookup"><span data-stu-id="86c04-150">Suppose that your `Person` class should only enable changing the value of the `FirstName` property from other methods in that class.</span></span> <span data-ttu-id="86c04-151">Podría asignar al descriptor de acceso set la accesibilidad `private` en lugar de `public`:</span><span class="sxs-lookup"><span data-stu-id="86c04-151">You could give the set accessor `private` accessibility instead of `public`:</span></span>

```csharp
public class Person
{
    public string FirstName { get; private set; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="86c04-152">Ahora, se puede obtener acceso a la propiedad `FirstName` desde cualquier código, pero solo puede asignarse desde otro código de la clase `Person`.</span><span class="sxs-lookup"><span data-stu-id="86c04-152">Now, the `FirstName` property can be accessed from any code, but it can only be assigned from other code in the `Person` class.</span></span>

<span data-ttu-id="86c04-153">Puede agregar cualquier modificador de acceso restrictivo al descriptor de acceso set o get.</span><span class="sxs-lookup"><span data-stu-id="86c04-153">You can add any restrictive access modifier to either the set or get accessors.</span></span> <span data-ttu-id="86c04-154">Ningún modificador de acceso que se coloque en el descriptor de acceso concreto debe ser más limitado que el modificador de acceso en la definición de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="86c04-154">Any access modifier you place on the individual accessor must be more limited than the access modifier on the property definition.</span></span> <span data-ttu-id="86c04-155">El ejemplo anterior es válido porque la propiedad `FirstName` es `public`, pero el descriptor de acceso set es `private`.</span><span class="sxs-lookup"><span data-stu-id="86c04-155">The above is legal because the `FirstName` property is `public`, but the set accessor is `private`.</span></span> <span data-ttu-id="86c04-156">No se puede declarar una propiedad `private` con un descriptor de acceso `public`.</span><span class="sxs-lookup"><span data-stu-id="86c04-156">You could not declare a `private` property with a `public` accessor.</span></span> <span data-ttu-id="86c04-157">Las declaraciones de propiedad también se pueden declarar como `protected`, `internal`, `protected internal`, `private protected` o incluso `private`.</span><span class="sxs-lookup"><span data-stu-id="86c04-157">Property declarations can also be declared `protected`, `internal`, `protected internal`, `private protected` or even `private`.</span></span>   

<span data-ttu-id="86c04-158">También es válido colocar el modificador más restrictivo en el descriptor de acceso `get`.</span><span class="sxs-lookup"><span data-stu-id="86c04-158">It is also legal to place the more restrictive modifier on the `get` accessor.</span></span> <span data-ttu-id="86c04-159">Por ejemplo, se podría tener una propiedad `public`, pero restringir el descriptor de acceso `get` a `private`.</span><span class="sxs-lookup"><span data-stu-id="86c04-159">For example, you could have a `public` property, but restrict the `get` accessor to `private`.</span></span> <span data-ttu-id="86c04-160">Ese escenario raramente se aplica en la práctica.</span><span class="sxs-lookup"><span data-stu-id="86c04-160">That scenario is rarely done in practice.</span></span>

<span data-ttu-id="86c04-161">También puede restringir las modificaciones de una propiedad, de manera que solo pueda establecerse en un constructor o en un inicializador de propiedades.</span><span class="sxs-lookup"><span data-stu-id="86c04-161">You can also restrict modifications to a property so that it can only be set in a constructor or a property initializer.</span></span> <span data-ttu-id="86c04-162">Puede modificar la clase `Person` de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="86c04-162">You can modify the `Person` class so as follows:</span></span>

```csharp
public class Person
{
    public Person(string firstName)
    {
        this.FirstName = firstName;
    }

    public string FirstName { get; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="86c04-163">Esta característica se usa normalmente para inicializar colecciones que están expuestas como propiedades de solo lectura:</span><span class="sxs-lookup"><span data-stu-id="86c04-163">This feature is most commonly used for initializing collections that are exposed as read-only properties:</span></span>

```csharp
public class Measurements
{
    public ICollection<DataPoint> points { get; } = new List<DataPoint>();
}
```

### <a name="computed-properties"></a><span data-ttu-id="86c04-164">Propiedades calculadas</span><span class="sxs-lookup"><span data-stu-id="86c04-164">Computed Properties</span></span>

<span data-ttu-id="86c04-165">Una propiedad no tiene por qué devolver únicamente el valor de un campo de miembro.</span><span class="sxs-lookup"><span data-stu-id="86c04-165">A property does not need to simply return the value of a member field.</span></span> <span data-ttu-id="86c04-166">Se pueden crear propiedades que devuelvan un valor calculado.</span><span class="sxs-lookup"><span data-stu-id="86c04-166">You can create properties that return a computed value.</span></span> <span data-ttu-id="86c04-167">Vamos a ampliar el objeto `Person` para que devuelva el nombre completo, que se calcula mediante la concatenación del nombre y el apellido:</span><span class="sxs-lookup"><span data-stu-id="86c04-167">Let's expand the `Person` object to return the full name, computed by concatenating the first and last names:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    public string FullName { get { return $"{FirstName} {LastName}"; } }
}
```

<span data-ttu-id="86c04-168">En el ejemplo anterior se usa la característica de [interpolación de cadenas](../csharp/language-reference/tokens/interpolated.md) para crear la cadena con formato para el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="86c04-168">The example above uses the [string interpolation](../csharp/language-reference/tokens/interpolated.md) feature to create the formatted string for the full name.</span></span>

<span data-ttu-id="86c04-169">También se pueden usar *miembros con forma de expresión*, que proporcionan una manera más concisa de crear la propiedad `FullName` calculada:</span><span class="sxs-lookup"><span data-stu-id="86c04-169">You can also use *expression-bodied members*, which provides a more succinct way to create the computed `FullName` property:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    public string FullName =>  $"{FirstName} {LastName}";
}
```
 
<span data-ttu-id="86c04-170">Los *miembros con forma de expresión* usan la sintaxis de *expresión lambda* para definir un método que contiene una única expresión.</span><span class="sxs-lookup"><span data-stu-id="86c04-170">*Expression-bodied members* use the *lambda expression* syntax to define a method that contain a single expression.</span></span> <span data-ttu-id="86c04-171">En este caso, esa expresión devuelve el nombre completo para el objeto person.</span><span class="sxs-lookup"><span data-stu-id="86c04-171">Here, that expression returns the full name for the person object.</span></span>

### <a name="lazy-evaluated-properties"></a><span data-ttu-id="86c04-172">Propiedades de evaluación diferida</span><span class="sxs-lookup"><span data-stu-id="86c04-172">Lazy Evaluated Properties</span></span>

<span data-ttu-id="86c04-173">Se puede combinar el concepto de una propiedad calculada con almacenamiento de información y crear una *propiedad de evaluación diferida*.</span><span class="sxs-lookup"><span data-stu-id="86c04-173">You can mix the concept of a computed property with storage and create a *lazy evaluated property*.</span></span>  <span data-ttu-id="86c04-174">Por ejemplo, se podría actualizar la propiedad `FullName` para que la cadena de formato solo apareciera la primera vez que se obtuvo acceso a ella:</span><span class="sxs-lookup"><span data-stu-id="86c04-174">For example, you could update the `FullName` property so that the string formatting only happened the first time it was accessed:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    private string fullName;
    public string FullName
    {
        get
        {
            if (fullName == null)
                fullName = $"{FirstName} {LastName}";
            return fullName;
        }
    }
}
```

<span data-ttu-id="86c04-175">Pero el código anterior contiene un error.</span><span class="sxs-lookup"><span data-stu-id="86c04-175">The above code contains a bug though.</span></span> <span data-ttu-id="86c04-176">Si el código actualiza el valor de la propiedad `FirstName` o `LastName`, el campo evaluado previamente `fullName` no es válido.</span><span class="sxs-lookup"><span data-stu-id="86c04-176">If code updates the value of either the `FirstName` or `LastName` property, the previously evaluated `fullName` field is invalid.</span></span> <span data-ttu-id="86c04-177">Es necesario actualizar los descriptores de acceso `set` de la propiedad `FirstName` y `LastName` para que el campo `fullName` se calcule de nuevo:</span><span class="sxs-lookup"><span data-stu-id="86c04-177">You need to update the `set` accessors of the `FirstName` and `LastName` property so that the `fullName` field is calculated again:</span></span>

```csharp
public class Person
{
    private string firstName;
    public string FirstName
    {
        get => firstName;
        set
        {
            firstName = value;
            fullName = null;
        }
    }

    private string lastName;
    public string LastName
    {
        get => lastName;
        set
        {
            lastName = value;
            fullName = null;
        }
    }

    private string fullName;
    public string FullName
    {
        get
        {
            if (fullName == null)
                fullName = $"{FirstName} {LastName}";
            return fullName;
        }
    }
}
```

<span data-ttu-id="86c04-178">Esta versión final da como resultado la propiedad `FullName` solo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="86c04-178">This final version evaluates the `FullName` property only when needed.</span></span>
<span data-ttu-id="86c04-179">Si la versión calculada previamente es válida, es la que se usa.</span><span class="sxs-lookup"><span data-stu-id="86c04-179">If the previously calculated version is valid, it's used.</span></span> <span data-ttu-id="86c04-180">Si otro cambio de estado invalida la versión calculada previamente, se vuelve a calcular.</span><span class="sxs-lookup"><span data-stu-id="86c04-180">If another state change invalidates the previously calculated version, it will be recalculated.</span></span> <span data-ttu-id="86c04-181">No es necesario que los desarrolladores que usan esta clase conozcan los detalles de la implementación.</span><span class="sxs-lookup"><span data-stu-id="86c04-181">Developers that use this class do not need to know the details of the implementation.</span></span> <span data-ttu-id="86c04-182">Ninguno de estos cambios internos afectan al uso del objeto Person.</span><span class="sxs-lookup"><span data-stu-id="86c04-182">None of these internal changes affect the use of the Person object.</span></span> <span data-ttu-id="86c04-183">Es el motivo principal para usar propiedades para exponer los miembros de datos de un objeto.</span><span class="sxs-lookup"><span data-stu-id="86c04-183">That's the key reason for using Properties to expose data members of an object.</span></span>
 
### <a name="inotifypropertychanged"></a><span data-ttu-id="86c04-184">INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="86c04-184">INotifyPropertyChanged</span></span>

<span data-ttu-id="86c04-185">Un último escenario donde se necesita escribir código en un descriptor de acceso de propiedad es para admitir la interfaz `INotifyPropertyChanged` que se usa para notificar a los clientes de enlace de datos el cambio de un valor.</span><span class="sxs-lookup"><span data-stu-id="86c04-185">A final scenario where you need to write code in a property accessor is to support the `INotifyPropertyChanged` interface used to notify data binding clients that a value has changed.</span></span> <span data-ttu-id="86c04-186">Cuando se cambia el valor de una propiedad, el objeto genera el evento `PropertyChanged` para indicar el cambio.</span><span class="sxs-lookup"><span data-stu-id="86c04-186">When the value of a property changes, the object raises the `PropertyChanged` event to indicate the change.</span></span> <span data-ttu-id="86c04-187">A su vez, las bibliotecas de enlace de datos actualizan los elementos de visualización en función de ese cambio.</span><span class="sxs-lookup"><span data-stu-id="86c04-187">The data binding libraries, in turn, update display elements based on that change.</span></span> <span data-ttu-id="86c04-188">El código siguiente muestra cómo se implementaría `INotifyPropertyChanged` para la propiedad `FirstName` de esta clase person.</span><span class="sxs-lookup"><span data-stu-id="86c04-188">The code below shows how you would implement `INotifyPropertyChanged` for the `FirstName` property of this person class.</span></span>

```csharp
public class Person : INotifyPropertyChanged
{
    public string FirstName
    {
        get => firstName;
        set
        {
            if (string.IsNullOrWhiteSpace(value))
                throw new ArgumentException("First name must not be blank");
            if (value != firstName)
            {
                PropertyChanged?.Invoke(this, 
                    new PropertyChangedEventArgs(nameof(FirstName)));
            }
            firstName = value;
        }
    }
    private string firstName;

    public event PropertyChangedEventHandler PropertyChanged;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="86c04-189">El operador `?.` se denomina *operador condicional NULL*.</span><span class="sxs-lookup"><span data-stu-id="86c04-189">The `?.` operator is called the *null conditional operator*.</span></span> <span data-ttu-id="86c04-190">Comprueba si existe una referencia nula antes de evaluar el lado derecho del operador.</span><span class="sxs-lookup"><span data-stu-id="86c04-190">It checks for a null reference before evaluating the right side of the operator.</span></span> <span data-ttu-id="86c04-191">El resultado final es que si no hay ningún suscriptor para el evento `PropertyChanged`, no se ejecuta el código para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="86c04-191">The end result is that if there are no subscribers to the `PropertyChanged` event, the code to raise the event doesn't execute.</span></span> <span data-ttu-id="86c04-192">En ese caso, se producirá una `NullReferenceException` sin esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="86c04-192">It would throw a `NullReferenceException` without this check in that case.</span></span> <span data-ttu-id="86c04-193">Para obtener más detalles, vea la página sobre [`events`](delegates-events.md).</span><span class="sxs-lookup"><span data-stu-id="86c04-193">See the page on [`events`](delegates-events.md) for more details.</span></span> <span data-ttu-id="86c04-194">En este ejemplo también se usa el nuevo operador `nameof` para convertir el símbolo de nombre de propiedad en su representación de texto.</span><span class="sxs-lookup"><span data-stu-id="86c04-194">This example also uses the new `nameof` operator to convert from the property name symbol to its text representation.</span></span>
<span data-ttu-id="86c04-195">Con `nameof` se pueden reducir los errores en los que no se escribió correctamente el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="86c04-195">Using `nameof` can reduce errors where you have mistyped the name of the property.</span></span>

<span data-ttu-id="86c04-196">De nuevo, es un ejemplo de un caso en el que se puede escribir código en los descriptores de acceso para admitir los escenarios que se necesitan.</span><span class="sxs-lookup"><span data-stu-id="86c04-196">Again, this is an example of a case where you can write code in your accessors to support the scenarios you need.</span></span>

## <a name="summing-up"></a><span data-ttu-id="86c04-197">Resumen</span><span class="sxs-lookup"><span data-stu-id="86c04-197">Summing up</span></span>

<span data-ttu-id="86c04-198">Las propiedades son una forma de campos inteligentes en una clase o un objeto.</span><span class="sxs-lookup"><span data-stu-id="86c04-198">Properties are a form of smart fields in a class or object.</span></span> <span data-ttu-id="86c04-199">Desde fuera del objeto, parecen campos en el objeto.</span><span class="sxs-lookup"><span data-stu-id="86c04-199">From outside the object, they appear like fields in the object.</span></span> <span data-ttu-id="86c04-200">Pero las propiedades pueden implementarse mediante la paleta completa de funcionalidad de C#.</span><span class="sxs-lookup"><span data-stu-id="86c04-200">However, properties can be implemented using the full palette of C# functionality.</span></span>
<span data-ttu-id="86c04-201">Se puede proporcionar validación, tipos diferentes de accesibilidad, evaluación diferida o los requisitos que se necesiten para cada escenario.</span><span class="sxs-lookup"><span data-stu-id="86c04-201">You can provide validation, different accessibility, lazy evaluation, or any requirements your scenarios need.</span></span>
