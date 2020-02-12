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
ms.openlocfilehash: bd2c4dce78e46163eb4628cb3aab829fc0173edf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123732"
---
# <a name="how-to-open-a-message-box"></a>Cómo: abrir un cuadro de mensaje
En este ejemplo se muestra cómo abrir un cuadro de mensaje.  
  
## <a name="example"></a>Ejemplo  
 Un cuadro de mensaje es un cuadro de diálogo modal prefabricado para mostrar información a los usuarios. Se abre un cuadro de mensaje mediante una llamada al método <xref:System.Windows.MessageBox.Show%2A> estático de la clase <xref:System.Windows.MessageBox>. Cuando se llama a <xref:System.Windows.MessageBox.Show%2A>, el mensaje se pasa mediante un parámetro de cadena. Varias sobrecargas de <xref:System.Windows.MessageBox.Show%2A> permiten configurar el modo en que aparecerá un cuadro de mensaje (vea <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>Consulte también

- [Ejemplo MessageBox](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)
