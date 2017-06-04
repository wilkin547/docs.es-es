---
title: "C&#243;mo: Enlazar las propiedades de dos controles | Microsoft Docs"
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
  - "enlazar propiedades de dos controles"
  - "controles, enlazar propiedades de"
  - "enlace de datos, enlazar propiedades de dos controles"
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Enlazar las propiedades de dos controles
En este ejemplo se muestra cómo enlazar la propiedad de un control del que se ha creado una instancia con la de otro, utilizando la propiedad <xref:System.Windows.Data.Binding.ElementName%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo enlazar la propiedad <xref:System.Windows.Controls.Panel.Background%2A> de un control <xref:System.Windows.Controls.Canvas> con la propiedad <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> de un control <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Cuando se representa este ejemplo tiene un aspecto similar a lo siguiente:  
  
 ![Lienzo con un fondo verde](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.png "DataBindingBindingDPsSample")  
  
 **Nota** La propiedad [de destino del enlace](GTMT) \(en este ejemplo, la propiedad <xref:System.Windows.Controls.Panel.Background%2A>\) debe ser una [propiedad de dependencia](GTMT).  Para obtener más información, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
## Vea también  
 [Especificar el origen de enlace](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)