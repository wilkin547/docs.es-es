---
title: "C&#243;mo: Crear un estilo para un encabezado de columna de GridView arrastrado | Microsoft Docs"
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
  - "ListView (controles), aplicar estilos"
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Crear un estilo para un encabezado de columna de GridView arrastrado
En este ejemplo se muestra cómo cambiar la apariencia de un control <xref:System.Windows.Controls.GridViewColumnHeader> arrastrado cuando el usuario cambia la posición de una columna.  
  
## Ejemplo  
 Al arrastrar un encabezado de columna hacia otra ubicación en un control <xref:System.Windows.Controls.ListView> que utiliza <xref:System.Windows.Controls.GridView> para el modo de vista, la columna se mueve a la nueva posición.  Mientras se arrastra el encabezado de columna, aparece una copia flotante de éste, además del encabezado original.  Un encabezado de columna de un control <xref:System.Windows.Controls.GridView> se representa mediante un objeto <xref:System.Windows.Controls.GridViewColumnHeader>.  
  
 Para personalizar la apariencia de los encabezados flotante y original, puede establecer <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> de modo que modifique el valor de <xref:System.Windows.Style> correspondiente a <xref:System.Windows.Controls.GridViewColumnHeader>.  La propiedad <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> se aplica cuando el valor de propiedad <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> es `true` y el valor de propiedad <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> es <xref:System.Windows.Controls.GridViewColumnHeaderRole>.  
  
 Cuando el usuario presiona el botón del mouse y lo mantiene presionado mientras el mouse se detiene en <xref:System.Windows.Controls.GridViewColumnHeader>, el valor de propiedad <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> cambia a `true`.  Igualmente, cuando el usuario comienza la operación de arrastre, la propiedad <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> cambia a <xref:System.Windows.Controls.GridViewColumnHeaderRole>.  
  
 En el ejemplo siguiente se muestra cómo establecer <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> para cambiar los colores de <xref:System.Windows.Controls.Control.Foreground%2A> y <xref:System.Windows.Controls.Control.Background%2A> de los encabezados original y flotante cuando el usuario arrastra una columna a una nueva posición.  
  
 [!code-xml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## Vea también  
 <xref:System.Windows.Controls.GridViewColumnHeader>   
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>   
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)