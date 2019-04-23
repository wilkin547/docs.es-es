---
title: Procedimiento Obtener una colección de líneas de un control TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: b7b2f1c2e071388635fb50b1e3573fd7f44334dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224642"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a>Procedimiento Obtener una colección de líneas de un control TextBox
En este ejemplo se muestra cómo obtener una colección de líneas de texto de un <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra un método simple que toma un <xref:System.Windows.Controls.TextBox> como argumento y devuelve un <xref:System.Collections.Specialized.StringCollection> que contiene las líneas de texto en el **TextBox**.  El <xref:System.Windows.Controls.TextBox.LineCount%2A> propiedad se utiliza para determinar cuántas líneas están actualmente en el **TextBox**y el <xref:System.Windows.Controls.TextBox.GetLineText%2A> método, a continuación, se usa para extraer cada línea y agregarla a la colección de líneas.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre TextBox](textbox-overview.md)
- [RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)
