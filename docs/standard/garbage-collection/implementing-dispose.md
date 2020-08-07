---
title: Implementación de un método Dispose
description: En este artículo, aprenderá a implementar el método Dispose, que libera los recursos no administrados que usa su código en .NET.
ms.date: 05/27/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
ms.openlocfilehash: 4f0cc9b88947d60638057ca83adb7f2e141c5d14
ms.sourcegitcommit: 7499bdb428d63ed0e19e97f54d3d576c41598659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "87455738"
---
# <a name="implement-a-dispose-method"></a>Implementación de un método Dispose

La implementación del método <xref:System.IDisposable.Dispose%2A> sirve principalmente para publicar recursos no administrados. Al trabajar con miembros de instancia que son implementaciones de <xref:System.IDisposable>, es habitual hacer llamadas de <xref:System.IDisposable.Dispose%2A> en cascada. Hay otras razones para implementar <xref:System.IDisposable.Dispose%2A>, por ejemplo, para liberar memoria que se ha asignado, quitar un elemento que se ha agregado a una colección o señalar la liberación de un bloqueo adquirido.

El [recolector de elementos no utilizados de .NET](index.md) no asigna ni libera memoria no administrada. El modelo para desechar un objeto, lo que se conoce como patrón de Dispose, sirve para imponer orden sobre la duración de un objeto. El patrón de Dispose se utiliza solo con los objetos que implementan la inferfaz <xref:System.IDisposable>, y es común al interactuar con identificadores de archivo y de canalización, identificadores de registro, identificadores de espera o punteros a bloques de memoria sin administrar. Esto se debe a que el recolector de elementos no utilizados no puede reclamar objetos no administrados.

Para asegurarse de que los recursos se limpien siempre correctamente, un método <xref:System.IDisposable.Dispose%2A> debe ser idempotente, de manera que sea invocable varias veces sin que se produzca una excepción. Además, las siguientes invocaciones de <xref:System.IDisposable.Dispose%2A> no deben hacer nada.

El ejemplo de código proporcionado para el método <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> muestra cómo la recolección de elementos no utilizados puede hacer que un finalizador se ejecute mientras una referencia no administrada al objeto o a sus miembros todavía está en uso. Usar <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> tiene sentido para hacer que el objeto no sea válido para la recolección de elementos no utilizados desde el principio de la rutina actual y hasta el momento en que se llamó a este método.

## <a name="safe-handles"></a>Identificadores seguros

La escritura de código para el finalizador de un objeto es una tarea compleja que puede producir problemas si no se realiza correctamente. Por tanto, se recomienda construir objetos <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> en lugar de implementar un finalizador.

Un <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> es un tipo administrado abstracto que contiene un <xref:System.IntPtr?displayProperty=nameWithType> que identifica un recurso no administrado. En Windows, puede identificar un identificador y, en UNIX, un descriptor de archivo. Proporciona toda la lógica necesaria para asegurarse de que este recurso se libera una vez y solo una vez, cuando se elimina `SafeHandle` o cuando se quitan todas las referencias a `SafeHandle` y se finaliza la instancia de `SafeHandle`.

<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> es una clase base abstracta. Las clases derivadas proporcionan instancias específicas para diferentes tipos de identificadores. Estas clases derivadas validan qué valores de <xref:System.IntPtr?displayProperty=nameWithType> se consideran no válidos y cómo liberar realmente el identificador. Por ejemplo, <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> se deriva de `SafeHandle` para ajustar `IntPtrs` que identifican los identificadores o descriptores de archivos abiertos e invalida su método <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle?displayProperty=nameWithType> para cerrarlo (a través de la función `close` en Unix o la función `CloseHandle` en Windows). La mayoría de las API de las bibliotecas de .NET que crean un recurso no administrado lo encapsularán en `SafeHandle` y devolverán ese `SafeHandle` según sea necesario, en lugar de volver a entregar el puntero básico. En situaciones en las que interactúe con un componente no administrado y obtenga `IntPtr` para un recurso no administrado, puede crear su propio tipo de `SafeHandle` para ajustarlo. Como resultado, algunos tipos no `SafeHandle` necesitan implementar finalizadores; la mayoría de las implementaciones de patrón descartable solo terminan con el ajuste de otros recursos administrados, algunos de los cuales pueden ser `SafeHandle`.

Las clases derivadas siguientes en el espacio de nombres <xref:Microsoft.Win32.SafeHandles> proporcionan controladores seguros:

- La clase <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> y <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> para archivos, archivos asignados en memoria y canalizaciones.
- La clase <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> para vistas de memoria.
- Las clases <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> y <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> para construcciones criptográficas.
- La clase <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> para claves del Registro.
- La clase <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> para identificadores de espera.

## <a name="dispose-and-disposebool"></a>Dispose() y Dispose (booleano)

La interfaz <xref:System.IDisposable> requiere la implementación de un único método sin parámetros, <xref:System.IDisposable.Dispose%2A>. Además, cualquier clase no sellada debe tener un método de sobrecarga `Dispose(bool)` adicional que se va a implementar:

- Una implementación `public` que no sea virtual ( `NonInheritable` en Visual Basic) de tipo <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> que no tenga parámetros.

- Un método `protected virtual` (`Overridable` en Visual Basic) de tipo `Dispose` cuya signatura sea:

  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]

  > [!IMPORTANT]
  > El parámetro `disposing` debe ser `false` cuando se llama desde un finalizador y `true` cuando se llama desde el método <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>. En otras palabras, es `true` cuando se llama de forma determinista y `false` cuando se llama de forma no determinista.

### <a name="the-dispose-method"></a>Método Dispose()

Dado que un consumidor del tipo llama a este método`Dispose` `public`, no virtual (`NonInheritable` en Visual Basic) y sin parámetros, su propósito consiste en liberar recursos no administrados, realizar limpiezas generales e indicar que el finalizador, si existe, no tiene que ejecutarse. La liberación de la memoria real asociada a un objeto administrado es siempre una tarea que corresponde al [recolector de elementos no utilizados](index.md). Debido a esto, se realiza una implementación estándar:

[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]

El método `Dispose` limpia todos los objetos, por lo que el recolector de elementos no utilizados no necesita llamar a la invalidación <xref:System.Object.Finalize%2A?displayProperty=nameWithType> de los objetos. Por consiguiente, la llamada al método <xref:System.GC.SuppressFinalize%2A> evita que el recolector de elementos no utilizados ejecute el finalizador. Si el tipo no tiene ningún finalizador, la llamada a <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> no tiene ningún efecto. Tenga en cuenta que la limpieza real se realiza mediante la sobrecarga del método `Dispose(bool)`.

### <a name="the-disposebool-method-overload"></a>Sobrecarga del método Dispose (bool)

En la sobrecarga, el parámetro `disposing` es un valor <xref:System.Boolean> que indica si la llamada al método procede de un método <xref:System.IDisposable.Dispose%2A> (su valor es `true`) o de un finalizador (su valor es `false`).

El cuerpo del método consta de dos bloques de código:

- Un bloque que libera los recursos no administrados. Este bloque se ejecuta independientemente del valor del parámetro `disposing`.
- Un bloque condicional que libera los recursos administrados. Este bloque se ejecuta si el valor de `disposing` es `true`. Estos son algunos de los recursos administrados que se liberan:

  - **Objetos administrados que implementan <xref:System.IDisposable>.** El bloque condicional se puede utilizar para llamar a la implementación <xref:System.IDisposable.Dispose%2A> (eliminación en cascada). Si ha utilizado una clase derivada de <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> para ajustar el recurso no administrado, debe llamar aquí a la implementación <xref:System.Runtime.InteropServices.SafeHandle.Dispose?displayProperty=nameWithType>.

  - **Objetos administrados que consumen gran cantidad de memoria o recursos insuficientes.** Asigne referencias de objetos administrados grandes a `null` para aumentar la probabilidad de que no se pueda acceder a ellos. De este modo, se liberan más rápido que si se recuperaran de forma no determinista.

Si la llamada al método procede de un finalizador, solo se debe ejecutar el código que libera los recursos no administrados. El implementador es responsable de garantizar que la ruta de acceso falsa no interactúe con los objetos administrados que se pueden haber reclamado. Esto es importante porque el orden en el que el recolector de elementos no utilizados destruye los objetos administrados durante la finalización no es determinista.

## <a name="cascade-dispose-calls"></a>Llamadas de eliminación en cascada

Si la clase posee un campo o una propiedad y su tipo implementa <xref:System.IDisposable>, la propia clase contenedora también debe implementar <xref:System.IDisposable>. Una clase que crea instancias de una implementación de <xref:System.IDisposable> y la almacena como un miembro de instancia, también es responsable de su limpieza. Esto ayuda a garantizar que los tipos descartables a los que se hace referencia tienen la oportunidad de realizar una limpieza determinista mediante el método <xref:System.IDisposable.Dispose%2A>. En este ejemplo, la clase es `sealed` (o `NotInheritable` en Visual Basic).

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/disposable1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/disposable1.vb#1)]

## <a name="implement-the-dispose-pattern"></a>Implementación del patrón Dispose

Todas las clases no selladas o (clases de Visual Basic no modificadas como `NotInheritable`) deben considerarse una clase base potencial, ya que se podrían heredar. Cuando se implementa el patrón de Dispose para cualquier clase base potencial, debe proporcionar lo siguiente:

- Una implementación <xref:System.IDisposable.Dispose%2A> que llame al método `Dispose(bool)`.
- Un método `Dispose(bool)` que realiza la tarea real de limpieza.
- Una clase derivada de <xref:System.Runtime.InteropServices.SafeHandle> que contiene el recurso no administrado (recomendado), o una invalidación del método <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. La clase <xref:System.Runtime.InteropServices.SafeHandle> proporciona un finalizador, por lo que no tiene que escribir uno personalmente.

> [!IMPORTANT]
> Es posible que una clase base solo haga referencia a objetos administrados e implemente el patrón de Dispose. En estos casos, un finalizador no es necesario. Un finalizador solo es necesario si se hace referencia directamente a los recursos no administrados.

A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase base que utiliza un controlador seguro.

[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]

> [!NOTE]
> El ejemplo anterior utiliza un objeto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> para ilustrar el patrón; cualquier objeto derivado de <xref:System.Runtime.InteropServices.SafeHandle> podría usarse en su lugar. Tenga en cuenta que el ejemplo no crea una instancia de su objeto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> correctamente.

A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase base que invalide a <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.

[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]

> [!TIP]
> En C#, se crea un [finalizador](../../csharp/programming-guide/classes-and-structs/destructors.md) invalidando <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. En Visual Basic, esto se hace con `Protected Overrides Sub Finalize()`.

## <a name="implement-the-dispose-pattern-for-a-derived-class"></a>Implementación del patrón de Dispose para una clase derivada

Una clase derivada de una clase que implemente la interfaz <xref:System.IDisposable> no debe implementar <xref:System.IDisposable>, porque la implementación de la clase base de <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> la heredan sus clases derivadas. En su lugar, para limpiar una clase derivada, debe proporcionar los siguientes elementos:

- Un método `protected override void Dispose(bool)` que invalide el método de la clase base y realice la limpieza real de la clase derivada. Este método también debe llamar al método `base.Dispose(bool)` (`MyBase.Dispose(bool)` en Visual Basic) de la clase base y pasar su estado disposing para el argumento.
- Una clase derivada de <xref:System.Runtime.InteropServices.SafeHandle> que contiene el recurso no administrado (recomendado), o una invalidación del método <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. La clase <xref:System.Runtime.InteropServices.SafeHandle> proporciona un finalizador que evita que tenga que codificar uno. Si proporciona un finalizador, debe llamar a la sobrecarga de `Dispose(bool)` con un argumento `disposing` que sea `false`.

A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase derivada que utiliza un controlador seguro:

[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]

> [!NOTE]
> El ejemplo anterior utiliza un objeto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> para ilustrar el patrón; cualquier objeto derivado de <xref:System.Runtime.InteropServices.SafeHandle> podría usarse en su lugar. Tenga en cuenta que el ejemplo no crea una instancia de su objeto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> correctamente.

A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase derivada que invalide a <xref:System.Object.Finalize%2A?displayProperty=nameWithType>:

[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]

## <a name="implement-the-dispose-pattern-with-safe-handles"></a>Implementación del patrón de Dispose con identificadores seguros

En el ejemplo siguiente se muestra el patrón de Dispose para una clase base, `DisposableStreamResource`, que utiliza un controlador seguro para encapsular los recursos no administrados. Define una clase `DisposableStreamResource` que utiliza un <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> para incluir un objeto <xref:System.IO.Stream> que representa un archivo abierto. La clase también incluye una propiedad única, `Size`, que devuelve el número total de bytes de la secuencia de archivos.

[!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
[!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]

## <a name="implement-the-dispose-pattern-for-a-derived-class-with-safe-handles"></a>Implementación del patrón de Dispose para una clase derivada con identificadores seguros

En el ejemplo siguiente se muestra el patrón de Dispose para una clase derivada, `DisposableStreamResource2`, que se hereda de la clase `DisposableStreamResource` mostrada en el ejemplo anterior. La clase agrega un método adicional, `WriteFileInfo`, y utiliza un objeto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> para incluir el identificador del archivo editable.

[!code-csharp[Conceptual.Disposable#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/derived1.cs#10)]
[!code-vb[Conceptual.Disposable#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/derived1.vb#10)]

## <a name="see-also"></a>Vea también

- <xref:System.GC.SuppressFinalize%2A>
- <xref:System.IDisposable>
- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>
- <xref:Microsoft.Win32.SafeHandles>
- <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>
- [Definición y uso de clases y estructuras (C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli)
