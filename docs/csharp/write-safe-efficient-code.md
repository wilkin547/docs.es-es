---
title: Escritura de código C# seguro y eficaz
description: Las mejoras aplicadas recientemente al lenguaje C# permiten escribir código seguro verificable que anteriormente se hubiera asociado a código no seguro.
ms.date: 10/23/2018
ms.technology: csharp-advanced-concepts
ms.custom: mvc
ms.openlocfilehash: f590a338d35966e2cd3a507164057a49b8a5f6f8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346700"
---
# <a name="write-safe-and-efficient-c-code"></a>Escritura de código C# seguro y eficaz

Las nuevas características de C# permiten escribir código seguro verificable con un mejor rendimiento. Si aplica estas técnicas cuidadosamente, habrá menos escenarios que requieran código no seguro. Estas características permiten usar con más facilidad las referencias a tipos de valor como argumentos de método y devoluciones de método. Si aplica estas técnicas de forma segura, minimizará la copia de tipos de valor. Al usar tipos de valor, también podrá minimizar el número de asignaciones y transferencias de recolección de elementos no utilizados.

En gran parte del código de ejemplo de este artículo se utilizan las características agregadas a la versión 7.2 de C#. Para poder usar esas características, tiene que configurar el proyecto para que use la versión 7.2 de C# o una posterior. Para obtener más información sobre cómo establecer la versión del lenguaje, vea cómo [configurar la versión del lenguaje](language-reference/configure-language-version.md).

Este artículo se centra en las técnicas que se deben aplicar para administrar recursos de forma eficaz. Una de las ventajas de utilizar tipos de valor es que a menudo evitan las asignaciones de montón. Pero también hay una desventaja, que es que se copian por valor. Este último aspecto dificulta la optimización de los algoritmos que funcionan en grandes cantidades de datos. Las nuevas características del lenguaje en C# 7.2 proporcionan mecanismos que permiten escribir código seguro y eficaz mediante referencias a tipos de valor. Use estas características acertadamente para minimizar tanto las asignaciones como las operaciones de copia. En este artículo se exploran estas nuevas características.

Este artículo se centra en estas técnicas de administración de recursos:

- Declare un valor [`readonly struct`](language-reference/keywords/readonly.md#readonly-struct-example) para indicar que un tipo es **inmutable**, lo cual permite al compilador ahorrar procesos de copia usando parámetros [`in`](language-reference/keywords/in-parameter-modifier.md).
- Si un tipo no puede ser inmutable, declare miembros `readonly` de `struct` para indicar que el miembro no modifica el estado.
- Utilice una devolución [`ref readonly`](language-reference/keywords/ref.md#reference-return-values) si el valor devuelto es un valor `struct` mayor que <xref:System.IntPtr.Size?displayProperty=nameWithType> y la duración del almacenamiento es superior al método que devuelve el valor.
- Si el tamaño de un valor `readonly struct` es mayor que <xref:System.IntPtr.Size?displayProperty=nameWithType>, deberá pasarlo como parámetro `in` por motivos de rendimiento.
- No pase nunca un elemento `struct` como parámetro `in` a menos que se declare con el modificador `readonly` o que el método solo llame a los miembros de `readonly` de la estructura. Infringir esta guía puede afectar negativamente al rendimiento y podría provocar un comportamiento oculto.
- Use un valor [`ref struct`](language-reference/keywords/ref.md#ref-struct-types), o bien un valor `readonly ref struct` como <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>, para que funcione con la memoria como secuencia de bytes.

Estas técnicas obligan a equilibrar dos objetivos contrapuestos en relación con las **referencias** y los **valores**. Las variables que son [tipos de referencia](programming-guide/types/index.md#reference-types) contienen una referencia a la ubicación en la memoria. Las variables que son [tipos de valor](programming-guide/types/index.md#value-types) contienen directamente su valor. Estas son diferencias clave importantes para administrar recursos de memoria. Los **tipos de valor** suelen copiarse cuando se pasan a un método o se devuelven desde uno. Este comportamiento incluye la copia del valor de `this` al llamar a los miembros de un tipo de valor. El costo de dicha copia está relacionado con el tamaño del tipo. Los **tipos de referencia** se asignan en el montón administrado. Cada nuevo objeto requiere una nueva asignación, y se debe reclamar posteriormente. Ambas operaciones llevan cierto tiempo. La referencia se copia cuando un tipo de referencia se pasa como argumento a un método o se devuelve desde un método.

En este artículo se utiliza el concepto de ejemplo siguiente de la estructura de punto 3D para explicar estas recomendaciones:

```csharp
public struct Point3D
{
    public double X;
    public double Y;
    public double Z;
}
```

Los distintos ejemplos utilizan implementaciones distintas de este concepto.

## <a name="declare-readonly-structs-for-immutable-value-types"></a>Declaración de valores struct de solo lectura para tipos de valor inmutables

Al declarar un valor `struct` utilizando el modificador `readonly`, se informa al compilador de que su intención es crear un tipo inmutable. El compilador aplica esa decisión de diseño con las siguientes reglas:

- Todos los miembro de campo deben ser `readonly`.
- Todas las propiedades deben ser de solo lectura, incluidas las implementadas automáticamente.

Estas dos reglas son suficientes para garantizar que ningún miembro de un valor `readonly struct` vaya a modificar el estado de ese valor struct. El valor `struct` es inmutable. La estructura de `Point3D` se podría definir como un valor struct inmutable tal como se muestra en este ejemplo:

```csharp
readonly public struct ReadonlyPoint3D
{
    public ReadonlyPoint3D(double x, double y, double z)
    {
        this.X = x;
        this.Y = y;
        this.Z = z;
    }

    public double X { get; }
    public double Y { get; }
    public double Z { get; }
}
```

Siga esta recomendación siempre que su intención de diseño sea crear un tipo de valor inmutable. Cualquier mejora de rendimiento que se aplique es una ventaja adicional. El valor `readonly struct` expresa claramente su intención de diseño.

## <a name="declare-readonly-members-when-a-struct-cant-be-immutable"></a>Declaración de miembros de solo lectura cuando una estructura no pueda ser inmutable

En C# 8.0 y versiones posteriores, cuando un tipo de estructura es mutable, debe declarar los miembros que no provocan la mutación para que sean `readonly`. Por ejemplo, lo siguiente es una variación mutable de la estructura de punto 3D:

```csharp
public struct Point3D
{
    public Point3D(double x, double y, double z)
    {
        _x = x;
        _y = y;
        _z = z;
    }

    private double _x;
    public double X
    {
        readonly get => _x;
        set => _x = value;
    }

    private double _y;
    public double Y
    {
        readonly get => _y;
        set => _y = value;
    }

    private double _z;
    public double Z
    {
        readonly get => _z;
        set => _z = value;
    }

    public readonly double Distance => Math.Sqrt(X * X + Y * Y + Z * Z);

    public readonly override string ToString() => $"{X}, {Y}, {Z}";
}
```

En el ejemplo anterior se muestran muchas de las ubicaciones en las que puede aplicar el modificador `readonly`: métodos, propiedades y descriptores de acceso de propiedad. Si usa propiedades implementadas automáticamente, el compilador agrega el modificador `readonly` al descriptor de acceso `get` para las propiedades de lectura y escritura. El compilador agrega el modificador `readonly` a las declaraciones de propiedad implementadas automáticamente para las propiedades con solo un descriptor de acceso `get`.

Agregar el modificador `readonly` a los miembros que no mutan el estado proporciona dos ventajas relacionadas. En primer lugar, el compilador aplica su intención. Ese miembro no puede mutar el estado de la estructura ni tener acceso a un miembro que no esté marcado también como `readonly`. En segundo lugar, el compilador no crea copias defensivas de parámetros `in` al obtener acceso a un miembro de `readonly`. El compilador puede hacer que esta optimización sea segura, ya que garantiza que un miembro de `readonly` no modifique `struct`.

## <a name="use-ref-readonly-return-statements-for-large-structures-when-possible"></a>Uso de instrucciones `ref readonly return` para grandes estructuras en la medida de lo posible

Puede devolver valores por referencia cuando el valor que se devuelva no sea local en el método de devolución. Al devolverlos de esta forma, se copiará solo la referencia, no la estructura. En el ejemplo siguiente, la propiedad `Origin` no puede usar ninguna devolución `ref` porque el valor que se está devolviendo es una variable local:

```csharp
public Point3D Origin => new Point3D(0,0,0);
```

Sin embargo, la siguiente definición de propiedad se puede devolver por referencia porque el valor devuelto es un miembro estático:

```csharp
public struct Point3D
{
    private static Point3D origin = new Point3D(0,0,0);

    // Dangerous! returning a mutable reference to internal storage
    public ref Point3D Origin => ref origin;

    // other members removed for space
}
```

Como no quiere que los autores de llamada modifiquen el origen, debe devolver el valor según su `ref readonly`:

```csharp
public struct Point3D
{
    private static Point3D origin = new Point3D(0,0,0);

    public static ref readonly Point3D Origin => ref origin;

    // other members removed for space
}
```

Al devolver `ref readonly`, se podrá ahorrar procesos de copia de estructuras mayores y conservar la inmutabilidad de los miembros de datos internos.

En el sitio de llamada, los autores de dicha llamada eligen utilizar la propiedad `Origin` como `ref readonly` o como valor:

[!code-csharp[AssignRefReadonly](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

La primera asignación en el código anterior realiza una copia de la constante `Origin` y asigna esa copia. La segunda asigna una referencia. Tenga en cuenta que el modificador `readonly` debe formar parte de la declaración de la variable. No se puede modificar la referencia a la que alude. Los intentos de hacerlo generarán un error en tiempo de compilación.

El modificador `readonly` es necesario en la declaración de `originReference`.

El compilador exige que el autor de una llamada no pueda modificar la referencia. Los intentos de asignar el valor directamente generan un error en tiempo de compilación. Sin embargo, el compilador no puede saber si algún método de miembro modifica el estado del valor struct.
Para asegurarse de que el objeto no se modifique, el compilador crea una copia y llama a las referencias de miembro usando esa copia. Las modificaciones se realizan sobre esa copia defensiva.

## <a name="apply-the-in-modifier-to-readonly-struct-parameters-larger-than-systemintptrsize"></a>Aplicación del modificador `in` en los parámetros `readonly struct` mayores que `System.IntPtr.Size`

La palabra clave `in` complementa las palabras clave `ref` y `out` existentes para pasar argumentos por referencia. La palabra clave `in` especifica que se pasa el argumento por referencia, pero el método llamado no modifica el valor.

Esta novedad proporciona un vocabulario completo para expresar la intención del diseño.
Los tipos de valor se copian al pasarlos a un método llamado cuando no se especifica ninguno de los siguientes modificadores en la firma de método. Cada uno de estos modificadores especifica que una variable se pasa por referencia, evitando la copia. Cada modificador expresa un propósito diferente:

- `out`: este método establece el valor del argumento utilizado como este parámetro.
- `ref`: este método puede establecer el valor del argumento utilizado como este parámetro.
- `in`: este método no modifica el valor del argumento utilizado como este parámetro.

Agregue el modificador `in` para pasar un argumento por referencia y declare la intención del diseño de pasar argumentos por referencia para evitar la copia innecesaria. No pretende modificar el objeto usado como ese argumento.

A menudo, esta práctica mejora el rendimiento de los tipos de valor de solo lectura que son mayores que <xref:System.IntPtr.Size?displayProperty=nameWithType>. En el caso de los tipos simples (`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, `bool` y `enum`), las posibles mejoras con respecto al rendimiento son mínimas. De hecho, el rendimiento puede empeorar al usar un parámetro de paso por referencia para los tipos menores que <xref:System.IntPtr.Size?displayProperty=nameWithType>.

El código siguiente muestra un ejemplo de un método que calcula la distancia entre dos puntos en un espacio 3D.

[!code-csharp[InArgument](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgument "Specifying an in argument")]

Los argumentos son dos estructuras que contienen cada una de ellas tres valores dobles. Un valor doble tiene 8 bytes, por lo que cada argumento es de 24 bytes. Al especificar el modificador `in`, se pasa una referencia de 4 u 8 bytes a esos argumentos, en función de la arquitectura de la máquina. La diferencia de tamaño es pequeña, pero aumenta rápidamente cuando la aplicación llama a este método en un bucle ajustado con muchos valores diferentes.

El modificador `in` complementa también a `out` y `ref` de otras maneras. No puede crear sobrecargas de un método que difiere solo en cuanto a la presencia de `in`, `out` o `ref`. Estas nuevas reglas extienden el mismo comportamiento que siempre se ha definido para los parámetros `out` y `ref`. Como en el caso de los modificadores `out` y `ref`, no se aplica la conversión boxing a los tipos de valor porque se aplica el modificador `in`.

El modificador `in` se puede aplicar a cualquier miembro que toma parámetros: métodos, delegados, expresiones lambda, funciones locales, indexadores u operadores.

Otra de las características de los parámetros `in` es que se pueden usar valores literales o constantes para el argumento en un parámetro `in`. Además, a diferencia de un parámetro `ref` o `out`, no es necesario aplicar el modificador `in` en el sitio de llamada. El código siguiente muestra dos ejemplos de llamada al método `CalculateDistance`. El primero usa dos variables locales pasadas por referencia. El segundo incluye una variable temporal creada como parte de la llamada al método.

[!code-csharp[UseInArgument](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#UseInArgument "Specifying an In argument")]

El compilador tiene varias maneras de aplicar la naturaleza de solo lectura de un argumento `in`.  En primer lugar, el método llamado no se puede asignar directamente a un parámetro `in`. No se puede asignar directamente a ningún campo de un parámetro `in` cuando el valor es un tipo `struct`. Además, no se puede pasar un parámetro `in` a ningún método que exija el modificador `ref` o `out`.
Estas reglas se aplican a cualquier campo de un parámetro `in`, siempre que el campo sea un tipo `struct` y el parámetro también sea un tipo `struct`. De hecho, estas reglas se aplican para varios niveles de acceso a miembros, siempre que los tipos en todos los niveles de acceso a miembros sean `structs`.
El compilador exige que los tipos `struct` que se pasan como argumentos `in` y sus miembros `struct` sean variables de solo lectura cuando se usan como argumentos para otros métodos.

El uso de parámetros `in` puede evitar los posibles costos de rendimiento que conlleva realizar copias. No cambia la semántica de ninguna llamada al método. Por lo tanto, no es necesario especificar el modificador `in` en el sitio de llamada. Al omitir el modificador `in` en el sitio de llamada, se indica al compilador que está permitido realizar una copia del argumento por estos motivos:

- Hay una conversión implícita, pero no una conversión de identidad desde el tipo de argumento hacia el tipo de parámetro.
- El argumento es una expresión, pero no tiene una variable de almacenamiento conocida.
- Existe una sobrecarga que se diferencia por la presencia o la ausencia de `in`. En ese caso, la sobrecarga por valor es una coincidencia mejor.

Estas reglas son útiles cuando se actualiza código existente para usar argumentos de referencia de solo lectura. En el método llamado, puede llamar a cualquier método de instancia que use parámetros por valor. En esos casos, se crea una copia del parámetro `in`. Dado que el compilador puede crear una variable temporal para cualquier parámetro `in`, también puede especificar valores predeterminados para cualquier parámetro `in`. En este código se especifica el origen (punto 0,0) como valor predeterminado para el segundo punto:

[!code-csharp[InArgumentDefault](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

Para forzar al compilador que pase argumentos de solo lectura por referencia, especifique el modificador `in` en los argumentos en el sitio de llamada, como se muestra en el este código:

[!code-csharp[UseInArgument](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#ExplicitInArgument "Specifying an In argument")]

Con este comportamiento es más fácil adoptar parámetros `in` con el tiempo en grandes bases de código donde es posible mejorar el rendimiento. Primero, puede agregar el modificador `in` para las firmas de método. Después, puede agregar el modificador `in` en sitios de llamada y crear tipos `readonly struct` para permitir al compilador que evite la creación de copias defensivas de parámetros `in` en más ubicaciones.

La designación del parámetro `in` también se puede usar con tipos de referencia o valores numéricos. Sin embargo, las ventajas de ambos casos son mínimas, si las hay.

## <a name="never-use-mutable-structs-as-in-in-argument"></a>No usar nunca valores struct mutables como en el argumento `in`

En las técnicas descritas anteriormente se explica cómo evitar copias devolviendo referencias y pasando los valores por referencia. Estas técnicas funcionan mejor cuando los tipos de argumento se declaran como tipos `readonly struct`. En caso contrario, el compilador deberá crear **copias defensivas** en muchas situaciones para aplicar la característica de solo lectura en cualquier argumento. Tenga en cuenta el comentario siguiente, en el que se calcula la distancia de un punto 3D respecto del origen:

[!code-csharp[InArgument](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgument "Specifying an in argument")]

La estructura `Point3D`*no* es un valor struct de solo lectura. Hay seis llamadas de acceso a propiedades en el cuerpo de este método. En el primer examen, es posible que haya pensado que esos accesos son seguros. Al fin y al cabo, un descriptor de acceso `get` no debe modificar el estado del objeto. Sin embargo, no hay ninguna regla de lenguaje que lo exija. Se trata solo de una convención habitual. Cualquier tipo podría implementar un descriptor de acceso `get` que haya modificado el estado interno. Si el compilador no dispone de ninguna garantía relativa al lenguaje, debe crear una copia temporal del argumento antes de llamar a algún miembro. El almacenamiento temporal se crea en la pila, los valores del argumento se copian al almacenamiento temporal y el valor se copia en la pila por cada acceso de miembro como argumento `this`. En muchas situaciones, estas copias perjudican tanto el rendimiento que el parámetro de paso por valor es más rápido que el de paso por referencia cuando el tipo de argumento no es un valor `readonly struct`.

En lugar de ello, si en el cálculo de distancia se usa la estructura inmutable, `ReadonlyPoint3D`, no se necesitan objetos temporales:

[!code-csharp[readonlyInArgument](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#ReadOnlyInArgument "Specifying a readonly in argument")]

El compilador genera un código más eficaz cuando se llama a los miembros de un valor `readonly struct`: La referencia `this`, en lugar de una copia del receptor, es siempre un parámetro `in` pasado por referencia al método del miembro. Esta optimización ahorra procesos de copia cuando se utiliza `readonly struct` como argumento `in`.

No se debe pasar un tipo de valor que admite un valor NULL como argumento `in`. El tipo <xref:System.Nullable%601> no se declara como una estructura de solo lectura. Eso significa que el compilador debe generar copias defensivas de cualquier argumento de tipo de valor que acepta valores NULL pasado a un método con el modificador `in` en la declaración de parámetros.

Puede ver un programa de ejemplo en el que se muestran las diferencias de rendimiento con [BenchmarkDotNet](https://www.nuget.org/packages/BenchmarkDotNet/) en el [repositorio de ejemplos](https://github.com/dotnet/samples/tree/master/csharp/safe-efficient-code/benchmark) de GitHub. Compara la transmisión de un valor struct mutable por valor y por referencia con la transmisión de un valor struct inmutable por valor y por referencia. El uso de un valor struct inmutable y de la transmisión por referencia es un proceso más rápido.

## <a name="use-ref-struct-types-to-work-with-blocks-or-memory-on-a-single-stack-frame"></a>Uso de los tipos `ref struct` para trabajar con bloques o memoria en un solo marco de pila

Una característica de lenguaje relacionada es la capacidad de declarar un tipo de valor que debe limitarse a un solo marco de pila. Esta restricción permite al compilador aplicar una serie de optimizaciones. La principal motivación para esta característica era <xref:System.Span%601> y las estructuras relacionadas. Conseguirá mejoras en el rendimiento a partir de estas optimizaciones usando las API de .NET nuevas y actualizadas que utilizan el tipo <xref:System.Span%601>.

Puede tener requisitos similares al trabajar con memoria creada mediante [`stackalloc`](language-reference/operators/stackalloc.md) o al usar memoria de las API de interoperabilidad. Puede definir sus propios tipos de `ref struct` para esas necesidades.

## <a name="readonly-ref-struct-type"></a>Tipo de `readonly ref struct`

Si declara una estructura como `readonly ref` se combinan las ventajas y las restricciones de las declaraciones `ref struct` y `readonly struct`. La memoria utilizada por el intervalo de solo lectura está limitada a un solo marco de pila y no se puede modificar.

## <a name="conclusions"></a>Conclusiones

El uso de tipos de valor minimiza el número de operaciones de asignación:

- El almacenamiento de los tipos de valor está asignado a la pila en las variables locales y los argumentos de método.
- En cuanto al almacenamiento de tipos de valor que son miembros de otros objetos, está asignado como parte del objeto en cuestión, no como una asignación separada.
- Respecto a los valores devueltos por tipo de valor, están asignados a la pila.

Es necesario contrastar eso con los tipos de referencia en estas mismas situaciones:

- El almacenamiento de los tipos de referencia se asigna al montón en las variables locales y los argumentos de método. La referencia se almacena en la pila.
- El almacenamiento de tipos de referencia que son miembros de otros objetos está asignado por separado en la pila. El objeto contenedor almacena la referencia.
- El almacenamiento de los valores devueltos por tipo de referencia está asignado a la pila. La referencia a ese almacenamiento se guarda en la pila.

La minimización de asignaciones conlleva una serie de renuncias. Se copia más memoria cuando el tamaño del valor `struct` es mayor que el de una referencia. Habitualmente, las referencias son de 64 o 32 bits y dependen de la CPU de la máquina de destino.

Dichas renuncias suelen tener un impacto mínimo en el rendimiento. Sin embargo, en el caso de los valores struct grandes o de las colecciones de mayor tamaño, el impacto sobre el rendimiento es mayor. Dicho impacto puede ser considerable en los bucles estrechos y las rutas de acceso activas de los programas.

Estas mejoras del lenguaje C# están diseñadas para algoritmos en los que el rendimiento es fundamental y la minimización de asignaciones de memoria es un factor principal para lograr el rendimiento necesario. Es posible que no use a menudo estas características en el código que escribe. Sin embargo, estas mejoras se han adoptado a través de .NET. Dado que cada vez son más las API que utilizan estas características, verá que el rendimiento de sus aplicaciones aumenta.

## <a name="see-also"></a>Vea también

- [ref (palabra clave)](language-reference/keywords/ref.md)
- [Devoluciones y variables locales ref](programming-guide/classes-and-structs/ref-returns.md)
