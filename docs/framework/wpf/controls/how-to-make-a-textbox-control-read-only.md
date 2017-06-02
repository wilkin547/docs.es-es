---
title: "C&#243;mo: Hacer que un control TextBox sea de s&#243;lo lectura | Microsoft Docs"
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
  - "controles TextBox de sólo lectura"
  - "TextBox (control) de sólo lectura"
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Hacer que un control TextBox sea de s&#243;lo lectura
En este ejemplo muestra cómo configurar un control <xref:System.Windows.Controls.TextBox> para que no admita datos proporcionados por el usuario ni modificaciones.  
  
## Ejemplo  
 Para evitar que los usuarios modifiquen el contenido de un control <xref:System.Windows.Controls.TextBox>, establezca el atributo <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> en **true**.  
  
 [!code-xml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 El atributo <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> afecta únicamente a los datos proporcionados por el usuario; no afecta al texto establecido en la descripción [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] de un control <xref:System.Windows.Controls.TextBox> ni al texto establecido mediante programación a través de la propiedad <xref:System.Windows.Controls.TextBox.Text%2A>.  
  
 El valor predeterminado de <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> es **false**.  
  
## Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)