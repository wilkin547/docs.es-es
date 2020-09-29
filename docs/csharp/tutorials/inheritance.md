---
title: Herencia en C#
description: Aprenda a usar la herencia en bibliotecas y aplicaciones en C#.
ms.date: 07/05/2018
ms.technology: csharp-fundamentals
ms.assetid: aeb68c74-0ea0-406f-9fbe-2ce02d47ef31
ms.openlocfilehash: b0d6a4a3db4d6606375cc3364ee7abc3029f1d9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190467"
---
# <a name="inheritance-in-c-and-net"></a>Herencia en C# y .NET

Este tutorial es una introducción a la herencia en C#. La herencia es una característica de los lenguajes de programación orientados a objetos que permite definir una clase base, que proporciona funcionalidad específica (datos y comportamiento), así como clases derivadas, que heredan o invalidan esa funcionalidad.

## <a name="prerequisites"></a>Requisitos previos

En este tutorial se supone que ha instalado el SDK de .NET Core. Visite la página de [descargas de .NET Core](https://dotnet.microsoft.com/download) para descargarlo. También necesitará un editor de código. En este tutorial se usa [Visual Studio Code](https://code.visualstudio.com), aunque puede elegir el que prefiera.

## <a name="running-the-examples"></a>Ejecución de los ejemplos

Para crear y ejecutar los ejemplos de este tutorial, use la utilidad [dotnet](../../core/tools/dotnet.md) desde la línea de comandos. Siga estos pasos para cada ejemplo:

1. Cree un directorio para almacenar el ejemplo.
1. Escriba el comando [dotnet new console](../../core/tools/dotnet-new.md) en el símbolo del sistema para crear un nuevo proyecto de .NET Core.
1. Copie y pegue el código del ejemplo en el editor de código.
1. Escriba el comando [dotnet restore](../../core/tools/dotnet-restore.md) desde la línea de comandos para cargar o restaurar las dependencias del proyecto.

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

1. Escriba el comando [dotnet run](../../core/tools/dotnet-run.md) para compilar y ejecutar el ejemplo.

## <a name="background-what-is-inheritance"></a>Información previa: ¿Qué es la herencia?

La *herencia* es uno de los atributos fundamentales de la programación orientada a objetos. Permite definir una clase secundaria que reutiliza (hereda), amplía o modifica el comportamiento de una clase primaria. La clase cuyos miembros son heredados se conoce como *clase base*. La clase que hereda los miembros de la clase base se conoce como *clase derivada*.

C# y .NET solo admiten *herencia única*. Es decir, una clase solo puede heredar de una clase única. Sin embargo, la herencia es transitiva, lo que le permite definir una jerarquía de herencia para un conjunto de tipos. En otras palabras, el tipo `D` puede heredar del tipo `C`, que hereda del tipo `B`, que hereda del tipo de clase base `A`. Dado que la herencia es transitiva, los miembros de tipo `A` están disponibles para el tipo `D`.

No todos los miembros de una clase base los heredan las clases derivadas. Los siguientes miembros no se heredan:

- [Constructores estáticos](../programming-guide/classes-and-structs/static-constructors.md), que inicializan los datos estáticos de una clase.

- [Constructores de instancias](../programming-guide/classes-and-structs/constructors.md), a los que se llama para crear una nueva instancia de la clase. Cada clase debe definir sus propios constructores.

- [Finalizadores](../programming-guide/classes-and-structs/destructors.md), llamados por el recolector de elementos no utilizados en tiempo de ejecución para destruir instancias de una clase.

Si bien las clases derivadas heredan todos los demás miembros de una clase base, que dichos miembros estén o no visibles depende de su accesibilidad. La accesibilidad del miembro afecta a su visibilidad en las clases derivadas del modo siguiente:

- Los miembros [privados](../language-reference/keywords/private.md) solo son visible en las clases derivadas que están anidadas en su clase base. De lo contrario, no son visibles en las clases derivadas. En el ejemplo siguiente, `A.B` es una clase anidada que se deriva de `A`, y `C` se deriva de `A`. El campo `A.value` privado es visible en A.B. Sin embargo, si quita los comentarios del método `C.GetValue` e intenta compilar el ejemplo, se produce el error del compilador CS0122: ""A.value" no es accesible debido a su nivel de protección".

  [!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/private.cs#1)]

- Los miembros [protegidos](../language-reference/keywords/protected.md) solo son visibles en las clases derivadas.

- Los miembros [internos](../language-reference/keywords/internal.md) solo son visibles en las clases derivadas que se encuentran en el mismo ensamblado que la clase base. No son visibles en las clases derivadas ubicadas en un ensamblado diferente al de la clase base.

- Los miembros [públicos](../language-reference/keywords/public.md) son visibles en las clases derivadas y forman parte de la interfaz pública de dichas clases. Los miembros públicos heredados se pueden llamar como si se definieran en la clase derivada. En el ejemplo siguiente, la clase `A` define un método denominado `Method1` y la clase `B` hereda de la clase `A`. El ejemplo llama a `Method1` como si fuera un método de instancia en `B`.

  [!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/basics.cs#1)]

Las clases derivadas pueden también *invalidar* los miembros heredados al proporcionar una implementación alternativa. Para poder invalidar un miembro, el miembro de la clase base debe marcarse con la palabra clave [virtual](../language-reference/keywords/virtual.md). De forma predeterminada, los miembros de clase base no están marcados con `virtual` y no se pueden invalidar. Al intentar invalidar un miembro no virtual, como en el ejemplo siguiente, se genera el error de compilador CS0506: "\<member> no se puede invalidar el miembro heredado \<member> porque no está marcado como virtual, abstract ni override.

```csharp
public class A
{
    public void Method1()
    {
        // Do something.
    }
}

public class B : A
{
    public override void Method1() // Generates CS0506.
    {
        // Do something else.
    }
}
```

En algunos casos, una clase derivada *debe* invalidar la implementación de la clase base. Los miembros de clase base marcados con la palabra clave [abstract](../language-reference/keywords/abstract.md) requieren que las clases derivadas los invaliden. Al intentar compilar el ejemplo siguiente, se genera el error de compilador CS0534, "&lt;class&gt; no implementa el miembro abstracto heredado &lt;member&gt;", porque la clase `B` no proporciona ninguna implementación para `A.Method1`.

```csharp
public abstract class A
{
    public abstract void Method1();
}

public class B : A // Generates CS0534.
{
    public void Method3()
    {
        // Do something.
    }
}
```

La herencia solo se aplica a clases e interfaces. Other type categories (structs, delegates, and enums) do not support inheritance. Debido a estas reglas, al intentar compilar código como el siguiente se genera el error de compilador CS0527: "El tipo 'ValueType' de la lista de interfaces no es una interfaz". El mensaje de error indica que, aunque se pueden definir las interfaces que implementa un struct, no se admite la herencia.

```csharp
using System;

public struct ValueStructure : ValueType // Generates CS0527.
{
}
```

## <a name="implicit-inheritance"></a>Herencia implícita

Aparte de los tipos de los que puedan heredar mediante herencia única, todos los tipos del sistema de tipos .NET heredan implícitamente de <xref:System.Object> o de un tipo derivado de este. La funcionalidad común de <xref:System.Object> está disponible para cualquier tipo.

Para ver lo que significa la herencia implícita, vamos a definir una nueva clase, `SimpleClass`, que es simplemente una definición de clase vacía:

[!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/simpleclass.cs#1)]

Después, se puede usar la reflexión (que permite inspeccionar los metadatos de un tipo para obtener información sobre ese tipo) con el fin de obtener una lista de los miembros que pertenecen al tipo `SimpleClass`. Aunque no se ha definido ningún miembro en la clase `SimpleClass`, la salida del ejemplo indica que en realidad tiene nueve miembros. Uno de ellos es un constructor sin parámetros (o predeterminado) que el compilador de C# proporciona de manera automática para el tipo `SimpleClass`. Los ocho restantes son miembros de <xref:System.Object>, el tipo del que heredan implícitamente a la larga todas las clases e interfaces del sistema de tipo .NET.

[!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/simpleclass.cs#2)]

La herencia implícita desde la clase <xref:System.Object> permite que estos métodos estén disponibles para la clase `SimpleClass`:

- El método público `ToString`, que convierte un objeto `SimpleClass` en su representación de cadena, devuelve el nombre de tipo completo. En este caso, el método `ToString` devuelve la cadena "SimpleClass".

- Tres métodos de prueba de igualdad de dos objetos: el método de instancia pública `Equals(Object)`, el método público estático `Equals(Object, Object)` y el método público estático `ReferenceEquals(Object, Object)`. De forma predeterminada, estos métodos prueban la igualdad de referencia; es decir, para que sean iguales, dos variables de objeto deben hacer referencia al mismo objeto.

- El método público `GetHashCode`, que calcula un valor que permite que una instancia del tipo se use en colecciones con hash.

- El método público `GetType`, que devuelve un objeto <xref:System.Type> que representa el tipo `SimpleClass`.

- El método protegido <xref:System.Object.Finalize%2A>, que está diseñado para liberar recursos no administrados antes de que el recolector de elementos no utilizados reclame la memoria de un objeto.

- El método protegido <xref:System.Object.MemberwiseClone%2A>, que crea un clon superficial del objeto actual.

Debido a la herencia implícita, se puede llamar a cualquier miembro heredado de un objeto `SimpleClass` como si realmente fuera un miembro definido en la clase `SimpleClass`. Así, en el ejemplo siguiente se llama al método `SimpleClass.ToString`, que `SimpleClass` hereda de <xref:System.Object>.

[!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/simpleclass2.cs#1)]

En la tabla siguiente se enumeran las categorías de tipos que se pueden crear en C# y los tipos de los que heredan implícitamente. Cada tipo base constituye un conjunto diferente de miembros disponible mediante herencia para los tipos derivados de forma implícita.

| Categoría de tipo | Hereda implícitamente de                                                      |
| ------------- | ----------------------------------------------------------------------------- |
| clase         | <xref:System.Object>                                                          |
| struct        | <xref:System.ValueType>, <xref:System.Object>                                 |
| enum          | <xref:System.Enum>, <xref:System.ValueType>, <xref:System.Object>             |
| delegado      | <xref:System.MulticastDelegate>, <xref:System.Delegate>, <xref:System.Object> |

## <a name="inheritance-and-an-is-a-relationship"></a>Herencia y una relación "is a"

Normalmente, la herencia se usa para expresar una relación "is a" entre una clase base y una o varias clases derivadas, donde las clases derivadas son versiones especializadas de la clase base; la clase derivada es un tipo de la clase base. Por ejemplo, la clase `Publication` representa una publicación de cualquier tipo y las clases `Book` y `Magazine` representan tipos específicos de publicaciones.

> [!NOTE]
> Una clase o struct puede implementar una o varias interfaces. Aunque a menudo la implementación se presenta como una solución alternativa para la herencia única o como una forma de usar la herencia con structs, su finalidad es expresar una relación diferente (una relación "can do") entre una interfaz y su tipo de implementación que la herencia. Una interfaz define un subconjunto de funcionalidad (por ejemplo, la posibilidad de probar la igualdad, comparar u ordenar objetos o de admitir análisis y formato con referencia cultural) que la interfaz pone a disposición de sus tipos de implementación.

Tenga en cuenta que "is a" también expresa la relación entre un tipo y una instancia específica de ese tipo. En el ejemplo siguiente, `Automobile` es una clase que tiene tres propiedades de solo lectura exclusivas: `Make`, el fabricante del automóvil; `Model`, el tipo de automóvil; y `Year`, el año de fabricación. La clase `Automobile` también tiene un constructor cuyos argumentos se asignan a los valores de propiedad, y reemplaza al método <xref:System.Object.ToString%2A?displayProperty=nameWithType> para crear una cadena que identifica de forma única la instancia de `Automobile` en lugar de la clase `Automobile`.

[!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/is-a.cs#1)]

En este caso, no se debe basar en la herencia para representar marcas y modelos de coche específicos. Por ejemplo, no es necesario definir un tipo `Packard` para representar los automóviles fabricados por la empresa de automóviles Packard Motor. En su lugar, se pueden representar mediante la creación de un objeto `Automobile` con los valores adecuados que se pasan a su constructor de clase, como en el ejemplo siguiente.

[!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/is-a.cs#2)]

Una relación "is a" basada en la herencia se aplica mejor a una clase base y a clases derivadas que agregan miembros adicionales a la clase base o que requieren funcionalidad adicional que no está presente en la clase base.

## <a name="designing-the-base-class-and-derived-classes"></a>Diseño de la clase base y las clases derivadas

Veamos el proceso de diseño de una clase base y sus clases derivadas. En esta sección, se definirá una clase base, `Publication`, que representa una publicación de cualquier tipo, como un libro, una revista, un periódico, un diario, un artículo, etc. También se definirá una clase `Book` que se deriva de `Publication`. El ejemplo se podría ampliar fácilmente para definir otras clases derivadas, como `Magazine`, `Journal`, `Newspaper` y `Article`.

### <a name="the-base-publication-class"></a>Clase base Publication

A la hora de diseñar la clase `Publication`, se deben tomar varias decisiones de diseño:

- Qué miembros se van a incluir en la clase `Publication` base, y si los miembros de `Publication` proporcionan implementaciones de método, o bien si `Publication` es una clase base abstracta que funciona como plantilla para sus clases derivadas.

  En este caso, la clase `Publication` proporcionará implementaciones de método. La sección [Diseño de clases base abstractas y sus clases derivadas](#abstract) contiene un ejemplo en el que se usa una clase base abstracta para definir los métodos que deben invalidar las clases derivadas. Las clases derivadas pueden proporcionar cualquier implementación que sea adecuada para el tipo derivado.

  La posibilidad de reutilizar el código (es decir, varias clases derivadas comparten la declaración y la implementación de los métodos de clase base y no tienen que invalidarlos) es una ventaja de las clases base no abstractas. Por tanto, se deben agregar miembros a `Publication` si es probable que algunos o la mayoría de los tipos `Publication` especializados compartan su código. Si no puede proporcionar implementaciones de clase base de forma eficaz, acabará por tener que proporcionar implementaciones de miembros prácticamente idénticas en las clases derivadas en lugar de una única implementación en la clase base. La necesidad de mantener código duplicado en varias ubicaciones es un origen potencial de errores.

  Para maximizar la reutilización del código y crear una jerarquía de herencia lógica e intuitiva, asegúrese de incluir en la clase `Publication` solo los datos y la funcionalidad común a todas o a la mayoría de las publicaciones. Así, las clases derivadas implementan miembros que son únicos para una clase determinada de publicación que representan.

- Hasta qué punto extender la jerarquía de clases. ¿Quiere desarrollar una jerarquía de tres o más clases, en lugar de simplemente una clase base y una o más clases derivadas? Por ejemplo, `Publication` podría ser una clase base de `Periodical`, que, a su vez, es una clase base de `Magazine`, `Journal` y `Newspaper`.

  En el ejemplo, se usará la jerarquía pequeña de una clase `Publication` y una sola clase derivada, `Book`. El ejemplo se podría ampliar fácilmente para crear una serie de clases adicionales que se derivan de `Publication`, como `Magazine` y `Article`.

- Si tiene sentido crear instancias de la clase base. Si no, se debe aplicar la palabra clave [abstract](../language-reference/keywords/abstract.md) a la clase. De lo contrario, se puede crear una instancia de la clase `Publication` mediante una llamada a su constructor de clase. Si se intenta crear una instancia de una clase marcada con la palabra clave `abstract` mediante una llamada directa a su constructor de clase, el compilador de C# genera el error CS0144: "No se puede crear una instancia de la interfaz o clase abstracta". Si se intenta crear una instancia de la clase mediante reflexión, el método de reflexión produce una excepción <xref:System.MemberAccessException>.

  De forma predeterminada, se puede crear una instancia de una clase base mediante una llamada a su constructor de clase. No es necesario definir un constructor de clase de forma explícita. Si uno no está presente en el código fuente de la clase base, el compilador de C# proporciona automáticamente un constructor (sin parámetros) de forma predeterminada.

  En el ejemplo, la clase `Publication` se marcará como [abstract](../language-reference/keywords/abstract.md) para que no se puedan crear instancias de ella.  Una clase `abstract` sin ningún método `abstract` indica que representa un concepto abstracto que se comparte entre varias clases concretas (como un `Book`, `Journal`).

- Si las clases derivadas deben heredar la implementación de la clase base de determinados miembros, si tienen la opción de invalidar la implementación de la clase base, o bien si deben proporcionar una implementación. La palabra clave [abstract](../language-reference/keywords/abstract.md) se usa para forzar que las clases derivadas proporcionen una implementación. La palabra clave [virtual](../language-reference/keywords/virtual.md) se usa para permitir que las clases derivadas invaliden un método de clase base. De forma predeterminada, *no se pueden invalidar* los métodos definidos en la clase base.

  La clase `Publication` no tiene ningún método `abstract`, pero la propia clase es `abstract`.

- Si una clase derivada representa la clase final en la jerarquía de herencia y no se puede usar ella misma como clase base para clases derivadas adicionales. De forma predeterminada, cualquier clase puede servir como clase base. Se puede aplicar la palabra clave [sealed](../language-reference/keywords/sealed.md) para indicar que una clase no puede servir como clase base para las clases adicionales. Al intentar derivar de una clase sealed se genera el error de compilador CS0509: "no puede derivar del tipo sealed \<typeName>".

  Para el ejemplo, la clase derivada se marcará como `sealed`.

En el ejemplo siguiente se muestra el código fuente para la clase `Publication`, así como una enumeración `PublicationType` que devuelve la propiedad `Publication.PublicationType`. Además de los miembros que hereda de <xref:System.Object>, la clase `Publication` define los siguientes miembros únicos e invalidaciones de miembros:

[!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/base-and-derived.cs#1)]

- Un constructor

  Dado que la clase `Publication` es `abstract`, no se puede crear una instancia de ella directamente desde código similar al del ejemplo siguiente:

  ```csharp
  var publication = new Publication("Tiddlywinks for Experts", "Fun and Games",
                                    PublicationType.Book);
  ```

  Sin embargo, su constructor de instancia se puede llamar directamente desde los constructores de clases derivadas, como muestra el código fuente de la clase `Book`.

- Dos propiedades relacionadas con la publicación

  `Title` es una propiedad <xref:System.String> de solo lectura cuyo valor se suministra mediante la llamada al constructor `Publication`.

  `Pages` es una propiedad <xref:System.Int32> de solo lectura que indica cuántas páginas en total tiene la publicación. El valor se almacena en un campo privado denominado `totalPages`. Debe ser un número positivo o se inicia una excepción <xref:System.ArgumentOutOfRangeException>.

- Miembros relacionados con el publicador

  Dos propiedades de solo lectura, `Publisher` y `Type`. Los valores se proporcionan originalmente mediante la llamada al constructor de clase `Publication`.

- Miembros relacionados con la publicación

  Dos métodos, `Publish` y `GetPublicationDate`, establecen y devuelven la fecha de publicación. El método `Publish` establece una marca `published` privada en `true` cuando se llama y asigna la fecha pasada a él como argumento al campo `datePublished` privado. El método `GetPublicationDate` devuelve la cadena "NYP" si la marca `published` es `false`, y el valor del campo `datePublished` si es `true`.

- Miembros relacionados con copyright

  El método `Copyright` toma como argumentos el nombre del propietario del copyright y el año del copyright, y los asigna a las propiedades `CopyrightName` y `CopyrightDate`.

- Una invalidación del método `ToString`

  Si un tipo no invalida al método <xref:System.Object.ToString%2A?displayProperty=nameWithType>, devuelve el nombre completo del tipo, que es de poca utilidad a la hora de diferenciar una instancia de otra. La clase `Publication` invalida <xref:System.Object.ToString%2A?displayProperty=nameWithType> para devolver el valor de la propiedad `Title`.

En la ilustración siguiente se muestra la relación entre la clase base `Publication` y su clase <xref:System.Object> heredada de forma implícita.

![Las clases de objeto y publicación](media/publication-class.jpg)

### <a name="the-book-class"></a>La clase `Book`.

La clase `Book` representa un libro como un tipo especializado de publicación. En el ejemplo siguiente se muestra el código fuente de la clase `Book`.

[!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/base-and-derived.cs#2)]

Además de los miembros que hereda de `Publication`, la clase `Book` define los siguientes miembros únicos e invalidaciones de miembros:

- Dos constructores

  Los dos constructores `Book` comparten tres parámetros comunes. Dos, *title* y *publisher*, corresponden a los parámetros del constructor `Publication`. La tercera es *author*, que se almacena para una propiedad `Author` pública inmutable. Un constructor incluye un parámetro *isbn*, que se almacena en la propiedad automática `ISBN`.

  El primer constructor usa [esta](../language-reference/keywords/this.md) palabra clave para llamar al otro constructor. El encadenamiento de constructores es un patrón común en la definición de constructores. Los constructores con menos parámetros proporcionan valores predeterminados al llamar al constructor con el mayor número de parámetros.

  El segundo constructor usa la palabra clave [base](../language-reference/keywords/base.md) para pasar el título y el nombre del editor al constructor de clase base. Si no realiza una llamada explícita a un constructor de clase base en el código fuente, el compilador de C# proporciona automáticamente una llamada al constructor sin parámetros o predeterminado de la clase base.

- Una propiedad `ISBN` de solo lectura, que devuelve el ISBN (International Standard Book Number) del objeto `Book`, un número exclusivo de 10 y 13 caracteres. El ISBN se proporciona como argumento para uno de los constructores `Book`. El ISBN se almacena en un campo de respaldo privado, generado automáticamente por el compilador.

- Una propiedad `Author` de solo lectura. El nombre del autor se proporciona como argumento para ambos constructores `Book` y se almacena en la propiedad.

- Dos propiedades relacionadas con el precio de solo lectura, `Price` y `Currency`. Sus valores se proporcionan como argumentos en una llamada al método `SetPrice`. La propiedad `Currency` es el símbolo de moneda ISO de tres dígitos (por ejemplo, USD para el dólar estadounidense). Los símbolos de moneda ISO se pueden recuperar de la propiedad <xref:System.Globalization.RegionInfo.ISOCurrencySymbol%2A>. Ambas propiedades son de solo lectura desde ubicaciones externas, pero se pueden establecer mediante código en la clase `Book`.

- Un método `SetPrice`, que establece los valores de las propiedades `Price` y `Currency`. Esos son los valores devueltos por dichas propiedades.

- Invalida el método `ToString` (heredado de `Publication`) y los métodos <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> y <xref:System.Object.GetHashCode%2A> (heredados de <xref:System.Object>).

  A menos que se invalide, el método <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> prueba la igualdad de referencia. Es decir, dos variables de objeto se consideran iguales si hacen referencia al mismo objeto. Por otro lado, en la clase `Book`, dos objetos `Book` deben ser iguales si tienen el mismo ISBN.

  Cuando invalide el método <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>, también debe invalidar el método <xref:System.Object.GetHashCode%2A>, que devuelve un valor que se usa en el entorno de ejecución para almacenar elementos en colecciones con hash para una recuperación eficiente. El código hash debe devolver un valor que sea coherente con la prueba de igualdad. Puesto que se ha invalidado <xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType> para devolver `true`, si las propiedades de ISBN de dos objetos `Book` son iguales, se devuelve el código hash calculado mediante la llamada al método <xref:System.String.GetHashCode%2A> de la cadena devuelta por la propiedad `ISBN`.

En la siguiente ilustración se muestra la relación entre la clase `Book` y `Publication`, su clase base.

![Clases de libro y publicación](media/book-class.jpg)

Ahora se puede crear una instancia de un objeto `Book`, invocar sus miembros únicos y heredados, y pasarla como argumento a un método que espera un parámetro de tipo `Publication` o de tipo `Book`, como se muestra en el ejemplo siguiente.

[!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/use-publication.cs#1)]

## <a name="designing-abstract-base-classes-and-their-derived-classes"></a>Diseño de clases base abstractas y sus clases derivadas

<a name="abstract"></a>

En el ejemplo anterior, se define una clase base que proporciona una implementación para una serie de métodos con el fin de permitir que las clases derivadas compartan código. En muchos casos, sin embargo, no se espera que la clase base proporcione una implementación. En su lugar, la clase base es una *clase abstracta* que declara *métodos abstractos*; sirve como una plantilla que define los miembros que debe implementar cada clase derivada. Normalmente, en una clase base abstracta, la implementación de cada tipo derivado es exclusiva de ese tipo. La clase se ha marcado con la palabra clave abstract porque no tenía mucho sentido crear instancias de un objeto `Publication`, aunque la clase proporcionara las implementaciones de funcionalidad común a las publicaciones.

Por ejemplo, cada forma geométrica bidimensional cerrada incluye dos propiedades: área, la extensión interna de la forma; y perímetro, o la distancia a lo largo de los bordes de la forma. La manera en que se calculan estas propiedades, sin embargo, depende completamente de la forma específica. La fórmula para calcular el perímetro (o la circunferencia) de un círculo, por ejemplo, es diferente a la de un triángulo. La clase `Shape` es una clase `abstract` con métodos `abstract`. Eso indica que las clases derivadas comparten la misma funcionalidad, pero que la implementan de otra manera.

En el ejemplo siguiente se define una clase base abstracta denominada `Shape` que define dos propiedades: `Area` y `Perimeter`. Además de marcar la clase con la palabra clave [abstract](../language-reference/keywords/abstract.md), cada miembro de instancia también se marca con la palabra clave [abstract](../language-reference/keywords/abstract.md). En este caso, `Shape` también invalida el método <xref:System.Object.ToString%2A?displayProperty=nameWithType> para devolver el nombre del tipo, en lugar de su nombre completo. Y define dos miembros estáticos, `GetArea` y `GetPerimeter`, que permiten que los llamadores recuperen fácilmente el área y el perímetro de una instancia de cualquier clase derivada. Cuando se pasa una instancia de una clase derivada a cualquiera de estos métodos, el runtime llama a la invalidación del método de la clase derivada.

[!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/shape.cs#1)]

Después, se pueden derivar algunas clases de `Shape` que representan formas concretas. El ejemplo siguiente define tres clases `Triangle`, `Rectangle` y `Circle`. Cada una usa una fórmula única para esa forma en particular para calcular el área y el perímetro. Algunas de las clases derivadas también definen propiedades, como `Rectangle.Diagonal` y `Circle.Diameter`, que son únicas para la forma que representan.

[!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/shape.cs#2)]

En el ejemplo siguiente se usan objetos derivados de `Shape`. Se crea una instancia de una matriz de objetos derivados de `Shape` y se llama a los métodos estáticos de la clase `Shape`, que ajusta los valores de propiedad `Shape` devueltos. El runtime recupera los valores de las propiedades invalidadas de los tipos derivados. En el ejemplo también se convierte cada objeto `Shape` de la matriz a su tipo derivado y, si la conversión se realiza correctamente, recupera las propiedades de esa subclase específica de `Shape`.

[!code-csharp[Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/shape.cs#3)]

## <a name="see-also"></a>Vea también

- [Herencia (Guía de programación de C#)](../programming-guide/classes-and-structs/inheritance.md)
