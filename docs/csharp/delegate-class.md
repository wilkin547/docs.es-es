---
title: System.Delegate y la palabra clave `delegate`
description: Obtenga información sobre las clases de .NET que admiten delegados y sobre cómo se asignan a la palabra clave "delegate".
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: f3742fda-13c2-4283-8966-9e21c2674393
ms.openlocfilehash: 3cfc9925be0f191dc3fc93c02f4a8f9a40b71895
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450926"
---
# <a name="systemdelegate-and-the-delegate-keyword"></a>System.Delegate y la palabra clave `delegate`

[Anterior](delegates-overview.md)

En este artículo se tratan las clases de .NET que admiten delegados y sobre cómo se asignan a la palabra clave `delegate`.

## <a name="define-delegate-types"></a>Definición de los tipos delegados

Comencemos con la palabra clave "delegate", ya que es lo que usará principalmente al trabajar con delegados. El código que genere el compilador cuando se usa la palabra clave `delegate` se asignará a las llamadas de método que invocan a miembros de las clases <xref:System.Delegate> y <xref:System.MulticastDelegate>. 

Para definir un tipo de delegado, se usa una sintaxis similar a la definición de una firma de método. Solo hace falta agregar la palabra clave `delegate` a la definición.

Vamos a usar el método List.Sort() como ejemplo. El primer paso consiste en crear un tipo para el delegado de comparación:

```csharp
// From the .NET Core library

// Define the delegate type:
public delegate int Comparison<in T>(T left, T right);
```

El compilador genera una clase derivada de `System.Delegate` que coincide con la firma usada (en este caso, un método que devuelve un entero y tiene dos argumentos). El tipo de ese delegado es `Comparison`. El tipo de delegado `Comparison` es un tipo genérico. [Aquí](programming-guide/generics/index.md) puede obtener más información sobre los genéricos.

Observe que puede parecer que la sintaxis declara una variable, pero en realidad declara un *tipo*. Puede definir tipos de delegado dentro de clases, directamente dentro de espacios de nombres o incluso en el espacio de nombres global.

> [!NOTE]
> No se recomienda declarar tipos de delegado (u otros tipos) directamente en el espacio de nombres global. 

El compilador también genera controladores de adición y eliminación para este nuevo tipo, de modo que los clientes de esta clase puedan agregar y quitar métodos de la lista de invocación de una instancia. El compilador forzará que la firma del método que se agrega o se quita coincida con la firma usada al declarar el método. 

## <a name="declare-instances-of-delegates"></a>Declaración de instancias de delegados

Después de definir el delegado, puede crear una instancia de ese tipo.
Al igual que todas las variables en C#, no puede declarar instancias de delegados directamente en un espacio de nombres o en el espacio de nombres global.

```csharp
// inside a class definition:

// Declare an instance of that type:
public Comparison<T> comparator;
```

El tipo de la variable es `Comparison<T>`, el tipo de delegado definido anteriormente. El nombre de la variable es `comparator`.
 
 El fragmento de código anterior declara una variable de miembro dentro de una clase. También puede declarar variables de delegado que sean variables locales o argumentos para los métodos.

## <a name="invoke-delegates"></a>Invocación de delegados

Para invocar los métodos que se encuentran en la lista de invocación de un delegado, llame a dicho delegado. Dentro del método `Sort()`, el código llamará al método de comparación para determinar en qué orden colocará los objetos:

```csharp
int result = comparator(left, right);
```

En la línea anterior, el código *invoca* al método asociado al delegado.
La variable se trata como un nombre de método y se invoca mediante la sintaxis de llamada de método normal.

Esa línea de código realiza una suposición no segura: No hay ninguna garantía de que se haya agregado un destino en el delegado. Si no se ha asociado ningún destino, la línea anterior haría que se produjese una `NullReferenceException`. Las expresiones que se usan para resolver este problema son más complicadas que una simple comprobación de null y se tratan más adelante en esta [serie](delegates-patterns.md).

## <a name="assign-add-and-remove-invocation-targets"></a>Asignación, adición y eliminación de destinos de invocación

Hemos visto cómo se define un tipo de delegado y cómo se declaran y se invocan las instancias de delegado.

Los programadores que quieran usar el método `List.Sort()` deben definir un método cuya firma coincida con la definición del tipo de delegado y asignarlo al delegado usado por el método de ordenación. Esta asignación agrega el método a la lista de invocación de ese objeto de delegado.

Supongamos que quiera ordenar una lista de cadenas por su duración. La función de comparación podría ser la siguiente:

```csharp
private static int CompareLength(string left, string right) =>
    left.Length.CompareTo(right.Length);
```

El método se ha declarado como un método privado. Esto es correcto, ya que tal vez no le interese que este método forme parte de la interfaz pública. Aun así, puede usarse como método de comparación cuando se asocia a un delegado. El código de llamada tendrá este método asociado a la lista de destino del objeto de delegado y puede tener acceso a él a través de ese delegado.

Para crear esta relación, pase ese método al método `List.Sort()`:

```csharp
phrases.Sort(CompareLength);
```

Observe que se usa el nombre del método sin paréntesis. Al usar el método como un argumento, le indica al compilador que convierta la referencia del método en una referencia que se puede usar como un destino de invocación del delegado y que asocie ese método como un destino de invocación.

También podría haber declarado de forma explícita una variable de tipo `Comparison<string>` y realizado una asignación:

```csharp
Comparison<string> comparer = CompareLength;
phrases.Sort(comparer);
```

En los casos en los que el método que se usa como destino del delegado es un método pequeño, es habitual usar la sintaxis de [expresión lambda](./programming-guide/statements-expressions-operators/lambda-expressions.md) para realizar la asignación:

```csharp
Comparison<string> comparer = (left, right) => left.Length.CompareTo(right.Length);
phrases.Sort(comparer);
```

El uso de expresiones lambda para destinos de delegados se explica con más detalle en una [sección posterior](delegates-patterns.md).

En el ejemplo de Sort() se suele asociar un método de destino único al delegado, pero los objetos delegados admiten listas de invocación que tienen varios métodos de destino asociados a un objeto delegado.

## <a name="delegate-and-multicastdelegate-classes"></a>Clases Delegate y MulticastDelegate

La compatibilidad de lenguaje descrita anteriormente proporciona las características y la compatibilidad que normalmente necesitará para trabajar con delegados. Estas características están integradas en dos clases en .NET Core Framework: <xref:System.Delegate> y <xref:System.MulticastDelegate>.

La clase `System.Delegate` y su única subclase directa `System.MulticastDelegate` proporcionan la compatibilidad con el marco para crear delegados, registrar métodos como destinos de delegados e invocar todos los métodos que se registran como un destino del delegado. 

Curiosamente, las clases `System.Delegate` y `System.MulticastDelegate` no son tipos de delegado, pero proporcionan la base para todos los tipos de delegado específicos. El propio proceso de diseño del lenguaje dictaba que no se puede declarar una clase que derive de `Delegate` o `MulticastDelegate`. Las reglas del lenguaje C# lo prohíben.
 
En cambio, el compilador de C# crea instancias de una clase derivada de `MulticastDelegate` cuando se usa la palabra clave del lenguaje C# para declarar tipos de delegado.

Este diseño tiene sus orígenes en la primera versión de C# y. NET. Uno de los objetivos del equipo de diseño era asegurarse de que el lenguaje aplicaba seguridad de tipos al usar delegados. Esto significaba que debían asegurarse no solo de que los delegados se invocaban con el tipo y el número adecuados de argumentos, sino de que todos los tipos de valor devueltos se indicaban correctamente en tiempo de compilación. Los delegados formaban parte de la versión 1.0 .NET, que apareció antes que los genéricos.

La mejor manera de aplicar la seguridad de tipos era que el compilador crease las clases de delegado concretas que representasen la firma del método que se usaba.

Aunque usted no puede crear clases derivadas directamente, usará los métodos definidos en estas clases. Vamos a ver los métodos más comunes que usará al trabajar con delegados.

Lo primero que debe recordar es que cada delegado con el que trabaje se deriva de `MulticastDelegate`. Un delegado multidifusión significa que se puede invocar más de un destino de método al invocar en un delegado. El diseño original consideraba la posibilidad de establecer una distinción entre los delegados en los que solo se podía asociar e invocar un método de destino y los delegados en los que se podía asociar e invocar varios métodos de destino. Esa distinción resultó ser menos útil en la práctica de lo que se pensaba. Las dos clases ya estaban creadas y se han conservado en el marco de trabajo desde la versión pública inicial.

Los métodos que usará más a menudo con los delegados son `Invoke()` y `BeginInvoke()` / `EndInvoke()`. `Invoke()` invocará todos los métodos que se han asociado a una instancia de delegado en concreto. Como ya hemos visto anteriormente, por lo general los delegados se invocan mediante la sintaxis de llamada de método en la variable de delegado. Como verá [más adelante en esta serie](delegates-patterns.md), hay patrones que funcionan directamente con estos métodos.

Ahora que ha visto la sintaxis del lenguaje y las clases que admiten delegados, examinemos cómo se usan, se crean y se invocan delegados fuertemente tipados.

[Siguiente](delegates-strongly-typed.md)
