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
ms.openlocfilehash: 4943121aaf8ee6524be3fc9004eafee4fa92e527
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353925"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>Filtrar Enlazar un adorno a un elemento
En este ejemplo se muestra cómo enlazar mediante programación un adorno a un determinado <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Ejemplo  
 Para enlazar un adorno a un determinado <xref:System.Windows.UIElement>, siga estos pasos:  
  
1.  Llame a la `static` método <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> para obtener un <xref:System.Windows.Documents.AdornerLayer> de objeto para el <xref:System.Windows.UIElement> que se va a adornar. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> recorre el árbol visual, empezando en el índice especificado **UIElement**y devuelve la primera capa de adornos que encuentra. (Si no se encuentra ninguna capa de adornos, el método devuelve null).  
  
2.  Llame a la <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar el adorno al destino **UIElement**.  
  
 El ejemplo siguiente enlaza el adorno SimpleCircleAdorner (mostrado anteriormente) a un <xref:System.Windows.Controls.TextBox> denominado *myTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.  
  
## <a name="see-also"></a>Vea también
- [Información general sobre adornos](adorners-overview.md)
