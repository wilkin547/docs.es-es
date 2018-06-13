---
title: 'Cómo: Aplicar FocusVisualStyle a un control'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: 34af5ca6f5ce6b3714d7d7e0d707841cdfc61349
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543737"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Cómo: Aplicar FocusVisualStyle a un control
Este ejemplo muestra cómo crear un estilo visual del foco en recursos y aplique el estilo a un control utilizando la <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un estilo que crea la composición del control adicional que solo se aplica cuando ese control recibe el foco del teclado en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Esto se logra mediante la definición de un estilo con un <xref:System.Windows.Controls.ControlTemplate>, a continuación, hacer referencia a ese estilo como un recurso al establecer el <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> propiedad.  
  
 Un rectángulo externo que parece un borde se coloca fuera del área rectangular. A menos que modifique en caso contrario, el tamaño del estilo utiliza el <xref:System.Windows.FrameworkElement.ActualHeight%2A> y <xref:System.Windows.FrameworkElement.ActualWidth%2A> del control rectangular que se aplica el estilo visual del foco. Este ejemplo establece los valores negativos para la <xref:System.Windows.FrameworkElement.Margin%2A> para hacer que el borde parezca ligeramente fuera del control tiene el foco.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> es suma para cualquier estilo de plantilla de control que se incluye desde un estilo explícito o un estilo de tema; el estilo de un control principal todavía se puede crear mediante el uso de un <xref:System.Windows.Controls.ControlTemplate> y establecer ese estilo en el <xref:System.Windows.FrameworkElement.Style%2A> propiedad.  
  
 Foco estilos visuales deben utilizarse de manera coherente a través de un tema o una interfaz de usuario, en lugar de utilizar uno diferente para cada elemento puede recibir el foco. Para obtener más información, consulte [aplicación de estilos para se centran en los controles y FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Aplicar estilo a los controles al recibir el foco y FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)
