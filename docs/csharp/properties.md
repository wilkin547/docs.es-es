---
title: Propiedades
description: Obtenga información sobre las propiedades de C#, que incluyen características para la validación, valores calculados, evaluación diferida y notificaciones de cambio de propiedad.
ms.technology: csharp-fundamentals
ms.date: 04/25/2018
ms.openlocfilehash: 28050a77e1f7b0ac148bba6112aa79ef4d46b710
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "89358913"
---
# <a name="properties"></a>Propiedades

Las propiedades son ciudadanos de primera clase en C#. El lenguaje define la sintaxis que permite a los desarrolladores escribir código que exprese con precisión su intención de diseño.

Las propiedades se comportan como campos cuando se obtiene acceso a ellas.
Pero, a diferencia de los campos, las propiedades se implementan con descriptores de acceso que definen las instrucciones que se ejecutan cuando se tiene acceso a una propiedad o se asigna.

## <a name="property-syntax"></a>Sintaxis de las propiedades

La sintaxis para propiedades es una extensión natural de los campos. Un campo define una ubicación de almacenamiento:

[!code-csharp[Person class with public fields](../../samples/snippets/csharp/properties/Person.cs#1)]

Una definición de propiedad contiene las declaraciones para un descriptor de acceso `get` y `set` que recupera y asigna el valor de esa propiedad:

[!code-csharp[Person class with public properties](../../samples/snippets/csharp/properties/Person.cs#2)]

La sintaxis anterior es la sintaxis *de propiedades automáticas*. El compilador genera la ubicación de almacenamiento para el campo que respalda a la propiedad. El compilador también implementa el cuerpo de los descriptores de acceso `get` y `set`.

A veces, necesita inicializar una propiedad en un valor distinto del predeterminado para su tipo.  C# permite esto estableciendo un valor después de la llave de cierre de la propiedad. Puede que prefiera que el valor inicial para la propiedad `FirstName` sea la cadena vacía en lugar de `null`. Debe especificarlo como se muestra a continuación:

[!code-csharp[Person class with properties and initializer](../../samples/snippets/csharp/properties/Person.cs#3)]

La inicialización específica es más útil en las propiedades de solo lectura, como verá posteriormente en este artículo.

También puede definir su propio almacenamiento, como se muestra a continuación:

[!code-csharp[Person class with properties and backing field](../../samples/snippets/csharp/properties/Person.cs#4)]

Cuando una implementación de propiedad es una expresión única, puede usar *miembros con forma de expresión* para el captador o establecedor:

[!code-csharp[Person class with properties and expression bodied getters and setters](../../samples/snippets/csharp/properties/Person.cs#5)]

Esta sintaxis simplificada se usará cuando sea necesario en todo el artículo.

La definición de propiedad anterior es una propiedad de lectura y escritura. Observe la palabra clave `value` en el descriptor de acceso set. El descriptor de acceso `set` siempre tiene un único parámetro denominado `value`. El descriptor de acceso `get` tiene que devolver un valor que se pueda convertir al tipo de la propiedad (`string` en este ejemplo).

Estos son los conceptos básicos de la sintaxis. Hay muchas variantes distintas que admiten diversos lenguajes de diseño diferentes. Vamos a explorarlas y a aprender las opciones de sintaxis de cada una.

## <a name="scenarios"></a>Escenarios

Los ejemplos anteriores mostraron uno de los casos más simples de definición de propiedad: una propiedad de lectura y escritura sin validación. Al escribir el código que quiere en los descriptores de acceso `get` y `set`, puede crear muchos escenarios diferentes.

### <a name="validation"></a>Validación

Puede escribir código en el descriptor de acceso `set` para asegurarse de que los valores representados por una propiedad siempre son válidos. Por ejemplo, suponga que una regla para la clase `Person` es que el nombre no puede estar en blanco ni tener espacios en blanco. Se escribiría de esta forma:

[!code-csharp[Validating property setters](../../samples/snippets/csharp/properties/Person.cs#6)]

El ejemplo anterior se puede simplificar usando una expresión `throw` como parte de la validación del establecedor de propiedad:

[!code-csharp[Validating property setters](../../samples/snippets/csharp/properties/Person.cs#7)]

En el ejemplo anterior, se aplica la regla de que el nombre no debe estar en blanco ni tener espacios en blanco. Si un desarrollador escribe:

```csharp
hero.FirstName = "";
```

Esa asignación produce una excepción `ArgumentException`. Dado que un descriptor de acceso set de propiedad debe tener un tipo de valor devuelto void, los errores se notifican en el descriptor de acceso set iniciando una excepción.

Se puede extender esta misma sintaxis para todo lo que se necesite en el escenario. Se pueden comprobar las relaciones entre las diferentes propiedades o validar con respecto a cualquier condición externa. Todas las instrucciones de C# válidas son válidas en un descriptor de acceso de propiedad.

### <a name="read-only"></a>Solo lectura

Hasta ahora, todas las definiciones de propiedad que se vieron son propiedades de lectura y escritura con descriptores de acceso públicos. No es la única accesibilidad válida para las propiedades.
Se pueden crear propiedades de solo lectura, o proporcionar accesibilidad diferente a los descriptores de acceso set y get. Suponga que su clase `Person` solo debe habilitar el cambio del valor de la propiedad `FirstName` desde otros métodos de esa clase. Podría asignar al descriptor de acceso set la accesibilidad `private` en lugar de `public`:

[!code-csharp[Using a private setter for a publicly readonly property](../../samples/snippets/csharp/properties/Person.cs#8)]

Ahora, se puede obtener acceso a la propiedad `FirstName` desde cualquier código, pero solo puede asignarse desde otro código de la clase `Person`.

Puede agregar cualquier modificador de acceso restrictivo al descriptor de acceso set o get. Ningún modificador de acceso que se coloque en el descriptor de acceso concreto debe ser más limitado que el modificador de acceso en la definición de la propiedad. El ejemplo anterior es válido porque la propiedad `FirstName` es `public`, pero el descriptor de acceso set es `private`. No se puede declarar una propiedad `private` con un descriptor de acceso `public`. Las declaraciones de propiedad también se pueden declarar como `protected`, `internal`, `protected internal` o incluso `private`.

También es válido colocar el modificador más restrictivo en el descriptor de acceso `get`. Por ejemplo, se podría tener una propiedad `public`, pero restringir el descriptor de acceso `get` a `private`. Ese escenario raramente se aplica en la práctica.

También puede restringir las modificaciones de una propiedad, de manera que solo pueda establecerse en un constructor o en un inicializador de propiedades. Puede modificar la clase `Person` de la manera siguiente:

[!code-csharp[A readonly auto implemented property](../../samples/snippets/csharp/properties/Person.cs#9)]

Esta característica se usa normalmente para inicializar colecciones que están expuestas como propiedades de solo lectura:

```csharp
public class Measurements
{
    public ICollection<DataPoint> points { get; } = new List<DataPoint>();
}
```

### <a name="computed-properties"></a>Propiedades calculadas

Una propiedad no tiene por qué devolver únicamente el valor de un campo de miembro. Se pueden crear propiedades que devuelvan un valor calculado. Vamos a ampliar el objeto `Person` para que devuelva el nombre completo, que se calcula mediante la concatenación del nombre y el apellido:

[!code-csharp[A computed property](../../samples/snippets/csharp/properties/Person.cs#10)]

En el ejemplo anterior se usa la característica de [interpolación de cadenas](./language-reference/tokens/interpolated.md) para crear la cadena con formato para el nombre completo.

También se pueden usar un *miembro con forma de expresión*, que proporciona una manera más concisa de crear la propiedad `FullName` calculada:

[!code-csharp[A computed property using an expression bodied member](../../samples/snippets/csharp/properties/Person.cs#11)]

Los *miembros con forma de expresión* usan la sintaxis de *expresión lambda* para definir métodos que contienen una única expresión. En este caso, esa expresión devuelve el nombre completo para el objeto person.

### <a name="cached-evaluated-properties"></a>Propiedades de evaluación en caché

Se puede combinar el concepto de una propiedad calculada con almacenamiento de información y crear una *propiedad de evaluación en caché*.  Por ejemplo, se podría actualizar la propiedad `FullName` para que la cadena de formato solo apareciera la primera vez que se obtuvo acceso a ella:

[!code-csharp[Caching the value of a computed property](../../samples/snippets/csharp/properties/Person.cs#12)]

Pero el código anterior contiene un error. Si el código actualiza el valor de la propiedad `FirstName` o `LastName`, el campo evaluado previamente `fullName` no es válido. Hay que modificar los descriptores de acceso `set` de la propiedad `FirstName` y `LastName` para que el campo `fullName` se calcule de nuevo:

[!code-csharp[Invalidating the cache correctly](../../samples/snippets/csharp/properties/Person.cs#13)]

Esta versión final da como resultado la propiedad `FullName` solo cuando sea necesario.
Si la versión calculada previamente es válida, es la que se usa. Si otro cambio de estado invalida la versión calculada previamente, se vuelve a calcular. No es necesario que los desarrolladores que usan esta clase conozcan los detalles de la implementación. Ninguno de estos cambios internos afectan al uso del objeto Person. Es el motivo principal para usar propiedades para exponer los miembros de datos de un objeto.

### <a name="attaching-attributes-to-auto-implemented-properties"></a>Asociar atributos a propiedades implementadas automáticamente

A partir de C# 7.3, los atributos de campo se pueden conectar al campo de respaldo generado por el compilador en las propiedades implementadas automáticamente. Por ejemplo, pensemos en una revisión de la clase `Person` que agrega una propiedad `Id` de entero único.
Escribimos la propiedad `Id` usando una propiedad implementada automáticamente, pero el diseño no requiere que la propiedad `Id` se conserve. <xref:System.NonSerializedAttribute> solo se puede asociar a campos, no a propiedades. <xref:System.NonSerializedAttribute> se puede asociar al campo de respaldo de la propiedad `Id` usando el especificador `field:` en el atributo, como se muestra en el siguiente ejemplo:

[!code-csharp[Attaching attributes to a backing field](../../samples/snippets/csharp/properties/Person.cs#14)]

Esta técnica funciona con cualquier atributo que se asocie al campo de respaldo en la propiedad implementada automáticamente.

### <a name="implementing-inotifypropertychanged"></a>Implementar INotifyPropertyChanged

Un último escenario donde se necesita escribir código en un descriptor de acceso de propiedad es para admitir la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> que se usa para notificar a los clientes de enlace de datos el cambio de un valor. Cuando se cambia el valor de una propiedad, el objeto genera el evento <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged?displayProperty=nameWithType> para indicar el cambio. A su vez, las bibliotecas de enlace de datos actualizan los elementos de visualización en función de ese cambio. El código siguiente muestra cómo se implementaría `INotifyPropertyChanged` para la propiedad `FirstName` de esta clase person.

[!code-csharp[invalidating the cache correctly](../../samples/snippets/csharp/properties/Person.cs#15)]

El operador `?.` se denomina *operador condicional NULL*. Comprueba si existe una referencia nula antes de evaluar el lado derecho del operador. El resultado final es que si no hay ningún suscriptor para el evento `PropertyChanged`, no se ejecuta el código para generar el evento. En ese caso, se producirá una `NullReferenceException` sin esta comprobación. Para obtener más información, vea [`events`](events-overview.md). En este ejemplo también se usa el nuevo operador `nameof` para convertir el símbolo de nombre de propiedad en su representación de texto.
Con `nameof` se pueden reducir los errores en los que no se escribió correctamente el nombre de la propiedad.

De nuevo, la implementación de <xref:System.ComponentModel.INotifyPropertyChanged> es un ejemplo de un caso en el que se puede escribir código en los descriptores de acceso para admitir los escenarios que se necesitan.

## <a name="summing-up"></a>Resumen

Las propiedades son una forma de campos inteligentes en una clase o un objeto. Desde fuera del objeto, parecen campos en el objeto. Pero las propiedades pueden implementarse mediante la paleta completa de funcionalidad de C#.
Se puede proporcionar validación, tipos diferentes de accesibilidad, evaluación diferida o los requisitos que se necesiten para cada escenario.
