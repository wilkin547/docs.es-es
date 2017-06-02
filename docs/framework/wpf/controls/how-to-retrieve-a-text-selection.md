---
title: "C&#243;mo: Recuperar una selecci&#243;n de texto | Microsoft Docs"
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
  - "recuperar texto"
  - "texto, recuperar"
  - "TextBox (control), recuperar texto"
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Recuperar una selecci&#243;n de texto
En este ejemplo se muestra una manera de utilizar la propiedad <xref:System.Windows.Controls.TextBox.SelectedText%2A> para recuperar texto que el usuario ha seleccionado en un control <xref:System.Windows.Controls.TextBox>.  
  
## Ejemplo  
 En el ejemplo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] siguiente se muestra la definición de un control <xref:System.Windows.Controls.TextBox> que contiene texto que se puede seleccionar y un control <xref:System.Windows.Controls.Button> con un método <xref:System.Windows.Controls.Button.OnClick%2A> especificado.  
  
 En este ejemplo, se utiliza un botón con un controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> asociado para recuperar la selección de texto.  Cuando el usuario hace clic en el botón, el método <xref:System.Windows.Controls.Button.OnClick%2A> copia en una cadena cualquier texto que esté seleccionado en el cuadro de texto.  Las circunstancias concretas en virtud de las que se recupera \(hacer clic en un botón\) la selección de texto, así como la acción que se lleva a cabo como consecuencia de esa selección \(copiar la selección de texto en una cadena\), se pueden modificar con facilidad para adaptarlas a gran variedad de escenarios.  
  
 [!code-xml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## Ejemplo  
 En el ejemplo de [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] se muestra un controlador de eventos <xref:System.Windows.Controls.Button.OnClick%2A> para el botón definido en el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de este ejemplo.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)