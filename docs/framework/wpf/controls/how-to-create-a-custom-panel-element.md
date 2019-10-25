---
title: 'Cómo: Crear un elemento de panel personalizado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799147"
---
# <a name="how-to-create-a-custom-panel-element"></a>Cómo: Crear un elemento de panel personalizado
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo invalidar el comportamiento de diseño predeterminado del elemento <xref:System.Windows.Controls.Panel> y crear elementos de diseño personalizados que se derivan de <xref:System.Windows.Controls.Panel>.  
  
 En el ejemplo se define un elemento de <xref:System.Windows.Controls.Panel> personalizado simple denominado `PlotPanel`, que coloca los elementos secundarios de acuerdo con dos coordenadas x e y codificadas de forma rígida. En este ejemplo, `x` y `y` están establecidos en `50`; por lo tanto, todos los elementos secundarios se colocan en esa ubicación en los ejes x e y.  
  
 Para implementar los comportamientos de <xref:System.Windows.Controls.Panel> personalizados, en el ejemplo se usan los métodos <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>. Cada método devuelve los datos <xref:System.Windows.Size> necesarios para colocar y representar los elementos secundarios.  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Panel>
- [Información general sobre elementos Panel](panels-overview.md)
