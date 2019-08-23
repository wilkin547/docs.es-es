---
title: Procedimiento Agregar adornos a elementos secundarios de un panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 739ccaa0273e66c4650c35217a1156d64336dbbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923524"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Procedimiento Agregar adornos a elementos secundarios de un panel
En este ejemplo se muestra cómo enlazar un adorno mediante programación a los elementos secundarios de <xref:System.Windows.Controls.Panel>un especificado.  
  
## <a name="example"></a>Ejemplo  
 Para enlazar un adorno a los elementos secundarios de <xref:System.Windows.Controls.Panel>, siga estos pasos:  
  
1. Declare un <xref:System.Windows.Documents.AdornerLayer> nuevo objeto y `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> llame al método para buscar una capa de adornos para el elemento cuyos elementos secundarios se van a adornar.  
  
2. Enumere los elementos secundarios del elemento primario y llame <xref:System.Windows.Documents.AdornerLayer.Add%2A> al método para enlazar un adorno a cada elemento secundario.  
  
 En el ejemplo siguiente se enlaza un adorno simplecircleadorner (mostrado anteriormente) a los elementos secundarios <xref:System.Windows.Controls.StackPanel> de un *myStackPanel*con nombre.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
> En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre adornos](adorners-overview.md)
