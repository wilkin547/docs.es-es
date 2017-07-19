---
title: "C&#243;mo: Cambiar el color de un elemento mediante eventos de foco | Microsoft Docs"
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
  - "colores de los elementos, cambiar"
  - "elementos, cambiar color de"
  - "eventos de foco, cambiar el color de los elementos para"
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Cambiar el color de un elemento mediante eventos de foco
En este ejemplo se muestra cómo cambiar el color de un elemento cuando recibe y pierde el foco utilizando los eventos <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus>.  
  
 Este ejemplo consta de un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y un archivo de código subyacente.  
  
## Ejemplo  
 En el [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] siguiente se crea la interfaz de usuario, que está compuesta de dos objetos <xref:System.Windows.Controls.Button>, y se asocian los controladores de eventos para los eventos <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus> a los objetos <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 En el siguiente código subyacente se crean los controladores de eventos <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus>.  Cuando <xref:System.Windows.Controls.Button> recibe el foco del teclado, la propiedad <xref:System.Windows.Controls.Control.Background%2A> de <xref:System.Windows.Controls.Button> se cambia al color rojo.  Cuando <xref:System.Windows.Controls.Button> pierde el foco del teclado, la propiedad <xref:System.Windows.Controls.Control.Background%2A> de <xref:System.Windows.Controls.Button> se vuelve a establecer en el color blanco.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## Vea también  
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)