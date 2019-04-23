---
title: Procedimiento Crear un elemento de panel personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: d4fc9d76ada9f27bd52619280b323691af9382c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139573"
---
# <a name="how-to-create-a-custom-panel-element"></a>Procedimiento Crear un elemento de panel personalizado
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo invalidar el comportamiento de diseño predeterminado de la <xref:System.Windows.Controls.Panel> elemento y crear elementos de diseño personalizado que se derivan <xref:System.Windows.Controls.Panel>.  
  
 El ejemplo define un simple personalizado <xref:System.Windows.Controls.Panel> elemento llamado `PlotPanel`, que coloca los elementos secundarios según dos rígida-coordenadas x e y-. En este ejemplo, `x` y `y` están establecidos en `50`; por lo tanto, todos los elementos secundarios se colocan en esa ubicación en la x e y ejes.  
  
 Para implementar personalizado <xref:System.Windows.Controls.Panel> comportamientos, el ejemplo utiliza la <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos. Cada método devuelve el <xref:System.Windows.Size> datos necesarios para colocar y representar los elementos secundarios.  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Panel>
- [Información general sobre elementos Panel](panels-overview.md)
- [Crear un ejemplo de Panel de ajuste de contenido personalizado](https://go.microsoft.com/fwlink/?LinkID=159979)
