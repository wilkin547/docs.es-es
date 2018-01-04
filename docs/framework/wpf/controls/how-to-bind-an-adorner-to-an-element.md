---
title: "Cómo: Enlazar un adorno a un elemento"
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
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3c657cde9da19f8ebc6b6d4d05077ed027781b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>Cómo: Enlazar un adorno a un elemento
Este ejemplo muestra cómo enlazar mediante programación un adorno a un determinado <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Ejemplo  
 Para enlazar un adorno a un determinado <xref:System.Windows.UIElement>, siga estos pasos:  
  
1.  Llamar a la `static` método <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> para obtener un <xref:System.Windows.Documents.AdornerLayer> de objeto para el <xref:System.Windows.UIElement> que se va a adornar. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>recorre el árbol visual, empezando en el índice especificado **UIElement**y devuelve la primera capa de adornos que encuentra. (Si no se encuentra ninguna capa de adornos, el método devuelve null).  
  
2.  Llame a la <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar el adorno al destino **UIElement**.  
  
 En el ejemplo siguiente se enlaza la etiqueta contextual SimpleCircleAdorner (mostrada anteriormente) a un <xref:System.Windows.Controls.TextBox> denominado *myTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre adornos](../../../../docs/framework/wpf/controls/adorners-overview.md)
