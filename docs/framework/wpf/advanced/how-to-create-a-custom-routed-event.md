---
title: "C&#243;mo: Crear un evento enrutado personalizado | Microsoft Docs"
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
  - "crear, eventos enrutados"
  - "eventos, enrutar"
  - "eventos enrutados, crear"
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Crear un evento enrutado personalizado
Para que un evento personalizado admita el [enrutamiento de eventos](GTMT), es preciso registrar un <xref:System.Windows.RoutedEvent> mediante el método <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>.  En este ejemplo se muestran los fundamentos para la creación de evento enrutado personalizado.  
  
## Ejemplo  
 Como se muestra en el ejemplo siguiente, primero se registra <xref:System.Windows.RoutedEvent> mediante el método <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>.  Por convención, el nombre del campo estático <xref:System.Windows.RoutedEvent> debe finalizar con el sufijo ***Event***.  En este ejemplo, el nombre del evento es `Tap` y la estrategia de enrutamiento del evento es <xref:System.Windows.RoutingStrategy>.  Después de la llamada de registro, puede proporcionar descriptores de acceso [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] de agregar y quitar al evento.  
  
 Tenga en cuenta que aunque el evento se provoca a través del método virtual `OnTap` en este ejemplo concreto, la manera de provocar un evento o cómo responda este a los cambios dependerá de sus necesidades.  
  
 Observe también que en este ejemplo se implementa básicamente una subclase completa de <xref:System.Windows.Controls.Button>; esa subclase se compila como un ensamblado independiente y, a continuación, se crea una instancia como una clase personalizada en una página [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] independiente.  El motivo de ello es ilustrar el concepto de que los controles con subclases pueden insertarse en árboles compuestos de otros controles y que, en esta situación, los eventos personalizados de estos controles tienen exactamente las mismas funciones de enrutamiento de eventos que cualquier elemento nativo de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 [!code-csharp[RoutedEventCustom#CustomClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xml[RoutedEventCustom#Page](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 Los eventos de tunelización se crean la misma manera, pero con la propiedad <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> establecida en <xref:System.Windows.RoutingStrategy> en la llamada de registro.  Por convención, los eventos de tunelización de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llevan el prefijo "Preview".  
  
 Para obtener un ejemplo de funcionamiento de los eventos de propagación, vea [Controlar un evento enrutado](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md).  
  
## Vea también  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md)