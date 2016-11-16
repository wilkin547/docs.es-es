---
title: .NET Primer
description: .NET Primer
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 10/05/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bbfe6465-329d-4982-869d-472e7ef85d93
translationtype: Human Translation
ms.sourcegitcommit: be774ae1291def36baafffbf2f717cf98565cd60
ms.openlocfilehash: fba870a93784b579da1065a07d82974951ac7e28

---

# <a name="net-primer"></a>.NET Primer

> Consulte los [tutoriales "Introducción a .NET Core"](../core/getting-started.md) para aprender a crear una aplicación .NET Core sencilla. En unos minutos su primera aplicación estará lista y funcionando.

.NET es una plataforma de desarrollo de uso general. Puede usarse para cualquier tipo de carga de trabajo o aplicación donde se usen soluciones de uso general. Tiene varias características clave que son atractivas para muchos desarrolladores, incluida la administración automática de la memoria y los lenguajes de programación modernos, que facilitan más la creación eficaz de aplicaciones de alta calidad. .NET hace posible un entorno de programación de alto nivel con muchas características útiles, a la vez que proporciona acceso de bajo nivel a la memoria nativa y a las API.

Hay disponibles varias implementaciones de .NET basadas en [estándares .NET](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) abiertos que especifican los fundamentos de la plataforma. Se optimizan independientemente para diferentes tipos de aplicaciones (por ejemplo, para escritorio, móviles, juegos o la nube) y admiten muchos chips (por ejemplo, x86/x64, ARM) y sistemas operativos (por ejemplo, Windows, Linux, iOS Android y macOS). El código abierto también es una parte importante del ecosistema de .NET, con varias implementaciones de .NET y muchas bibliotecas disponibles bajo licencias con aprobación de OSI.

Consulte el documento [Información general sobre implementaciones de .NET](../about/products.md) para obtener información sobre todas las ediciones diferentes de .NET que están disponibles, de Microsoft y de otros proveedores.

Este manual le ayudará a entender algunos de los conceptos clave de la plataforma .NET y le indicará más recursos para cada tema determinado. Al final del mismo, debería tener suficiente información para poder reconocer términos y conceptos significativos de la plataforma .NET, y para saber cómo obtener más información acerca de ellos. 

## <a name="a-stroll-through-net"></a>Un paseo por .NET

Como cualquier marco de desarrollo de aplicaciones avanzadas y experimentadas, .NET tiene muchas características eficaces que facilitan el trabajo del desarrollador y que pretenden que la acción de escribir código sea más eficaz y expresiva. En esta sección se describen los conceptos básicos de las características más destacables y se indica cómo acceder a información más detallada en caso aplicable. Tras finalizar este paseo, debería tener suficiente información para poder leer los ejemplos de nuestros repositorios de GitHub, así como otro código y comprender su funcionamiento.

*   [Lenguajes de programación](#programming-languages)
*   [Administración de memoria automática](#automatic-memory-management)
*   [Seguridad de tipos](#type-safety)
*   [Delegados y expresiones lambda](#delegates-and-lambdas)
*   [Tipos genéricos (genéricos)](#generic-types-generics)
*   [Language-Integrated Query (LINQ)](#language-integrated-query-linq)
*   [Programación asincrónica](#async-programming)
*   [Interoperabilidad nativa](#native-interoperability)
*   [Código no seguro](#unsafe-code)

### <a name="programming-languages"></a>Lenguajes de programación

Como desarrollador, puede elegir cualquier lenguaje de programación compatible con .NET para crear la aplicación. Dado que .NET proporciona independencia e interoperabilidad entre lenguajes, puede interactuar con otras aplicaciones y componentes de .NET independientemente del lenguaje con el fueron desarrolladas.

Los lenguajes que permitan desarrollar aplicaciones de la plataforma .NET cumple la [especificación de Common Language Infrastructure (CLI)](https://www.visualstudio.com/en-us/mt639507).

Los lenguajes de Microsoft que admiten .NET incluyen C#, F # y Visual Basic. 

* C# es simple, eficaz, incluye seguridad de tipos y está orientado a objetos, al mismo tiempo que mantiene la expresividad y elegancia de los lenguajes de estilo C. Cualquiera que esté familiarizado con C y lenguajes similares, encontrará pocos problemas para adaptarse a C#.

* F # es un lenguaje de programación multiplataforma, principalmente funcional, que también admite la programación tradicional imperativa y orientada en objetos.

* Visual Basic es un lenguaje fácil de aprender que puede usar para crear una gran variedad de aplicaciones que se ejecutan en .NET Framework.

> [!NOTE]
> En la versión actual de .NET Core, solo C# es totalmente compatible en todas las herramientas de Microsoft.  F # es compatible con .NET Core SDK, pero todavía no tiene herramientas de Visual Studio.  La compatibilidad con Visual Basic para las herramientas de Visual Studio y SDK estará disponible próximamente.

### <a name="automatic-memory-management"></a>Administración de memoria automática

La recolección de elementos no utilizados es la característica más conocida de .NET. Los desarrolladores no necesitan administrar activamente la memoria, aunque hay mecanismos destinados a proporcionar más información para el recolector de elementos no utilizados (GC). C# incluye la palabra clave `new` para asignar memoria en términos de un tipo determinado y la palabra clave `using` para proporcionar un ámbito para el uso del objeto. El GC opera con un enfoque diferido para la administración de memoria y prefiere el rendimiento de la aplicación sobre la recolección inmediata de la memoria.

Las dos líneas siguientes asignan memoria:

```cs
var title = ".NET Primer";
var list = new List<string>;

```

No hay ninguna palabra clave análoga para anular la asignación de memoria, ya que la anulación de la asignación se realiza automáticamente cuando el recolector de elementos no utilizados reclama la memoria a través de su ejecución programada.

Las variables del método normalmente quedan fuera de ámbito cuando se completa un método, en cuyo momento pueden recopilarse. Pero puede indicar en el GC que un objeto determinado esté fuera de ámbito antes de que salga el método a través de la instrucción `using`.

```cs
using(FileStream stream = GetFileStream(context))
{
    //operations on the stream
}

```

Una vez que se complete el bloque de `using`, el GC sabrá que el objeto `stream` en el ejemplo anterior ya se puede recopilar y reclamar su memoria.

La protección de la memoria es una de las características menos obvias, pero con un alcance bastante grande, que es posible gracias a un recolector de elementos no utilizados. El valor invariable de protección de la memoria es muy simple: un programa tiene protección de la memoria si solo tiene acceso a la memoria que se ha asignado (y no liberado). Los punteros pendientes siempre suponen errores y localizarlos suele ser bastante difícil.

El runtime de .NET proporciona servicios adicionales para completar la promesa de protección de la memoria, que no ofrece de forma natural un GC. Garantiza que los programas no indicen el final de una matriz ni tengan acceso a un campo fantasma al final de un objeto.

En el ejemplo siguiente, se iniciará una excepción como resultado de la protección de la memoria.

```cs
int[] numbers = new int[42];
int number = numbers[42]; // will throw (indexes are 0-based)

```

### <a name="type-safety"></a>Seguridad de tipos

Los objetos se asignan en términos de tipos. Las únicas operaciones permitidas para un objeto determinado, y la memoria que consume, son los de su tipo. Un tipo `Dog` puede tener métodos `Jump` y `WagTail`, pero no es probable que tenga un método `SumTotal`. Un programa solo puede llamar a los métodos declarados de un tipo determinado. Todas las demás llamadas producirán un error en tiempo de compilación o una excepción en tiempo de ejecución (en el caso de usar características dinámicas o `object`).

Los lenguajes .NET están orientados a objetos, con las jerarquías de clases base y derivadas. El runtime de .NET solo permitirá llamadas y conversaciones de objetos que se alineen con la jerarquía de objetos. Recuerde que cada tipo definido en cualquier lenguaje .NET se deriva del tipo `object` base.

```cs
Dog dog = Dog.AdoptDog(); // Returns a Dog type
Pet pet = (Pet)dog; // Dog derives from Pet
pet.ActCute();
Car car = (Car)dog; // will throw - no relationship between Car and Dog
object temp = (object)dog; // legal - a Dog is an object
car = (Car)temp; // will throw - the runtime isn't fooled
car.Accelerate() // the dog won't like this, nor will the program get this far

```

La seguridad de tipos también se usa para ayudar a aplicar la encapsulación a través de la garantía de la fidelidad de las palabras clave del descriptor de acceso. Las palabras clave del descriptor de acceso son artefactos que controlan el acceso a los miembros de un tipo determinado a través de otro código. Normalmente se usan para distintos tipos de datos dentro de un tipo, que se usan para administrar su comportamiento.

```cs
Dog dog = Dog._nextDogToBeAdopted; // will throw - this is a private field

```

Algunos lenguajes .NET admiten **inferencia de tipos**. La inferencia de tipos significa que el compilador deducirá el tipo de expresión en el lado izquierdo a partir de la expresión en el lado derecho. Esto no significa que la seguridad de tipos se divida o evite. El tipo resultante **tiene** un tipo seguro con todo lo que ello implica. Reescribamos las dos primeras líneas del ejemplo anterior para introducir la inferencia de tipos. Puede observar que el resto del ejemplo es completamente el mismo.

```cs
  var dog = Dog.AdoptDog();
  var pet = (Pet)dog;
  pet.ActCute();
  Car car = (Car)dog; // will throw - no relationship between Car and Dog
  object temp = (object)dog; // legal - a Dog is an object
  car = (Car)temp; // will throw - the runtime isn't fooled
  car.Accelerate() // the dog won't like this, nor will the program get this far

```

### <a name="delegates-and-lambdas"></a>Delegados y expresiones lambda

Los delegados son como los punteros de función de C++, con la gran diferencia de que tienen seguridad de tipos. Son un tipo de método sin conexión en el sistema de tipos de CLR. Los métodos regulares están conectados a una clase y solo se pueden llamar a través de convenciones de llamadas estáticas o de instancias.

Los delegados se usan en varias API y lugares en el mundo .NET, especialmente a través de expresiones lambda, que son los pilares de LINQ.

Obtenga más información al respecto en el documento [Delegados y expresiones lambda](delegates-lambdas.md).

### <a name="generic-types-generics"></a>Tipos genéricos (genéricos)

Los tipos genéricos, también denominados comúnmente "genéricos", son una característica que se agregó en .NET Framework 2.0. En resumen, los genéricos permiten al programador introducir un "parámetro de tipo" al diseñar sus clases, que permite al código de cliente (los usuarios del tipo) especificar el tipo exacto que se debe usar en lugar del parámetro de tipo.

Los genéricos se agregaron para ayudar a los programadores a implementar estructuras de datos genéricos. Antes de que se agregasen, por ejemplo, para que un tipo _List_ fuese genérico, tendría que trabajar con elementos que fuesen de tipo _object_. Esto tendría diferentes problemas de rendimiento, así como semánticos, además de los posibles errores sutiles de tiempo de ejecución. Los más destacados de este último se producirían cuando una estructura de datos contiene, por ejemplo, enteros y cadenas, y se inicia _InvalidCastException_ al trabajar con los miembros de la lista.

El siguiente ejemplo muestra un ejecución de programa básico mediante una instancia de tipos @System.Collections.Generic.List%601.

```cs
using System;
using System.Collections.Generic;

namespace GenericsSampleShort {
    public static void Main(string[] args){
        // List<string> is the client way of specifying the actual type for the type parameter T
        List<string> listOfStrings = new List<string> { "First", "Second", "Third" };

        // listOfStrings can accept only strings, both on read and write.
        listOfStrings.Add("Fourth");

        // Below will throw a compile-time error, since the type parameter
        // specifies this list as containing only strings.
        listOfStrings.Add(1);

    }
}

```

Para obtener más información, consulte el artículo [Información general (genéricos) de tipos genéricos](generics.md).

### <a name="async-programming"></a>Programación asincrónica

La programación asincrónica es un concepto de primera clase en .NET, con compatibilidad asincrónica en el tiempo de ejecución, las bibliotecas de Framework y las construcciones de lenguaje .NET. Internamente, se basa en objetos (como `Task`) que sacan partido del sistema operativo para realizar trabajos dependientes de E/s de la forma más eficaz posible.

Para obtener más información acerca de la programación asincrónica en .NET, comience con la [Información general sobre la asincronía](async.md).

### <a name="language-integrated-query-linq"></a>Language-Integrated Query (LINQ)

LINQ es un conjunto eficaz de características para C# y VB que permiten escribir código simple y declarativo para operar en los datos. Los datos pueden estar en muchos formatos (como objetos en memoria, en una base de datos SQL o un documento XML), pero el código LINQ que escriba normalmente no aparecerá de forma diferente para cada origen de datos.

Para obtener más información y ver algunos ejemplos, consulte [LINQ (Language-Integrated Query)](using-linq.md).

### <a name="native-interoperability"></a>Interoperabilidad nativa

Cada sistema operativo actualmente en uso proporciona mucha compatibilidad de plataformas para varias tareas de programación. .NET proporciona varias maneras de aprovechar dichas API. En conjunto, esta compatibilidad se denomina "interoperabilidad nativa" y en esta sección explicaremos cómo tener acceso a las API nativas desde código administrado . NET.

La principal manera de crear interoperabilidad nativa es a través de "invocación de plataforma" o P/Invoke para abreviar. Esta compatibilidad con .NET Core está disponible en plataformas Windows y Linux. Otra manera de crear interoperabilidad nativa exclusiva de Windows se conoce como "Interoperabilidad COM", que se usa para trabajar con [componentes COM](https://msdn.microsoft.com/library/bwa2bx93.aspx) en código administrado. Se basa en la infraestructura de P/Invoke, pero funciona de forma ligeramente diferente.

La mayoría de la compatibilidad de interoperabilidad de Mono (y, por tanto, de Xamarin) para Java y Objective-C se compila de forma similar, es decir, usan los mismos principios.

Obtenga más información al respecto en el documento [Interoperabilidad nativa](native-interop.md).

### <a name="unsafe-code"></a>Código no seguro

El CLR permite la capacidad de tener acceso a la memoria nativa y realizar aritmética de punteros a través de código `unsafe`. Estas operaciones son necesarias para determinados algoritmos y para la interoperabilidad del sistema. Aunque es eficaz, se desaconseja el uso de código no seguro a menos que sea necesario para la interoperabilidad con las API del sistema o para implementar el algoritmo más eficaz. Es posible que el código no seguro no se ejecute del mismo modo en entornos diferentes y que también pierda las ventajas de un recolector de elementos no utilizados y de la seguridad de tipos. Se recomienda limitar y centralizar el código no seguro lo máximo posible, y probar el código a conciencia.

El método `ToString()` de la [clase StringBuilder](https://github.com/dotnet/coreclr/blob/master/src/mscorlib/src/System/Text/StringBuilder.cs#L327) ilustra cómo el uso del código `unsafe` puede implementar de forma eficaz un algoritmo al moverse por fragmentos de memoria directamente:

```cs
public override String ToString() {
          Contract.Ensures(Contract.Result<String>() != null);

          VerifyClassInvariant();

          if (Length == 0)
              return String.Empty;

          string ret = string.FastAllocateString(Length);
          StringBuilder chunk = this;
          unsafe {
              fixed (char* destinationPtr = ret)
              {
                  do
                  {
                      if (chunk.m_ChunkLength > 0)
                      {
                          // Copy these into local variables so that they are stable even in the presence of ----s (hackers might do this)
                          char[] sourceArray = chunk.m_ChunkChars;
                          int chunkOffset = chunk.m_ChunkOffset;
                          int chunkLength = chunk.m_ChunkLength;

                          // Check that we will not overrun our boundaries.
                          if ((uint)(chunkLength + chunkOffset) <= ret.Length && (uint)chunkLength <= (uint)sourceArray.Length)
                          {
                              fixed (char* sourcePtr = sourceArray)
                                  string.wstrcpy(destinationPtr + chunkOffset, sourcePtr, chunkLength);
                          }
                          else
                          {
                              throw new ArgumentOutOfRangeException("chunkLength", Environment.GetResourceString("ArgumentOutOfRange_Index"));
                          }
                      }
                      chunk = chunk.m_ChunkPrevious;
                  } while (chunk != null);
              }
          }
          return ret;
      }

```

## <a name="notes"></a>Notas

El término "runtime de .NET" se usa en todo el documento para abarcar las múltiples implementaciones de. NET, como CLR, Mono, IL2CPP y otros. Los nombres más específicos se usan solo si es necesario.

Este documento no pretende ser de naturaleza histórica, sino describir la plataforma .NET tal y como es ahora. No es importante si una característica de .NET ha estado disponible siempre o se ha introducido recientemente, solo cabe destacar que es lo suficientemente importante para resaltarla y analizarla.



<!--HONumber=Nov16_HO1-->


