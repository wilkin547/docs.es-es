---
title: "Cómo: Representar un intervalo para cada fotograma mediante CompositionTarget"
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
- CompositionTarget objects [WPF], rendering per frame
- rendering per frame using CompositionTarget objects [WPF]
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7616a418b9f2f6b175b925e4385322c42546e9bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-render-on-a-per-frame-interval-using-compositiontarget"></a>Cómo: Representar un intervalo para cada fotograma mediante CompositionTarget
El motor de animación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona muchas características para crear animaciones basadas en fotogramas. Sin embargo, hay escenarios de aplicación en el los que necesita un control específico sobre la representación según el fotograma. La <xref:System.Windows.Media.CompositionTarget> objeto proporciona la capacidad para crear animaciones personalizadas basándose en una devolución de llamada por fotograma.  
  
 <xref:System.Windows.Media.CompositionTarget>es una clase estática que representa la superficie de presentación en el que se va a dibujar la aplicación. El <xref:System.Windows.Media.CompositionTarget.Rendering> evento se desencadena cada vez que se dibuja la escena de la aplicación. La velocidad de los fotogramas de representación es el número de veces que se dibuja la escena por segundo.  
  
> [!NOTE]
>  Para obtener un ejemplo de código completo uso <xref:System.Windows.Media.CompositionTarget>, consulte [Using the CompositionTarget Sample](http://go.microsoft.com/fwlink/?LinkID=160045).  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Media.CompositionTarget.Rendering> evento se desencadena durante la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proceso de representación. En el ejemplo siguiente se muestra cómo registrar un <xref:System.EventHandler> delegar en el método estático <xref:System.Windows.Media.CompositionTarget.Rendering> método en <xref:System.Windows.Media.CompositionTarget>.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 Puede utilizar el método de controlador de eventos de representación para crear contenido de dibujo personalizado. Se llama a este método de control de eventos una vez por cada fotograma. Cada vez que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] serializa los datos de representación conservados en el árbol visual hasta el gráfico de escena de composición, se llama a este método de control de eventos. Además, si los cambios en el árbol visual fuerzan actualizaciones en el gráfico de escena de composición, también se llama al método de controlador de eventos. Observe que se llama a su método de controlador de eventos después de calcular el diseño. Sin embargo, puede modificar el diseño en su método de controlador de eventos, lo que significa que el diseño se calcula una vez más antes de su representación.  
  
 En el ejemplo siguiente se muestra cómo puede proporcionar dibujos personalizados una <xref:System.Windows.Media.CompositionTarget> método de controlador de eventos. En este caso, el color de fondo de la <xref:System.Windows.Controls.Canvas> se dibuja con un valor de color basado en las coordenadas de posición del mouse. Si mueve el mouse dentro de la <xref:System.Windows.Controls.Canvas>, sus cambios de color de fondo. Además, se calcula la velocidad de fotogramas media, según el tiempo transcurrido actual y el número total de fotogramas representados.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Es posible que descubra que el dibujo personalizado se ejecuta a distintas velocidades en equipos diferentes. Esto es porque el dibujo personalizado no depende de la velocidad de los fotogramas. Según el sistema que se está ejecutando y la carga de trabajo de ese sistema, la <xref:System.Windows.Media.CompositionTarget.Rendering> evento se puede llamar a un número diferente de veces por segundo. Para información sobre el establecimiento de una capacidad de hardware gráfico y el rendimiento de un dispositivo que ejecute una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Niveles de representación de gráficos](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 Adición o eliminación de una representación <xref:System.EventHandler> delegado mientras se está activando el evento se retrasará hasta que finalice el evento activación. Esto es coherente con la forma de <xref:System.MulticastDelegate>-se controlan los eventos en función de Common Language Runtime (CLR). Tenga en cuenta que no se garantiza que los eventos de representación se llamen en un orden determinado. Si tiene varios <xref:System.EventHandler> delegados que se basan en un orden determinado, debe registrar una sola <xref:System.Windows.Media.CompositionTarget.Rendering> eventos y multiplexado los delegados en el valor correcto orden por sí mismo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.CompositionTarget>  
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
