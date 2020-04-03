---
title: Subprocesamiento administrado
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
ms.openlocfilehash: c5ca102dc98e50067d39d2f0c51a6ff75e342e9f
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588667"
---
# <a name="managed-threading"></a>Subprocesamiento administrado
Tanto si va a desarrollar aplicaciones para equipos con uno o varios procesadores, desea que la aplicación proporcione la interacción con mayor capacidad de respuesta con el usuario, incluso si la aplicación actualmente hace otro trabajo. Usar varios subprocesos de ejecución es una de las formas más eficaces de mantener que la aplicación siga respondiendo al usuario y, al mismo tiempo, usar el procesador entre eventos de usuario o durante los mismos. Si bien esta sección presenta los conceptos básicos del subprocesamiento, se centra en los conceptos del subprocesamiento administrado y su uso.  
  
> [!NOTE]
> A partir de .NET Framework 4, la programación multiproceso se ha simplificado significativamente con las clases <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md), clases de colecciones simultáneas nuevas en el espacio de nombres <xref:System.Collections.Concurrent?displayProperty=nameWithType> y un nuevo modelo de programación basado en el concepto de tareas en lugar de subprocesos. Para más información, consulte [Programación en paralelo](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Principios básicos del subprocesamiento administrado](../../../docs/standard/threading/managed-threading-basics.md)  
 Proporciona información general sobre el subprocesamiento administrado y describe cuándo usar varios subprocesos.  
  
 [Usar subprocesos y subprocesamiento](../../../docs/standard/threading/using-threads-and-threading.md)  
 Explica cómo crear, iniciar, pausar, reanudar y anular subprocesos.  
  
 [Procedimientos recomendados para el subprocesamiento administrado](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Se describen los niveles de sincronización, cómo evitar interbloqueos y condiciones de carrera y otros problemas de subprocesos.  
  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)  
 Describe las clases administradas que puede usar para sincronizar las actividades de subprocesamientos y los datos de objetos accedidos en distintos subprocesos, y proporciona información general sobre los subprocesos de grupos de subprocesos.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Threading>  
 Contiene clases para usar y sincronizar subprocesos administrados.  
  
 <xref:System.Collections.Concurrent>  
 Contiene clases de colección seguras para usarlas con varios subprocesos.  
  
 <xref:System.Threading.Tasks>  
 Contiene clases para crear y programar tareas de procesamiento simultáneo.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Dominios de aplicación](../../../docs/framework/app-domains/application-domains.md)  
 Proporciona información genera sobre los dominios de aplicación y de su uso en Common Language Infrastructure.  
  
 [E/S de archivos asincrónica](../../../docs/standard/io/asynchronous-file-i-o.md)  
 Describe las ventajas de rendimiento y el funcionamiento básico de la E/S asincrónica.  
  
 [Modelo asincrónico basado en tareas (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 Proporciona una introducción del patrón recomendado para programación asincrónica en. NET.  
  
 [Llamada a métodos sincrónicos de forma asincrónica](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Explica cómo llamar a métodos en los subprocesos de grupos de subprocesos con características integradas de delegados.  
  
 [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)  
 Describe las bibliotecas de programación en paralelo, las que simplifican el uso de varios subprocesos en las aplicaciones.  
  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
 Describe un sistema para ejecutar consultas en paralelo a fin de aprovechar los distintos procesadores.
