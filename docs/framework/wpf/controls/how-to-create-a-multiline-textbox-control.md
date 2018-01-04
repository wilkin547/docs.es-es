---
title: "Cómo: Crear un control TextBox multilínea"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a6885a594e5fcd747f85dedf1afbd39ec644717
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Cómo: Crear un control TextBox multilínea
Este ejemplo muestra cómo usar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un <xref:System.Windows.Controls.TextBox> control que se expande automáticamente para alojar varias líneas de texto.  
  
## <a name="example"></a>Ejemplo  
 Establecer el <xref:System.Windows.Controls.TextBox.TextWrapping%2A> atribuir a **ajustar** hará que el texto escrito ajustar en una nueva línea cuando el borde de la <xref:System.Windows.Controls.TextBox> control se alcanza, expanda automáticamente la <xref:System.Windows.Controls.TextBox> control debe incluir el espacio para una nueva línea, si es necesario.  
  
 Establecer el <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> atribuir a **true** provoca una nueva línea insertará cuando se presiona la tecla ENTRAR, se expande automáticamente una vez más la <xref:System.Windows.Controls.TextBox> incluir espacio para una nueva línea, si es necesario.  
  
 El <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> atributo agrega una barra de desplazamiento a la <xref:System.Windows.Controls.TextBox>, de modo que el contenido de la <xref:System.Windows.Controls.TextBox> puede desplazarse a través de if el <xref:System.Windows.Controls.TextBox> se expande más allá del tamaño del marco o la ventana que lo incluye.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.TextWrapping>  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)
