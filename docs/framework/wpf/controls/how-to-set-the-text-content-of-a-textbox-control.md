---
title: Filtrar Establecer el contenido de texto de un control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: da91e27b804d649f5b8010bc9d7c074425be26f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212198"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Filtrar Establecer el contenido de texto de un control TextBox
En este ejemplo se muestra cómo usar el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad para establecer el contenido inicial del texto de un <xref:System.Windows.Controls.TextBox> control.  
  
 **Tenga en cuenta** aunque el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] podría usar la versión del ejemplo el `<TextBox.Text>` etiquetas alrededor del texto de cada botón <xref:System.Windows.Controls.TextBox> contenido, no es necesario porque el <xref:System.Windows.Controls.TextBox> se aplica el <xref:System.Windows.Markup.ContentPropertyAttribute> atributo a la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad. Para obtener más información, consulte [información general sobre XAML (WPF)](../advanced/xaml-overview-wpf.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre TextBox](textbox-overview.md)
- [Información general sobre el control RichTextBox](richtextbox-overview.md)
