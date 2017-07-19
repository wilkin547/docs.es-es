---
title: "C&#243;mo: Detectar cu&#225;ndo se presiona la tecla ENTRAR | Microsoft Docs"
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
  - "Entrar (tecla), detectar"
  - "claves, Entrar"
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Detectar cu&#225;ndo se presiona la tecla ENTRAR
En este ejemplo se muestra cómo detectar cuándo se presiona la tecla <xref:System.Windows.Input.Key> en el teclado.  
  
 Este ejemplo consta de un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y un archivo de código subyacente.  
  
## Ejemplo  
 Cuando el usuario presiona la tecla <xref:System.Windows.Input.Key> en el control <xref:System.Windows.Controls.TextBox>, los datos que se han especificado en el cuadro de texto aparecen en otra área de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 El [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] siguiente crea la interfaz de usuario, que está compuesta de un control <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xml[keydown#KeyDownUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 En el siguiente código subyacente se crea el controlador de eventos <xref:System.Windows.UIElement.KeyDown>.  Si la tecla que se presiona es <xref:System.Windows.Input.Key>, se muestra un mensaje en el control <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[keydown#KeyDownSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## Vea también  
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)