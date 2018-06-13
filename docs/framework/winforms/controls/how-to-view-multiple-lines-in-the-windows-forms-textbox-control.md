---
title: 'Cómo: Ver múltiples líneas en el control TextBox de formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: c826a519d8be05430eb6e2434209424514347b5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538572"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="380a3-102">Cómo: Ver múltiples líneas en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="380a3-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="380a3-103">De forma predeterminada, los formularios Windows Forms <xref:System.Windows.Forms.TextBox> control muestra una sola línea de texto y no muestra barras de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="380a3-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="380a3-104">Si el texto es más largo que el espacio disponible, solo una parte del texto está visible.</span><span class="sxs-lookup"><span data-stu-id="380a3-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="380a3-105">Puede cambiar este comportamiento predeterminado estableciendo la <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, y <xref:System.Windows.Forms.TextBox.ScrollBars%2A> propiedades en los valores adecuados.</span><span class="sxs-lookup"><span data-stu-id="380a3-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="380a3-106">Para mostrar un retorno de carro en el control de cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="380a3-106">To display a carriage return in the TextBox control</span></span>  
  
-   <span data-ttu-id="380a3-107">Para mostrar un retorno de carro en una de varias líneas <xref:System.Windows.Forms.TextBox>, use el <xref:System.Environment.NewLine%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="380a3-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="380a3-108">Tenga en cuenta que la interpretación de caracteres de escape (\\) es específico del idioma.</span><span class="sxs-lookup"><span data-stu-id="380a3-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="380a3-109">Visual Basic usa `Chr$(13) & Chr$(10)` para la combinación de caracteres de retorno de carro y de transporte.</span><span class="sxs-lookup"><span data-stu-id="380a3-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="380a3-110">Para ver varias líneas en el control de cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="380a3-110">To view multiple lines in the TextBox control</span></span>  
  
1.  <span data-ttu-id="380a3-111">Establezca la propiedad <xref:System.Windows.Forms.TextBox.Multiline%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="380a3-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="380a3-112">Si <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> es `true` (valor predeterminado), a continuación, el texto en el control se mostrará como uno o varios párrafos; en caso contrario, aparecerá como una lista, en el que algunas líneas pueden quedar cortadas en el borde del control.</span><span class="sxs-lookup"><span data-stu-id="380a3-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2.  <span data-ttu-id="380a3-113">Establezca la propiedad <xref:System.Windows.Forms.TextBox.ScrollBars%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="380a3-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="380a3-114">Valor</span><span class="sxs-lookup"><span data-stu-id="380a3-114">Value</span></span>|<span data-ttu-id="380a3-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="380a3-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="380a3-116">Utilice este valor si el texto será un párrafo que casi siempre se ajusta el control.</span><span class="sxs-lookup"><span data-stu-id="380a3-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="380a3-117">El usuario puede utilizar el puntero del mouse para moverse por el control si el texto es demasiado largo para mostrarse a la vez.</span><span class="sxs-lookup"><span data-stu-id="380a3-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="380a3-118">Use este valor si desea mostrar una lista de líneas, algunas de las cuales pueden ser mayor que el ancho de la <xref:System.Windows.Forms.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="380a3-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="380a3-119">Utilice este valor si la lista puede ser mayor que el alto del control.</span><span class="sxs-lookup"><span data-stu-id="380a3-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3.  <span data-ttu-id="380a3-120">Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="380a3-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="380a3-121">Valor</span><span class="sxs-lookup"><span data-stu-id="380a3-121">Value</span></span>|<span data-ttu-id="380a3-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="380a3-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="380a3-123">Texto en el control no automáticamente se ajustará, por lo que se desplazará a la derecha hasta que se alcance un salto de línea.</span><span class="sxs-lookup"><span data-stu-id="380a3-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="380a3-124">Utilice este valor si eligió <xref:System.Windows.Forms.ScrollBars.Horizontal> las barras de desplazamiento o <xref:System.Windows.Forms.ScrollBars.Both>anteriormente.</span><span class="sxs-lookup"><span data-stu-id="380a3-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="380a3-125">`true` (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="380a3-125">`true` (default)</span></span>|<span data-ttu-id="380a3-126">No se mostrará la barra de desplazamiento horizontal.</span><span class="sxs-lookup"><span data-stu-id="380a3-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="380a3-127">Utilice este valor si eligió <xref:System.Windows.Forms.ScrollBars.Vertical> las barras de desplazamiento o <xref:System.Windows.Forms.ScrollBars.None>, anterior, para mostrar uno o varios párrafos.</span><span class="sxs-lookup"><span data-stu-id="380a3-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="380a3-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="380a3-128">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="380a3-129">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="380a3-129">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="380a3-130">Controlar el punto de inserción en un control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="380a3-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="380a3-131">Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="380a3-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="380a3-132">Crear un cuadro de texto de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="380a3-132">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="380a3-133">Insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="380a3-133">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="380a3-134">Seleccionar texto en el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="380a3-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="380a3-135">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="380a3-135">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
