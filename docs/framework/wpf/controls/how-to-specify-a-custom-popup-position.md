---
title: 'Cómo: Especificar una posición emergente personalizada'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: b48dedc044b418062642af5c5bb40afab78a3c97
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635747"
---
# <a name="how-to-specify-a-custom-popup-position"></a>Cómo: Especificar una posición emergente personalizada
En este ejemplo se muestra cómo <xref:System.Windows.Controls.Primitives.Popup> especificar <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> una posición <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>personalizada para un control cuando la propiedad se establece en .  
  
## <a name="example"></a>Ejemplo  
 Cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> la propiedad <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>se <xref:System.Windows.Controls.Primitives.Popup> establece en , <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> las llamadas a una instancia definida del delegado. Este delegado devuelve un conjunto de posibles puntos que son relativos a la esquina <xref:System.Windows.Controls.Primitives.Popup>superior izquierda del área de destino y la esquina superior izquierda del archivo . La <xref:System.Windows.Controls.Primitives.Popup> colocación se produce en el punto que proporciona la mejor visibilidad.  
  
 En el ejemplo siguiente se muestra <xref:System.Windows.Controls.Primitives.Popup> cómo <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> definir <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>la posición de a estableciendo la propiedad en . También muestra cómo crear y <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> asignar un delegado <xref:System.Windows.Controls.Primitives.Popup>para posicionar el archivo .  El delegado de <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> devolución de llamada devuelve dos objetos.  Si <xref:System.Windows.Controls.Primitives.Popup> el está oculto por un borde <xref:System.Windows.Controls.Primitives.Popup> de pantalla en la primera posición, el se coloca en la segunda posición.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Para ver el ejemplo completo, consulte Ejemplo de [ubicación emergente](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Primitives.Popup>
- [Descripción general de Popup](popup-overview.md)
- [Artículos de información como](popup-how-to-topics.md)
