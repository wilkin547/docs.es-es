---
title: Filtrar para establecer atributos de fuente para el control RichTextBox de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
ms.openlocfilehash: a6fe5b30c457fae2d53c946092b214f492fe5e9b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331213"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a><span data-ttu-id="0fd5f-102">Filtrar para establecer atributos de fuente para el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0fd5f-102">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="0fd5f-103">Los formularios de Windows <xref:System.Windows.Forms.RichTextBox> control tiene numerosas opciones para dar formato al texto que muestra.</span><span class="sxs-lookup"><span data-stu-id="0fd5f-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="0fd5f-104">Puede realizar los caracteres seleccionados en negrita, subrayado o cursiva, utilizando el <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="0fd5f-104">You can make the selected characters bold, underlined, or italic, using the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property.</span></span> <span data-ttu-id="0fd5f-105">También puede usar esta propiedad para cambiar el tamaño y el tipo de letra de los caracteres seleccionados.</span><span class="sxs-lookup"><span data-stu-id="0fd5f-105">You can also use this property to change the size and typeface of the selected characters.</span></span> <span data-ttu-id="0fd5f-106">El <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> propiedad le permite cambiar el color de los caracteres seleccionados.</span><span class="sxs-lookup"><span data-stu-id="0fd5f-106">The <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property enables you to change the selected characters' color.</span></span>  
  
### <a name="to-change-the-appearance-of-characters"></a><span data-ttu-id="0fd5f-107">Para cambiar la apariencia de los caracteres</span><span class="sxs-lookup"><span data-stu-id="0fd5f-107">To change the appearance of characters</span></span>  
  
1. <span data-ttu-id="0fd5f-108">Establecer el <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> propiedad en una fuente adecuada.</span><span class="sxs-lookup"><span data-stu-id="0fd5f-108">Set the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property to an appropriate font.</span></span>  
  
     <span data-ttu-id="0fd5f-109">Para permitir que los usuarios establezcan la familia de fuentes, el tamaño y tipo de letra en una aplicación, normalmente usaría el <xref:System.Windows.Forms.FontDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="0fd5f-109">To enable users to set the font family, size, and typeface in an application, you would typically use the <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="0fd5f-110">Para obtener información general al respecto, consulte [Información general sobre el componente FontDialog](fontdialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0fd5f-110">For an overview, see [FontDialog Component Overview](fontdialog-component-overview-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="0fd5f-111">Establecer el <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> propiedad en un color adecuado.</span><span class="sxs-lookup"><span data-stu-id="0fd5f-111">Set the <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property to an appropriate color.</span></span>  
  
     <span data-ttu-id="0fd5f-112">Para permitir que los usuarios establezcan el color en una aplicación, normalmente usaría el <xref:System.Windows.Forms.ColorDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="0fd5f-112">To enable users to set the color in an application, you would typically use the <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="0fd5f-113">Para obtener información general al respecto, consulte [Información general sobre el componente ColorDialog](colordialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0fd5f-113">For an overview, see [ColorDialog Component Overview](colordialog-component-overview-windows-forms.md).</span></span>  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="0fd5f-114">Estas propiedades solo afectan al texto seleccionado o, si no hay texto seleccionado, al texto que se escriba en la posición actual del punto de inserción.</span><span class="sxs-lookup"><span data-stu-id="0fd5f-114">These properties only affect selected text, or, if no text is selected, the text that is typed at the current location of the insertion point.</span></span> <span data-ttu-id="0fd5f-115">Para obtener información sobre cómo seleccionar texto mediante programación, vea <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="0fd5f-115">For information on selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd5f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fd5f-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="0fd5f-117">Control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0fd5f-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="0fd5f-118">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0fd5f-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
