---
title: Procedimiento Extraer el contenido de texto de un control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 220da59ec893528c99014e9ec95fb185c461b291
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001707"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>Procedimiento Extraer el contenido de texto de un control RichTextBox
En este ejemplo se muestra cómo extraer el contenido de un <xref:System.Windows.Controls.RichTextBox> como texto sin formato.  
  
## <a name="example"></a>Ejemplo  
 La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] código describe una con nombre <xref:System.Windows.Controls.RichTextBox> control con contenido simple.  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente implementa un método que toma un <xref:System.Windows.Controls.RichTextBox> como un argumento y devuelve una cadena que representa el contenido de texto sin formato de la <xref:System.Windows.Controls.RichTextBox>.  
  
 El método crea un nuevo <xref:System.Windows.Documents.TextRange> desde el contenido de la <xref:System.Windows.Controls.RichTextBox>, usando la <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> y <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> para indicar el intervalo del contenido para extraer.  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> y <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> devuelven propiedades de cada una <xref:System.Windows.Documents.TextPointer>y son accesibles en FlowDocument subyacente que representa el contenido de la <xref:System.Windows.Controls.RichTextBox>.  <xref:System.Windows.Documents.TextRange> Proporciona una propiedad de texto, que devuelve las partes de texto sin formato de la <xref:System.Windows.Documents.TextRange> como una cadena.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>Vea también

- [RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)
- [Información general sobre TextBox](textbox-overview.md)
