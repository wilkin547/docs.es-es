---
title: "Información general sobre eventos de control de tiempo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- timelines [WPF]
- timing events [WPF]
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f50923d9e314d2f677e26416cef59fdf380213e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="timing-events-overview"></a>Información general sobre eventos de control de tiempo
Este tema describe cómo utilizar los cinco eventos de control de tiempo disponible en <xref:System.Windows.Media.Animation.Timeline> y <xref:System.Windows.Media.Animation.Clock> objetos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe entender cómo crear y utilizar animaciones. Para empezar a usar la animación, consulte el [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Hay varias maneras de animar propiedades en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **Usar objetos de guión gráfico** (marcado y código): puede usar <xref:System.Windows.Media.Animation.Storyboard> objetos para organizar y distribuir animaciones a uno o más objetos. Para obtener un ejemplo, vea [animar una propiedad mediante un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
-   **Mediante animaciones locales** (sólo mediante código): puede aplicar <xref:System.Windows.Media.Animation.AnimationTimeline> objetos directamente a las propiedades que animan. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
-   **Mediante relojes** (solo código): puede administrar la creación de un reloj explícitamente y distribuir los relojes de animación personalmente.  Para obtener un ejemplo, vea [animar una propiedad usando un objeto AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Dado que puede usar en código y marcado, los ejemplos de esta información general usan <xref:System.Windows.Media.Animation.Storyboard> objetos. Sin embargo, los conceptos descritos pueden aplicarse a los otros métodos existentes para animar propiedades.  
  
### <a name="what-is-a-clock"></a>¿Qué es un reloj?  
 Un objeto Timeline, por sí mismo, realmente no hace nada más que describir un segmento de tiempo. Es la escala de tiempo <xref:System.Windows.Media.Animation.Clock> objeto que realiza el trabajo real: mantiene el estado de tiempo de ejecución relacionados con el control de tiempo para la escala de tiempo. En la mayoría de los casos, como cuando se utilizan objetos Storyboard, se crea automáticamente un reloj para dichos objetos. También puede crear un <xref:System.Windows.Media.Animation.Clock> explícitamente mediante el <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> método. Para obtener más información acerca de <xref:System.Windows.Media.Animation.Clock> los objetos, vea la [animación y temporización información general del sistema](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="why-use-events"></a>¿Por qué usar eventos?  
 Con excepción de una operación, (operación de búsqueda alineada con el último ciclo), todas las operaciones de control de tiempo interactivas son asincrónicas. No hay ninguna manera de saber exactamente cuándo se ejecutarán. Esto puede ser un problema cuando hay otro código que depende de la operación de control de tiempo. Suponga que desea detener un objeto Timeline que anima un rectángulo. Una vez detenido el objeto Timeline, desea cambiar el color del rectángulo.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 En el ejemplo anterior, la segunda línea de código podría ejecutarse antes de que se detenga el objeto Storyboard. Esto se debe a que la detención es una operación asincrónica. Al indicar a un objeto Timeline o Clock que se detenga, se crea una "solicitud de detención" que no se procesa hasta el siguiente ciclo del motor de control de tiempo.  
  
 Para ejecutar comandos una vez finalizada la reproducción de un objeto Timeline, utilice eventos de control de tiempo. En el ejemplo siguiente, se utiliza un controlador de eventos para cambiar el color de un rectángulo al detenerse el objeto Storyboard.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 Para obtener un ejemplo más completo, vea [cambios de recibir notificación cuando un reloj de estado](../../../../docs/framework/wpf/graphics-multimedia/how-to-receive-notification-when-clock-state-changes.md).  
  
## <a name="public-events"></a>Eventos públicos  
 El <xref:System.Windows.Media.Animation.Timeline> y <xref:System.Windows.Media.Animation.Clock> clases proporcionan cinco eventos de control de tiempo. En la tabla siguiente se enumeran estos eventos y las condiciones que los desencadenan.  
  
|Evento|Operación interactiva desencadenante|Otros desencadenadores|  
|-----------|--------------------------------------|--------------------|  
|**Completed**|Omitir hasta completar|El reloj se completa.|  
|**CurrentGlobalSpeedInvalidated**|Pausar, reanudar, buscar, establecer la relación de velocidad, omitir hasta completar, detener|El reloj se invierte, acelera, inicia o detiene.|  
|**CurrentStateInvalidated**|Comenzar, omitir hasta completar, detener|El reloj se inicia, detiene o completa.|  
|**CurrentTimeInvalidated**|Comenzar, buscar, omitir hasta completar, detener|El reloj progresa.|  
|**RemoveRequested**|Quitar||  
  
## <a name="ticking-and-event-consolidation"></a>Ciclos y consolidación de eventos  
 Al animar objetos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es el motor de tiempo que administra las animaciones. El motor de control de tiempo realiza el seguimiento de la progresión del tiempo y calcula el estado de cada animación. Realiza muchas de estos pasos de evaluación en un segundo. Estos pasos de evaluación se denominan "ciclos".  
  
 Aunque los ciclos se producen con frecuencia, pueden ocurrir muchas cosas entre ellos. Por ejemplo, un objeto Timeline se podría detener, iniciar y detener de nuevo, en cuyo caso su estado actual habría cambiado tres veces. En teoría, el evento puede generarse varias veces en un único ciclo; sin embargo, el motor de control de tiempo consolida los eventos, para que cada evento se pueda generar como máximo una vez por ciclo.  
  
## <a name="registering-for-events"></a>Registro para eventos  
 Hay dos formas de registrarse para eventos de control de tiempo: con el objeto Timeline o con un objeto Clock creado a partir del objeto Timeline. Registrarse para un evento directamente con un reloj es bastante sencillo, aunque solo puede realizarse desde el código. Puede registrarse para eventos con un objeto Timeline tanto en marcado como en código. En la sección siguiente se describe cómo registrarse para eventos de reloj con un objeto Timeline.  
  
<a name="registeringforclockeventswithatimeline"></a>   
## <a name="registering-for-clock-events-with-a-timeline"></a>Registrarse para eventos de reloj con un objeto Timeline  
 Aunque una escala de tiempo <xref:System.Windows.Media.Animation.Timeline.Completed>, <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, y <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> eventos parecen estar asociado con la escala de tiempo, registrar para estos eventos realmente asocia un controlador de eventos con el <xref:System.Windows.Media.Animation.Clock> crear para la escala de tiempo.  
  
 Al registrarse para la <xref:System.Windows.Media.Animation.Timeline.Completed> eventos en una escala de tiempo, por ejemplo, en realidad está indicando al sistema que registre para el <xref:System.Windows.Media.Animation.Clock.Completed> eventos de cada reloj que se crea para la escala de tiempo. En el código, debe registrar para este evento antes de la <xref:System.Windows.Media.Animation.Clock> se crea para esta escala de tiempo; en caso contrario, no recibirá la notificación. Esto sucede automáticamente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; el analizador se registra automáticamente para el evento antes de la <xref:System.Windows.Media.Animation.Clock> se crea.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre sistemas de control de tiempo y animación ](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre comportamientos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
