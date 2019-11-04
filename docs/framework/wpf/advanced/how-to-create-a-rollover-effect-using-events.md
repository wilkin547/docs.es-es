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
ms.openlocfilehash: ccdc8aeb26b538814b2f9020e1e3a5b311fa5a99
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460163"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Cómo: Crear un efecto de activación mediante eventos
En este ejemplo se muestra cómo cambiar el color de un elemento a medida que el puntero del Mouse entra y sale del área ocupada por el elemento.  
  
 Este ejemplo consta de un archivo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y un archivo de código subyacente.  
  
> [!NOTE]
> En este ejemplo se muestra cómo utilizar los eventos, pero la manera recomendada de lograr este mismo efecto es usar una <xref:System.Windows.Trigger> en un estilo. Para obtener más información, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
## <a name="example"></a>Ejemplo  
 El código XAML siguiente crea la interfaz de usuario, que consta de <xref:System.Windows.Controls.Border> alrededor de un <xref:System.Windows.Controls.TextBlock>, y asocia los controladores de eventos <xref:System.Windows.Input.Mouse.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave> a la <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 El siguiente código subyacente crea los controladores de eventos <xref:System.Windows.UIElement.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave>.  Cuando el puntero del Mouse entra en el <xref:System.Windows.Controls.Border>, el fondo del <xref:System.Windows.Controls.Border> cambia a rojo.  Cuando el puntero del mouse sale del <xref:System.Windows.Controls.Border>, el fondo del <xref:System.Windows.Controls.Border> se vuelve a cambiar a blanco.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
