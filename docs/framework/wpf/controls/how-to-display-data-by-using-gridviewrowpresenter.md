---
title: "C&#243;mo: Mostrar datos mediante GridViewRowPresenter | Microsoft Docs"
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
  - "mostrar datos mediante GridViewRowPresenter"
  - "GridViewRowPresenter"
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Mostrar datos mediante GridViewRowPresenter
En este ejemplo se muestra cómo usar los objetos <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter> para mostrar los datos en columnas.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar un objeto <xref:System.Windows.Controls.GridViewColumnCollection> que muestre las propiedades <xref:System.DateTime.DayOfWeek%2A> y <xref:System.DateTime.Year%2A> de un objeto <xref:System.DateTime> mediante el uso de objetos <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter>.  En el ejemplo también se define un <xref:System.Windows.Style> para la propiedad <xref:System.Windows.Controls.GridViewColumn.Header%2A> de <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## Vea también  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>   
 <xref:System.Windows.Controls.GridViewRowPresenter>   
 <xref:System.Windows.Controls.GridViewColumnCollection>   
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)