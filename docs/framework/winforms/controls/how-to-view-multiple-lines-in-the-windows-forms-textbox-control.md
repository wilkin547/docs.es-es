---
title: Ver varias líneas en el control TextBox
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
ms.openlocfilehash: 61ea671c1e86fa8254bfc1b043a46f3b7aa6af1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728279"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="30eee-102">Cómo: Ver múltiples líneas en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30eee-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="30eee-103">De forma predeterminada, el control Windows Forms <xref:System.Windows.Forms.TextBox> muestra una sola línea de texto y no muestra barras de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="30eee-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="30eee-104">Si el texto es más largo que el espacio disponible, solo parte del texto es visible.</span><span class="sxs-lookup"><span data-stu-id="30eee-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="30eee-105">Puede cambiar este comportamiento predeterminado si establece las propiedades <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>y <xref:System.Windows.Forms.TextBox.ScrollBars%2A> en los valores adecuados.</span><span class="sxs-lookup"><span data-stu-id="30eee-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="30eee-106">Para mostrar un retorno de carro en el control TextBox</span><span class="sxs-lookup"><span data-stu-id="30eee-106">To display a carriage return in the TextBox control</span></span>  
  
- <span data-ttu-id="30eee-107">Para mostrar un retorno de carro en un <xref:System.Windows.Forms.TextBox>de varias líneas, use la propiedad <xref:System.Environment.NewLine%2A>.</span><span class="sxs-lookup"><span data-stu-id="30eee-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="30eee-108">Tenga en cuenta que la interpretación de los caracteres de escape (\\) es específica del idioma.</span><span class="sxs-lookup"><span data-stu-id="30eee-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="30eee-109">Visual Basic usa `Chr$(13) & Chr$(10)` para la combinación de caracteres de retorno de carro y avance de carro.</span><span class="sxs-lookup"><span data-stu-id="30eee-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="30eee-110">Para ver varias líneas en el control TextBox</span><span class="sxs-lookup"><span data-stu-id="30eee-110">To view multiple lines in the TextBox control</span></span>  
  
1. <span data-ttu-id="30eee-111">Establezca la propiedad <xref:System.Windows.Forms.TextBox.Multiline%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="30eee-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="30eee-112">Si <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> es `true` (valor predeterminado), el texto del control aparecerá como uno o más párrafos; en caso contrario, aparecerá como una lista, en la que algunas líneas se pueden recortar en el borde del control.</span><span class="sxs-lookup"><span data-stu-id="30eee-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2. <span data-ttu-id="30eee-113">Establezca la propiedad <xref:System.Windows.Forms.TextBox.ScrollBars%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="30eee-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="30eee-114">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="30eee-114">Value</span></span>|<span data-ttu-id="30eee-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="30eee-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="30eee-116">Use este valor si el texto va a ser un párrafo que casi siempre se ajusta al control.</span><span class="sxs-lookup"><span data-stu-id="30eee-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="30eee-117">El usuario puede usar el puntero del mouse para desplazarse por el control si el texto es demasiado largo para mostrarlo todos a la vez.</span><span class="sxs-lookup"><span data-stu-id="30eee-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="30eee-118">Use este valor si desea que se muestre una lista de líneas, algunas de las cuales pueden ser mayores que el ancho del control <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="30eee-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="30eee-119">Use este valor si la lista puede ser más larga que el alto del control.</span><span class="sxs-lookup"><span data-stu-id="30eee-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3. <span data-ttu-id="30eee-120">Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="30eee-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="30eee-121">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="30eee-121">Value</span></span>|<span data-ttu-id="30eee-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="30eee-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="30eee-123">El texto del control no se ajustará automáticamente, por lo que se desplazará hacia la derecha hasta que se alcance un salto de línea.</span><span class="sxs-lookup"><span data-stu-id="30eee-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="30eee-124">Use este valor si eligió <xref:System.Windows.Forms.ScrollBars.Horizontal> barras de desplazamiento o <xref:System.Windows.Forms.ScrollBars.Both>, arriba.</span><span class="sxs-lookup"><span data-stu-id="30eee-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="30eee-125">`true` (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="30eee-125">`true` (default)</span></span>|<span data-ttu-id="30eee-126">No aparecerá la barra de desplazamiento horizontal.</span><span class="sxs-lookup"><span data-stu-id="30eee-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="30eee-127">Use este valor si eligió <xref:System.Windows.Forms.ScrollBars.Vertical> barras de desplazamiento o <xref:System.Windows.Forms.ScrollBars.None>, arriba, para mostrar uno o más párrafos.</span><span class="sxs-lookup"><span data-stu-id="30eee-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30eee-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="30eee-128">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="30eee-129">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="30eee-129">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="30eee-130">Controlar el punto de inserción en un control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30eee-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="30eee-131">Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30eee-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="30eee-132">Crear un cuadro de texto de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="30eee-132">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="30eee-133">Insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="30eee-133">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="30eee-134">Seleccionar texto en el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30eee-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="30eee-135">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="30eee-135">TextBox Control</span></span>](textbox-control-windows-forms.md)
