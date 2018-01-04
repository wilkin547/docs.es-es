---
title: "Cómo: Establecer el contenido de texto de un control TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef354a986ee71cfa7a8e00a62905ee909d9cf30d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Cómo: Establecer el contenido de texto de un control TextBox
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad que se va a establecer el contenido de texto inicial de un <xref:System.Windows.Controls.TextBox> control.  
  
 **Tenga en cuenta** aunque el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] podría utilizar la versión del ejemplo la `<TextBox.Text>` etiquetas alrededor del texto de cada botón <xref:System.Windows.Controls.TextBox> contenido, no es necesario porque el <xref:System.Windows.Controls.TextBox> se aplica el <xref:System.Windows.Markup.ContentPropertyAttribute> atribuir a la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad. Para obtener más información, consulte [información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)
