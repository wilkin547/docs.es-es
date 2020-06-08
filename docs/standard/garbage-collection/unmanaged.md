---
title: Limpiar recursos no administrados
ms.date: 05/13/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- Close method
- Dispose method
- garbage collector
- garbage collection, unmanaged resources
- cleanup operations
- explicit cleanups
- unmanaged resource cleanup
- Finalize method
ms.assetid: a17b0066-71c2-4ba4-9822-8e19332fc213
ms.openlocfilehash: 2d8b22063a184773928e5bc072f51a9f7d5d45ba
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396987"
---
# <a name="cleaning-up-unmanaged-resources"></a>Limpiar recursos no administrados

En el caso de la mayoría de los objetos creados por la aplicación, puede usar el [recolector de elementos no utilizados de .NET](index.md) para administrar la memoria. No obstante, cuando se crean objetos que incluyen recursos no administrados, debe liberar explícitamente dichos recursos cuando termine de usarlos. Los tipos más comunes de recursos no administrados son objetos que contienen recursos del sistema operativo, como archivos, ventanas, conexiones de red o conexiones de bases de datos. Aunque el recolector de elementos no utilizados puede realizar el seguimiento de la duración de un objeto que encapsula un recurso no administrado, no conoce cómo liberar y limpiar el recurso no administrado.

Si sus tipos utilizan recursos no administrados, debe hacer lo siguiente:

- Implementar el [patrón Dispose](implementing-dispose.md). Para ello es necesario proporcionar una implementación <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> a fin de permitir la liberación determinista de recursos no administrados. Un consumidor de su tipo llama a <xref:System.IDisposable.Dispose%2A> cuando el objeto, y los recursos que utiliza, ya no se necesitan. El método <xref:System.IDisposable.Dispose%2A> libera inmediatamente los recursos no administrados.

- En caso de que un consumidor de su tipo olvide llamar a <xref:System.IDisposable.Dispose%2A>, proporcione una manera de liberar los recursos no administrados. Existen dos modos para hacer esto:

  - Utilizar un controlador seguro para incluir el recurso no administrado. Esta es la técnica recomendada. Los controladores seguros se derivan de la clase <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> abstracta e incluyen un método <xref:System.Object.Finalize%2A> eficaz. Al usar un controlador seguro, simplemente se implementa la interfaz <xref:System.IDisposable> y se llama al método <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> del controlador seguro en la implementación <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>. El recolector de elementos no utilizados llama automáticamente al finalizador del controlador seguro si no se llama a su método <xref:System.IDisposable.Dispose%2A>.

    **o**

  - Invalide el método <xref:System.Object.Finalize%2A?displayProperty=nameWithType> . La finalización habilita la liberación de forma no determinista de recursos no administrados cuando el consumidor de un tipo no llama a <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> para deshacerse de ellos de forma determinista. Defina un [finalizador](../../csharp/programming-guide/classes-and-structs/destructors.md) mediante la invalidación del método <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.

  > [!WARNING]
  > Sin embargo, como la finalización del objeto puede ser una operación compleja y propensa a errores, se recomienda usar un controlador seguro en lugar de proporcionar su propio finalizador.

Los consumidores de su tipo pueden entonces llamar a la implementación <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> directamente para liberar la memoria que utilizan los recursos no administrados. Cuando se implementa correctamente un método <xref:System.IDisposable.Dispose%2A>, el método <xref:System.Object.Finalize%2A> del controlador seguro o su propia invalidación del método <xref:System.Object.Finalize%2A?displayProperty=nameWithType> actúa como medida de seguridad para limpiar los recursos en caso de que no se llame al método <xref:System.IDisposable.Dispose%2A>.

## <a name="in-this-section"></a>En esta sección

En [Implementar un método Dispose](implementing-dispose.md) se describe cómo implementar el patrón de eliminación para liberar recursos no administrados.

En [Uso de objetos que implementan `IDisposable`](../../../docs/standard/garbage-collection/using-objects.md) se describe cómo los consumidores de un tipo garantizan que se llame a su implementación de <xref:System.IDisposable.Dispose%2A>. Para realizar este procedimiento, se recomienda usar la instrucción `using` de C# (o la instrucción `Using` de Visual Basic).

## <a name="reference"></a>Referencia

| Tipo o miembro | Descripción |
|--|--|
| <xref:System.IDisposable?displayProperty=nameWithType> | Define el método <xref:System.IDisposable.Dispose%2A> para liberar recursos no administrados. |
| <xref:System.Object.Finalize%2A?displayProperty=nameWithType> | Proporciona la finalización del objeto si el método <xref:System.IDisposable.Dispose%2A> no libera los recursos no administrados. |
| <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> | Suprime la finalización. Se llama a este método de forma personalizada desde un método `Dispose` para impedir que se ejecute un finalizador. |
