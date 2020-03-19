---
title: Implementar un método Dispose
ms.date: 04/07/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
ms.openlocfilehash: f3d3269ccf56954f963762503d2bc1c53b9e6b83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78238993"
---
# <a name="implementing-a-dispose-method"></a>Implementar un método Dispose

El método <xref:System.IDisposable.Dispose%2A> se implementa para liberar recursos no administrados que la aplicación usa. El recolector de elementos no utilizados de .NET no asigna ni libera memoria no administrada.  
  
El modelo para desechar un objeto, lo que se conoce como [modelo de Dispose](implementing-dispose.md), sirve para imponer orden sobre la duración de un objeto. El patrón de Dispose se utiliza solo con los objetos que tienen acceso a recursos no administrados, como identificadores de archivo y de canalización, identificadores de registro, identificadores de espera o punteros a bloques de memoria sin administrar. Esto se debe a que el recolector de elementos no utilizados es muy eficaz a la hora de reclamar objetos administrados no usados, aunque no puede reclamar objetos no administrados.  
  
El patrón de Dispose tiene dos variaciones:  
  
- Incluir los recursos no administrados que utilice un tipo en un controlador seguro (es decir, en una clase derivada de <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>). En este caso, se implementa la interfaz <xref:System.IDisposable> y un método `Dispose(Boolean)` adicional. Esta es la variación recomendada y no requiere invalidar el método <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.  
  
  > [!NOTE]
  > El espacio de nombres <xref:Microsoft.Win32.SafeHandles?displayProperty=nameWithType> proporciona un conjunto de clases derivadas de <xref:System.Runtime.InteropServices.SafeHandle> que aparecen enumeradas en la sección [Uso de controladores seguros](#SafeHandles). Si no encuentra ninguna clase que sea capaz de liberar el recurso no administrado, puede implementar su propia subclase de <xref:System.Runtime.InteropServices.SafeHandle>.  
  
- Puede implementar la interfaz <xref:System.IDisposable> y un método `Dispose(Boolean)` adicional, así como invalidar el método <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. Debe invalidar <xref:System.Object.Finalize%2A> para asegurarse de que los recursos no administrados se eliminan en el caso de que un consumidor de su tipo no llame a la implementación <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>. Si utiliza la técnica recomendada analizada en el punto anterior, la clase <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> realiza este procedimiento en su nombre.  
  
Para asegurarse de que los recursos se limpien siempre correctamente, un método <xref:System.IDisposable.Dispose%2A> debe debe ser invocable varias veces sin que se produzca una excepción.  
  
El ejemplo de código proporcionado para el método <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> muestra cómo la recolección de elementos no utilizados puede hacer que un finalizador se ejecute mientras una referencia no administrada al objeto o a sus miembros todavía está en uso. Usar <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> tiene sentido para hacer que el objeto no sea válido para la recolección de elementos no utilizados desde el principio de la rutina actual y hasta el momento en que se llamó a este método.
  
<a name="Dispose2"></a>
## <a name="dispose-and-disposeboolean"></a>Dispose() y Dispose (booleano)  

La interfaz <xref:System.IDisposable> requiere la implementación de un único método sin parámetros, <xref:System.IDisposable.Dispose%2A>. Sin embargo, el patrón de Dispose requiere dos métodos `Dispose` para implementarse:  
  
- Una implementación pública que no sea virtual (`NonInheritable` en Visual Basic) <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> y que no tenga parámetros.  
  
- Un método protegido virtual (`Overridable` in Visual Basic) `Dispose` cuya signatura es:  
  
  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]  
  
### <a name="the-dispose-overload"></a>La sobrecarga Dispose()

Dado que un consumidor del tipo llama a este método `NonInheritable` público, no virtual (`Dispose` en Visual Basic) y sin parámetros, su propósito consiste en liberar recursos no administrados e indicar que el finalizador, si existe, no tiene que ejecutarse. Debido a esto, se realiza una implementación estándar:  
  
[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]  
  
El método `Dispose` limpia todos los objetos, por lo que el recolector de elementos no utilizados no necesita llamar a la invalidación <xref:System.Object.Finalize%2A?displayProperty=nameWithType> de los objetos. Por consiguiente, la llamada al método <xref:System.GC.SuppressFinalize%2A> evita que el recolector de elementos no utilizados ejecute el finalizador. Si el tipo no tiene ningún finalizador, la llamada a <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> no tiene ningún efecto. Observe que el trabajo real de liberar recursos no administrados lo realiza la segunda sobrecarga del método `Dispose`.  
  
### <a name="the-disposeboolean-overload"></a>La sobrecarga Dispose(Boolean)

En la segunda sobrecarga, el parámetro *disposing* es un valor <xref:System.Boolean> que indica si la llamada al método procede de un método <xref:System.IDisposable.Dispose%2A> (su valor es `true`) o de un finalizador (su valor es `false`).  
  
El cuerpo del método consta de dos bloques de código:  
  
- Un bloque que libera los recursos no administrados. Este bloque se ejecuta independientemente del valor del parámetro `disposing`.  
  
- Un bloque condicional que libera los recursos administrados. Este bloque se ejecuta si el valor de `disposing` es `true`. Estos son algunos de los recursos administrados que se liberan:  
  
  **Objetos administrados que implementan <xref:System.IDisposable>.** El bloque condicional se puede utilizar para llamar a la implementación <xref:System.IDisposable.Dispose%2A>. Si ha utilizado un controlador seguro para incluir el recurso no administrado, debe llamar aquí a la implementación <xref:System.Runtime.InteropServices.SafeHandle.Dispose%28System.Boolean%29?displayProperty=nameWithType>.  
  
  **Objetos administrados que consumen gran cantidad de memoria o recursos insuficientes.** Al liberar estos objetos explícitamente en el método `Dispose`, se liberan más rápido que si el recolector de elementos no utilizados los reclamara de forma no determinista.  
  
Si la llamada al método procede de un finalizador (es decir, *disposing* es `false`), solo se ejecuta el código que libera los recursos no administrados. Como no se define el orden en que el recolector de elementos no utilizados destruye los objetos administrados durante la finalización, la llamada a esta sobrecarga `Dispose` con un valor de `false` evita que el finalizador intente liberar los recursos administrados que ya se hayan reclamado.  
  
## <a name="implementing-the-dispose-pattern-for-a-base-class"></a>Implementación del patrón de Dispose para una clase base

Cuando se implementa el patrón de Dispose para una clase base, debe proporcionar lo siguiente:  
  
> [!IMPORTANT]
> Implemente este patrón para todas las clases base que implementen <xref:System.IDisposable.Dispose> y no sean `sealed` (`NotInheritable` en Visual Basic).  
  
- Una implementación <xref:System.IDisposable.Dispose%2A> que llame al método `Dispose(Boolean)`.  
  
- Un método `Dispose(Boolean)` que realiza el trabajo real de liberar recursos.  
  
- Una clase derivada de <xref:System.Runtime.InteropServices.SafeHandle> que contiene el recurso no administrado (recomendado), o una invalidación del método <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. La clase <xref:System.Runtime.InteropServices.SafeHandle> proporciona un finalizador que evita que tenga que codificar uno.  
  
A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase base que utiliza un controlador seguro.  
  
[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]  
  
> [!NOTE]
> El ejemplo anterior utiliza un objeto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> para ilustrar el patrón; cualquier objeto derivado de <xref:System.Runtime.InteropServices.SafeHandle> podría usarse en su lugar. Tenga en cuenta que el ejemplo no crea una instancia de su objeto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> correctamente.  
  
A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase base que invalide a <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.  
  
[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]  
  
> [!NOTE]
> En C#, invalida a <xref:System.Object.Finalize%2A?displayProperty=nameWithType> definiendo un [destructor](../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## <a name="implementing-the-dispose-pattern-for-a-derived-class"></a>Implementación del patrón de Dispose para una clase derivada

Una clase derivada de una clase que implemente la interfaz <xref:System.IDisposable> no debe implementar <xref:System.IDisposable>, porque la implementación de la clase base de <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> la heredan sus clases derivadas. En su lugar, para liberar los recursos de una clase derivada, debe proporcionar los siguientes elementos:  
  
- Un método `protected Dispose(Boolean)` que invalide el método de la clase base y realice el trabajo real de liberar los recursos de la clase derivada. Este método también debe llamar al método `Dispose(Boolean)` de la clase base y pasar su estado disposing para el argumento.  
  
- Una clase derivada de <xref:System.Runtime.InteropServices.SafeHandle> que contiene el recurso no administrado (recomendado), o una invalidación del método <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. La clase <xref:System.Runtime.InteropServices.SafeHandle> proporciona un finalizador que evita que tenga que codificar uno. Si proporciona un finalizador, debe llamar a la sobrecarga de `Dispose(Boolean)` con un argumento *disposing* que sea `false`.  
  
A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase derivada que utiliza un controlador seguro:  
  
[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]  
  
> [!NOTE]
> El ejemplo anterior utiliza un objeto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> para ilustrar el patrón; cualquier objeto derivado de <xref:System.Runtime.InteropServices.SafeHandle> podría usarse en su lugar. Tenga en cuenta que el ejemplo no crea una instancia de su objeto <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> correctamente.  
  
A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase derivada que invalide a <xref:System.Object.Finalize%2A?displayProperty=nameWithType>:  
  
[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]  
  
> [!NOTE]
> En C#, invalida a <xref:System.Object.Finalize%2A?displayProperty=nameWithType> definiendo un [destructor](../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
<a name="SafeHandles"></a>
## <a name="using-safe-handles"></a>Uso de controladores seguros

La escritura de código para el finalizador de un objeto es una tarea compleja que puede producir problemas si no se realiza correctamente. Por tanto, se recomienda construir objetos <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> en lugar de implementar un finalizador.  
  
Las clases derivadas de la clase <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> simplifican los problemas de duración de objetos mediante la asignación y liberación de identificadores sin interrupción. Contienen un finalizador crítico cuya ejecución está garantizada mientras se descarga un dominio de aplicación. Para obtener más información sobre las ventajas de usar un controlador seguro, vea <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>. Las clases derivadas siguientes en el espacio de nombres <xref:Microsoft.Win32.SafeHandles> proporcionan controladores seguros:  
  
- La clase <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> y <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> para archivos, archivos asignados en memoria y canalizaciones.  
  
- La clase <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> para vistas de memoria.  
  
- Las clases <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> y <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> para construcciones criptográficas.  
  
- La clase <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> para claves del Registro.  
  
- La clase <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> para identificadores de espera.  
  
<a name="base"></a>
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-base-class"></a>Uso de un controlador seguro para implementar el patrón de Dispose para una clase base

En el ejemplo siguiente se muestra el patrón de Dispose para una clase base, `DisposableStreamResource`, que utiliza un controlador seguro para encapsular los recursos no administrados. Define una clase `DisposableResource` que utiliza un <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> para incluir un objeto <xref:System.IO.Stream> que representa un archivo abierto. El método `DisposableResource` también incluye una propiedad única, `Size`, que devuelve el número total de bytes de la secuencia de archivos.  
  
[!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
[!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]  
  
<a name="derived"></a>
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-derived-class"></a>Uso de un controlador seguro para implementar el patrón de Dispose para una clase derivada

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
- [Cómo: Definir y usar clases y structs (C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli)
- [Patrón de Dispose](implementing-dispose.md)
