---
title: 'Cómo: abrir un cuadro de mensaje'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: f05190030ed6324917348fa1926abd5385e30f7e
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353153"
---
# <a name="how-to-open-a-message-box"></a>Cómo: abrir un cuadro de mensaje
En este ejemplo se muestra cómo abrir un cuadro de mensaje.  
  
## <a name="example"></a>Ejemplo  
 Un cuadro de mensaje es un cuadro de diálogo modal prefabricado para mostrar información a los usuarios. Se abre un cuadro de mensaje mediante una llamada a estático <xref:System.Windows.MessageBox.Show%2A> método de la <xref:System.Windows.MessageBox> clase. Cuando <xref:System.Windows.MessageBox.Show%2A> es llama, el mensaje se pasa mediante un parámetro de cadena. Varias sobrecargas de <xref:System.Windows.MessageBox.Show%2A> le permiten configurar cómo aparecerá un cuadro de mensaje (consulte <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de cuadro de mensajes](https://go.microsoft.com/fwlink/?LinkID=160023)
