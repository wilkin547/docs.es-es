---
title: "C&#243;mo: Especificar una posici&#243;n emergente personalizada | Microsoft Docs"
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
  - "Popup (control), especificar una posición personalizada"
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Especificar una posici&#243;n emergente personalizada
En este ejemplo se muestra cómo especificar una posición personalizada para un control <xref:System.Windows.Controls.Primitives.Popup> cuando la propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> está establecida en <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
## Ejemplo  
 Cuando la propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> está establecida en <xref:System.Windows.Controls.Primitives.PlacementMode>, <xref:System.Windows.Controls.Primitives.Popup> llama a una instancia definida del delegado <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.  Este delegado devuelve un conjunto de puntos posibles relativos a la esquina superior izquierda del área de destino y a la esquina superior izquierda de <xref:System.Windows.Controls.Primitives.Popup>.  La colocación de <xref:System.Windows.Controls.Primitives.Popup> tiene lugar en el punto que proporciona la mejor visibilidad.  
  
 En el ejemplo siguiente se muestra cómo definir la posición de <xref:System.Windows.Controls.Primitives.Popup> estableciendo la propiedad <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> en <xref:System.Windows.Controls.Primitives.PlacementMode>.  También se muestra cómo crear y asignar un delegado <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> para colocar el control <xref:System.Windows.Controls.Primitives.Popup>.  El delegado de devolución de llamada devuelve dos objetos <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>.  Si un borde de la pantalla oculta el control <xref:System.Windows.Controls.Primitives.Popup> en la primera posición, éste se coloca en la segunda posición.  
  
 [!code-xml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Para obtener el ejemplo completo, vea [Popup Placement Sample](http://go.microsoft.com/fwlink/?LinkID=160032).  
  
## Vea también  
 <xref:System.Windows.Controls.Primitives.Popup>   
 [Información general sobre el control Popup](../../../../docs/framework/wpf/controls/popup-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)