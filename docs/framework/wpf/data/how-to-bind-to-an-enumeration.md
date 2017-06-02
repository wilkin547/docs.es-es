---
title: "C&#243;mo: Enlazar a una enumeraci&#243;n | Microsoft Docs"
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
  - "enlazar datos, enumeración"
  - "enlace de datos, enumeración"
  - "enumeración"
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Enlazar a una enumeraci&#243;n
En este ejemplo se muestra cómo enlazar a una enumeración enlazando al método GetValues de la misma.  
  
## Ejemplo  
 En el ejemplo siguiente, <xref:System.Windows.Controls.ListBox> muestra la lista de valores de <xref:System.Windows.HorizontalAlignment> de la enumeración mediante el enlace de datos.  <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.Button> están enlazados de tal modo que puede cambiar el valor de propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> de <xref:System.Windows.Controls.Button> seleccionando un valor en <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## Vea también  
 [Enlazar a un método](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)