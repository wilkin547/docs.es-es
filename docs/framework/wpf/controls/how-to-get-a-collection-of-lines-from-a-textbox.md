---
title: "C&#243;mo: Obtener una colecci&#243;n de l&#237;neas de un control TextBox | Microsoft Docs"
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
  - "líneas, obtener colección de"
  - "TextBox (control), obtener colección de líneas"
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Obtener una colecci&#243;n de l&#237;neas de un control TextBox
En este ejemplo se muestra cómo obtener una colección de líneas de texto de un control <xref:System.Windows.Controls.TextBox>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un método simple que toma <xref:System.Windows.Controls.TextBox> como argumento y devuelve una colección <xref:System.Collections.Specialized.StringCollection> que contiene las líneas de texto del control **TextBox**.  Se utiliza la propiedad <xref:System.Windows.Controls.TextBox.LineCount%2A> para determinar cuántas líneas contiene actualmente el control **TextBox** y, a continuación, se utiliza el método <xref:System.Windows.Controls.TextBox.GetLineText%2A> para extraer cada línea y agregarla a la colección de líneas.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)