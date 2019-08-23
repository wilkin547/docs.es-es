---
title: Procedimiento Representar un intervalo para cada fotograma mediante CompositionTarget
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CompositionTarget objects [WPF], rendering per frame
- rendering per frame using CompositionTarget objects [WPF]
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
ms.openlocfilehash: 8864204ccdd1e860cc910dfe8baa2f25edfb2fcc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956984"
---
# <a name="how-to-render-on-a-per-frame-interval-using-compositiontarget"></a>Procedimiento Representar un intervalo para cada fotograma mediante CompositionTarget
El motor de animación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona muchas características para crear animaciones basadas en fotogramas. Sin embargo, hay escenarios de aplicación en el los que necesita un control específico sobre la representación según el fotograma. El <xref:System.Windows.Media.CompositionTarget> objeto proporciona la capacidad de crear animaciones personalizadas basadas en una devolución de llamada por fotograma.  
  
 <xref:System.Windows.Media.CompositionTarget>es una clase estática que representa la superficie de presentación en la que se dibuja la aplicación. El <xref:System.Windows.Media.CompositionTarget.Rendering> evento se desencadena cada vez que se dibuja la escena de la aplicación. La velocidad de los fotogramas de representación es el número de veces que se dibuja la escena por segundo.  
  
> [!NOTE]
> Para obtener un ejemplo de código <xref:System.Windows.Media.CompositionTarget>completo con, vea [usar el ejemplo de CompositionTarget](https://go.microsoft.com/fwlink/?LinkID=160045).  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Media.CompositionTarget.Rendering> evento se desencadena durante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el proceso de representación. En el ejemplo siguiente se muestra cómo registrar <xref:System.EventHandler> un delegado en el <xref:System.Windows.Media.CompositionTarget.Rendering> método estático <xref:System.Windows.Media.CompositionTarget>en.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 Puede utilizar el método de controlador de eventos de representación para crear contenido de dibujo personalizado. Se llama a este método de control de eventos una vez por cada fotograma. Cada vez que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] serializa los datos de representación conservados en el árbol visual hasta el gráfico de escena de composición, se llama a este método de control de eventos. Además, si los cambios en el árbol visual fuerzan actualizaciones en el gráfico de escena de composición, también se llama al método de controlador de eventos. Observe que se llama a su método de controlador de eventos después de calcular el diseño. Sin embargo, puede modificar el diseño en su método de controlador de eventos, lo que significa que el diseño se calcula una vez más antes de su representación.  
  
 En el ejemplo siguiente se muestra cómo puede proporcionar un dibujo personalizado <xref:System.Windows.Media.CompositionTarget> en un método de control de eventos. En este caso, el color de fondo de <xref:System.Windows.Controls.Canvas> se dibuja con un valor de color basado en la posición de la coordenada del mouse. Si mueve el mouse dentro de <xref:System.Windows.Controls.Canvas>, cambia el color de fondo. Además, se calcula la velocidad de fotogramas media, según el tiempo transcurrido actual y el número total de fotogramas representados.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Es posible que descubra que el dibujo personalizado se ejecuta a distintas velocidades en equipos diferentes. Esto es porque el dibujo personalizado no depende de la velocidad de los fotogramas. En función del sistema que se esté ejecutando y de la carga de trabajo de ese <xref:System.Windows.Media.CompositionTarget.Rendering> sistema, el evento se puede llamar un número diferente de veces por segundo. Para información sobre el establecimiento de una capacidad de hardware gráfico y el rendimiento de un dispositivo que ejecute una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Niveles de representación de gráficos](../advanced/graphics-rendering-tiers.md).  
  
 La adición o eliminación de un <xref:System.EventHandler> delegado de representación mientras se activa el evento se retrasará hasta que finalice la activación del evento. Esto es coherente con la <xref:System.MulticastDelegate>forma en que se administran los eventos basados en en Common Language Runtime (CLR). Tenga en cuenta que no se garantiza que los eventos de representación se llamen en un orden determinado. Si tiene varios <xref:System.EventHandler> delegados que dependen de un orden determinado, debe registrar un solo <xref:System.Windows.Media.CompositionTarget.Rendering> evento y multiplexar los delegados en el orden correcto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.CompositionTarget>
- [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md)
