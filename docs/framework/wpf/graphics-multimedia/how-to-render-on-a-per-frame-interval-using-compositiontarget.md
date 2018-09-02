---
title: 'Cómo: Representar un intervalo para cada fotograma mediante CompositionTarget'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CompositionTarget objects [WPF], rendering per frame
- rendering per frame using CompositionTarget objects [WPF]
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
ms.openlocfilehash: cc043e6d225ad3dbe57a0924593fac0f68af7eb1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43473923"
---
# <a name="how-to-render-on-a-per-frame-interval-using-compositiontarget"></a>Cómo: Representar un intervalo para cada fotograma mediante CompositionTarget
El motor de animación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona muchas características para crear animaciones basadas en fotogramas. Sin embargo, hay escenarios de aplicación en el los que necesita un control específico sobre la representación según el fotograma. La <xref:System.Windows.Media.CompositionTarget> objeto proporciona la capacidad para crear animaciones personalizadas basándose en una devolución de llamada por fotograma.  
  
 <xref:System.Windows.Media.CompositionTarget> es una clase estática que representa la superficie de visualización en el que se va a dibujar la aplicación. El <xref:System.Windows.Media.CompositionTarget.Rendering> evento se provoca cada vez que se dibuja la escena de la aplicación. La velocidad de los fotogramas de representación es el número de veces que se dibuja la escena por segundo.  
  
> [!NOTE]
>  Para obtener un ejemplo de código completo con <xref:System.Windows.Media.CompositionTarget>, consulte [mediante el ejemplo de CompositionTarget](https://go.microsoft.com/fwlink/?LinkID=160045).  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Media.CompositionTarget.Rendering> evento se desencadena durante el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proceso de representación. El ejemplo siguiente muestra cómo registrar un <xref:System.EventHandler> delegar a estático <xref:System.Windows.Media.CompositionTarget.Rendering> método <xref:System.Windows.Media.CompositionTarget>.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 Puede utilizar el método de controlador de eventos de representación para crear contenido de dibujo personalizado. Se llama a este método de control de eventos una vez por cada fotograma. Cada vez que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] serializa los datos de representación conservados en el árbol visual hasta el gráfico de escena de composición, se llama a este método de control de eventos. Además, si los cambios en el árbol visual fuerzan actualizaciones en el gráfico de escena de composición, también se llama al método de controlador de eventos. Observe que se llama a su método de controlador de eventos después de calcular el diseño. Sin embargo, puede modificar el diseño en su método de controlador de eventos, lo que significa que el diseño se calcula una vez más antes de su representación.  
  
 El ejemplo siguiente muestra cómo puede proporcionar dibujos personalizados una <xref:System.Windows.Media.CompositionTarget> método controlador de eventos. En este caso, el color de fondo el <xref:System.Windows.Controls.Canvas> se dibuja con un valor de color basado en la posición de la coordenada del mouse. Si mueve el mouse dentro de la <xref:System.Windows.Controls.Canvas>, sus cambios de color de fondo. Además, se calcula la velocidad de fotogramas media, según el tiempo transcurrido actual y el número total de fotogramas representados.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Es posible que descubra que el dibujo personalizado se ejecuta a distintas velocidades en equipos diferentes. Esto es porque el dibujo personalizado no depende de la velocidad de los fotogramas. Según el sistema que se está ejecutando y la carga de trabajo de ese sistema, el <xref:System.Windows.Media.CompositionTarget.Rendering> evento se puede llamar a un número diferente de veces por segundo. Para información sobre el establecimiento de una capacidad de hardware gráfico y el rendimiento de un dispositivo que ejecute una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Niveles de representación de gráficos](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 Adición o eliminación de una representación <xref:System.EventHandler> delegado mientras se está activando el evento se retrasará hasta que una vez finalizado la el evento de activación. Esto es coherente con la forma <xref:System.MulticastDelegate>-basado en eventos se controlan en Common Language Runtime (CLR). Tenga en cuenta que no se garantiza que los eventos de representación se llamen en un orden determinado. Si tiene varios <xref:System.EventHandler> delegados que se basan en un orden determinado, debe registrar una sola <xref:System.Windows.Media.CompositionTarget.Rendering> eventos y multiplexado orden los delegados en el lugar correcto usted mismo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.CompositionTarget>  
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
