---
title: "C&#243;mo: Colocar un men&#250; contextual personalizado en un control RichTextBox | Microsoft Docs"
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
  - "menús contextuales personalizados, posición"
  - "colocar menús contextuales personalizados"
  - "RichTextBox (control), colocar menús contextuales personalizados"
  - "menús contextuales, posición"
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Colocar un men&#250; contextual personalizado en un control RichTextBox
Este ejemplo muestra cómo colocar un menú contextual personalizado para un <xref:System.Windows.Controls.RichTextBox>.  
  
 Cuando se implementa un menú contextual personalizado para un **RichTextBox**, usted es responsable de controlar la posición del menú contextual.  De forma predeterminada, se abre un menú contextual personalizado en el centro de la **RichTextBox**.  
  
## <a name="example"></a>Ejemplo  
 Para invalidar el comportamiento de colocación predeterminado, agregue un agente de escucha para el <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> eventos.  En el ejemplo siguiente se muestra cómo hacerlo mediante programación.  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una implementación correspondiente <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> escucha de eventos.  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a>Vea también  
 [Información general del control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)