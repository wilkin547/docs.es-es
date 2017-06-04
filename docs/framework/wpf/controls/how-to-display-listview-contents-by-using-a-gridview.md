---
title: "C&#243;mo: Mostrar el contenido de ListView mediante un control GridView | Microsoft Docs"
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
  - "GridView, mostrar el contenido de ListView"
  - "ListView (controles), mostrar contenido con GridView"
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Mostrar el contenido de ListView mediante un control GridView
En este ejemplo se muestra cómo definir un modo de vista de <xref:System.Windows.Controls.GridView> para un control <xref:System.Windows.Controls.ListView>.  
  
## Ejemplo  
 Puede definir el modo de vista de <xref:System.Windows.Controls.GridView> especificando objetos <xref:System.Windows.Controls.GridViewColumn>.  En el ejemplo siguiente se muestra cómo definir objetos <xref:System.Windows.Controls.GridViewColumn> que se enlazan al contenido de datos que se especifica para el control <xref:System.Windows.Controls.ListView>.  En este ejemplo de <xref:System.Windows.Controls.GridView> se especifican tres objetos <xref:System.Windows.Controls.GridViewColumn> que se asignan a los campos `FirstName`, `LastName` y `EmployeeNumber` del origen `EmployeeInfoDataSource` establecido como la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del control <xref:System.Windows.Controls.ListView>.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 En la ilustración siguiente se muestra cómo aparece este ejemplo.  
  
 ![ListView con resultado GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
## Vea también  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)