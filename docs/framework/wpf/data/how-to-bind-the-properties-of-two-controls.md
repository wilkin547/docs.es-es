---
title: 'Cómo: Enlazar las propiedades de dos controles'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 66c759c28747de5b0288c906f5d51e4253fb7d52
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459171"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Cómo: Enlazar las propiedades de dos controles
En este ejemplo se muestra cómo enlazar la propiedad de un control con instancias a otro utilizando la propiedad <xref:System.Windows.Data.Binding.ElementName%2A>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo enlazar la propiedad <xref:System.Windows.Controls.Panel.Background%2A> de una <xref:System.Windows.Controls.Canvas> a la <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> propiedad de un <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Cuando se representa este ejemplo, tiene un aspecto similar a lo siguiente:  
  
![Captura de pantalla que muestra un cuadro combinado con el valor verde seleccionado y un cuadrado verde.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> La propiedad de destino de enlace (en este ejemplo, la propiedad <xref:System.Windows.Controls.Panel.Background%2A>) debe ser una propiedad de dependencia. Para obtener más información, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Especificación del origen de enlace](how-to-specify-the-binding-source.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
