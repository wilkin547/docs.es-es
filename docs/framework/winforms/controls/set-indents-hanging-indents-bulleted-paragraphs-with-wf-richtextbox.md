---
title: Establecer sangrías, sangrías francesas y párrafos con viñetas con el control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: 4dcd5691f328eac6d94675c50ed41a7d7cc36596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743007"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="bec38-102">Cómo: Establecer sangrías, sangrías francesas y párrafos con viñetas con el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bec38-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="bec38-103">El control <xref:System.Windows.Forms.RichTextBox> de Windows Forms tiene numerosas opciones para dar formato al texto que muestra.</span><span class="sxs-lookup"><span data-stu-id="bec38-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="bec38-104">Puede dar formato a los párrafos seleccionados como listas con viñetas estableciendo la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>.</span><span class="sxs-lookup"><span data-stu-id="bec38-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="bec38-105">También puede usar las propiedades <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>y <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> para establecer la sangría de los párrafos con respecto a los bordes izquierdo y derecho del control, y el borde izquierdo de otras líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="bec38-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="bec38-106">Para aplicar formato a un párrafo como una lista con viñetas</span><span class="sxs-lookup"><span data-stu-id="bec38-106">To format a paragraph as a bulleted list</span></span>  
  
1. <span data-ttu-id="bec38-107">Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="bec38-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="bec38-108">Para aplicar sangría a un párrafo</span><span class="sxs-lookup"><span data-stu-id="bec38-108">To indent a paragraph</span></span>  
  
1. <span data-ttu-id="bec38-109">Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> en un entero que represente la distancia en píxeles entre el borde izquierdo del control y el borde izquierdo del texto.</span><span class="sxs-lookup"><span data-stu-id="bec38-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2. <span data-ttu-id="bec38-110">Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> en un entero que represente la distancia en píxeles entre el borde izquierdo de la primera línea de texto del párrafo y el borde izquierdo de las líneas siguientes del mismo párrafo.</span><span class="sxs-lookup"><span data-stu-id="bec38-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="bec38-111">El valor de la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> solo se aplica a las líneas de un párrafo que se ajustan debajo de la primera línea.</span><span class="sxs-lookup"><span data-stu-id="bec38-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3. <span data-ttu-id="bec38-112">Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> en un entero que represente la distancia en píxeles entre el borde derecho del control y el borde derecho del texto.</span><span class="sxs-lookup"><span data-stu-id="bec38-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="bec38-113">Todas estas propiedades afectan a todos los párrafos que contienen texto seleccionado y también al texto que se escribe después del punto de inserción actual.</span><span class="sxs-lookup"><span data-stu-id="bec38-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="bec38-114">Por ejemplo, cuando un usuario selecciona una palabra dentro de un párrafo y, a continuación, ajusta la sangría, la nueva configuración se aplica a todo el párrafo que contiene la palabra y a los párrafos que se escriben después del párrafo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bec38-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="bec38-115">Para obtener información sobre cómo seleccionar texto mediante programación, vea <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="bec38-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec38-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bec38-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="bec38-117">RichTextBox (control)</span><span class="sxs-lookup"><span data-stu-id="bec38-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="bec38-118">Controles que se utilizan en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bec38-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
