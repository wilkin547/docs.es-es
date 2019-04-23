---
title: Procedimiento Especificar una posición emergente personalizada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: dc516f0eb1cfcbac6662497eb4019041eefec2a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200589"
---
# <a name="how-to-specify-a-custom-popup-position"></a>Procedimiento Especificar una posición emergente personalizada
En este ejemplo se muestra cómo especificar una posición personalizada para un <xref:System.Windows.Controls.Primitives.Popup> controlar cuándo el <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad está establecida en <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.  
  
## <a name="example"></a>Ejemplo  
 Cuando el <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad está establecida en <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, <xref:System.Windows.Controls.Primitives.Popup> llama a una instancia definida de la <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegar. Este delegado devuelve un conjunto de posibles puntos que son relativas a la esquina superior izquierda del área de destino y en la esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>. El <xref:System.Windows.Controls.Primitives.Popup> selección de ubicación se produce en el momento en que proporciona la mejor visibilidad.  
  
 El ejemplo siguiente muestra cómo definir la posición de un <xref:System.Windows.Controls.Primitives.Popup> estableciendo el <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. También muestra cómo crear y asignar un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegado con el fin de colocar el <xref:System.Windows.Controls.Primitives.Popup>.  El delegado de devolución de llamada devuelve dos <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objetos.  Si el <xref:System.Windows.Controls.Primitives.Popup> está oculto por un borde de la pantalla en la primera posición, el <xref:System.Windows.Controls.Primitives.Popup> se coloca en la segunda posición.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Para obtener un ejemplo completo, vea [Popup Placement Sample](https://go.microsoft.com/fwlink/?LinkID=160032).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Primitives.Popup>
- [Información general sobre el control Popup](popup-overview.md)
- [Temas "Cómo..."](popup-how-to-topics.md)
