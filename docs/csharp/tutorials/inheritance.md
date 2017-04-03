---
title: Herencia en C#
description: Aprenda a usar la herencia en bibliotecas y aplicaciones en C#.
keywords: herencia (C#), clases base, clases derivadas, clases base abstractas
author: rpetrusha
manager: wpickett
ms.author: ronpet
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: aeb68c74-0ea0-406f-9fbe-2ce02d47ef31
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c14a2ecfa4b9c9522278098d54aad258b5feb1dc
ms.lasthandoff: 03/13/2017

---
# <a name="inheritance-in-c-and-net"></a>Herencia en C# y .NET #

## <a name="introduction"></a>Introducción ##

Este tutorial es una introducción a la herencia en C#. La herencia es una característica de los lenguajes de programación orientados a objetos que permite definir una clase base, que proporciona funcionalidad específica (datos y comportamiento), así como clases derivadas, que heredan o invalidan esa funcionalidad.

## <a name="prerequisites"></a>Requisitos previos ##

En este tutorial se supone que ha instalado .NET Core. Para obtener instrucciones de instalación, consulte [.NET Core installation guide](https://www.microsoft.com/net/core) (Guía de instalación de .NET Core). También necesitará un editor de código. En este tutorial se usa [Visual Studio Code](https://code.visualstudio.com), aunque puede elegir el que prefiera.

## <a name="running-the-examples"></a>Ejecución de los ejemplos ##

Para crear y ejecutar los ejemplos de este tutorial, use la utilidad [dotnet](../../core/tools/dotnet.md) desde la línea de comandos. Siga estos pasos para cada ejemplo:

1. Cree un directorio para almacenar el ejemplo.

1. Escriba el comando [dotnet new console](../../core/tools/dotnet-new.md) en el símbolo del sistema para crear un nuevo proyecto de .NET Core.

1. Copie y pegue el código del ejemplo en el editor de código.

1. Escriba el comando [dotnet restore](../../core/tools/dotnet-restore.md) desde la línea de comandos para cargar o restaurar las dependencias del proyecto.

1. Escriba el comando [dotnet run](../../core/tools/dotnet-run.md) para compilar y ejecutar el ejemplo.

## <a name="background-what-is-inheritance"></a>Contexto: ¿Qué es la herencia? ##

La *herencia* es uno de los atributos fundamentales de la programación orientada a objetos. Permite definir una clase secundaria que reutiliza (hereda), amplía o modifica el comportamiento de una clase primaria. La clase cuyos miembros son heredados se conoce como *clase base*. La clase que hereda los miembros de la clase base se conoce como *clase derivada*.

C# y .NET solo admiten *herencia única*. Es decir, una clase solo puede heredar de una clase única. Sin embargo, la herencia es transitiva, lo que le permite definir una jerarquía de herencia para un conjunto de tipos. En otras palabras, el tipo `D` puede heredar del tipo `C`, que hereda del tipo `B`, que hereda del tipo de clase base `A`. Dado que la herencia es transitiva, los miembros de tipo `A` están disponibles para el tipo `D`.

No todos los miembros de una clase base los heredan las clases derivadas. Los siguientes miembros no se heredan:

- [Constructores estáticos](../programming-guide/classes-and-structs/static-constructors.md), que inicializan los datos estáticos de una clase.

- [Constructores de instancias](../programming-guide/classes-and-structs/constructors.md), a los que se llama para crear una nueva instancia de la clase. Cada clase debe definir sus propios constructores.

- [Destructores](../programming-guide/classes-and-structs/destructors.md), denominados recolectores de elementos no utilizados del entorno de tiempo de ejecución para destruir instancias de una clase.

Si bien las clases derivadas heredan todos los demás miembros de una clase base, que dichos miembros estén o no visibles depende de su accesibilidad. La accesibilidad del miembro afecta a su visibilidad en las clases derivadas del modo siguiente:

- Los miembros [privados](../language-reference/keywords/private.md) solo son visible en las clases derivadas que están anidadas en su clase base. De lo contrario, no son visibles en las clases derivadas. En el ejemplo siguiente, `A.B` es una clase anidada que se deriva de `A`, y `C` se deriva de `A`. El campo `A.value` privado es visible en A.B. Sin embargo, si quita los comentarios del método `C.GetValue` e intenta compilar el ejemplo, se produce el error del compilador CS0122: ""A.value" no es accesible debido a su nivel de protección".

   [!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/private.cs#1)]

- Los miembros [protegidos](../language-reference/keywords/protected.md) solo son visibles en las clases derivadas.

- Los miembros [internos](../language-reference/keywords/protected.md) solo son visibles en las clases derivadas que se encuentran en el mismo ensamblado que la clase base. No son visibles en las clases derivadas ubicadas en un ensamblado diferente al de la clase base.

- Los miembros [públicos] (../language-reference/keywords/protected.md) son visibles en las clases derivadas y forman parte de la interfaz pública de dichas clases. Los miembros públicos heredados se pueden llamar como si se hubieran definido en la clase derivada. En el ejemplo siguiente, la clase `A` define un método denominado `Method1` y la clase `B` hereda de la clase `A`. El ejemplo llama a `Method1` como si fuera un método de instancia en `B`.

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/basics.cs#1)]

Las clases derivadas pueden también *invalidar* los miembros heredados al proporcionar una implementación alternativa. Para poder invalidar un miembro, el miembro de la clase base debe marcarse con la palabra clave [virtual](../language-reference/keywords/virtual.md). De forma predeterminada, los miembros de clase base no están marcados con `virtual` y no se pueden invalidar. Al intentar invalidar un miembro no virtual, como en el ejemplo siguiente, se genera el error de compilador CS0506: "<member> no se puede invalidar el miembro heredado <member> porque no está marcado como virtual, abstract ni override.

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
      public override void Method1()  // Generates CS0506.
      {
         // Do something else.
      }
   }
   ```

En algunos casos, una clase derivada *debe* invalidar la implementación de la clase base. Los miembros de clase base marcados con la palabra clave [abstract](../language-reference/keywords/abstract.md) requieren que las clases derivadas los invaliden. Al intentar compilar el ejemplo siguiente, se genera el error de compilador CS0534, "<class> no implementa el miembro abstracto heredado <member>", porque la clase `B` no proporciona ninguna implementación para `A.Method1`.

   ```csharp
   public abstract class A
   {
      public abstract void Method1();
   }

   public class B : A                  // Generates CS0534.
   {
      public void Method3()
      {
         // Do something.
      }
   }
   ```

La herencia solo se aplica a clases e interfaces. Other type categories (structs, delegates, and enums) do not support inheritance. Por este motivo, al intentar compilar código como el siguiente se genera el error de compilador CS0527: "El tipo "ValueType" de la lista de interfaces no es una interfaz". El mensaje de error indica que, aunque se pueden definir las interfaces que implementa un struct, no se admite la herencia.

   ```csharp
   using System;

   public struct ValueStructure : ValueType       // Generates CS0527.
   {
   }
   ```

## <a name="implicit-inheritance"></a>Herencia implícita ##

Aparte de los tipos de los que puedan heredar mediante herencia única, todos los tipos del sistema de tipos .NET heredan implícitamente de @System.Object o de un tipo derivado de este. Esto garantiza que la funcionalidad común está disponible para cualquier tipo.

Para ver lo que significa la herencia implícita, vamos a definir una nueva clase, `SimpleClass`, que es simplemente una definición de clase vacía:

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/simpleclass.cs#1)]

A continuación, podemos usar reflexión (que nos permite inspeccionar los metadatos de un tipo para obtener información sobre ese tipo) para obtener una lista de los miembros que pertenecen al tipo `SimpleClass`. Aunque no hemos definido ningún miembro en nuestra clase `SimpleClass`, la salida del ejemplo indica que en realidad tiene nueve miembros. Uno de ellos es un constructor sin parámetros (o predeterminado) que el compilador de C# proporciona automáticamente para el tipo `SimpleClass`. Los otros ocho son miembros de @System.Object, el tipo del que heredan implícitamente a la larga todas las clases e interfaces del sistema de tipo .NET.

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/simpleclass.cs#2)]

La herencia implícita desde la clase @System.Object permite que estos métodos estén disponibles para la clase `SimpleClass`:

- El método público `ToString`, que convierte un objeto `SimpleClass` en su representación de cadena, el nombre de tipo completo. En este caso, el método `ToString` devuelve la cadena "SimpleClass".

- Tres métodos de prueba de igualdad de dos objetos: el método de instancia pública `Equals(Object)`, el método público estático `Equals(Object, Object)` y el método público estático `ReferenceEquals(Object, Object)`. De forma predeterminada, estos métodos prueban la igualdad de referencia; es decir, para que sean iguales, dos variables de objeto deben hacer referencia al mismo objeto.

- El método público `GetHashCode`, que calcula un valor que permite que una instancia del tipo se use en colecciones con hash.

- El método público `GetType`, que devuelve un objeto @System.Type que representa el tipo `SimpleClass`.

- El método protegido @System.Object.Finalize, que está diseñado para liberar recursos no administrados antes de que el recolector de elementos no utilizados reclame la memoria de un objeto.

- El método protegido @System.Object.MemberwiseClone, que crea un clon superficial del objeto actual.

Debido a la herencia implícita, podemos llamar a cualquier miembro heredado de un objeto `SimpleClass` como si fuera realmente un miembro definido en la clase `SimpleClass`. Así, en el ejemplo siguiente se llama al método `SimpleClass.ToString`, que `SimpleClass` hereda de @System.Object.

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/simpleclass2.cs#1)]

En la tabla siguiente se enumeran las categorías de tipos que se pueden crear en C# y los tipos de los que heredan implícitamente. Cada tipo base constituye un conjunto diferente de miembros disponible mediante herencia para los tipos derivados de forma implícita.

| Categoría de tipo | Hereda implícitamente de... |
| :--- | :---: | ---: |
| clase | @System.Object |
| struct | @System.ValueType, @System.Object |
| enum | @System.Enum, System.ValueType, @System.Object |
| delegado | @System.MulticastDelegate, @System.Delegate, @System.Object |

## <a name="inheritance-and-an-is-a-relationship"></a>Herencia y una relación "is a" ##

Normalmente, la herencia se usa para expresar una relación "is a" entre una clase base y una o varias clases derivadas, donde las clases derivadas son versiones especializadas de la clase base; la clase derivada es un tipo de la clase base. Por ejemplo, la clase `Publication` representa una publicación de cualquier tipo y las clases `Book` y `Magazine` representan tipos específicos de publicaciones.

   [!NOTE] Una clase o struct puede implementar una o varias interfaces. Aunque a menudo la implementación se presenta como una solución alternativa para la herencia única o como una forma de usar la herencia con structs, su finalidad es expresar una relación diferente (una relación "can do") entre una interfaz y su tipo de implementación que la herencia. Una interfaz define un subconjunto de funcionalidad (por ejemplo, la posibilidad de probar la igualdad, comparar u ordenar objetos o de admitir análisis y formato con referencia cultural) que la interfaz pone a disposición de sus tipos de implementación.

Tenga en cuenta que "is a" también expresa la relación entre un tipo y una instancia específica de ese tipo. En el ejemplo siguiente, `Automobile` es una clase que tiene tres propiedades de solo lectura exclusivas: `Moke`, el fabricante del automóvil; `Model`, el tipo de automóvil; y `Year`, el año de fabricación. Nuestra clase `Automobile` también tiene un constructor cuyos argumentos se asignan a los valores de propiedad, y reemplaza al método @System.Object.ToString para producir una cadena que identifica de forma única la instancia `Automobile` en lugar de la clase `Automobile`.

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/is-a.cs#1)]

En este caso, no debemos confiar en la herencia para representar marcas y modelos de coches específicos. Por ejemplo, no es necesario definir un tipo `Packard` para representar los automóviles fabricados por la empresa de automóviles Packard Motor. En su lugar, se pueden representar mediante la creación de un objeto `Automobile` con los valores adecuados que se pasan a su constructor de clase, como en el siguiente ejemplo.

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/is-a.cs#2)]

Una relación "is a" basada en la herencia se aplica mejor a una clase base y a clases derivadas que agregan miembros adicionales a la clase base o que requieren funcionalidad adicional que no está presente en la clase base.

## <a name="designing-the-base-class-and-derived-classes"></a>Diseño de la clase base y las clases derivadas ##

Veamos el proceso de diseño de una clase base y sus clases derivadas. En esta sección, se definirá una clase base, `Publication`, que representa una publicación de cualquier tipo, como un libro, una revista, un periódico, un diario, un artículo, etc. También definiremos una clase `Book` que se deriva de `Publication`. Podríamos ampliar fácilmente el ejemplo para definir otras clases derivadas, como `Magazine`, `Journal`, `Newspaper` y `Article`.

### <a name="the-base-publication-class"></a>La clase base `Publication` ###

A la hora de diseñar nuestra clase `Publication`, debemos tomar varias decisiones en cuanto al diseño:

- Qué miembros se incluirán en nuestra clase base `Publication` y si los miembros de `Publication` proporcionarán implementaciones de método, o si `Publication` es una clase base abstracta que funciona como plantilla para sus clases derivadas.

   En este caso, la clase `Publication` proporcionará implementaciones de método. La sección [Diseño de clases base abstractas y sus clases derivadas](#abstract) contiene un ejemplo en el que se usa una clase base abstracta para definir los métodos que deben invalidar las clases derivadas. Las clases derivadas pueden proporcionar cualquier implementación que sea adecuada para el tipo derivado.

   La posibilidad de reutilizar el código (es decir, varias clases derivadas comparten la declaración y la implementación de los métodos de clase base y no tienen que invalidarlos) es una ventaja de las clases base no abstractas. Por lo tanto, debemos agregar miembros a `Publication` si es probable que algunos o la mayoría de tipos `Publication` especializados compartan su código. Si no lo hacemos bien, acabaremos por tener que proporcionar implementaciones de miembros prácticamente idénticas en las clases derivadas en lugar de una única implementación en la clase base. La necesidad de mantener código duplicado en varias ubicaciones es un origen potencial de errores.

   Tanto para maximizar la reutilización del código como para crear una jerarquía de herencia lógica e intuitiva, queremos estar seguros de incluir en la clase `Publication` solo los datos y la funcionalidad común a todos o a la mayoría de las publicaciones. Así, las clases derivadas implementan miembros que son únicos para una clase determinada de publicación que representan.

- Hasta qué punto extender nuestra jerarquía de clases. ¿Desea desarrollar una jerarquía de tres o más clases, en lugar de simplemente una clase base y una o más clases derivadas? Por ejemplo, `Publication` podría ser una clase base de `Periodical`, que, a su vez, es una clase base de `Magazine`, `Journal` y `Newspaper`.

   En nuestro ejemplo, vamos a usar la jerarquía simple de una clase `Publication` y una sola clase derivada, `Book`. Podríamos extender fácilmente el ejemplo para crear una serie de clases adicionales que se derivan de `Publication`, como `Magazine` y `Article`.

- Si tiene sentido crear instancias de la clase base. Si no, debemos aplicar la palabra clave [abstract](../language-reference/keywords/abstract.md) a la clase. Si se intenta crear una instancia de una clase marcada con la palabra clave `abstract` mediante una llamada directa a su constructor de clase, el compilador de C# genera el error CS0144: "No se puede crear una instancia de la interfaz o clase abstracta". Si se intenta crear una instancia de la clase mediante reflexión, el método de reflexión produce una excepción @System.MemberAccessException. De lo contrario, se puede crear una instancia de nuestra clase `Publication` mediante una llamada a su constructor de clase.

   De forma predeterminada, se puede crear una instancia de una clase base mediante una llamada a su constructor de clase. Tenga en cuenta que no tenemos que definir explícitamente un constructor de clase. Si uno no está presente en el código fuente de la clase base, el compilador de C# proporciona automáticamente un constructor (sin parámetros) de forma predeterminada.

   En nuestro ejemplo, marcaremos la clase `Publication` como [abstract](../language-reference/keywords/abstract.md) para que no se pueden crear instancias.

- Si las clases derivadas deben heredar la implementación de la clase base de un determinado miembro o tienen la opción de invalidar la implementación de la clase base. Debemos usar la palabra clave [virtual](../language-reference/keywords/virtual.md) para permitir que las clases derivadas invaliden un método de clase base. De forma predeterminada, *no se pueden invalidar* los métodos definidos en la clase base.

- Si una clase derivada representa la clase final en la jerarquía de herencia y no se puede usar ella misma como clase base para clases derivadas adicionales. De forma predeterminada, cualquier clase puede servir como clase base. Podemos aplicar la palabra clave [sealed](../language-reference/keywords/sealed.md) para indicar que una clase no puede servir como clase base para las clases adicionales. Al intentar derivar de una clase sealed se genera el error de compilador CS0509: "no puede derivar del tipo sealed <typeName>".

   En nuestro ejemplo, marcaremos nuestra clase derivada como `sealed`.

En el ejemplo siguiente se muestra el código fuente para la clase `Publication`, así como una enumeración `PublicationType` que devuelve la propiedad `Publication.PublicationType`. Además de los miembros que hereda de @System.Object, la clase `Publication` define los siguientes miembros únicos e invalidaciones de miembros:

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/base-and-derived.cs#1)]

- Un constructor

  Dado que la clase `Publication` es `abstract`, no se puede crear una instancia de ella directamente desde código similar al siguiente:

  ```csharp
  var publication = new Publication("Tiddlywinks for Experts", "Fun and Games",
                                    PublicationType.Book);
  ```

  Sin embargo, su constructor de instancia se puede llamar directamente desde los constructores de clases derivadas, como muestra el código fuente de la clase `Book`.

- Dos propiedades relacionadas con la publicación

  `Title` es una propiedad @System.String de solo lectura cuyo valor se suministra mediante la llamada al constructor `Publication`, que almacena el valor en un campo privado llamado `pubTitle`.

  `Pages` es una propiedad @System.Int32 de solo lectura que indica cuántas páginas en total tiene la publicación. El valor se almacena en un campo privado denominado `totalPages`. Debe ser un número positivo o se inicia una excepción @System.ArgumentOutOfRangeException.

- Miembros relacionados con el publicador

  Dos propiedades de solo lectura, `Publisher` y `Type`, devuelven el valor de los campos privados `pubName` y `pubType`. Los valores se proporcionan originalmente mediante la llamada al constructor de clase `Publication`.

- Miembros relacionados con la publicación

  Dos métodos, `Publish` y `GetPublicationDate`, establecen y devuelven la fecha de publicación. El método `Publish` establece una marca `published` privada en `true` cuando se llama y asigna la fecha pasada a él como argumento al campo `datePublished` privado. El método `GetPublicationDate` devuelve la cadena "NYP" si la marca `published` es `false`, y el valor del campo `datePublished` si es `true`.

- Miembros relacionados con copyright

  El método `Copyright` toma el nombre del propietario del copyright y el año del copyright como argumentos y los asigna a los campos privados `copyrName` y `copyrDate`. Los valores se pueden recuperar desde las propiedades `CopyrightName` y `CopyrightDate`.

- Una invalidación del método `ToString`

  Si un tipo no invalida al método @System.Object.ToString, devuelve el nombre completo del tipo, que es de poca utilidad a la hora de diferenciar una instancia de otra. La clase `Publication` invalida @System.Object.ToString para devolver el valor de la propiedad `Title`.

En la siguiente ilustración se muestra la relación entre nuestra clase base `Publication` y su clase heredada implícitamente @System.Object.

![Las clases de objeto y publicación](media/publication-class.jpg)

### <a name="the-book-class"></a>La clase `Book`. ###

La clase `Book` representa un libro como un tipo especializado de publicación. En el ejemplo siguiente se muestra el código fuente de la clase `Book`.

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/base-and-derived.cs#2)]

Además de los miembros que hereda de `Publication`, la clase `Book` define los siguientes miembros únicos e invalidaciones de miembros:

- Dos constructores

  Los dos constructores `Book` comparten tres parámetros comunes. Dos, *title* y *publisher*, corresponden a los parámetros del constructor `Publication`. El tercero, *author*, se almacena en un campo privado `authorName`. Un constructor incluye un parámetro *isbn*, que se almacena en un campo privado `id`.

  El primer constructor usa [esta](../language-reference/keywords/this.md) palabra clave para llamar al otro constructor. Este es un patrón común en la definición de constructores; los constructores con menos parámetros proporcionan valores predeterminados al llamar al constructor con el mayor número de parámetros.

  El segundo constructor usa la palabra clave [base](../language-reference/keywords/base.md) para pasar el título y el nombre del editor al constructor de clase base. Si no realiza una llamada explícita a un constructor de clase base en el código fuente, el compilador de C# proporciona automáticamente una llamada al constructor sin parámetros o predeterminado de la clase base.

- Una propiedad `ISBN` de solo lectura, que devuelve el ISBN (International Standard Book Number) del objeto `Book`, un número exclusivo de 10 y 13 caracteres. El ISBN se proporciona como argumento para uno de los constructores `Book` y se almacena en el campo privado `id`.

- Una propiedad `Author` de solo lectura. El nombre del autor se proporciona como argumento para ambos constructores `Book` y se almacena en el campo privado `authorName`.

- Dos propiedades relacionadas con el precio de solo lectura, `Price` y `Currency`. Sus valores se proporcionan como argumentos en una llamada al método `SetPrice`. El precio se almacena en un campo privado, `bookPrice`. La propiedad `Currency` es el símbolo de moneda ISO de tres dígitos (por ejemplo, USD para el dólar estadounidense) y se almacena en el campo privado `ISOCurrencySymbol`. Los símbolos de moneda ISO se pueden recuperar de la propiedad @System.Globalization.RegionInfo.ISOCurrencySymbol.

- Un método `SetPrice`, que establece los valores de los campos `bookPrice` y `ISOCurrencySymbol`. Estos son los valores devueltos por las propiedades `Price` y `Currency`.

- Invalida el método `ToString` (heredado de `Publication`) y los métodos @System.Object.Equals(System.Object) y @System.Object.GetHashCode (heredados de @System.Object).

  A menos que se invalide, el método @System.Object.Equals(System.Object) prueba la igualdad de referencia. Es decir, dos variables de objeto se consideran iguales si hacen referencia al mismo objeto. Por otro lado, en el caso de la clase `Book`, dos objetos `Book` deben ser iguales si tienen el mismo ISBN.

  Cuando invalide el método @System.Object.Equals(System.Object), también debe invalidar el método @System.Object.GetHashCode, que devuelve un valor que se usa en tiempo de ejecución para almacenar elementos en colecciones con hash para una recuperación eficiente. El código hash debe devolver un valor que sea coherente con la prueba de igualdad. Puesto que hemos invalidado @System.Object.Equals(System.Object) para devolver `true` si las propiedades de ISBN de dos objetos `Book` son iguales, se devuelve el código hash calculado mediante la llamada al método @System.String.GetHashCode de la cadena devuelta por la propiedad `ISBN`.

En la siguiente ilustración se muestra la relación entre la clase `Book` y `Publication`, su clase base.

![Clases de libro y publicación](media/book-class.jpg)

Ahora podemos crear una instancia de un objeto `Book`, invocar sus miembros únicos y heredados y pasarla como argumento a un método que espera un parámetro de tipo `Publication` o de tipo `Book`, como se muestra en el ejemplo siguiente.

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/use-publication.cs#1)]

## <a name="abstract"></a> Diseño de clases base abstractas y sus clases derivadas ##

En el ejemplo anterior, hemos definido una clase base que proporciona una implementación para una serie de métodos para permitir que las clases derivadas compartan código. En muchos casos, sin embargo, no se espera que la clase base proporcione una implementación. En su lugar, la clase base es un *clase abstracta*; sirve como plantilla que define los miembros que debe implementar cada clase derivada. Normalmente, en el caso de una clase base abstracta, la implementación de cada tipo derivado es exclusiva de ese tipo.

Por ejemplo, cada forma geométrica bidimensional cerrada incluye dos propiedades: área, la extensión interna de la forma; y perímetro, o la distancia a lo largo de los bordes de la forma. La manera en que se calculan estas propiedades, sin embargo, depende completamente de la forma específica. La fórmula para calcular el perímetro (o circunferencia) de un círculo, por ejemplo, es muy diferente a la de un triángulo.

En el ejemplo siguiente se define una clase base abstracta denominada `Shape` que define dos propiedades: `Area` y `Perimeter`. Tenga en cuenta que, además de marcar la clase con la palabra clave [abstract](../language-reference/keywords/abstract.md), cada miembro de instancia también se marca con esta palabra clave [abstract](../language-reference/keywords/abstract.md). En este caso, `Shape` también invalida el método @System.Object.ToString para devolver el nombre del tipo, en lugar de su nombre completo. Y define dos miembros estáticos, `GetArea` y `GetPerimeter`, que permiten que los llamadores recuperen fácilmente el área y el perímetro de una instancia de cualquier clase derivada. Cuando se pasa una instancia de una clase derivada a cualquiera de estos métodos, el tiempo de ejecución llama a la invalidación del método de la clase derivada.

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/shape.cs#1)]

Luego podemos derivar algunas clases de `Shape` que representan formas concretas. El ejemplo siguiente define tres clases `Triangle`, `Rectangle` y `Circle`. Cada una usa una fórmula única para esa forma en particular para calcular el área y el perímetro. Algunas de las clases derivadas también definen propiedades, como `Rectangle.Diagonal` y `Circle.Diameter`, que son únicas para la forma que representan.

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/shape.cs#2)]

En el ejemplo siguiente se usan objetos derivados de `Shape`. Se crea una instancia de una matriz de objetos derivados de `Shape` y se llama a los métodos estáticos de la clase `Shape`, que ajusta los valores de propiedad `Shape` devueltos. Tenga en cuenta que el tiempo de ejecución recupera los valores de las propiedades invalidadas de los tipos derivados. En el ejemplo también se convierte cada objeto `Shape` de la matriz a su tipo derivado y, si la conversión se realiza correctamente, recupera las propiedades de esa subclase específica de `Shape`. 

[!CODE [Inheritance](../../../samples/snippets/csharp/tutorials/inheritance/shape.cs#3)]

## <a name="see-also"></a>Vea también ##

[Clases y objetos](../tour-of-csharp/classes-and-objects.md)</br>
[Herencia (Guía de programación de C#)](../programming-guide/classes-and-structs/inheritance.md)

