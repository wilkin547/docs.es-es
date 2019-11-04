---
title: 'Cómo: Aplicar FocusVisualStyle a un control'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: b44330ee7554f953389556bd62ff49db120b5db9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459809"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Cómo: Aplicar FocusVisualStyle a un control
En este ejemplo se muestra cómo crear un estilo visual de foco en los recursos y cómo aplicar el estilo a un control mediante la propiedad <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un estilo que crea una composición de control adicional que solo se aplica cuando ese control tiene el foco de teclado en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Esto se logra definiendo un estilo con un <xref:System.Windows.Controls.ControlTemplate>y haciendo referencia a ese estilo como un recurso al establecer la propiedad <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
 Un rectángulo externo similar a un borde se coloca fuera del área rectangular. A menos que se modifique de otro modo, el tamaño del estilo utiliza el <xref:System.Windows.FrameworkElement.ActualHeight%2A> y <xref:System.Windows.FrameworkElement.ActualWidth%2A> del control rectangular donde se aplica el estilo visual de foco. Este ejemplo establece los valores negativos del <xref:System.Windows.FrameworkElement.Margin%2A> para que el borde aparezca ligeramente fuera del control con foco.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 Un <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> es aditivo para cualquier estilo de plantilla de control que proceda de un estilo explícito o de un estilo de tema. el estilo principal de un control todavía se puede crear con una <xref:System.Windows.Controls.ControlTemplate> y establecer ese estilo en la propiedad <xref:System.Windows.FrameworkElement.Style%2A>.  
  
 Los estilos visuales de foco deben usarse de forma coherente en un tema o una interfaz de usuario, en lugar de usar uno diferente para cada elemento que pueda recibir el foco. Para obtener más información, vea [aplicar estilo a los controles y FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Aplicar estilo a los controles al recibir el foco y FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)
