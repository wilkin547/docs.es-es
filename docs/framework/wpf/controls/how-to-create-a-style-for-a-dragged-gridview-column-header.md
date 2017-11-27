---
title: "Cómo: Crear un estilo para un encabezado de columna de GridView arrastrado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 503683de875b8853e219139800eef2a5417a1574
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a>Cómo: Crear un estilo para un encabezado de columna de GridView arrastrado
Este ejemplo muestra cómo cambiar la apariencia de un arrastrado <xref:System.Windows.Controls.GridViewColumnHeader> cuando el usuario cambia la posición de una columna.  
  
## <a name="example"></a>Ejemplo  
 Cuando se arrastra un encabezado de columna a otra ubicación en un <xref:System.Windows.Controls.ListView> que utiliza <xref:System.Windows.Controls.GridView> para el modo de vista, la columna se mueve a la nueva posición. Mientras arrastra el encabezado de columna, aparece una copia flotante del encabezado además del encabezado original. Un encabezado de columna en una <xref:System.Windows.Controls.GridView> se representa mediante un <xref:System.Windows.Controls.GridViewColumnHeader> objeto.  
  
 Para personalizar la apariencia de los encabezados de punto flotantes y originales, puede establecer <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> para modificar el <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>. Estos <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> se aplican cuando la <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> es el valor de la propiedad `true` y <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> es el valor de la propiedad <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 Cuando el usuario presiona el botón del mouse y se mantiene presionada mientras el mouse hace una pausa en la <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> cambia el valor de propiedad para `true`. Del mismo modo, cuando el usuario comienza la operación de arrastre, el <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> propiedad cambia a <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 En el ejemplo siguiente se muestra cómo establecer <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> para cambiar la <xref:System.Windows.Controls.Control.Foreground%2A> y <xref:System.Windows.Controls.Control.Background%2A> colores de los encabezados originales y de punto flotantes cuando el usuario arrastra una columna a una nueva posición.  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Temas de procedimientos](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
