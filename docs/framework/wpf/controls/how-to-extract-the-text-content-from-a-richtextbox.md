---
title: "Cómo: Extraer el contenido de texto de un control RichTextBox"
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
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f24b71bcb5f013c4b7054dd0948e5f2709230a99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>Cómo: Extraer el contenido de texto de un control RichTextBox
Este ejemplo muestra cómo extraer el contenido de un <xref:System.Windows.Controls.RichTextBox> como texto sin formato.  
  
## <a name="example"></a>Ejemplo  
 El siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] código describe un conjunto con nombre <xref:System.Windows.Controls.RichTextBox> control con contenido simple.  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente implementa un método que toma un <xref:System.Windows.Controls.RichTextBox> como un argumento y devuelve una cadena que representa el contenido de texto sin formato de la <xref:System.Windows.Controls.RichTextBox>.  
  
 El método crea un nuevo <xref:System.Windows.Documents.TextRange> con el contenido de la <xref:System.Windows.Controls.RichTextBox>, usando la <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> y <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> para indicar el intervalo del contenido para extraer.  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A>y <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> propiedades cada devuelven un <xref:System.Windows.Documents.TextPointer>y son accesibles en el objeto FlowDocument subyacente que representa el contenido de la <xref:System.Windows.Controls.RichTextBox>.  <xref:System.Windows.Documents.TextRange>Proporciona una propiedad de texto, que devuelve las partes de texto sin formato de la <xref:System.Windows.Documents.TextRange> como una cadena.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>Vea también  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
