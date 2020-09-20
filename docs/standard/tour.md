---
title: Paseo por .NET
description: Un paseo guiado a través de algunas de las características más importantes de .NET.
author: cartermp
ms.author: wiwagn
ms.date: 05/22/2017
ms.technology: dotnet-standard
ms.assetid: bbfe6465-329d-4982-869d-472e7ef85d93
ms.openlocfilehash: a44c3692dc9ed9b3de37955191edfb279403f152
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "89516026"
---
# <a name="tour-of-net"></a>Paseo por .NET

.NET es una plataforma de desarrollo de uso general. Tiene varias características clave, como la compatibilidad con varios lenguajes de programación, modelos de programación asincrónica y simultánea e interoperabilidad nativa, que permiten una amplia variedad de escenarios en diversas plataformas.

En este artículo, se ofrece un paseo guiado por algunas de las características clave de .NET. Consulte el tema [Componentes de la arquitectura .NET](components.md) para obtener más información sobre las piezas de arquitectura de .NET y para qué se usan.

## <a name="how-to-run-the-code-samples"></a>Ejecución de ejemplos de código

Para obtener más información sobre cómo configurar un entorno de desarrollo para ejecutar los ejemplos de código, consulte el tema [Introducción](get-started.md). Copie y pegue los ejemplos de código de esta página en su entorno para ejecutarlos.

## <a name="programming-languages"></a>Lenguajes de programación

.NET admite varios lenguajes de programación. Las implementaciones de .NET implementan [Common Language Infrastructure (CLI)](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/), que, entre otras cosas, especifica un entorno de ejecución independiente del lenguaje y la interoperabilidad del lenguaje. Esto significa que elige cualquier lenguaje .NET para crear aplicaciones y servicios en .NET.

Microsoft desarrolla activamente y admite tres lenguajes .NET: C#, F# y Visual Basic.

* C# es simple, eficaz, incluye seguridad de tipos y está orientado a objetos, al mismo tiempo que mantiene la expresividad y elegancia de los lenguajes de estilo C. Cualquiera que esté familiarizado con C y lenguajes similares, encuentra pocos problemas para adaptarse a C#. Consulte la [Guía de C#](../csharp/index.yml) para más información sobre C#.

* F# es un lenguaje de programación multiplataforma, principalmente funcional, que también admite la programación tradicional imperativa y orientada en objetos. Consulte la [Guía de F#](../fsharp/index.yml) para más información sobre F#.

* Visual Basic es un lenguaje fácil de aprender que se usa para crear una gran variedad de aplicaciones que se ejecutan en .NET. Entré los lenguajes .NET, la sintaxis de Visual Basic es la más cercana al lenguaje humano normal, lo que a menudo facilita el trabajo a las personas sin experiencia en el desarrollo de software.

## <a name="automatic-memory-management"></a>Administración de memoria automática

.NET usa la [recolección de elementos no utilizados](garbage-collection/index.md) para proporcionar administración automática de memoria para los programas. La GC funciona con un enfoque diferido para la administración de memoria y prefiere el rendimiento de la aplicación sobre la recolección inmediata de la memoria. Para más información sobre GC de .NET, consulte [Fundamentos de la recolección de elementos no utilizados (GC)](garbage-collection/fundamentals.md).

Las dos líneas siguientes asignan memoria:

[!code-csharp[MemoryManagement](../../samples/snippets/csharp/snippets/tour/MemoryManagement.csx#L1-L2)]

No hay ninguna palabra clave análoga para anular la asignación de memoria, ya que la anulación de la asignación se realiza automáticamente cuando el recolector de elementos no utilizados reclama la memoria a través de su ejecución programada.

El recolector de elementos no utilizados es uno de los servicios que ayudan a garantizar la *protección de la memoria*. Un programa tiene protección de la memoria si tiene acceso solo a la memoria asignada. Por ejemplo, el entorno de ejecución garantiza que una aplicación no accede a memoria sin asignar más allá de los límites de una matriz.

En el ejemplo siguiente, el entorno de ejecución devuelve una excepción <xref:System.IndexOutOfRangeException> para activar la protección de la memoria:

[!code-csharp[MemoryManagement](../../samples/snippets/csharp/snippets/tour/MemoryManagement.csx#L4-L5)]

## <a name="working-with-unmanaged-resources"></a>Trabajar con recursos no administrados

Algunos objetos hacen referencia a *recursos no administrados*. Los recursos no administrados son recursos que el entorno de ejecución .NET no mantiene de forma automática. Por ejemplo, un identificador de archivo es un recurso no administrado. Un objeto <xref:System.IO.FileStream> es un objeto administrado, pero hace referencia a un identificador de archivo, que es uno no administrado. Cuando haya acabado de usar <xref:System.IO.FileStream>, deberá liberar el identificador de archivo.

En .NET, los objetos que hacen referencia a recursos no administrados implementan la interfaz de <xref:System.IDisposable>. Cuando haya acabado de usar el objeto, deberá llamar al método <xref:System.IDisposable.Dispose> del objeto, que es el responsable de liberar cualquier recurso no administrado. Los lenguajes .NET ofrecen una [`using` instrucción ](../csharp/language-reference/keywords/using.md) muy útil para esos objetos, como se muestra en el ejemplo siguiente:

[!code-csharp[UnmanagedResources](../../samples/snippets/csharp/snippets/tour/UnmanagedResources.csx#L1-L6)]

Cuando el bloque `using` se completa, el entorno de ejecución .NET llama automáticamente al método <xref:System.IDisposable.Dispose> del objeto `stream`, que libera el identificador de archivo. El entorno de ejecución también sigue el mismo procedimiento en caso de que una excepción provoque que el control abandone el bloque.

Para obtener más información, consulte los siguientes temas:

* Para C#, vea el tema [using (Instrucción, Referencia de C#)](../csharp/language-reference/keywords/using-statement.md).
* En F#, consulte [Administración de recursos: la palabra clave use](../fsharp/language-reference/resource-management-the-use-keyword.md).
* Para VB, vea el tema [Using (Instrucción, Visual Basic)](../visual-basic/language-reference/statements/using-statement.md).

## <a name="type-safety"></a>Seguridad de tipos

Un objeto es una instancia de un tipo específico. Las únicas operaciones permitidas para un objeto determinado son las de su tipo. Un tipo `Dog` puede tener métodos `Jump` y `WagTail`, pero no un método `SumTotal`. Un programa solo llama a los métodos que pertenecen a un tipo determinado. Todas las demás llamadas producirán un error en tiempo de compilación o una excepción en tiempo de ejecución (en el caso de usar características dinámicas u `object`).

Los lenguajes .NET están orientados a objetos, con las jerarquías de clases base y derivadas. El entorno de ejecución .NET solo permite llamadas y conversiones de objetos que se alineen con la jerarquía de objetos. Recuerde que cada tipo definido en cualquier lenguaje .NET se deriva del tipo <xref:System.Object> base.

[!code-csharp[TypeSafety](../../samples/snippets/csharp/snippets/tour/TypeSafety.csx#L19-L23)]

La seguridad de tipos también se usa para ayudar a aplicar la encapsulación a través de la garantía de la fidelidad de las palabras clave del descriptor de acceso. Las palabras clave del descriptor de acceso son artefactos que controlan el acceso a los miembros de un tipo determinado a través de otro código. Normalmente se usan para distintos tipos de datos dentro de un tipo, que se usan para administrar su comportamiento.

[!code-csharp[TypeSafety](../../samples/snippets/csharp/snippets/tour/TypeSafety.csx#L3-L3)]

C#, Visual Basic y F# admiten *inferencia de tipos* local. La inferencia de tipos significa que el compilador deduce el tipo de la expresión en el lado izquierdo a partir de la expresión en el lado derecho. Esto no significa que la seguridad de tipos se divida o evite. El tipo resultante tiene un tipo seguro con todo lo que ello implica. En el ejemplo anterior, se vuelve a escribir `dog` para introducir la inferencia de tipos, y el resto del ejemplo no se modifica:

[!code-csharp[TypeSafety](../../samples/snippets/csharp/snippets/tour/TypeSafety.csx#L28-L34)]

F# tiene incluso más funcionalidades de inferencia de tipos que la inferencia de tipos method-local encontrada en C# y Visual Basic. Para obtener más información, consulte [Inferencia de tipos](../fsharp/language-reference/type-inference.md).

## <a name="delegates-and-lambdas"></a>Delegados y expresiones lambda

Un delegado se representa mediante una firma de método. Cualquier método con esa firma puede asignarse al delegado y se ejecuta cuando se invoca el delegado.

Los delegados son como los punteros de función de C++, pero tienen seguridad de tipos. Son un tipo de método sin conexión en el sistema de tipos de CLR. Los métodos regulares están conectados a una clase y solo se pueden llamar a través de convenciones de llamadas estáticas o de instancias.

En .NET, los delegados se usan habitualmente en controladores de eventos, en la definición de operaciones asincrónicas y en las expresiones lambda, que son los pilares de LINQ. Obtenga más información en el tema [Delegados y expresiones lambda](delegates-lambdas.md).

## <a name="generics"></a>Genéricos

Los genéricos permiten al programador introducir un *parámetro de tipo* al diseñar sus clases, que permite al código de cliente (los usuarios del tipo) especificar el tipo exacto que se debe usar en lugar del parámetro de tipo.

Los genéricos se agregaron para ayudar a los programadores a implementar estructuras de datos genéricos. Antes de su llegada, para que un tipo como `List` fuera genérico, habría que trabajar con elementos que fueran de tipo `object`. Como consecuencia, había problemas de rendimiento y semántica, junto con posibles errores sutiles en tiempo de ejecución. Un error en tiempo de ejecución común es cuando una estructura de datos contiene, por ejemplo, enteros y cadenas, y se produce una excepción <xref:System.InvalidCastException> al procesar los miembros de la lista.

En el siguiente ejemplo, se muestra una ejecución básica de programa mediante una instancia de tipos <xref:System.Collections.Generic.List%601>:

[!code-csharp[GenericsShort](../../samples/snippets/csharp/snippets/tour/GenericsShort.csx)]

Para obtener más información, consulte el tema [Información general (genéricos) de tipos genéricos](generics.md).

## <a name="async-programming"></a>Programación asincrónica

La programación asincrónica es un concepto de primera clase en .NET, con compatibilidad asincrónica en el entorno de ejecución, las bibliotecas del marco y las construcciones de lenguaje .NET. Internamente, se basa en objetos (como `Task`) que sacan partido del sistema operativo para realizar trabajos dependientes de E/S de la forma más eficaz posible.

Para obtener más información sobre la programación asincrónica en .NET, comience con el tema [Async en profundidad](async.md).

## <a name="language-integrated-query-linq"></a>Language-Integrated Query (LINQ)

LINQ es un conjunto eficaz de características para C# y Visual Basic que permiten escribir código simple y declarativo para operar en los datos. Los datos pueden estar en muchos formatos (como objetos en memoria, una base de datos SQL o un documento XML), pero el código LINQ que escriba normalmente no es diferente según el origen de datos.

Para obtener más información y ver algunos ejemplos, consulte el artículo [Información general de LINQ (Language Integrated Query)](./linq/index.md).

## <a name="native-interoperability"></a>Interoperabilidad nativa

Cada sistema operativo incluye una interfaz de programación de aplicaciones (API) que proporciona servicios del sistema. .NET proporciona varias maneras de llamar a esas API.

La manera principal de crear interoperabilidad nativa es a través de la "invocación de plataforma" o P/Invoke para abreviar, que se admite en las plataformas Linux y Windows. Una manera de crear interoperabilidad nativa exclusiva de Windows se conoce como "Interoperabilidad COM", que se usa para trabajar con [componentes COM](/cpp/atl/introduction-to-com) en código administrado. Se basa en la infraestructura de P/Invoke, pero funciona de forma ligeramente diferente.

La mayoría de la compatibilidad de interoperabilidad de Mono (y, por tanto, de Xamarin) para Java y Objective-C se compila de forma similar, es decir, usan los mismos principios.

Para obtener más información sobre la interoperabilidad nativa, consulte el artículo [Interoperabilidad nativa](native-interop/index.md).

## <a name="unsafe-code"></a>Código no seguro

Según la compatibilidad con el lenguaje, CLR le permite tener acceso a memoria nativa y usar la aritmética de punteros a través de código `unsafe`. Estas operaciones son necesarias para determinados algoritmos y para la interoperabilidad del sistema. Aunque es eficaz, se desaconseja el uso de código no seguro a menos que sea necesario para la interoperabilidad con las API del sistema o para implementar el algoritmo más eficaz. Es posible que el código no seguro no se ejecute del mismo modo en entornos diferentes y que también pierda las ventajas de un recolector de elementos no utilizados y de la seguridad de tipos. Se recomienda limitar y centralizar el código no seguro lo máximo posible, y probar el código a conciencia.

El ejemplo siguiente es una versión modificada del método `ToString()` desde la clase `StringBuilder`. Ilustra cómo mediante el código `unsafe` se puede implementar de forma eficiente un algoritmo desplazándose por los fragmentos de memoria directamente:

[!code-csharp[Unsafe](../../samples/snippets/csharp/snippets/tour/Unsafe.csx)]

## <a name="next-steps"></a>Pasos siguientes

Si está interesado en un paseo por las características de C#, consulte [Paseo por C#](../csharp/tour-of-csharp/index.md).

Si está interesado en un paseo por las características de F#, consulte [Paseo por F#](../fsharp/tour.md).

Si quiere empezar a escribir su propio código, consulte [Introducción](get-started.md).

Para más información sobre los principales componentes de. NET, consulte [Componentes de la arquitectura .NET](components.md).
