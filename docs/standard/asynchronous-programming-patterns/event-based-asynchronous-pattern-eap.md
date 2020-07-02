---
title: Patrón asincrónico basado en eventos (EAP)
description: Vea vínculos a artículos sobre el modelo asincrónico basado en eventos (EAP) en .NET, como la implementación, los procedimientos recomendados y la implementación de un cliente EAP, entre otros.
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: 03b4d914d72b96b882c774565654c022b145b5f2
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768877"
---
# <a name="event-based-asynchronous-pattern-eap"></a>Patrón asincrónico basado en eventos (EAP)

Hay varias maneras de exponer las características asincrónicas al código de cliente. El modelo asincrónico basado en eventos prescribe una manera para que las clases presenten comportamiento asincrónico.  
  
> [!NOTE]
> A partir de .NET Framework 4, la biblioteca TPL (Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas) ofrece un nuevo modelo para programación asincrónica y paralela. Para obtener más información, vea [Biblioteca de procesamiento paralelo basado en tareas (TPL)](../parallel-programming/task-parallel-library-tpl.md) y [Modelo asincrónico basado en tareas (TAP)](task-based-asynchronous-pattern-tap.md).
  
## <a name="in-this-section"></a>En esta sección

 [Información general sobre el modelo asincrónico basado en eventos](event-based-asynchronous-pattern-overview.md)  
 Describe cómo el Modelo asincrónico basado en evento pone a su disposición las ventajas de las aplicaciones multithreading ocultando muchos de los problemas complejos inherentes al diseño multithreading.  
  
 [Implementación del modelo asincrónico basado en eventos](implementing-the-event-based-asynchronous-pattern.md)  
 Describe la manera estándar de empaquetar una clase que tiene características asincrónicas.  
  
 [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 Describe los requisitos para exponer las características asincrónicas según el Modelo asincrónico basado en evento.  
  
 [Decisión de cuándo implementar el modelo asincrónico basado en eventos](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 En este tema se describe cómo determinar el momento conveniente para implementar el modelo asincrónico basado en eventos en lugar del modelo <xref:System.IAsyncResult>, representado por el [modelo de programación asincrónica (APM)](asynchronous-programming-model-apm.md).
  
 [Cómo: Implementación de un componente que admita el modelo asincrónico basado en eventos](component-that-supports-the-event-based-asynchronous-pattern.md)  
 En este tema se describe cómo crear un componente que implemente el modelo asincrónico basado en eventos. Se implementa utilizando las clases del asistente del espacio de nombres <xref:System.ComponentModel?displayProperty=nameWithType>, que garantiza que el componente funciona correctamente bajo cualquier modelo de aplicación.  

 [Cómo: Implementar un cliente en un modelo asincrónico basado en eventos](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 En este tema se describe cómo crear un cliente que use un componente que implemente el modelo asincrónico basado en eventos.
  
 [Cómo: Uso de componentes que admitan el modelo asincrónico basado en eventos](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 Describe cómo utilizar un componente que admite el Modelo asincrónico basado en evento.  
  
## <a name="reference"></a>Referencia

 <xref:System.ComponentModel.AsyncOperation>  
 Describe la clase <xref:System.ComponentModel.AsyncOperation> y contiene vínculos a todos sus miembros.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Describe la clase <xref:System.ComponentModel.AsyncOperationManager> y contiene vínculos a todos sus miembros.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Describe el componente <xref:System.ComponentModel.BackgroundWorker> y contiene vínculos a todos sus miembros.  
  
## <a name="related-sections"></a>Secciones relacionadas

 [Biblioteca TPL](../parallel-programming/task-parallel-library-tpl.md)  
 Describe un modelo de programación para operaciones asincrónicas y paralelas.  
  
 [Subprocesamiento](../threading/index.md)  
 En este tema se describen las características de multithreading en .NET.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos recomendados para el subprocesamiento administrado](../threading/managed-threading-best-practices.md)
- [Eventos](../events/index.md)
- [Patrones para la programación asincrónica](index.md)
