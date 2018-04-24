---
title: Patrón asincrónico basado en eventos (EAP)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
caps.latest.revision: 20
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fecd71355d53f1e3937d3724569b10fa0c8e50da
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="event-based-asynchronous-pattern-eap"></a>Patrón asincrónico basado en eventos (EAP)
Hay varias maneras de exponer las características asincrónicas al código de cliente. El modelo asincrónico basado en eventos prescribe una manera para que las clases presenten comportamiento asincrónico.  
  
> [!NOTE]
>  A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la biblioteca TPL (Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas) proporciona un nuevo modelo para programación asincrónica y en paralelo. Para más información, consulte [Parallel Programming](../../../docs/standard/parallel-programming/index.md) (Programación en paralelo).  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Describe cómo el Modelo asincrónico basado en evento pone a su disposición las ventajas de las aplicaciones multithreading ocultando muchos de los problemas complejos inherentes al diseño multithreading.  
  
 [Implementación del modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 Describe la manera estándar de empaquetar una clase que tiene características asincrónicas.  
  
 [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 Describe los requisitos para exponer las características asincrónicas según el Modelo asincrónico basado en evento.  
  
 [Decisión de cuándo implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 Describe cómo determinar cuándo se debería decidir implementar el Modelo asincrónico basado en evento en lugar del modelo <xref:System.IAsyncResult>.  
  
 [Tutorial: Implementación de un componente que admita el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 Explica cómo crear un componente que implementa el Modelo asincrónico basado en evento. Se implementa utilizando las clases auxiliares del espacio de nombres <xref:System.ComponentModel?displayProperty=nameWithType>, que garantiza que el componente funciona correctamente bajo cualquier modelo de aplicación.  
  
 [Uso de componentes que admitan el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 Describe cómo utilizar un componente que admite el Modelo asincrónico basado en evento.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ComponentModel.AsyncOperation>  
 Describe la clase <xref:System.ComponentModel.AsyncOperation> y contiene vínculos a todos sus miembros.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Describe la clase <xref:System.ComponentModel.AsyncOperationManager> y contiene vínculos a todos sus miembros.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Describe el componente <xref:System.ComponentModel.BackgroundWorker> y contiene vínculos a todos sus miembros.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Biblioteca TPL](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 Describe un modelo de programación para operaciones asincrónicas y paralelas.  
  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 Describe las características de multithreading en .NET Framework.  
  
 [Subprocesamiento](https://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 Describe las características de multithreading en los lenguajes Visual Basic y C#.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos recomendados para el subprocesamiento administrado](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [Eventos](../../../docs/standard/events/index.md)  
 [Subprocesamiento múltiple en componentes](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [Asynchronous Programming Design Patterns](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Patrones de diseño para programación asincrónica)
