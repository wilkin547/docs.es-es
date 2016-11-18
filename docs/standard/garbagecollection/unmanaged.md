---
title: Limpiar recursos no administrados
description: Limpiar recursos no administrados
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/18/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 8c97c3e2-8619-47ce-ae29-d6a3140bfa83
translationtype: Human Translation
ms.sourcegitcommit: 213ce098bcc2b5e31c55e759d895254d5ca33caa
ms.openlocfilehash: c0600eb27c27261f6496fb45310514f7f716b3b3

---

# <a name="cleaning-up-unmanaged-resources"></a>Limpiar recursos no administrados

En el caso de la mayoría de los objetos creados por la aplicación, puede usar el recolector de elementos no utilizados de .NET para administrar la memoria. No obstante, cuando se crean objetos que incluyen recursos no administrados, debe liberar explícitamente dichos recursos cuando termine de utilizarlos en la aplicación. Los tipos más comunes de recurso no administrado son objetos que contienen recursos del sistema operativo, como archivos, ventanas, conexiones de red o conexiones de bases de datos. Aunque el recolector de elementos no utilizados puede realizar el seguimiento de la duración de un objeto que encapsula un recurso no administrado, no conoce cómo liberar y limpiar el recurso no administrado. 

Si sus tipos utilizan recursos no administrados, debe hacer lo siguiente: 

* Implementar el patrón Dispose. Para esto es necesario proporcionar una implementación [IDisposable.Dispose](xref:System.IDisposable.Dispose) a fin de habilitar la liberación de recursos no administrados de forma determinista. Un consumidor de su tipo llama a [Dispose](xref:System.IDisposable.Dispose) cuando el objeto (y los recursos que usa) ya no se necesita. El método [Dispose](xref:System.IDisposable.Dispose) libera inmediatamente los recursos no administrados. 

* Planificar la liberación de los recursos no administrados en el caso de que un consumidor de su tipo olvide llamar a [Dispose](xref:System.IDisposable.Dispose). Existen dos modos para hacer esto: 

    * Utilizar un controlador seguro para incluir el recurso no administrado. Esta es la técnica recomendada. Se derivan controladores seguros de la clase [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) y se incluye un método [Finalize](xref:System.Object.Finalize) sólido. Cuando se usa un controlador seguro, simplemente se implementa la interfaz [IDisposable](xref:System.IDisposable) y se llama al método [Dispose](xref:System.IDisposable.Dispose) del controlador seguro en la implementación [IDisposable.Dispose](xref:System.IDisposable.Dispose). El recolector de elementos no utilizados llama automáticamente al finalizador del controlador seguro si no se llama a su método [Dispose](xref:System.IDisposable.Dispose). 

      -O bien-

    * Invalidar el método [Object.Finalize](xref:System.Object.Finalize). La finalización habilita la liberación de forma no determinista de recursos no administrados cuando el consumidor de un tipo no llama a [IDisposable.Dispose](xref:System.IDisposable.Dispose) para deshacerse de ellos de forma determinista. Sin embargo, como la finalización del objeto puede ser una operación compleja y propensa a errores, se recomienda usar un controlador seguro en lugar de proporcionar su propio finalizador. 

Los consumidores de su tipo pueden entonces llamar a la implementación [IDisposable.Dispose](xref:System.IDisposable.Dispose) directamente para liberar la memoria que usan los recursos no administrados. Cuando se implementa correctamente un método [Dispose](xref:System.IDisposable.Dispose), el método [Finalize](xref:System.Object.Finalize) del controlador seguro o su propia invalidación del método [Object.Finalize](xref:System.Object.Finalize) actúan como medida de seguridad para limpiar los recursos en caso de que no se llame al método [Dispose](xref:System.IDisposable.Dispose). 

## <a name="in-this-section"></a>En esta sección

[Implementar un método Dispose](implementing-dispose.md): describe cómo implementar el patrón de Dispose para liberar recursos no administrados.

[Usar objetos que implementan IDisposable](using-objects.md): describe cómo los consumidores de un tipo garantizan que se llame a su implementación de Dispose. Se recomienda usar la instrucción using de C# o la instrucción Using de Visual Basic para realizar este procedimiento.

## <a name="reference"></a>Referencia

[System.IDisposable](xref:System.IDisposable): define el método `Dispose` para liberar recursos no administrados.

[Object.Finalize](xref:System.Object.Finalize): proporciona la finalización del objeto si el método `Dispose` no libera los recursos no administrados. 

[GC.SuppressFinalize](xref:System.GC#System_GC_SuppressFinalize_System_Object_): suprime la finalización. Se llama a este método de forma personalizada desde un método `Dispose` para impedir que se ejecute un finalizador. 



<!--HONumber=Nov16_HO3-->


