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
ms.openlocfilehash: ee45441e9ad09c60d8b61ecce4ef08b0027ce29e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145415"
---
# <a name="timing-events-overview"></a>Información general sobre eventos de control de tiempo
En este tema se describe cómo usar <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> los cinco eventos de tiempo disponibles y objetos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe entender cómo crear y utilizar animaciones. Para empezar a usar la animación, consulte Información general sobre [animaciones](animation-overview.md).  
  
 Hay varias formas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]animar propiedades en:  
  
- Uso de **objetos de guión gráfico** (marcado y código): puede usar <xref:System.Windows.Media.Animation.Storyboard> objetos para organizar y distribuir animaciones a uno o varios objetos. Para obtener un ejemplo, vea [Animar una propiedad mediante un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md).  
  
- Uso de **animaciones locales** (solo código): puede aplicar <xref:System.Windows.Media.Animation.AnimationTimeline> objetos directamente a las propiedades que animan. Para obtener un ejemplo, vea [Animar una propiedad sin usar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).  
  
- **Mediante relojes** (solo código): puede administrar la creación de un reloj explícitamente y distribuir los relojes de animación personalmente.  Para obtener un ejemplo, vea [Animar una propiedad mediante un AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Dado que puede usarlos en el marcado y <xref:System.Windows.Media.Animation.Storyboard> el código, los ejemplos de esta información general usan objetos. Sin embargo, los conceptos descritos pueden aplicarse a los otros métodos existentes para animar propiedades.  
  
### <a name="what-is-a-clock"></a>¿Qué es un reloj?  
 Un objeto Timeline, por sí mismo, realmente no hace nada más que describir un segmento de tiempo. Es el objeto de <xref:System.Windows.Media.Animation.Clock> la línea de tiempo el que realiza el trabajo real: mantiene el estado de tiempo de ejecución relacionado con el tiempo de ejecución de la línea de tiempo. En la mayoría de los casos, como cuando se utilizan objetos Storyboard, se crea automáticamente un reloj para dichos objetos. También puede crear <xref:System.Windows.Media.Animation.Clock> un explícitamente <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> mediante el método. Para obtener <xref:System.Windows.Media.Animation.Clock> más información acerca de los objetos, vea Información general sobre el sistema de [animación y temporización](animation-and-timing-system-overview.md).  
  
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
  
 Para obtener un ejemplo más completo, vea [Recibir notificación cuando cambia](how-to-receive-notification-when-clock-state-changes.md)el estado de un reloj .  
  
## <a name="public-events"></a>Eventos públicos  
 Las <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> clases y proporcionan cinco eventos de temporización. En la tabla siguiente se enumeran estos eventos y las condiciones que los desencadenan.  
  
|Evento|Operación interactiva desencadenante|Otros desencadenadores|  
|-----------|--------------------------------------|--------------------|  
|**Completado**|Omitir hasta completar|El reloj se completa.|  
|**CurrentGlobalSpeedInvalidated**|Pausar, reanudar, buscar, establecer la relación de velocidad, omitir hasta completar, detener|El reloj se invierte, acelera, inicia o detiene.|  
|**CurrentStateInvalidated**|Comenzar, omitir hasta completar, detener|El reloj se inicia, detiene o completa.|  
|**CurrentTimeInvalidated**|Comenzar, buscar, omitir hasta completar, detener|El reloj progresa.|  
|**RemoveRequested**|Remove||  
  
## <a name="ticking-and-event-consolidation"></a>Ciclos y consolidación de eventos  
 Al animar objetos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es el motor de sincronización que administra las animaciones. El motor de control de tiempo realiza el seguimiento de la progresión del tiempo y calcula el estado de cada animación. Realiza muchas de estos pasos de evaluación en un segundo. Estos pasos de evaluación se denominan "ciclos".  
  
 Aunque los ciclos se producen con frecuencia, pueden ocurrir muchas cosas entre ellos. Por ejemplo, un objeto Timeline se podría detener, iniciar y detener de nuevo, en cuyo caso su estado actual habría cambiado tres veces. En teoría, el evento puede generarse varias veces en un único ciclo; sin embargo, el motor de control de tiempo consolida los eventos, para que cada evento se pueda generar como máximo una vez por ciclo.  
  
## <a name="registering-for-events"></a>Registro para eventos  
 Hay dos formas de registrarse para eventos de control de tiempo: con el objeto Timeline o con un objeto Clock creado a partir del objeto Timeline. Registrarse para un evento directamente con un reloj es bastante sencillo, aunque solo puede realizarse desde el código. Puede registrarse para eventos con un objeto Timeline tanto en marcado como en código. En la sección siguiente se describe cómo registrarse para eventos de reloj con un objeto Timeline.  
  
<a name="registeringforclockeventswithatimeline"></a>
## <a name="registering-for-clock-events-with-a-timeline"></a>Registrarse para eventos de reloj con un objeto Timeline  
 Aunque los eventos <xref:System.Windows.Media.Animation.Timeline.Completed> <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> , , y los eventos de una escala de tiempo parecen <xref:System.Windows.Media.Animation.Clock> estar asociados a la escala de tiempo, el registro de estos eventos en realidad asocia un controlador de eventos con el creado para la escala de tiempo.  
  
 Cuando se registra <xref:System.Windows.Media.Animation.Timeline.Completed> para el evento en una línea de tiempo, por <xref:System.Windows.Media.Animation.Clock.Completed> ejemplo, en realidad está diciendo al sistema que se registre para el evento de cada reloj que se crea para la línea de tiempo. En el código, debe registrarse <xref:System.Windows.Media.Animation.Clock> para este evento antes de que se cree para esta escala de tiempo; de lo contrario, no recibirá una notificación. Esto sucede [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]automáticamente en ; el analizador se registra automáticamente para <xref:System.Windows.Media.Animation.Clock> el evento antes de que se cree.  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre sistemas de control de tiempo y animación](animation-and-timing-system-overview.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre comportamientos de control de tiempo](timing-behaviors-overview.md)
