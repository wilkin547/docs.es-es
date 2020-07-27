---
title: 'Cómo: Colocar el cursor al principio o al final del texto de un control'
description: Obtenga información sobre cómo colocar el cursor al principio o al final del contenido de texto de un control TextBox de Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: afe8b11d032b5d61fa91cbf324f02cd8415d2ea8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167507"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a>Cómo: Colocar el cursor al principio o al final del texto de un control
En este ejemplo se muestra cómo colocar el cursor al principio o al final del contenido de texto de un <xref:System.Windows.Controls.TextBox> control.  
  
## <a name="example"></a>Ejemplo  
 En el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] código siguiente se describe un <xref:System.Windows.Controls.TextBox> control y se le asigna un nombre.  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a>Ejemplo  
 Para colocar el cursor al principio del contenido de un <xref:System.Windows.Controls.TextBox> control, llame al <xref:System.Windows.Controls.TextBox.Select%2A> método y especifique la posición inicial de la selección de 0, y una longitud de selección de 0.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a>Ejemplo  
 Para colocar el cursor al final del contenido de un <xref:System.Windows.Controls.TextBox> control, llame al <xref:System.Windows.Controls.TextBox.Select%2A> método y especifique la posición inicial de la selección igual a la longitud del contenido de texto y una longitud de selección de 0.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre TextBox](textbox-overview.md)
- [Información general sobre el control RichTextBox](richtextbox-overview.md)
