---
title: 'Cómo: Crear un efecto de activación mediante eventos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: d458d87586614093b35fcd73969dea04fe620351
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Cómo: Crear un efecto de activación mediante eventos
Este ejemplo muestra cómo cambiar el color de un elemento cuando el puntero del mouse entra y sale del área ocupada por el elemento.  
  
 Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.  
  
> [!NOTE]
>  En este ejemplo se muestra cómo usar los eventos, pero la manera recomendada para lograr este mismo efecto es utilizar un <xref:System.Windows.Trigger> en un estilo. Para obtener más información, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea la interfaz de usuario, que consta de <xref:System.Windows.Controls.Border> alrededor de una <xref:System.Windows.Controls.TextBlock>y asocia el <xref:System.Windows.Input.Mouse.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave> controladores de eventos para el <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Crea el código siguiente detrás de la <xref:System.Windows.UIElement.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave> controladores de eventos.  Cuando el puntero del mouse entra en el <xref:System.Windows.Controls.Border>, el fondo de la <xref:System.Windows.Controls.Border> se cambia a rojo.  Cuando el puntero del mouse deja el <xref:System.Windows.Controls.Border>, el fondo de la <xref:System.Windows.Controls.Border> vuelve a establecerse en blanco.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
