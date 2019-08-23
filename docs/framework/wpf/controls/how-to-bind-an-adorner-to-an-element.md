---
title: Procedimiento Enlazar un adorno a un elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: e8c7eb929042bfe1455bfc9bf459fc466de5c397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923497"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>Procedimiento Enlazar un adorno a un elemento
En este ejemplo se muestra cómo enlazar un adorno a un especificado <xref:System.Windows.UIElement>mediante programación.  
  
## <a name="example"></a>Ejemplo  
 Para enlazar un adorno a un determinado <xref:System.Windows.UIElement>, siga estos pasos:  
  
1. Llame al <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> <xref:System.Windows.Documents.AdornerLayer> método para obtener un objeto para el <xref:System.Windows.UIElement> elemento que se va a adornar. `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>avanza el árbol visual, comenzando en el **UIElement**especificado y devuelve la primera capa de adornos que encuentra. (Si no se encuentra ninguna capa de adornos, el método devuelve null).  
  
2. Llame al método para enlazar el adorno al UIElement de destino. <xref:System.Windows.Documents.AdornerLayer.Add%2A>  
  
 En el ejemplo siguiente se enlaza un adorno simplecircleadorner (mostrado anteriormente) a <xref:System.Windows.Controls.TextBox> un denominado *mytextbox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre adornos](adorners-overview.md)
