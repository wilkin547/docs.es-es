---
title: Procedimiento Detectar cuándo se presiona la tecla entrar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: e2337826077c836696937f91541d6d261f1270aa
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004826"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Procedimiento Detectar cuándo se presiona la tecla entrar
Este ejemplo muestra cómo detectar cuándo se presiona la tecla <xref:System.Windows.Input.Key.Enter> en el teclado.  
  
 Este ejemplo consta de un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y un archivo de código subyacente.  
  
## <a name="example"></a>Ejemplo  
 Cuando el usuario presiona la tecla <xref:System.Windows.Input.Key.Enter> en el <xref:System.Windows.Controls.TextBox>, la entrada en el cuadro de texto aparece en otra área de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 El código XAML siguiente crea la interfaz de usuario, que consta de un <xref:System.Windows.Controls.StackPanel>, un <xref:System.Windows.Controls.TextBlock> y un <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 El siguiente código subyacente crea el controlador de eventos <xref:System.Windows.UIElement.KeyDown>.  Si la tecla que se presiona es la tecla <xref:System.Windows.Input.Key.Enter>, se muestra un mensaje en el <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre acciones del usuario](input-overview.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)
