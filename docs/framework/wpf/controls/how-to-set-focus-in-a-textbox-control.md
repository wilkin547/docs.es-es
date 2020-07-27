---
title: 'Cómo: Establecer el foco en un control TextBox'
description: Aprenda a usar el método Focus para establecer el foco en un control TextBox Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: e107c22a3c5b701e02cbc8506d10fa35ee15c79d
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168061"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a>Cómo: Establecer el foco en un control TextBox
En este ejemplo se muestra cómo utilizar el <xref:System.Windows.UIElement.Focus%2A> método para establecer el foco en un <xref:System.Windows.Controls.TextBox> control.  
  
## <a name="example"></a>Ejemplo  
 En el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplo siguiente se describe un <xref:System.Windows.Controls.TextBox> control simple denominado *tbFocusMe*  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se llama al <xref:System.Windows.UIElement.Focus%2A> método para establecer el foco en el <xref:System.Windows.Controls.TextBox> control con el nombre *tbFocusMe*.  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [Información general sobre TextBox](textbox-overview.md)
- [Información general sobre el control RichTextBox](richtextbox-overview.md)
