---
title: Limpiar recursos no administrados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fea76042bb603889764a9d42b5a7836d704fcd48
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="cleaning-up-unmanaged-resources"></a>Limpiar recursos no administrados
En el caso de la mayoría de los objetos creados por la aplicación, puede usar el recolector de elementos no utilizados de .NET para administrar la memoria. No obstante, cuando se crean objetos que incluyen recursos no administrados, debe liberar explícitamente dichos recursos cuando termine de utilizarlos en la aplicación. Los tipos más comunes de recurso no administrado son objetos que contienen recursos del sistema operativo, como archivos, ventanas, conexiones de red o conexiones de bases de datos. Aunque el recolector de elementos no utilizados puede realizar el seguimiento de la duración de un objeto que encapsula un recurso no administrado, no conoce cómo liberar y limpiar el recurso no administrado.  
  
 Si sus tipos utilizan recursos no administrados, debe hacer lo siguiente:  
  
-   Implementar el [patrón Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md). Para esto es necesario proporcionar una implementación <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> a fin de habilitar la liberación de recursos no administrados de forma determinista. Un consumidor de su tipo llama a <xref:System.IDisposable.Dispose%2A> cuando el objeto (y los recursos que utiliza) ya no se necesita. El método <xref:System.IDisposable.Dispose%2A> libera inmediatamente los recursos no administrados.  
  
-   Planifique la liberación de los recursos no administrados en el caso de que un consumidor de su tipo olvide llamar a <xref:System.IDisposable.Dispose%2A>. Existen dos modos para hacer esto:  
  
    -   Utilizar un controlador seguro para incluir el recurso no administrado. Esta es la técnica recomendada. Los controladores seguros se derivan de la clase <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> e incluyen un método <xref:System.Object.Finalize%2A> eficaz. Al usar un controlador seguro, simplemente se implementa la interfaz <xref:System.IDisposable> y se llama al método <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> del controlador seguro en la implementación <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>. El recolector de elementos no utilizados llama automáticamente al finalizador del controlador seguro si no se llama a su método <xref:System.IDisposable.Dispose%2A>.  
  
         -O bien-  
  
    -   Invalide el método <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. La finalización habilita la liberación de forma no determinista de recursos no administrados cuando el consumidor de un tipo no llama a <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> para deshacerse de ellos de forma determinista. Sin embargo, como la finalización del objeto puede ser una operación compleja y propensa a errores, se recomienda usar un controlador seguro en lugar de proporcionar su propio finalizador.  
  
 Los consumidores de su tipo pueden entonces llamar a la implementación <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> directamente para liberar la memoria que utilizan los recursos no administrados. Cuando se implementa correctamente un método <xref:System.IDisposable.Dispose%2A>, el método <xref:System.Object.Finalize%2A> del controlador seguro o su propia invalidación del método <xref:System.Object.Finalize%2A?displayProperty=nameWithType> actúa como medida de seguridad para limpiar los recursos en caso de que no se llame al método <xref:System.IDisposable.Dispose%2A>.  
  
## <a name="in-this-section"></a>En esta sección  
 [Implementar un método Dispose](../../../docs/standard/garbage-collection/implementing-dispose.md)  
 Describe cómo implementar el [patrón de Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md) para liberar recursos no administrados.  
  
 [Uso de objetos que implementan IDisposable](../../../docs/standard/garbage-collection/using-objects.md)  
 Describe cómo los consumidores de un tipo garantizan que se llame a su implementación <xref:System.IDisposable.Dispose%2A>. Se recomienda utilizar la instrucción `using` de C# o la instrucción `Using` Visual Basic para realizar este procedimiento.  
  
## <a name="reference"></a>Referencia  
 <xref:System.IDisposable?displayProperty=nameWithType>  
 Define el método <xref:System.IDisposable.Dispose%2A> para liberar recursos no administrados.  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 Proporciona la finalización del objeto si el método <xref:System.IDisposable.Dispose%2A> no libera los recursos no administrados.  
  
 <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>  
 Suprime la finalización. Se llama a este método de forma personalizada desde un método `Dispose` para impedir que se ejecute un finalizador.
