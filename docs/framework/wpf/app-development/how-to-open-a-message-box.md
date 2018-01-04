---
title: "Cómo: abrir un cuadro de mensaje"
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
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1754fa190a638c1a200805e339f91bd582d27c4c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-open-a-message-box"></a>Cómo: abrir un cuadro de mensaje
Este ejemplo muestra cómo abrir un cuadro de mensaje.  
  
## <a name="example"></a>Ejemplo  
 Un cuadro de mensaje es un cuadro de diálogo modal prefabricado para mostrar información a los usuarios. Se abre un cuadro de mensaje mediante una llamada a estático <xref:System.Windows.MessageBox.Show%2A> método de la <xref:System.Windows.MessageBox> clase. Cuando <xref:System.Windows.MessageBox.Show%2A> es llama, se pasa el mensaje mediante un parámetro de cadena. Varias sobrecargas de <xref:System.Windows.MessageBox.Show%2A> le permiten configurar cómo aparecerá un cuadro de mensaje (consulte <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de cuadro de mensajes](http://go.microsoft.com/fwlink/?LinkID=160023)
