---
title: Procedimiento Aplicar un FocusVisualStyle a un control
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: 53d4984946143c15c4a2b71095529fb5ee7de4b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133554"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Procedimiento Aplicar un FocusVisualStyle a un control
En este ejemplo se muestra cómo crear un estilo visual de foco en recursos y aplicar el estilo a un control, mediante el <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un estilo que crea la composición del control adicional que solo se aplica cuando ese control recibe el foco del teclado en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Esto se logra definiendo un estilo con un <xref:System.Windows.Controls.ControlTemplate>, a continuación, hacer referencia a ese estilo como un recurso al establecer el <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> propiedad.  
  
 Un rectángulo externo que parece un borde se coloca fuera del área rectangular. A menos que modifique en caso contrario, el tamaño del estilo usa la <xref:System.Windows.FrameworkElement.ActualHeight%2A> y <xref:System.Windows.FrameworkElement.ActualWidth%2A> del control rectangular donde se aplica el estilo visual de foco. Este ejemplo establece los valores negativos para la <xref:System.Windows.FrameworkElement.Margin%2A> para que el borde parezca ligeramente fuera del control con el foco.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 Un <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> es aditiva para cualquier estilo de plantilla de control que se incluye desde un estilo explícito o un estilo de tema; el estilo de un control principal todavía se puede crear mediante el uso de un <xref:System.Windows.Controls.ControlTemplate> y si ese estilo se establece en el <xref:System.Windows.FrameworkElement.Style%2A> propiedad.  
  
 Los estilos visuales deben usarse de forma coherente en un tema o una interfaz de usuario, el foco en lugar de usar otro diferente para cada elemento puede recibir el foco. Para obtener más información, consulte [aplicar estilo a controles y FocusVisualStyle foco](styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Aplicar estilos y plantillas](../controls/styling-and-templating.md)
- [Aplicar estilo a los controles al recibir el foco y FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)
