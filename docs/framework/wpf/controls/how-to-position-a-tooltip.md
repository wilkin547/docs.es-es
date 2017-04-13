---
title: "C&#243;mo: Situar una informaci&#243;n sobre herramientas | Microsoft Docs"
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
  - "colocar controles ToolTip"
  - "ToolTip (control), colocar"
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Situar una informaci&#243;n sobre herramientas
En este ejemplo se muestra cómo especificar la posición de una información sobre herramientas en la pantalla.  
  
## Ejemplo  
 Puede colocar una información sobre herramientas mediante el uso de un conjunto de cinco propiedades que se definen en las clases <xref:System.Windows.Controls.ToolTip> y <xref:System.Windows.Controls.ToolTipService>.  En la tabla siguiente se muestran estos dos conjuntos de cinco propiedades y se proporcionan vínculos a la documentación de referencia de acuerdo con la clase.  
  
### Propiedades de información sobre herramientas por clase  
  
|Propiedades de la clase <xref:System.Windows.Controls.ToolTip?displayProperty=fullName>|Propiedades de la clase <xref:System.Windows.Controls.ToolTipService?displayProperty=fullName>|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=fullName>|  
  
 Si define el contenido de una información sobre herramientas mediante un objeto <xref:System.Windows.Controls.ToolTip>, puede usar las propiedades de cualquiera de las dos clases, pero las propiedades de <xref:System.Windows.Controls.ToolTipService> tienen prioridad.  Use las propiedades de <xref:System.Windows.Controls.ToolTipService> para informaciones sobre herramientas que no se definen como objetos <xref:System.Windows.Controls.ToolTip>.  
  
 Las ilustraciones siguientes muestran cómo colocar una información sobre herramientas mediante estas propiedades.  Aunque los ejemplos de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] de estas ilustraciones muestran cómo establecer las propiedades que son definidas por la clase <xref:System.Windows.Controls.ToolTip>, las propiedades correspondientes de la clase <xref:System.Windows.Controls.ToolTipService> siguen las mismas reglas de diseño.  Para obtener más información acerca de los posibles valores de la propiedad Placement, vea [Posición de un control Popup](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  
  
 ![Colocación de ToolTip](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
Posicionamiento de la información sobre herramientas mediante la propiedad Placement  
  
 ![Colocar ToolTip mediante un rectángulo de colocación](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
Posicionamiento de la información sobre herramientas mediante las propiedades Placement y PlacementRectangle  
  
 ![Diagrama de colocación de ToolTip](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
Posicionamiento de la información sobre herramientas mediante las propiedades Placement, PlacementRectangle y Offset  
  
 En el ejemplo siguiente se muestra cómo usar las propiedades de <xref:System.Windows.Controls.ToolTip> para especificar la posición de una información sobre herramientas cuyo contenido es un objeto <xref:System.Windows.Controls.ToolTip>.  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 En el ejemplo siguiente se muestra cómo usar las propiedades de <xref:System.Windows.Controls.ToolTipService> para especificar la posición de una información sobre herramientas cuyo contenido no es un objeto <xref:System.Windows.Controls.ToolTip>.  
  
 [!code-xml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## Vea también  
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)   
 [Información general de información sobre herramientas](../../../../docs/framework/wpf/controls/tooltip-overview.md)   
 [Use the ContextMenuService and ToolTipService](http://msdn.microsoft.com/es-es/809b0e9c-d612-4cda-b8af-1a698c68f4d1)