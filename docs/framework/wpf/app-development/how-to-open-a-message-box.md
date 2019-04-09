---
title: Filtrar Abrir un cuadro de mensaje
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: cf7534cdee5e17d53e95294573023d660135e395
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101112"
---
# <a name="how-to-open-a-message-box"></a>Filtrar Abrir un cuadro de mensaje
En este ejemplo se muestra cómo abrir un cuadro de mensaje.  
  
## <a name="example"></a>Ejemplo  
 Un cuadro de mensaje es un cuadro de diálogo modal prefabricado para mostrar información a los usuarios. Se abre un cuadro de mensaje mediante una llamada a estático <xref:System.Windows.MessageBox.Show%2A> método de la <xref:System.Windows.MessageBox> clase. Cuando <xref:System.Windows.MessageBox.Show%2A> es llama, el mensaje se pasa mediante un parámetro de cadena. Varias sobrecargas de <xref:System.Windows.MessageBox.Show%2A> le permiten configurar cómo aparecerá un cuadro de mensaje (consulte <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>Vea también

- [Ejemplo de cuadro de mensajes](https://go.microsoft.com/fwlink/?LinkID=160023)
