---
title: "Eventos de vista previa | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "eventos, Vista previa"
  - "eventos, suprimir"
  - "eventos de vista previa"
  - "suprimir eventos"
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Eventos de vista previa
Los eventos de vista previa, también denominados eventos de túnel, son eventos enrutados cuya dirección de ruta se desplaza desde la raíz de la aplicación hacia el elemento que ha provocado el evento y se comunica como el origen en los datos de evento.  No todos los escenarios de eventos admiten o requieren los eventos de vista previa; en este tema se describen las situaciones en que existe este tipo de eventos, cómo deben controlarlos las aplicaciones o los componentes, y los casos en que puede ser conveniente crearlos en componentes o clases personalizados.  
  
## Eventos de vista previa y entrada  
 Al administrar eventos de vista previa en general, extreme las precauciones en relación con marcarlos como controlados en los datos de evento.  Controlar un evento de vista previa para cualquier elemento que no sea el que lo provocó \(aquél que se comunica como origen en los datos de evento\) hace que no se proporcione a este último la oportunidad de controlar el evento que ha provocado.  A veces, éste es el resultado deseado, en particular si los elementos en cuestión existan en relaciones contenidas en una composición de controles de un control.  
  
 En concreto para los eventos de entrada, los eventos de vista previa también comparten instancias de datos de evento con el evento de propagación equivalente.  Si utiliza un controlador de clase de evento de vista previa para marcar como controlado el evento de entrada, no se invocará el controlador de clase de evento de entrada de propagación.  Por otra parte, si utiliza un controlador de instancia de evento de vista previa para marcar el evento como controlado, normalmente no se invocarán los controladores correspondientes al evento de propagación.  Los controladores de clase o de instancia se pueden registrar o asociar con la opción de invocarlos aunque el evento esté marcado como controlado, pero se trata de una técnica de uso poco frecuente.  
  
 Para obtener más información sobre el control de clases y su relación con los eventos de vista previa, vea [Marcar eventos enrutados como controlados y control de clases](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
### Evitar la supresión de eventos por parte de los controles  
 Un escenario donde se suelen utilizar eventos de vista previa es el control de eventos de entrada en controles compuestos.  A veces, el autor del control impide que se provoque determinado evento desde su control, quizás para sustituir un evento definido por el componente que lleva más información o implica un comportamiento más concreto.  Por ejemplo, un <xref:System.Windows.Controls.Button> de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] suprime los eventos de propagación <xref:System.Windows.UIElement.MouseLeftButtonDown> y <xref:System.Windows.UIElement.MouseLeftButtonDown> generados por el objeto <xref:System.Windows.Controls.Button> o sus elementos compuestos a favor de capturar el mouse y generar un evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> que siempre lo genera el propio objeto <xref:System.Windows.Controls.Button>.  El evento y sus datos siguen su curso a lo largo de la ruta, pero puesto que <xref:System.Windows.Controls.Button> marca los datos de evento como <xref:System.Windows.RoutedEventArgs.Handled%2A>, únicamente se invoca a los controladores del evento cuya actuación se indica específicamente en el caso `handledEventsToo`.  Si otros elementos situados más cerca de la raíz de la aplicación tuvieran que tener la oportunidad de controlar un evento suprimido por un control, una alternativa consiste en adjuntar controladores en código especificando `handledEventsToo` en `true`.  Sin embargo, es más sencilla la técnica de cambiar la dirección de enrutamiento que se administra de modo que sea el equivalente de vista previa de un evento de entrada.  Por ejemplo, si un control suprime <xref:System.Windows.UIElement.MouseLeftButtonDown>, intente adjuntar en su lugar un controlador para <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>.  Esta técnica sólo funciona para los eventos de entrada del elemento base, como <xref:System.Windows.UIElement.MouseLeftButtonDown>.  Estos eventos de entrada utilizan pares de túnel\/propagación, provocan ambos eventos y comparten los datos de evento.  
  
 Cada una de estas técnicas tiene efectos secundarios o limitaciones.  El efecto secundario de controlar el evento de vista previa reside en que controlarlo en ese punto podría deshabilitar los controladores que esperan controlar el evento de propagación, y por consiguiente la limitación consiste en que no suele ser conveniente marcar el evento como controlado mientras se encuentre en la parte de la ruta correspondiente a la vista previa.  La limitación de la técnica de `handledEventsToo` es que no se puede especificar un controlador de `handledEventsToo` en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como un atributo, hay que registrar el controlador de eventos en código después de obtener una referencia de objeto al elemento al que se asociará el controlador.  
  
## Vea también  
 [Marcar eventos enrutados como controlados y control de clases](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)