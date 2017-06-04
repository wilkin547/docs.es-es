---
title: "C&#243;mo: Crear un bot&#243;n que tenga una imagen | Microsoft Docs"
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
  - "Button (controles) [WPF], crear"
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Crear un bot&#243;n que tenga una imagen
En este ejemplo se muestra cómo incluir una imagen en un control <xref:System.Windows.Controls.Button>.  
  
## Ejemplo  
 En el ejemplo siguiente se crean dos controles <xref:System.Windows.Controls.Button>.  Un control <xref:System.Windows.Controls.Button> contiene texto y el otro una imagen.  La imagen está en una carpeta denominada datos, que es una subcarpeta de la carpeta de proyecto del ejemplo.  Cuando un usuario hace clic en el control <xref:System.Windows.Controls.Button> que tiene la imagen, cambian el fondo y el texto del otro <xref:System.Windows.Controls.Button>.  
  
 En este ejemplo, los controles <xref:System.Windows.Controls.Button> se crean mediante marcado, pero se usa código para escribir los controladores de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  
  
 [!code-xml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## Vea también  
 [Controles](../../../../docs/framework/wpf/controls/index.md)   
 [Biblioteca de controles](../../../../docs/framework/wpf/controls/control-library.md)