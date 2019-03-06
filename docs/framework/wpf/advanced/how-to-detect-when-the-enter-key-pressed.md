---
title: Procedimiento Detectar cuando la escriba tecla presionada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: 1796127d33087a3fd4504d03f175f8afe5323630
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351871"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Filtrar Detectar cuando la escriba tecla presionada
En este ejemplo se muestra cómo detectar cuándo el <xref:System.Windows.Input.Key.Enter> se presiona la tecla del teclado.  
  
 Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.  
  
## <a name="example"></a>Ejemplo  
 Cuando el usuario presiona el <xref:System.Windows.Input.Key.Enter> clave en el <xref:System.Windows.Controls.TextBox>, la entrada en el cuadro de texto aparece en otra área de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 La siguiente [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea la interfaz de usuario, que consta de un <xref:System.Windows.Controls.StackPanel>, un <xref:System.Windows.Controls.TextBlock>y un <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 El código subyacente siguiente crea el <xref:System.Windows.UIElement.KeyDown> controlador de eventos.  Si es la clave que se presiona el <xref:System.Windows.Input.Key.Enter> clave, se muestra un mensaje en el <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre acciones del usuario](input-overview.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)
