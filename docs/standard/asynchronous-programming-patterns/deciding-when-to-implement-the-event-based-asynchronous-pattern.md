---
title: "Decidir cuándo implementar el modelo asincrónico basado en eventos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48de1b736c251a61a2ad34975c77bc2bca139626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a>Decidir cuándo implementar el modelo asincrónico basado en eventos
El modelo asincrónico basado en eventos proporciona un patrón para exponer el comportamiento asincrónico de una clase. Con la introducción de este modelo, el [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] define dos modelos para exponer el comportamiento asincrónico: el modelo asincrónico basado en la <xref:System.IAsyncResult?displayProperty=nameWithType> interfaz y el modelo basado en eventos. Este tema describe cuándo es adecuado para permitirle implementar ambos modelos.  
  
 Para obtener más información sobre la programación asincrónica con el <xref:System.IAsyncResult> de la interfaz, vea [patrón asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
## <a name="general-principles"></a>Principios generales  
 En general, se deben exponer las características asincrónicas mediante el modelo asincrónico basado en eventos siempre que sea posible. Sin embargo, hay algunos requisitos que no puede cumplir el modelo basado en eventos. En esos casos, puede que necesite implementar el <xref:System.IAsyncResult> modelo además del modelo basado en eventos.  
  
> [!NOTE]
>  Es raro que las <xref:System.IAsyncResult> patrón para que se implementen sin el modelo basado en eventos y también que se va a implementar.  
  
## <a name="guidelines"></a>Instrucciones  
 En la lista siguiente se describe las instrucciones para cuando debería implementar el modelo asincrónico basado en evento:  
  
-   Utilice el modelo basado en eventos como la API predeterminada para exponer el comportamiento asincrónico para la clase.  
  
-   No exponga el <xref:System.IAsyncResult> patrón cuando la clase se utiliza principalmente en una aplicación de cliente, por ejemplo, Windows Forms.  
  
-   Exponer solo las <xref:System.IAsyncResult> patrón cuando sea necesario para satisfacer sus requisitos. Por ejemplo, compatibilidad con una API existente puede requerir que se exponga la <xref:System.IAsyncResult> patrón.  
  
-   No exponga el <xref:System.IAsyncResult> patrón sin exponer también el modelo basado en eventos.  
  
-   Si debe exponer el <xref:System.IAsyncResult> de patrón, hacerlo como una opción avanzada. Por ejemplo, si genera un objeto de proxy, generar el modelo basado en eventos de forma predeterminada, con una opción para generar el <xref:System.IAsyncResult> patrón.  
  
-   Compile su implementación del modelo basado en eventos su <xref:System.IAsyncResult> implementación del modelo.  
  
-   Evitar exponer tanto el modelo basado en eventos y el <xref:System.IAsyncResult> patrón en la misma clase. Exponga el modelo basado en eventos en las clases de "nivel superior" y el <xref:System.IAsyncResult> "Disminuir nivel" de clases de patrón. Por ejemplo, compare el modelo basado en eventos en el <xref:System.Net.WebClient> componente con el <xref:System.IAsyncResult> de patrón en el <xref:System.Web.HttpRequest> clase.  
  
    -   Exponga el modelo basado en eventos y el <xref:System.IAsyncResult> patrón en la misma clase cuando lo requiera la compatibilidad. Por ejemplo, si ya ha publicado una API que usa el <xref:System.IAsyncResult> patrón, quizá necesite conservar el <xref:System.IAsyncResult> patrón por compatibilidad con versiones anteriores.  
  
    -   Exponga el modelo basado en eventos y el <xref:System.IAsyncResult> de patrón en la misma clase si la complejidad del modelo de objetos resultante supera con creces las ventajas de separar las implementaciones. Es mejor exponer ambos modelos en una sola clase que evitar exponer el modelo basado en eventos.  
  
    -   Si debe exponer tanto el modelo basado en eventos y <xref:System.IAsyncResult> patrón en una sola clase, use <xref:System.ComponentModel.EditorBrowsableAttribute> establecido en <xref:System.ComponentModel.EditorBrowsableState.Advanced> para marcar el <xref:System.IAsyncResult> implementación del modelo como una característica avanzada. Esto indica a los entornos de diseño, como [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] IntelliSense, no se muestre la <xref:System.IAsyncResult> propiedades y métodos. Estas propiedades y métodos todavía son totalmente utilizables, pero el desarrollador que trabaja con IntelliSense tiene una visión más clara de la API.  
  
## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a>Criterios para exponer el modelo IAsyncResult además del modelo basado en eventos  
 Mientras que el modelo asincrónico basado en evento tiene muchas ventajas en los escenarios mencionados anteriormente, tiene algunas desventajas, que debe tener en cuenta si el rendimiento es el requisito más importante.  
  
 Hay tres escenarios que no se corrige el modelo basado en eventos, así como la <xref:System.IAsyncResult> patrón:  
  
-   Bloquear la espera en uno<xref:System.IAsyncResult>  
  
-   Bloquear la espera de muchos <xref:System.IAsyncResult> objetos  
  
-   Sondear la finalización de en el<xref:System.IAsyncResult>  
  
 Puede resolver estos escenarios utilizando el modelo basado en eventos, pero si lo hace, es más complicado que el uso de la <xref:System.IAsyncResult> patrón.  
  
 Los desarrolladores suelen utilizar el <xref:System.IAsyncResult> patrón para los servicios que normalmente tienen requisitos de muy alto rendimiento. Por ejemplo, el sondeo para el escenario de finalización es una técnica de servidor de alto rendimiento.  
  
 Además, el modelo basado en eventos es menos eficaz que el <xref:System.IAsyncResult> patrón porque crea más objetos, especialmente <xref:System.EventArgs>, y debido a que sincroniza entre subprocesos.  
  
 La lista siguiente muestra algunas recomendaciones que deben seguirse si opta por utilizar la <xref:System.IAsyncResult> patrón:  
  
-   Solo se exponen los <xref:System.IAsyncResult> modelo cuando necesite específicamente la compatibilidad con <xref:System.Threading.WaitHandle> o <xref:System.IAsyncResult> objetos.  
  
-   Exponer solo las <xref:System.IAsyncResult> patrón cuando tenga una API existente que usa el <xref:System.IAsyncResult> patrón.  
  
-   Si tiene una API existente basada en la <xref:System.IAsyncResult> de patrón, considere la posibilidad de exponer también el modelo basado en eventos en la próxima versión.  
  
-   Exponer solo <xref:System.IAsyncResult> modelo si tiene requisitos de alto rendimiento que han comprobado no puede cumplir el modelo basado en eventos, pero puede cumplirse mediante la <xref:System.IAsyncResult> patrón.  
  
## <a name="see-also"></a>Vea también  
 [Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md) (Tutorial: Implementación de un componente que admita el modelo asincrónico basado en eventos)  
 [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Programación multiproceso con el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [Implementación del modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)
