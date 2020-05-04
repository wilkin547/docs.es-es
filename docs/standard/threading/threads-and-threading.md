---
title: Subprocesos y subprocesamiento
ms.date: 11/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET]
- threading [.NET], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
ms.openlocfilehash: bac2a3ca3278b48b35d0372d52bcb79025ba1148
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739727"
---
# <a name="threads-and-threading"></a>Subprocesos y subprocesamiento

El multithreading le permite aumentar la capacidad de respuesta de su aplicación y, en el caso de que la aplicación se ejecute en un sistema con varios procesadores o núcleos, aumentar su rendimiento.

## <a name="processes-and-threads"></a>Procesos y subprocesos

Un *proceso* es un programa en ejecución. Un sistema operativo utiliza procesos para separar las aplicaciones que se están ejecutando. Un *subproceso* es la unidad básica a la que el sistema operativo asigna tiempo de procesador. Cada subproceso tiene una [prioridad de programación](scheduling-threads.md) y mantiene un conjunto de estructuras que el sistema usa para guardar el contexto del subproceso mientras la ejecución del subproceso está pausada. El contexto del subproceso incluye toda la información que el subproceso necesita para reanudar sin problemas la ejecución, incluido el conjunto de pila y registros de CPU del subproceso. Dentro de un proceso, se pueden ejecutar varios subprocesos. Todos los subprocesos de un proceso comparten su espacio de direcciones virtuales. Un subproceso puede ejecutar cualquier parte del código de programa, incluidas las partes que esté ejecutando otro subproceso.

> [!NOTE]
> .NET Framework proporciona una manera de aislar las aplicaciones dentro de un proceso mediante el uso de *dominios de aplicación*. Los dominios de aplicación no están disponibles en .NET Core. Para obtener más información, vea la sección [Dominios de aplicación y subprocesos](../../framework/app-domains/application-domains.md#application-domains-and-threads) del artículo [Dominios de aplicación](../../framework/app-domains/application-domains.md).

De forma predeterminada, un programa de .NET se inicia con un único subproceso, que se suele conocer como subproceso *principal*. Sin embargo, puede crear subprocesos adicionales para ejecutar código en paralelo o simultáneamente con el subproceso principal. Normalmente, estos subprocesos se denominan subprocesos de *trabajo*.

## <a name="when-to-use-multiple-threads"></a>Cuándo utilizar varios subprocesos

Utilice varios subprocesos para aumentar la capacidad de respuesta de la aplicación y aprovechar las ventajas de un sistema con varios procesadores o núcleos que le permita aumentar el rendimiento de la aplicación.

Le recomendamos que use una aplicación de escritorio en la que el subproceso principal sea responsable de los elementos de la interfaz de usuario e interactivo. Use subprocesos de trabajo para realizar operaciones complejas que ocuparían el subproceso principal e impedirían la interacción con la interfaz de usuario. También puede usar un subproceso dedicado para la comunicación mediante red o dispositivo, de modo que su capacidad de respuesta ante los mensajes y eventos entrantes sea mayor.

Si el programa realiza operaciones que pueden realizarse en paralelo, puede reducir el tiempo de ejecución total realizándolas en subprocesos separados y ejecutando el programa en un sistema con varios procesadores o núcleos. En un sistema de este tipo, el uso del mutithreading puede aumentar el rendimiento y la capacidad de respuesta.

## <a name="how-to-use-multithreading-in-net"></a>Cómo usar el multithreading en .NET

A partir de .NET Framework 4, el método recomendado para utilizar el multithreading es usar las bibliotecas [TPL](../parallel-programming/task-parallel-library-tpl.md) y [PLINQ](../parallel-programming/introduction-to-plinq.md). Para obtener más información, vea [Programación en paralelo](../parallel-programming/index.md).

Las bibliotecas TPL y PLINQ se basan en los subprocesos de <xref:System.Threading.ThreadPool>. La clase <xref:System.Threading.ThreadPool?displayProperty=nameWithType> proporciona una aplicación .NET con un grupo de subprocesos de trabajo. También puede usar grupos de subprocesos. Para obtener más información, vea [Grupo de subprocesos administrado](the-managed-thread-pool.md).

Por último, puede usar la clase <xref:System.Threading.Thread?displayProperty=nameWithType> que representa un subproceso administrado. Para obtener más información, vea [Uso de subprocesos y subprocesamiento](using-threads-and-threading.md).

Puede que se necesiten varios subprocesos para acceder a un recurso compartido. Para mantener el recurso en un estado no dañado y evitar las condiciones de carrera, debe sincronizar el acceso del subproceso a este. También puede optar por coordinar la interacción en varios subprocesos. .NET proporciona una variedad de tipos que puede usar para sincronizar el acceso a un recurso compartido o coordinar la interacción de subprocesos. Para obtener más información, vea [Información general sobre las primitivas de sincronización](overview-of-synchronization-primitives.md).

Controle las excepciones de los subprocesos. Las excepciones no controladas en los subprocesos suelen finalizar el proceso. Para más información, consulte [Excepciones en subprocesos administrados](exceptions-in-managed-threads.md).

## <a name="see-also"></a>Vea también

- [Objetos y características de subprocesos](threading-objects-and-features.md)
- [Procedimientos recomendados para el subprocesamiento administrado](managed-threading-best-practices.md)
- [Procesamiento paralelo, simultaneidad y programación asincrónica en .NET](../parallel-processing-and-concurrency.md)
- [Acerca de los procesos y los subprocesos](/windows/desktop/procthread/about-processes-and-threads)
