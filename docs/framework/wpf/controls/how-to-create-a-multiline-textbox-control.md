---
title: Procedimiento Crear un control TextBox multilínea
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: ca1b499b2acdfd9fd2ff0f57f2b0c07d7da10789
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517830"
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Procedimiento Crear un control TextBox multilínea
En este ejemplo se muestra cómo usar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un <xref:System.Windows.Controls.TextBox> control que se expandirá automáticamente para alojar varias líneas de texto.  
  
## <a name="example"></a>Ejemplo  
 Establecer el <xref:System.Windows.Controls.TextBox.TextWrapping%2A> atribuir a **ajustar** hará que el texto especificado se ajuste a una nueva línea cuando el borde de la <xref:System.Windows.Controls.TextBox> se alcanza el control, se expande automáticamente el <xref:System.Windows.Controls.TextBox> control para incluir espacio para una nueva línea, si es necesario.  
  
 Establecer el <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> atributo **true** provoca una nueva línea va a insertar cuando se presiona la tecla ENTRAR, se expande automáticamente una vez más la <xref:System.Windows.Controls.TextBox> para incluir espacio para una nueva línea, si es necesario.  
  
 El <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> atributo agrega una barra de desplazamiento a la <xref:System.Windows.Controls.TextBox>, de modo que el contenido de la <xref:System.Windows.Controls.TextBox> se puede desplazar y si el <xref:System.Windows.Controls.TextBox> se expande más allá del tamaño del marco o la ventana que lo contiene.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.TextWrapping>
- [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)
