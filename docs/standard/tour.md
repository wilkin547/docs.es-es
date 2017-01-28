---
title: Paseo por .NET
description: "Una visita guiada a través de algunas de las características más importantes de la plataforma. NET."
keywords: ".NET, .NET Core, Paseo, Lenguajes de programación, Unsafe, Administración de memoria, Seguridad de tipos, Asincrónico"
author: cartermp
manager: wpickett
ms.author: phcart
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bbfe6465-329d-4982-869d-472e7ef85d93
translationtype: Human Translation
ms.sourcegitcommit: 2c57b5cebd63b1d94b127cd269e3b319fb24dd97
ms.openlocfilehash: 02e2fa22e36fd2f6618527ad3c89cbbd8587dfe2

---

# <a name="tour-of-net"></a>Paseo por .NET

.NET es una plataforma de desarrollo de uso general.  Tiene varias características importantes, como varios lenguajes de programación, modelos de programación asincrónica y simultánea e interoperabilidad nativa que permite una amplia variedad de escenarios en diversas plataformas.

Este artículo ofrece un paseo guiado por algunas de las características clave de la plataforma. NET.

Consulte [Componentes de la arquitectura .NET](components.md) para más información sobre cada una de las "piezas" de arquitectura .NET y para qué se usan.

## <a name="how-to-run-the-code-samples"></a>Ejecución de ejemplos de código

Para más información sobre cómo configurar un entorno de desarrollo para ejecutar los ejemplos de código, consulte [Introducción](getting-started.md).  Puede copiar y pegar ejemplos de código de esta página para ejecutarlos en su entorno. 

> [!NOTE]
En el futuro, este sitio de documentación tendrá la posibilidad de ejecutar estos ejemplos de código en el explorador.

## <a name="programming-languages"></a>Lenguajes de programación

.NET admite varios lenguajes de programación.  Los entornos de tiempo de ejecución .NET implementan [Common Language Infrastructure (CLI)](https://www.visualstudio.com/en-us/mt639507), que, entre otras cosas, especifica un entorno de tiempo de ejecución independiente del lenguaje y la interoperabilidad del lenguaje.  Esto significa que puede elegir cualquier lenguaje .NET para crear aplicaciones y servicios en. NET.

Microsoft desarrolla activamente y admite tres lenguajes. NET: C#, F # y Visual Basic. NET. 

* C# es simple, eficaz, incluye seguridad de tipos y está orientado a objetos, al mismo tiempo que mantiene la expresividad y elegancia de los lenguajes de estilo C. Cualquiera que esté familiarizado con C y lenguajes similares, encontrará pocos problemas para adaptarse a C#.  Consulte la [Guía de C#](../csharp/index.md) para más información sobre C#.

* F # es un lenguaje de programación multiplataforma, principalmente funcional, que también admite la programación tradicional imperativa y orientada en objetos.  Consulte la [Guía de F #](../fsharp/index.md) para más información sobre F #.

* Visual Basic es un lenguaje fácil de aprender que puede usar para crear una gran variedad de aplicaciones que se ejecutan en .NET Framework.

## <a name="automatic-memory-management"></a>Administración de memoria automática

.NET utiliza [recolección de elementos no utilizados](garbagecollection/index.md) para proporcionar administración automática de memoria para los programas.  El GC opera con un enfoque diferido para la administración de memoria y prefiere el rendimiento de la aplicación sobre la recolección inmediata de la memoria.  Para más información sobre GC de .NET, consulte [Fundamentals of garbage collection (GC)](garbagecollection/fundamentals.md) (Fundamentos de la recolección de elementos no utilizados [GC]).

Las dos líneas siguientes asignan memoria:

[!code-csharp[MemoryManagement](../../samples/csharp/snippets/tour/MemoryManagement.csx#L1-L2)]

No hay ninguna palabra clave análoga para anular la asignación de memoria, ya que la anulación de la asignación se realiza automáticamente cuando el recolector de elementos no utilizados reclama la memoria a través de su ejecución programada.

Los tipos dentro de un ámbito dado quedan normalmente fuera de ámbito cuando se completa un método, momento en el cual pueden recopilarse. Sin embargo, puede indicar al GC que un objeto determinado esté fuera de ámbito en cuanto el método se cierre mediante la instrucción `using`.

[!code-csharp[MemoryManagement](../../samples/csharp/snippets/tour/MemoryManagement.csx#L6-L9)]

Una vez que se complete el bloque de `using`, el GC sabrá que el objeto `stream` en el ejemplo anterior ya se puede recopilar y reclamar su memoria.

Reglas para esto tienen una semántica ligeramente diferente en F#.  Para más información sobre la administración de recursos en F #, consulte el artículo sobre la [administración de recursos y la palabra clave `use` ](../fsharp/language-reference/resource-management-the-use-keyword.md).

La protección de la memoria es una de las características menos obvias, pero con un alcance bastante grande, que es posible gracias a un recolector de elementos no utilizados. El valor invariable de protección de la memoria es muy simple: un programa tiene protección de la memoria si solo tiene acceso a la memoria que se ha asignado (y no liberado). Los punteros pendientes siempre suponen errores y localizarlos suele ser bastante difícil.

El runtime de .NET proporciona servicios adicionales para completar la promesa de protección de la memoria, que no ofrece de forma natural un GC. Garantiza que los programas no indicen el final de una matriz ni tengan acceso a un campo fantasma al final de un objeto.

En el ejemplo siguiente, se iniciará una excepción como resultado de la protección de la memoria.

[!code-csharp[MemoryManagement](../../samples/csharp/snippets/tour/MemoryManagement.csx#L11-L12)]

## <a name="type-safety"></a>Seguridad de tipos

Los objetos se asignan en términos de tipos. Las únicas operaciones permitidas para un objeto determinado, y la memoria que consume, son los de su tipo. Un tipo `Dog` puede tener métodos `Jump` y `WagTail`, pero no es probable que tenga un método `SumTotal`. Un programa solo puede llamar a los métodos declarados de un tipo determinado. Todas las demás llamadas producirán un error en tiempo de compilación o una excepción en tiempo de ejecución (en el caso de usar características dinámicas o `object`).

Los lenguajes .NET están orientados a objetos, con las jerarquías de clases base y derivadas. El runtime de .NET solo permitirá llamadas y conversaciones de objetos que se alineen con la jerarquía de objetos. Recuerde que cada tipo definido en cualquier lenguaje .NET se deriva del tipo `object` base.

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L18-L23)]

La seguridad de tipos también se usa para ayudar a aplicar la encapsulación a través de la garantía de la fidelidad de las palabras clave del descriptor de acceso. Las palabras clave del descriptor de acceso son artefactos que controlan el acceso a los miembros de un tipo determinado a través de otro código. Normalmente se usan para distintos tipos de datos dentro de un tipo, que se usan para administrar su comportamiento.

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L3-L3)]

C#, Visual Basic y F# admiten **inferencia de tipos** local. La inferencia de tipos significa que el compilador deducirá el tipo de expresión en el lado izquierdo a partir de la expresión en el lado derecho. Esto no significa que la seguridad de tipos se divida o evite. El tipo resultante **tiene** un tipo seguro con todo lo que ello implica. Reescribamos las dos primeras líneas del ejemplo anterior para introducir la inferencia de tipos. Observe que el resto del ejemplo es completamente lo mismo.

[!code-csharp[TypeSafety](../../samples/csharp/snippets/tour/TypeSafety.csx#L28-L34)]

F# tiene incluso más funcionalidades de inferencia de tipos que la inferencia de tipos method-local encontrada en C# y Visual Basic.  Para más información, consulte [Type Inference](../fsharp/language-reference/type-inference.md) (Inferencia de tipos).

## <a name="delegates-and-lambdas"></a>Delegados y expresiones lambda

Los delegados son como los punteros de función de C++, con la gran diferencia de que tienen seguridad de tipos. Son un tipo de método sin conexión en el sistema de tipos de CLR. Los métodos regulares están conectados a una clase y solo se pueden llamar a través de convenciones de llamadas estáticas o de instancias.

Los delegados se usan en varias API y lugares en el mundo .NET, especialmente a través de expresiones lambda, que son los pilares de LINQ.

Obtenga más información al respecto en el documento [Delegados y expresiones lambda](delegates-lambdas.md).

## <a name="generics"></a>Genéricos

Los genéricos son una característica que se agregó en .NET Framework 2.0. En resumen, los genéricos permiten al programador introducir un "parámetro de tipo" al diseñar sus clases, que permite al código de cliente (los usuarios del tipo) especificar el tipo exacto que se debe usar en lugar del parámetro de tipo.

Los genéricos se agregaron para ayudar a los programadores a implementar estructuras de datos genéricos. Antes de su llegada, para que un tipo `List` fuese genérico, por ejemplo, habría que trabajar con elementos que fuesen de tipo `object`. Esto tendría diferentes problemas de rendimiento, así como semánticos, además de los posibles errores sutiles de tiempo de ejecución. Lo más destacado de esto último se produciría cuando una estructura de datos contiene, por ejemplo, enteros y cadenas, y se inicia la excepción `InvalidCastException` al trabajar con los miembros de la lista.

El siguiente ejemplo muestra un ejecución de programa básico mediante una instancia de tipos @System.Collections.Generic.List%601.

[!code-csharp[GenericsShort](../../samples/csharp/snippets/tour/GenericsShort.csx)]

Para obtener más información, consulte el artículo [Información general (genéricos) de tipos genéricos](generics.md).

## <a name="async-programming"></a>Programación asincrónica

La programación asincrónica es un concepto de primera clase en .NET, con compatibilidad asincrónica en el tiempo de ejecución, las bibliotecas de Framework y las construcciones de lenguaje .NET. Internamente, se basa en objetos (como `Task`) que sacan partido del sistema operativo para realizar trabajos dependientes de E/s de la forma más eficaz posible.

Para obtener más información acerca de la programación asincrónica en .NET, comience con la [Información general sobre la asincronía](async.md).

## <a name="language-integrated-query-linq"></a>Language-Integrated Query (LINQ)

LINQ es un conjunto eficaz de características para C# y VB que permiten escribir código simple y declarativo para operar en los datos. Los datos pueden estar en muchos formatos (como objetos en memoria, en una base de datos SQL o un documento XML), pero el código LINQ que escriba normalmente no aparecerá de forma diferente para cada origen de datos.

Para obtener más información y ver algunos ejemplos, consulte [LINQ (Language-Integrated Query)](using-linq.md).

## <a name="native-interoperability"></a>Interoperabilidad nativa

Cada sistema operativo actualmente en uso proporciona mucha compatibilidad de plataformas para varias tareas de programación. .NET proporciona varias maneras de aprovechar dichas API. En conjunto, esta compatibilidad se denomina "interoperabilidad nativa" y en esta sección explicaremos cómo tener acceso a las API nativas desde código administrado . NET.

La principal manera de crear interoperabilidad nativa es a través de "invocación de plataforma" o P/Invoke para abreviar. Esta compatibilidad con .NET Core está disponible en plataformas Windows y Linux. Otra manera de crear interoperabilidad nativa exclusiva de Windows se conoce como "Interoperabilidad COM", que se usa para trabajar con [componentes COM](https://msdn.microsoft.com/library/bwa2bx93.aspx) en código administrado. Se basa en la infraestructura de P/Invoke, pero funciona de forma ligeramente diferente.

La mayoría de la compatibilidad de interoperabilidad de Mono (y, por tanto, de Xamarin) para Java y Objective-C se compila de forma similar, es decir, usan los mismos principios.

Obtenga más información al respecto en el documento [Interoperabilidad nativa](native-interop.md).

## <a name="unsafe-code"></a>Código no seguro

El CLR permite la capacidad de tener acceso a la memoria nativa y realizar aritmética de punteros a través de código `unsafe`. Estas operaciones son necesarias para determinados algoritmos y para la interoperabilidad del sistema. Aunque es eficaz, se desaconseja el uso de código no seguro a menos que sea necesario para la interoperabilidad con las API del sistema o para implementar el algoritmo más eficaz. Es posible que el código no seguro no se ejecute del mismo modo en entornos diferentes y que también pierda las ventajas de un recolector de elementos no utilizados y de la seguridad de tipos. Se recomienda limitar y centralizar el código no seguro lo máximo posible, y probar el código a conciencia.

El ejemplo siguiente es una versión modificada del método `ToString()` desde la clase `StringBuilder`.  Ilustra cómo mediante el código `unsafe` se puede implementar de forma eficiente un algoritmo desplazándose por los fragmentos de memoria directamente:

[!code-csharp[Unsafe](../../samples/csharp/snippets/tour/Unsafe.csx)]

## <a name="next-steps"></a>Pasos siguientes

Si está interesado en un paseo por las características de C#, consulte [Paseo por C#](../csharp/tour-of-csharp/index.md).

Si está interesado en un paseo por las características de F #, consulte [Paseo por F #](../fsharp/tour.md).

Si desea empezar a escribir su propio código, consulte [Introducción](getting-started.md).

Para más información sobre los principales componentes de. NET, consulte [Componentes de la arquitectura .NET](components.md).


<!--HONumber=Nov16_HO3-->


