---
title: Colaboración Modificar la tipografía de texto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
ms.openlocfilehash: 4c027424632f8671ba8d7cae1c899ef3a53edc26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078868"
---
# <a name="how-to-alter-the-typography-of-text"></a><span data-ttu-id="18ed8-102">Colaboración Modificar la tipografía de texto</span><span class="sxs-lookup"><span data-stu-id="18ed8-102">How-to: Alter the Typography of Text</span></span>
<span data-ttu-id="18ed8-103">El ejemplo siguiente muestra cómo establecer el <xref:System.Windows.Documents.TextElement.Typography%2A> atributo, mediante <xref:System.Windows.Documents.Paragraph> como elemento de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="18ed8-103">The following example shows how to set the <xref:System.Windows.Documents.TextElement.Typography%2A> attribute, using <xref:System.Windows.Documents.Paragraph> as the example element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18ed8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18ed8-104">Example</span></span>  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 <span data-ttu-id="18ed8-105">En la ilustración siguiente, se muestra cómo se representa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="18ed8-105">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="18ed8-106">![Captura de pantalla: Texto con tipografía modificada](./media/textelement-typog.png "TextElement_Typog")</span><span class="sxs-lookup"><span data-stu-id="18ed8-106">![Screenshot: Text with altered typography](./media/textelement-typog.png "TextElement_Typog")</span></span>  
  
 <span data-ttu-id="18ed8-107">En cambio, en la siguiente ilustración se muestra cómo se representa un ejemplo similar con propiedades tipográficas predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="18ed8-107">In contrast, the following figure shows how a similar example with default typographic properties renders.</span></span>  
  
 <span data-ttu-id="18ed8-108">![Captura de pantalla: Texto con tipografía modificada](./media/textelement-typog-default.png "TextElement_Typog_Default")</span><span class="sxs-lookup"><span data-stu-id="18ed8-108">![Screenshot: Text with altered typography](./media/textelement-typog-default.png "TextElement_Typog_Default")</span></span>  
  
## <a name="example"></a><span data-ttu-id="18ed8-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18ed8-109">Example</span></span>  
 <span data-ttu-id="18ed8-110">El ejemplo siguiente muestra cómo establecer el <xref:System.Windows.Controls.TextBox.Typography%2A> propiedad mediante programación.</span><span class="sxs-lookup"><span data-stu-id="18ed8-110">The following example shows how to set the <xref:System.Windows.Controls.TextBox.Typography%2A> property programmatically.</span></span>  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a><span data-ttu-id="18ed8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="18ed8-111">See also</span></span>

- [<span data-ttu-id="18ed8-112">Información general sobre documentos dinámicos</span><span class="sxs-lookup"><span data-stu-id="18ed8-112">Flow Document Overview</span></span>](flow-document-overview.md)
