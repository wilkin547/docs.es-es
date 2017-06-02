---
title: "C&#243;mo: Representar un intervalo para cada fotograma mediante CompositionTarget | Microsoft Docs"
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
  - "CompositionTarget (objetos), representar por fotograma"
  - "representar por fotograma mediante objetos CompositionTarget"
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Representar un intervalo para cada fotograma mediante CompositionTarget
El motor de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona muchas características para crear animaciones basadas en fotogramas.  Sin embargo, hay escenarios de aplicación en los que se necesita un control más preciso de la representación por fotogramas.  El objeto <xref:System.Windows.Media.CompositionTarget> proporciona la posibilidad de crear animaciones personalizadas basándose en una devolución de llamada por fotograma.  
  
 <xref:System.Windows.Media.CompositionTarget> es una clase estática que representa la superficie de la pantalla en la que se dibuja la aplicación.  El evento <xref:System.Windows.Media.CompositionTarget.Rendering> se provoca cada vez que se dibuja la escena de la aplicación.  La velocidad de representación de los fotogramas es la cantidad de veces que se dibuja la escena por segundo.  
  
> [!NOTE]
>  Para obtener un ejemplo de código completo sobre cómo utilizar <xref:System.Windows.Media.CompositionTarget>, vea [Using the CompositionTarget Sample](http://go.microsoft.com/fwlink/?LinkID=160045).  
  
## Ejemplo  
 El evento <xref:System.Windows.Media.CompositionTarget.Rendering> se provoca durante el proceso de representación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  En el ejemplo siguiente se muestra cómo se registra un delegado <xref:System.EventHandler> en el método <xref:System.Windows.Media.CompositionTarget.Rendering> estático de <xref:System.Windows.Media.CompositionTarget>.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 Puede usar el método de control de eventos de representación para crear contenido de dibujo personalizado.  Se llama a este método de control de eventos una vez por cada fotograma.  Cada vez que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] calcula las referencias de los datos de representación conservados en el [árbol visual](GTMT) hasta el gráfico de escena de composición, se llama a este método de control de eventos.  Además, si algún cambio efectuado en el [de árbol visual](GTMT) fuerza la actualización del gráfico de escena de composición, también se llama al método de control de eventos.  Tenga en cuenta que se llama al método de control de eventos después de calcular el diseño.  Sin embargo, puede modificar el diseño en el método de control de eventos; es decir, el diseño se calculará una vez más antes de la representación.  
  
 En el ejemplo siguiente se muestra cómo se proporciona un dibujo personalizado en un método de control de eventos de <xref:System.Windows.Media.CompositionTarget>.  En este caso, el color de fondo de <xref:System.Windows.Controls.Canvas> se dibuja con un valor de color basado en la posición de las coordenadas del mouse.  Si mueve el mouse dentro de <xref:System.Windows.Controls.Canvas>, su fondo cambia de color.  Además, se calcula la velocidad de fotogramas media, según el tiempo transcurrido actual y el número total de fotogramas representados.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Puede suceder que el dibujo personalizado se ejecute a distintas velocidades en equipos diferentes.  Esto es porque el dibujo personalizado no es independiente de la velocidad de fotogramas.  Según el sistema que se ejecute y de la carga de trabajo de este último, se puede llamar al evento <xref:System.Windows.Media.CompositionTarget.Rendering> una cantidad distinta de veces por segundo.  Para obtener información sobre cómo determinar la capacidad y el rendimiento del hardware de gráficos para un dispositivo que ejecuta una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Niveles de representación de gráficos](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 La adición o eliminación de un delegado de <xref:System.EventHandler> de representación mientras se está activando el evento se retrasará hasta que el evento haya terminado de activarse.  Esto es coherente con la manera de controlar los eventos basados en <xref:System.MulticastDelegate> en Common Language Runtime \(CLR\).  Tenga en cuenta asimismo que no se garantiza que se llame a los eventos de representación en ningún orden determinado.  Si tiene varios delegados de <xref:System.EventHandler> que requieren un orden concreto, debe registrar un solo evento <xref:System.Windows.Media.CompositionTarget.Rendering> y multiplexar manualmente los delegados en el orden correcto.  
  
## Vea también  
 <xref:System.Windows.Media.CompositionTarget>   
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)