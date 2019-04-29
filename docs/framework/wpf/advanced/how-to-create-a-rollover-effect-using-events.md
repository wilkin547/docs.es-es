---
title: Procedimiento Crear un efecto de sustitución mediante eventos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 87740a215136863199d962a2704cf691f27fc3bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776654"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Procedimiento Crear un efecto de sustitución mediante eventos
En este ejemplo se muestra cómo cambiar el color de un elemento cuando el puntero del mouse entra y sale del área ocupado por el elemento.  
  
 Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.  
  
> [!NOTE]
>  Este ejemplo muestra cómo usar los eventos, pero la manera recomendada para lograr este efecto mismo es usar un <xref:System.Windows.Trigger> en un estilo. Para obtener más información, consulte [Aplicar estilos y plantillas](../controls/styling-and-templating.md).  
  
## <a name="example"></a>Ejemplo  
 La siguiente [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea la interfaz de usuario, que consta de <xref:System.Windows.Controls.Border> en torno a un <xref:System.Windows.Controls.TextBlock>y adjunta el <xref:System.Windows.Input.Mouse.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave> controladores de eventos para el <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 El código subyacente siguiente crea el <xref:System.Windows.UIElement.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave> controladores de eventos.  Cuando el puntero del mouse entra en el <xref:System.Windows.Controls.Border>, el fondo de la <xref:System.Windows.Controls.Border> se cambia a rojo.  Cuando el puntero del mouse abandona el <xref:System.Windows.Controls.Border>, el fondo de la <xref:System.Windows.Controls.Border> se vuelve a cambiar en blanco.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
