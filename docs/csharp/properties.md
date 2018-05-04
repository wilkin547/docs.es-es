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
ms.openlocfilehash: 05e51d527dc3c05301fc85d7717c751dc46bf9fa
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="properties"></a>Propiedades

Las propiedades son ciudadanos de primera clase en C#. El lenguaje define la sintaxis que permite a los desarrolladores escribir código que exprese con precisión su intención de diseño.

Las propiedades se comportan como campos cuando se obtiene acceso a ellas.
Pero, a diferencia de los campos, las propiedades se implementan con descriptores de acceso que definen las instrucciones que se ejecutan cuando se tiene acceso a una propiedad o se asigna.

## <a name="property-syntax"></a>Sintaxis de propiedades

La sintaxis para propiedades es una extensión natural de los campos. Un campo define una ubicación de almacenamiento:

```csharp
public class Person
{
    public string FirstName;
    // remaining implementation removed from listing
}
```

Una definición de propiedad contiene las declaraciones para un descriptor de acceso `get` y `set` que recupera y asigna el valor de esa propiedad:

```csharp
public class Person
{
    public string FirstName { get; set; }

    // remaining implementation removed from listing
}
```

La sintaxis anterior es la sintaxis *de propiedades automáticas*. El compilador genera la ubicación de almacenamiento para el campo que respalda a la propiedad. El compilador también implementa el cuerpo de los descriptores de acceso `get` y `set`.

A veces, necesita inicializar una propiedad en un valor distinto del predeterminado para su tipo.  C# permite esto estableciendo un valor después de la llave de cierre de la propiedad. Puede que prefiera que el valor inicial para la propiedad `FirstName` sea la cadena vacía en lugar de `null`. Debe especificarlo como se muestra a continuación:

```csharp
public class Person
{
    public string FirstName { get; set; } = string.Empty;

    // remaining implementation removed from listing
}
```

Esto es más útil para las propiedades de solo lectura, como verá posteriormente en este tema.

También puede definir su propio almacenamiento, como se muestra a continuación:

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

Cuando una implementación de propiedad es una expresión única, puede usar *miembros con forma de expresión* para el captador o establecedor:

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

Esta sintaxis simplificada se usará cuando sea necesario en todo el tema.

La definición de propiedad anterior es una propiedad de lectura y escritura. Observe la palabra clave `value` en el descriptor de acceso set. El descriptor de acceso `set` siempre tiene un único parámetro denominado `value`. El descriptor de acceso `get` tiene que devolver un valor que se pueda convertir al tipo de la propiedad (`string` en este ejemplo).
 
Estos son los conceptos básicos de la sintaxis. Hay muchas variantes distintas que admiten diversos lenguajes de diseño diferentes. Vamos a explorarlos y a aprender las opciones de sintaxis de cada uno.

## <a name="scenarios"></a>Escenarios

Los ejemplos anteriores mostraron uno de los casos más simples de definición de propiedad: una propiedad de lectura y escritura sin validación. Al escribir el código que quiere en los descriptores de acceso `get` y `set`, puede crear muchos escenarios diferentes.

### <a name="validation"></a>Validación

Puede escribir código en el descriptor de acceso `set` para asegurarse de que los valores representados por una propiedad siempre son válidos. Por ejemplo, suponga que una regla para la clase `Person` es que el nombre no puede estar en blanco ni tener espacios en blanco. Se escribiría de esta forma:

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

En el ejemplo anterior, se aplica la regla de que el nombre no debe estar en blanco ni tener espacios en blanco. Si un desarrollador escribe:

```csharp
hero.FirstName = "";
```

Esa asignación produce una excepción `ArgumentException`. Dado que un descriptor de acceso set de propiedad debe tener un tipo de valor devuelto void, los errores se notifican en el descriptor de acceso set iniciando una excepción.

Es un caso sencillo de validación. Se puede extender esta misma sintaxis para todo lo que se necesite en el escenario. Se pueden comprobar las relaciones entre las diferentes propiedades o validar con respecto a cualquier condición externa. Todas las instrucciones de C# válidas son válidas en un descriptor de acceso de propiedad.

### <a name="read-only"></a>De sólo lectura

Hasta ahora, todas las definiciones de propiedad que se vieron son propiedades de lectura y escritura con descriptores de acceso públicos. No es la única accesibilidad válida para las propiedades.
Se pueden crear propiedades de solo lectura, o proporcionar accesibilidad diferente a los descriptores de acceso set y get. Suponga que su clase `Person` solo debe habilitar el cambio del valor de la propiedad `FirstName` desde otros métodos de esa clase. Podría asignar al descriptor de acceso set la accesibilidad `private` en lugar de `public`:

```csharp
public class Person
{
    public string FirstName { get; private set; }

    // remaining implementation removed from listing
}
```

Ahora, se puede obtener acceso a la propiedad `FirstName` desde cualquier código, pero solo puede asignarse desde otro código de la clase `Person`.

Puede agregar cualquier modificador de acceso restrictivo al descriptor de acceso set o get. Ningún modificador de acceso que se coloque en el descriptor de acceso concreto debe ser más limitado que el modificador de acceso en la definición de la propiedad. El ejemplo anterior es válido porque la propiedad `FirstName` es `public`, pero el descriptor de acceso set es `private`. No se puede declarar una propiedad `private` con un descriptor de acceso `public`. Las declaraciones de propiedad también se pueden declarar como `protected`, `internal`, `protected internal`, `private protected` o incluso `private`.   

También es válido colocar el modificador más restrictivo en el descriptor de acceso `get`. Por ejemplo, se podría tener una propiedad `public`, pero restringir el descriptor de acceso `get` a `private`. Ese escenario raramente se aplica en la práctica.

También puede restringir las modificaciones de una propiedad, de manera que solo pueda establecerse en un constructor o en un inicializador de propiedades. Puede modificar la clase `Person` de la manera siguiente:

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

Esta característica se usa normalmente para inicializar colecciones que están expuestas como propiedades de solo lectura:

```csharp
public class Measurements
{
    public ICollection<DataPoint> points { get; } = new List<DataPoint>();
}
```

### <a name="computed-properties"></a>Propiedades calculadas

Una propiedad no tiene por qué devolver únicamente el valor de un campo de miembro. Se pueden crear propiedades que devuelvan un valor calculado. Vamos a ampliar el objeto `Person` para que devuelva el nombre completo, que se calcula mediante la concatenación del nombre y el apellido:

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    public string FullName { get { return $"{FirstName} {LastName}"; } }
}
```

En el ejemplo anterior se usa la característica de [interpolación de cadenas](../csharp/language-reference/tokens/interpolated.md) para crear la cadena con formato para el nombre completo.

También se pueden usar *miembros con forma de expresión*, que proporcionan una manera más concisa de crear la propiedad `FullName` calculada:

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    public string FullName =>  $"{FirstName} {LastName}";
}
```
 
Los *miembros con forma de expresión* usan la sintaxis de *expresión lambda* para definir un método que contiene una única expresión. En este caso, esa expresión devuelve el nombre completo para el objeto person.

### <a name="lazy-evaluated-properties"></a>Propiedades de evaluación diferida

Se puede combinar el concepto de una propiedad calculada con almacenamiento de información y crear una *propiedad de evaluación diferida*.  Por ejemplo, se podría actualizar la propiedad `FullName` para que la cadena de formato solo apareciera la primera vez que se obtuvo acceso a ella:

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

Pero el código anterior contiene un error. Si el código actualiza el valor de la propiedad `FirstName` o `LastName`, el campo evaluado previamente `fullName` no es válido. Es necesario actualizar los descriptores de acceso `set` de la propiedad `FirstName` y `LastName` para que el campo `fullName` se calcule de nuevo:

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

Esta versión final da como resultado la propiedad `FullName` solo cuando sea necesario.
Si la versión calculada previamente es válida, es la que se usa. Si otro cambio de estado invalida la versión calculada previamente, se vuelve a calcular. No es necesario que los desarrolladores que usan esta clase conozcan los detalles de la implementación. Ninguno de estos cambios internos afectan al uso del objeto Person. Es el motivo principal para usar propiedades para exponer los miembros de datos de un objeto.
 
### <a name="inotifypropertychanged"></a>INotifyPropertyChanged

Un último escenario donde se necesita escribir código en un descriptor de acceso de propiedad es para admitir la interfaz `INotifyPropertyChanged` que se usa para notificar a los clientes de enlace de datos el cambio de un valor. Cuando se cambia el valor de una propiedad, el objeto genera el evento `PropertyChanged` para indicar el cambio. A su vez, las bibliotecas de enlace de datos actualizan los elementos de visualización en función de ese cambio. El código siguiente muestra cómo se implementaría `INotifyPropertyChanged` para la propiedad `FirstName` de esta clase person.

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

El operador `?.` se denomina *operador condicional NULL*. Comprueba si existe una referencia nula antes de evaluar el lado derecho del operador. El resultado final es que si no hay ningún suscriptor para el evento `PropertyChanged`, no se ejecuta el código para generar el evento. En ese caso, se producirá una `NullReferenceException` sin esta comprobación. Para obtener más detalles, vea la página sobre [`events`](delegates-events.md). En este ejemplo también se usa el nuevo operador `nameof` para convertir el símbolo de nombre de propiedad en su representación de texto.
Con `nameof` se pueden reducir los errores en los que no se escribió correctamente el nombre de la propiedad.

De nuevo, es un ejemplo de un caso en el que se puede escribir código en los descriptores de acceso para admitir los escenarios que se necesitan.

## <a name="summing-up"></a>Resumen

Las propiedades son una forma de campos inteligentes en una clase o un objeto. Desde fuera del objeto, parecen campos en el objeto. Pero las propiedades pueden implementarse mediante la paleta completa de funcionalidad de C#.
Se puede proporcionar validación, tipos diferentes de accesibilidad, evaluación diferida o los requisitos que se necesiten para cada escenario.
