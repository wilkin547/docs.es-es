---
title: "Deciding When to Implement the Event-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "AsyncOperation class"
  - "AsyncCompletedEventArgs class"
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Deciding When to Implement the Event-based Asynchronous Pattern
El Modelo asincrónico basado en evento proporciona un modelo para exponer el comportamiento asincrónico de una clase.  Con la introducción de este modelo, [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] define dos modelos para exponer el comportamiento asincrónico: el Modelo asincrónico basado en la interfaz <xref:System.IAsyncResult?displayProperty=fullName> y el modelo basado en eventos.  En este tema se explica cuándo es adecuado implementar ambos modelos.  
  
 Para obtener más información sobre la programación asincrónica con la interfaz <xref:System.IAsyncResult>, vea [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
## Principios generales  
 En general, siempre que sea posible debería exponer las características asincrónicas mediante el Modelo asincrónico basado en evento.  Sin embargo, hay algunos requisitos que no puede cumplir el modelo basado en eventos.  En esos casos, puede ser necesario implementar el modelo <xref:System.IAsyncResult> además del modelo basado en eventos.  
  
> [!NOTE]
>  Es raro que se implemente el modelo <xref:System.IAsyncResult> sin que también se implemente el modelo basado en eventos.  
  
## Instrucciones  
 La lista siguiente incluye instrucciones sobre cuándo se debería implementar el Modelo asincrónico basado en evento:  
  
-   Utilice el modelo basado en eventos como la API predeterminada para exponer el comportamiento asincrónico de su clase.  
  
-   No exponga el modelo <xref:System.IAsyncResult> cuando su clase se utilice principalmente en una aplicación cliente como, por ejemplo, Windows Forms.  
  
-   Exponga el modelo <xref:System.IAsyncResult> sólo cuando sea necesario para cumplir sus requisitos.  Por ejemplo, la compatibilidad con una API existente puede requerir que se exponga el modelo <xref:System.IAsyncResult>.  
  
-   No exponga el modelo <xref:System.IAsyncResult> sin exponer también el modelo basado en evento.  
  
-   Si debe exponer el modelo <xref:System.IAsyncResult>, hágalo como una opción avanzada.  Por ejemplo, si genera un objeto de servidor proxy, genere de forma predeterminada el modelo basado en eventos, con una opción para generar el modelo <xref:System.IAsyncResult>.  
  
-   Compile su implementación del modelo basado en eventos en su implementación del modelo <xref:System.IAsyncResult>.  
  
-   Evite exponer el modelo basado en eventos y el modelo <xref:System.IAsyncResult> en la misma clase.  Exponga el modelo basado en eventos en las clases de "alto nivel" y el modelo <xref:System.IAsyncResult> en clases de "nivel inferior".  Por ejemplo, compare el modelo basado en eventos en el componente <xref:System.Net.WebClient> con el modelo <xref:System.IAsyncResult> en la clase <xref:System.Web.HttpRequest>.  
  
    -   Exponga el modelo basado en eventos y el modelo <xref:System.IAsyncResult> en la misma clase cuando lo requiera la compatibilidad.  Por ejemplo, si ya ha publicado una API que utiliza el modelo <xref:System.IAsyncResult>, sería necesario conservar el modelo <xref:System.IAsyncResult> para la compatibilidad con versiones anteriores.  
  
    -   Exponga el modelo basado en eventos y el modelo <xref:System.IAsyncResult> en la misma clase si la complejidad del modelo de objetos resultante no compensará la ventaja de separar las implementaciones.  Es mejor exponer ambos modelos en una sola clase que evitar exponer el modelo basado en evento.  
  
    -   Si debe exponer tanto el modelo basado en eventos como el modelo <xref:System.IAsyncResult> en una única clase, utilice <xref:System.ComponentModel.EditorBrowsableAttribute> establecido en <xref:System.ComponentModel.EditorBrowsableState> para marcar la implementación del modelo <xref:System.IAsyncResult> como característica avanzada.  Esto indica a los entornos de diseño, como el IntelliSense de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], que no deben mostrar las propiedades y métodos de <xref:System.IAsyncResult>.  Estas propiedades y métodos todavía son totalmente utilizables, pero el desarrollador que trabaja con IntelliSense tiene una visión más clara de la API.  
  
## Criterios para exponer el modelo IAsyncResult además del modelo basado en eventos  
 Aunque el Modelo asincrónico basado en evento tiene muchas ventajas en los escenarios mencionados anteriormente, tiene algunos inconvenientes que debería conocer si el factor más importante para sus aplicaciones es el rendimiento.  
  
 Hay tres escenarios que no prevé el modelo basado en eventos así como el modelo <xref:System.IAsyncResult>:  
  
-   Bloquear la espera de un <xref:System.IAsyncResult>  
  
-   Bloquear la espera de muchos objetos <xref:System.IAsyncResult>  
  
-   Sondear la finalización en <xref:System.IAsyncResult>  
  
 Puede afrontar estos escenarios utilizando el modelo basado en eventos, pero hacerlo resulta más torpe que utilizar el modelo <xref:System.IAsyncResult>.  
  
 A menudo, los desarrolladores utilizan el modelo <xref:System.IAsyncResult> para los servicios que normalmente tienen requisitos de muy alto rendimiento.  Por ejemplo, el escenario de sondeo de finalización es una técnica de servidor de alto rendimiento.  
  
 Además, el modelo basado en eventos es menos eficaz que el modelo <xref:System.IAsyncResult> porque crea más objetos, sobre todo <xref:System.EventArgs>, y porque sincroniza los subprocesos.  
  
 La lista siguiente muestra algunas recomendaciones que seguir si decide utilizar el modelo <xref:System.IAsyncResult>:  
  
-   Exponga sólo el modelo <xref:System.IAsyncResult> cuando requiere específicamente la compatibilidad para los objetos <xref:System.Threading.WaitHandle> o <xref:System.IAsyncResult>.  
  
-   Exponga el modelo <xref:System.IAsyncResult> sólo cuando tenga una API existente que utilice el modelo <xref:System.IAsyncResult>.  
  
-   Si tiene una API existente basada en el modelo <xref:System.IAsyncResult>, plantéese exponer también el modelo basado en eventos en su siguiente versión publicada.  
  
-   Exponga el modelo <xref:System.IAsyncResult> sólo si requiere un rendimiento algo que haya comprobado que no puede obtener con el modelo basado en eventos pero que sí se puede conseguir con el modelo <xref:System.IAsyncResult>.  
  
## Vea también  
 [Walkthrough: Implementing a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)   
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)   
 [Implementing the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)   
 [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)