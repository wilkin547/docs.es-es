---
title: "Cómo: Modificar la tipografía de texto"
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
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd18434c971831ea49813cda4ffdbc462154511a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-alter-the-typography-of-text"></a>Cómo: Modificar la tipografía de texto
En el ejemplo siguiente se muestra cómo establecer el <xref:System.Windows.Documents.TextElement.Typography%2A> atributo, mediante <xref:System.Windows.Documents.Paragraph> como elemento de ejemplo.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: texto con tipografía modificada](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")  
  
 En cambio, en la siguiente ilustración se muestra cómo se representa un ejemplo similar con propiedades tipográficas predeterminadas.  
  
 ![Captura de pantalla: texto con tipografía modificada](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo establecer el <xref:System.Windows.Controls.TextBox.Typography%2A> propiedad mediante programación.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre documentos dinámicos](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
