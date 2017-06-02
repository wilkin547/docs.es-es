---
title: "C&#243;mo: Detectar cu&#225;ndo cambia el texto en un control TextBox | Microsoft Docs"
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
  - "detectar cambios del texto"
  - "cambios del texto, detectar"
  - "TextBox (control), detectar cambios del texto"
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Detectar cu&#225;ndo cambia el texto en un control TextBox
En este ejemplo se muestra una manera de utilizar el evento <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> para ejecutar un método cada vez que cambia el texto de un control <xref:System.Windows.Controls.TextBox>.  
  
 En la clase de código subyacente para el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el control <xref:System.Windows.Controls.TextBox> cuyos cambios desea supervisar, inserte un método al que llamar cada vez que se activa el evento <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>.  Este método debe tener una firma que coincida con lo que espera el delegado de <xref:System.Windows.Controls.TextChangedEventHandler>.  
  
 Se llama al controlador de eventos cada vez que cambia el contenido del control <xref:System.Windows.Controls.TextBox>, ya sea por el usuario o mediante programación.  
  
 **Nota:** este evento se activa cuando se crea el control <xref:System.Windows.Controls.TextBox> y se rellena de texto inicialmente.  
  
## Ejemplo  
 En el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que define el control <xref:System.Windows.Controls.TextBox>, especifique el atributo <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> con un valor que coincida con el nombre del método de control de eventos.  
  
 [!code-xml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## Ejemplo  
 En la clase de código subyacente para el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el control <xref:System.Windows.Controls.TextBox> cuyos cambios desea supervisar, inserte un método al que llamar cada vez que se activa el evento <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>.  Este método debe tener una firma que coincida con lo que espera el delegado de <xref:System.Windows.Controls.TextChangedEventHandler>.  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 Se llama al controlador de eventos cada vez que cambia el contenido del control <xref:System.Windows.Controls.TextBox>, ya sea por el usuario o mediante programación.  
  
 **Nota:** este evento se activa cuando se crea el control <xref:System.Windows.Controls.TextBox> y se rellena de texto inicialmente.  
  
 Comentarios  
  
## Vea también  
 <xref:System.Windows.Controls.TextChangedEventArgs>   
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)