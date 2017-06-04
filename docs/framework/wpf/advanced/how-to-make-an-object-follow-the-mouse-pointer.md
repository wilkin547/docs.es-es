---
title: "C&#243;mo: Crear un objeto que siga el puntero del mouse | Microsoft Docs"
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
  - "cursor (puntero del mouse), hacer que los objetos sigan al"
  - "seguir el puntero del mouse (cursor)"
  - "puntero del mouse (cursor), hacer que los objetos sigan al"
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Crear un objeto que siga el puntero del mouse
En este ejemplo se muestra cómo cambiar las dimensiones de un objeto cuando el puntero del mouse se mueve por la pantalla.  
  
 El ejemplo incluye un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que crea la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] y un archivo de código subyacente que crea el controlador de eventos.  
  
## Ejemplo  
 En el [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] siguiente se crea la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], que está compuesta de un elemento <xref:System.Windows.Shapes.Ellipse> dentro de un control <xref:System.Windows.Controls.StackPanel>, y se adjunta el controlador de eventos para el evento <xref:System.Windows.UIElement.MouseMove>.  
  
 [!code-xml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 En el siguiente código subyacente se crea el controlador de eventos <xref:System.Windows.UIElement.MouseMove>.  Cuando el puntero del mouse se mueve, el alto y el ancho de <xref:System.Windows.Shapes.Ellipse> aumentan y disminuyen.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## Vea también  
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)