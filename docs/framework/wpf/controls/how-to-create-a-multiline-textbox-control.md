---
title: 'Cómo: Crear un control TextBox multilínea'
description: Obtenga información sobre cómo usar XAML para definir un control de cuadro de texto que se expande para alojar varias líneas de texto en una aplicación Windows Presentation Foundation.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 0a88d4d768884df135afddb491431650b9ba2d24
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166250"
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Cómo: Crear un control TextBox multilínea
En este ejemplo se muestra cómo usar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un <xref:System.Windows.Controls.TextBox> control que se expandirá automáticamente para alojar varias líneas de texto.  
  
## <a name="example"></a>Ejemplo  
 Al establecer el <xref:System.Windows.Controls.TextBox.TextWrapping%2A> atributo en **Wrap** , el texto escrito se ajustará a una nueva línea cuando se alcance el borde del <xref:System.Windows.Controls.TextBox> control, expandiendo automáticamente el <xref:System.Windows.Controls.TextBox> control para que incluya espacio para una nueva línea, si es necesario.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>Si se establece el atributo en **true** , se insertará una nueva línea cuando se presione la tecla entrar; de esta forma, se expandirá automáticamente el <xref:System.Windows.Controls.TextBox> para incluir el espacio para una nueva línea, si es necesario.  
  
 El <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> atributo agrega una barra de desplazamiento a <xref:System.Windows.Controls.TextBox> , de modo que el contenido de <xref:System.Windows.Controls.TextBox> se puede desplazar a través de si el objeto se <xref:System.Windows.Controls.TextBox> expande más allá del tamaño del marco o de la ventana que lo incluye.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.TextWrapping>
- [Información general sobre TextBox](textbox-overview.md)
- [Información general sobre el control RichTextBox](richtextbox-overview.md)
