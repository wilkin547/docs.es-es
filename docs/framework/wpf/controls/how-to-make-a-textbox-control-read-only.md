---
title: 'Cómo: Hacer que un control TextBox sea de sólo lectura'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 3ba93cae5977f3c8c76f3bfa9f5732d3f0736af7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554546"
---
# <a name="how-to-make-a-textbox-control-read-only"></a>Cómo: Hacer que un control TextBox sea de sólo lectura
Este ejemplo muestra cómo configurar un <xref:System.Windows.Controls.TextBox> control no permitir la intervención del usuario o la modificación.  
  
## <a name="example"></a>Ejemplo  
 Para impedir que los usuarios modifiquen el contenido de un <xref:System.Windows.Controls.TextBox> de control, establezca la <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atribuir a **true**.  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 El <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atributo afecta a los proporcionados por el usuario sólo; no afecta al texto establecido el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] descripción de un <xref:System.Windows.Controls.TextBox> control ni al texto establecido mediante programación a través del <xref:System.Windows.Controls.TextBox.Text%2A> propiedad.  
  
 El valor predeterminado de <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> es **false**.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)
