---
title: "Informaci&#243;n general sobre eventos de control de tiempo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Clock (clase)"
  - "clases de reloj"
  - "Escalas de tiempo"
  - "eventos de temporización"
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Informaci&#243;n general sobre eventos de control de tiempo
Este tema describe cómo utilizar los cinco eventos de control de tiempo disponibles en <xref:System.Windows.Media.Animation.Timeline> y <xref:System.Windows.Media.Animation.Clock> objetos.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe entender cómo crear y utilizar animaciones. Para empezar a trabajar con animación, consulte el [Introducción a la animación](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Hay varias maneras de animar propiedades en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **Usar objetos de guión gráfico** (marcado y código): puede usar <xref:System.Windows.Media.Animation.Storyboard> objetos para organizar y distribuir animaciones a uno o más objetos. Para obtener un ejemplo, vea [animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
-   **Mediante animaciones locales** (sólo mediante código): puede aplicar <xref:System.Windows.Media.Animation.AnimationTimeline> objetos directamente a las propiedades que animan. Para obtener un ejemplo, vea [animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
-   **Mediante relojes** (sólo mediante código): puede administrar la creación de reloj explícitamente y distribuir los relojes de animación personalmente.  Para obtener un ejemplo, vea [animar una propiedad usando un objeto AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Puesto que puede usar en código y marcado, utilizan los ejemplos de esta información general <xref:System.Windows.Media.Animation.Storyboard> objetos. Sin embargo, los conceptos descritos pueden aplicarse a los otros métodos de las propiedades de animación.  
  
### <a name="what-is-a-clock"></a>¿Qué es un reloj?  
 Una escala de tiempo, por sí mismo, realmente no hace nada más que describir un segmento de tiempo. Es la escala de tiempo <xref:System.Windows.Media.Animation.Clock> objeto que hace el trabajo real: mantiene el estado de tiempo de ejecución relacionados con la sincronización de la escala de tiempo. En la mayoría de los casos, como cuando se utilizan guiones gráficos, se crea automáticamente un reloj para la escala de tiempo. También puede crear un <xref:System.Windows.Media.Animation.Clock> explícitamente mediante la <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> método. Para obtener más información acerca de <xref:System.Windows.Media.Animation.Clock> los objetos, vea la [Animation and Timing System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="why-use-events"></a>¿Por qué usar eventos?  
 A excepción de uno (seek alineada con el último paso), todas las operaciones de tiempo interactivo son asincrónicas. No hay ninguna manera de saber exactamente cuándo se ejecutarán. Esto puede ser un problema cuando hay otro código que depende de la operación de control de tiempo. Suponga que desea detener una escala de tiempo que anima un rectángulo. Una vez detenida la escala de tiempo, cambiar el color del rectángulo.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 En el ejemplo anterior, la segunda línea de código podría ejecutarse antes de que deje de guión gráfico. Eso es porque la detención es una operación asincrónica. Que indica una escala de tiempo o el reloj para detener, crea una "solicitud de detención" de tipo que no se procesa hasta el siguiente paso del motor de tiempo.  
  
 Para ejecutar comandos una vez finalizada una escala de tiempo, usar eventos de temporización. En el ejemplo siguiente, se utiliza un controlador de eventos para cambiar el color de un rectángulo después el guión gráfico se detiene.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 Para obtener un ejemplo más completo, vea [cambios de recibir notificación cuando un reloj de estado](../../../../docs/framework/wpf/graphics-multimedia/how-to-receive-notification-when-clock-state-changes.md).  
  
## <a name="public-events"></a>Eventos públicos  
 El <xref:System.Windows.Media.Animation.Timeline> y <xref:System.Windows.Media.Animation.Clock> clases proporcionan cinco eventos de temporización. En la tabla siguiente se enumera estos eventos y las condiciones que desencadenan.  
  
|Evento|Operación interactiva desencadenante|Otros desencadenadores|  
|-----------|--------------------------------------|--------------------|  
|**Completado**|Omitir hasta completar|El reloj se completa.|  
|**CurrentGlobalSpeedInvalidated**|Pausar, reanudar, buscar, establecer la relación de velocidad, omitir hasta completar, detener|El reloj se invierte, acelera, inicia o detiene.|  
|**CurrentStateInvalidated**|Comenzar, omitir hasta completar, detener|El reloj se detiene, que inicia o completa.|  
|**CurrentTimeInvalidated**|Comenzar, buscar, omitir hasta completar, detener|El reloj progresa.|  
|**RemoveRequested**|Quitar||  
  
## <a name="ticking-and-event-consolidation"></a>Pasos y consolidación de eventos  
 Puede animar objetos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es el motor de tiempo que administra las animaciones. El motor de tiempo realiza el seguimiento de la progresión de tiempo y calcula el estado de cada animación. Resulta que estos pasos de evaluación en un segundo. Estos pasos de evaluación se denominan "pasos."  
  
 Mientras que los pasos se producen con frecuencia, es posible para muchas cosas que han ocurrido entre los pasos. Por ejemplo, una escala de tiempo podría se detenido, iniciar y detener de nuevo, en cuyo caso su estado actual habría cambiado tres veces. En teoría, el evento puede generarse varias veces en un único paso; Sin embargo, el motor de control de tiempo consolida los eventos, para que cada evento se puede generar como máximo una vez por paso.  
  
## <a name="registering-for-events"></a>Registrarse para eventos  
 Hay dos formas para el registro de eventos de temporización: puede registrar con la escala de tiempo o con el reloj creado a partir de la escala de tiempo. Registrar un evento directamente con un reloj es bastante sencillo, aunque sólo puede realizarse desde el código. Puede registrarse para eventos con una escala de tiempo en el marcado o código. La siguiente sección describe cómo registrarse para eventos de reloj con una escala de tiempo.  
  
<a name="registeringforclockeventswithatimeline"></a>   
## <a name="registering-for-clock-events-with-a-timeline"></a>Registrarse para eventos de reloj con una escala de tiempo  
 Aunque una escala de tiempo <xref:System.Windows.Media.Animation.Timeline.Completed>, <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, y <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> eventos parecen estar asociado con la escala de tiempo, registro de estos eventos realmente asocia un controlador de eventos con el <xref:System.Windows.Media.Animation.Clock> creado para la escala de tiempo.  
  
 Cuando se registra para la <xref:System.Windows.Media.Animation.Timeline.Completed> evento en una escala de tiempo, por ejemplo, en realidad está indicando al sistema que registre para el <xref:System.Windows.Media.Animation.Clock.Completed> eventos de cada reloj que se crea para la escala de tiempo. En el código, debe registrar para este evento antes de la <xref:System.Windows.Media.Animation.Clock> se crea para esta escala de tiempo; en caso contrario, no recibirá la notificación. Esto sucede automáticamente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; el analizador se registra automáticamente para el evento antes de la <xref:System.Windows.Media.Animation.Clock> se crea.  
  
## <a name="see-also"></a>Vea también  
 [Información general del sistema de temporización y animación](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Información general de animación](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre comportamientos de temporización](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)