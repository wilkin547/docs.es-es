---
title: "Cómo: Especificar una posición emergente personalizada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ab9baca1103adf8de96204bdb1b3353a5456b94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-a-custom-popup-position"></a>Cómo: Especificar una posición emergente personalizada
Este ejemplo muestra cómo especificar una posición personalizada para un <xref:System.Windows.Controls.Primitives.Popup> controlar cuándo el <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad está establecida en <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.  
  
## <a name="example"></a>Ejemplo  
 Cuando el <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad está establecida en <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, el <xref:System.Windows.Controls.Primitives.Popup> llama a una instancia definida de los <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegar. Este delegado devuelve un conjunto de posibles puntos que son relativas a la esquina superior izquierda del área de destino y la esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>. El <xref:System.Windows.Controls.Primitives.Popup> selección de ubicación se produce en el punto que proporciona la mejor visibilidad.  
  
 En el ejemplo siguiente se muestra cómo definir la posición de un <xref:System.Windows.Controls.Primitives.Popup> estableciendo la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. También muestra cómo crear y asignar una <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegado con el fin de colocar el <xref:System.Windows.Controls.Primitives.Popup>.  El delegado de devolución de llamada devuelve dos <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objetos.  Si el <xref:System.Windows.Controls.Primitives.Popup> está oculto por un borde de la pantalla en la primera posición, el <xref:System.Windows.Controls.Primitives.Popup> se coloca en la segunda posición.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Para obtener un ejemplo completo, vea [Popup Placement Sample](http://go.microsoft.com/fwlink/?LinkID=160032).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [Información general sobre el control Popup](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)
