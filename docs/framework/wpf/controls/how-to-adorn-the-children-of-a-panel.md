---
title: 'Cómo: Incluir adornos en los elementos secundarios de un panel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 4babbf1df57f340a3f6be218f213ad1c868ec9f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550224"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Cómo: Incluir adornos en los elementos secundarios de un panel
Este ejemplo muestra cómo enlazar mediante programación un adorno a los elementos secundarios de un determinado <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Ejemplo  
 Para enlazar un adorno a los elementos secundarios de un <xref:System.Windows.Controls.Panel>, siga estos pasos:  
  
1.  Declarar un nuevo <xref:System.Windows.Documents.AdornerLayer> objeto y llame al método el `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> método para buscar una capa de adornos para el elemento cuyos elementos secundarios se van a etiquetar.  
  
2.  Enumerar los elementos secundarios del elemento primario y llamada la <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar un adorno a cada elemento secundario.  
  
 En el ejemplo siguiente se enlaza la etiqueta contextual SimpleCircleAdorner (mostrada anteriormente) a los elementos secundarios de un <xref:System.Windows.Controls.StackPanel> denominado *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre adornos](../../../../docs/framework/wpf/controls/adorners-overview.md)
