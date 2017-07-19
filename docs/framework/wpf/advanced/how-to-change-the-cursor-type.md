---
title: "C&#243;mo: Cambiar el tipo de cursor | Microsoft Docs"
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
  - "cursor (puntero del mouse)"
  - "puntero del mouse (cursor), tipo de cursor"
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Cambiar el tipo de cursor
En este ejemplo se muestra cómo cambiar el objeto <xref:System.Windows.Input.Cursor> del puntero del mouse para un elemento concreto y para la aplicación.  
  
 Este ejemplo consta de un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y de un archivo de código subyacente.  
  
## Ejemplo  
 Se crea la interfaz de usuario que consiste en un control <xref:System.Windows.Controls.ComboBox> donde seleccionar el objeto <xref:System.Windows.Input.Cursor> deseado, un par de objetos <xref:System.Windows.Controls.RadioButton> para determinar si el cambio del cursor se aplica a un solo elemento o a la aplicación completa, y un objeto <xref:System.Windows.Controls.Border> que es el elemento al que se aplica el nuevo cursor.  
  
 [!code-xml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 El código subyacente siguiente crea un controlador de eventos <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> al que se llama cuando se cambia el tipo de cursor en el control <xref:System.Windows.Controls.ComboBox>.  Una instrucción switch aplica un filtro al nombre del cursor y establece la propiedad <xref:System.Windows.FrameworkElement.Cursor%2A> del objeto <xref:System.Windows.Controls.Border>, denominado *DisplayArea*.  
  
 Si el cambio del cursor se establece en "Entire Application", la propiedad <xref:System.Windows.Input.Mouse.OverrideCursor%2A> se establece en la propiedad <xref:System.Windows.FrameworkElement.Cursor%2A> del control <xref:System.Windows.Controls.Border>.  Esto obliga al cursor a cambiar para toda la aplicación.  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## Vea también  
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)