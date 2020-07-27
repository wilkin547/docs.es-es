---
title: 'Cómo: Detectar cuándo se presiona la tecla ENTRAR'
description: Detecta cuándo se selecciona la tecla entrar en el teclado en Windows Presentation Foundation. Este ejemplo consta de XAML y un archivo de código subyacente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a955f52ec7bf93b32c70259b27fb51747664ac2e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163184"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Cómo: Detectar cuándo se presiona la tecla ENTRAR
Este ejemplo muestra cómo detectar cuándo <xref:System.Windows.Input.Key.Enter> se presiona la tecla en el teclado.  
  
 Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.  
  
## <a name="example"></a>Ejemplo  
 Cuando el usuario presiona la <xref:System.Windows.Input.Key.Enter> tecla en la <xref:System.Windows.Controls.TextBox> , la entrada en el cuadro de texto aparece en otra área de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] .  
  
 En el código XAML siguiente se crea la interfaz de usuario, que consta de un <xref:System.Windows.Controls.StackPanel> , un <xref:System.Windows.Controls.TextBlock> y un <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 El siguiente código subyacente crea el <xref:System.Windows.UIElement.KeyDown> controlador de eventos.  Si la tecla que se presiona es la <xref:System.Windows.Input.Key.Enter> tecla, se muestra un mensaje en el <xref:System.Windows.Controls.TextBlock> .  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre acciones del usuario](input-overview.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)
