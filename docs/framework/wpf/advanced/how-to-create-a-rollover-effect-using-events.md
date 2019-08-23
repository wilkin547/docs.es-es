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
ms.openlocfilehash: 3996a3b9bb976dd5f2e5b675de3894bbaba7d9d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960385"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Procedimiento Crear un efecto de sustitución mediante eventos
En este ejemplo se muestra cómo cambiar el color de un elemento a medida que el puntero del Mouse entra y sale del área ocupada por el elemento.  
  
 Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.  
  
> [!NOTE]
> En este ejemplo se muestra cómo utilizar los eventos, pero la manera recomendada de lograr este mismo efecto es usar <xref:System.Windows.Trigger> un en un estilo. Para obtener más información, consulte [Aplicar estilos y plantillas](../controls/styling-and-templating.md).  
  
## <a name="example"></a>Ejemplo  
 Lo siguiente [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea la interfaz de usuario, que se <xref:System.Windows.Controls.Border> compone de <xref:System.Windows.Controls.TextBlock>un, y asocia los <xref:System.Windows.Input.Mouse.MouseEnter> controladores <xref:System.Windows.UIElement.MouseLeave> de eventos y a <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 El siguiente código subyacente crea los <xref:System.Windows.UIElement.MouseEnter> controladores <xref:System.Windows.UIElement.MouseLeave> de eventos y.  Cuando el puntero del Mouse entra <xref:System.Windows.Controls.Border>en, el fondo <xref:System.Windows.Controls.Border> de se cambia a rojo.  Cuando el puntero del mouse sale <xref:System.Windows.Controls.Border>de, el fondo <xref:System.Windows.Controls.Border> de se vuelve a cambiar a blanco.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
