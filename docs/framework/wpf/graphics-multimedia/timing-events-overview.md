---
title: Información general sobre eventos de control de tiempo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- timelines [WPF]
- timing events [WPF]
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
ms.openlocfilehash: 91e335f4d5adaa5279fb16805604f2e2848eeb8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167172"
---
# <a name="timing-events-overview"></a>Información general sobre eventos de control de tiempo
Este tema describe cómo utilizar los cinco eventos de control de tiempo disponible en <xref:System.Windows.Media.Animation.Timeline> y <xref:System.Windows.Media.Animation.Clock> objetos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe entender cómo crear y utilizar animaciones. Para empezar a trabajar con animación, vea el [información general sobre animaciones](animation-overview.md).  
  
 Hay varias maneras de animar propiedades en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **Usar objetos storyboard** (marcado y código): Puede usar <xref:System.Windows.Media.Animation.Storyboard> objetos para organizar y distribuir animaciones a uno o varios objetos. Para obtener un ejemplo, vea [animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md).  
  
-   **Mediante animaciones locales** (solo código): Puede aplicar <xref:System.Windows.Media.Animation.AnimationTimeline> objetos directamente a las propiedades que animan. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).  
  
-   **Mediante relojes** (solo código): Puede administrar la creación de un reloj explícitamente y distribuir los relojes de animación personalmente.  Para obtener un ejemplo, vea [animar una propiedad usando un objeto AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Dado que puede usar en la marcación y código, utilizan los ejemplos en esta introducción <xref:System.Windows.Media.Animation.Storyboard> objetos. Sin embargo, los conceptos descritos pueden aplicarse a los otros métodos existentes para animar propiedades.  
  
### <a name="what-is-a-clock"></a>¿Qué es un reloj?  
 Un objeto Timeline, por sí mismo, realmente no hace nada más que describir un segmento de tiempo. Es la escala de tiempo <xref:System.Windows.Media.Animation.Clock> objeto que hace el trabajo real: mantiene el estado de tiempo de ejecución relacionados con el control de tiempo para la escala de tiempo. En la mayoría de los casos, como cuando se utilizan objetos Storyboard, se crea automáticamente un reloj para dichos objetos. También puede crear un <xref:System.Windows.Media.Animation.Clock> explícitamente mediante el <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> método. Para obtener más información acerca de <xref:System.Windows.Media.Animation.Clock> objetos, vea el [Animation and Timing System Overview](animation-and-timing-system-overview.md).  
  
## <a name="why-use-events"></a>¿Por qué usar eventos?  
 Con excepción de una operación, (operación de búsqueda alineada con el último ciclo), todas las operaciones de control de tiempo interactivas son asincrónicas. No hay ninguna manera de saber exactamente cuándo se ejecutarán. Esto puede ser un problema cuando hay otro código que depende de la operación de control de tiempo. Suponga que desea detener un objeto Timeline que anima un rectángulo. Una vez detenido el objeto Timeline, desea cambiar el color del rectángulo.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 En el ejemplo anterior, la segunda línea de código podría ejecutarse antes de que se detenga el objeto Storyboard. Esto se debe a que la detención es una operación asincrónica. Al indicar a un objeto Timeline o Clock que se detenga, se crea una "solicitud de detención" que no se procesa hasta el siguiente ciclo del motor de control de tiempo.  
  
 Para ejecutar comandos una vez finalizada la reproducción de un objeto Timeline, utilice eventos de control de tiempo. En el ejemplo siguiente, se utiliza un controlador de eventos para cambiar el color de un rectángulo al detenerse el objeto Storyboard.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 Para obtener un ejemplo más completo, vea [los cambios de recibir notificación cuando un reloj de estado](how-to-receive-notification-when-clock-state-changes.md).  
  
## <a name="public-events"></a>Eventos públicos  
 El <xref:System.Windows.Media.Animation.Timeline> y <xref:System.Windows.Media.Animation.Clock> clases proporcionan cinco eventos de temporización. En la tabla siguiente se enumeran estos eventos y las condiciones que los desencadenan.  
  
|evento|Operación interactiva desencadenante|Otros desencadenadores|  
|-----------|--------------------------------------|--------------------|  
|**Completada**|Omitir hasta completar|El reloj se completa.|  
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
 Aunque una escala de tiempo <xref:System.Windows.Media.Animation.Timeline.Completed>, <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, y <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> parecen estar asociados con la escala de tiempo, registrar para estos eventos realmente asocia un controlador de eventos con eventos el <xref:System.Windows.Media.Animation.Clock> creado para la escala de tiempo.  
  
 Cuando se registra para el <xref:System.Windows.Media.Animation.Timeline.Completed> eventos en una escala de tiempo, por ejemplo, en realidad está indicando al sistema que se registre para el <xref:System.Windows.Media.Animation.Clock.Completed> eventos de cada reloj que se crea para la escala de tiempo. En el código, debe registrar para este evento antes de la <xref:System.Windows.Media.Animation.Clock> se crea para esta escala de tiempo; en caso contrario, no recibirá la notificación. Esto sucede automáticamente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; el analizador se registra automáticamente para el evento antes de la <xref:System.Windows.Media.Animation.Clock> se crea.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre sistemas de temporización y animación](animation-and-timing-system-overview.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre comportamientos de control de tiempo](timing-behaviors-overview.md)
