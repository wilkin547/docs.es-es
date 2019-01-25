---
title: Procedimiento Hacer que un control TextBox sea de sólo lectura
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 1e9d333f22099d9593e58b4087f185b2988215ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517180"
---
# <a name="how-to-make-a-textbox-control-read-only"></a>Procedimiento Hacer que un control TextBox sea de sólo lectura
En este ejemplo se muestra cómo configurar un <xref:System.Windows.Controls.TextBox> control no permitir la entrada del usuario o la modificación.  
  
## <a name="example"></a>Ejemplo  
 Para evitar que los usuarios modifiquen el contenido de un <xref:System.Windows.Controls.TextBox> , establezca el <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atributo **true**.  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 El <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atributo afecta a los proporcionados por el usuario sólo; no afecta al texto establecido el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] descripción de un <xref:System.Windows.Controls.TextBox> control o texto establecido mediante programación a través del <xref:System.Windows.Controls.TextBox.Text%2A> propiedad.  
  
 El valor predeterminado de <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> es **false**.  
  
## <a name="see-also"></a>Vea también
- [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)
