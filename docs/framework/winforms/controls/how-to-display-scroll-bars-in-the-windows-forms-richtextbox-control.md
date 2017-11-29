---
title: "Cómo: Mostrar barras de desplazamiento en el control RichTextBox de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b20c526b27eb185bf79eaf0ace47e5a9fded42a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="3d244-102">Cómo: Mostrar barras de desplazamiento en el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d244-102">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="3d244-103">De forma predeterminada, los formularios Windows Forms <xref:System.Windows.Forms.RichTextBox> control muestra las barras de desplazamiento horizontal y vertical según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3d244-103">By default, the Windows Forms <xref:System.Windows.Forms.RichTextBox> control displays horizontal and vertical scroll bars as necessary.</span></span> <span data-ttu-id="3d244-104">Hay siete valores posibles para la <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> propiedad de la <xref:System.Windows.Forms.RichTextBox> control, que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3d244-104">There are seven possible values for the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property of the <xref:System.Windows.Forms.RichTextBox> control, which are described in the table below.</span></span>  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a><span data-ttu-id="3d244-105">Para mostrar las barras de desplazamiento en el control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="3d244-105">To display scroll bars in a RichTextBox control</span></span>  
  
1.  <span data-ttu-id="3d244-106">Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.Multiline%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="3d244-106">Set the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="3d244-107">Se mostrará ningún tipo de barra, incluidos los de desplazamiento horizontal, si la <xref:System.Windows.Forms.RichTextBox.Multiline%2A> propiedad está establecida en `false`.</span><span class="sxs-lookup"><span data-stu-id="3d244-107">No type of scroll bar, including horizontal, will display if the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property is set to `false`.</span></span>  
  
2.  <span data-ttu-id="3d244-108">Establecer el <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> propiedad en un valor apropiado de la <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeración.</span><span class="sxs-lookup"><span data-stu-id="3d244-108">Set the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property to an appropriate value of the <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeration.</span></span>  
  
    |<span data-ttu-id="3d244-109">Valor</span><span class="sxs-lookup"><span data-stu-id="3d244-109">Value</span></span>|<span data-ttu-id="3d244-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d244-110">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="3d244-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="3d244-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (default)</span></span>|<span data-ttu-id="3d244-112">Muestra las barras de desplazamiento horizontal o vertical, o ambas, sólo cuando el texto supera el ancho o el alto del control.</span><span class="sxs-lookup"><span data-stu-id="3d244-112">Displays horizontal or vertical scroll bars, or both, only when text exceeds the width or length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|<span data-ttu-id="3d244-113">Nunca muestra ningún tipo de barra de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="3d244-113">Never displays any type of scroll bar.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|<span data-ttu-id="3d244-114">Muestra una barra solo cuando el texto supera el ancho del control de desplazamiento horizontal.</span><span class="sxs-lookup"><span data-stu-id="3d244-114">Displays a horizontal scroll bar only when the text exceeds the width of the control.</span></span> <span data-ttu-id="3d244-115">(Esto sucede, el <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> propiedad debe establecerse en `false`.)</span><span class="sxs-lookup"><span data-stu-id="3d244-115">(For this to occur, the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property must be set to `false`.)</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|<span data-ttu-id="3d244-116">Muestra una barra solo cuando el texto supera el alto del control de desplazamiento vertical.</span><span class="sxs-lookup"><span data-stu-id="3d244-116">Displays a vertical scroll bar only when the text exceeds the height of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<span data-ttu-id="3d244-117">Muestra si la barra de desplazamiento horizontal del <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> propiedad está establecida en `false`.</span><span class="sxs-lookup"><span data-stu-id="3d244-117">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="3d244-118">La barra de desplazamiento aparece atenuada cuando el texto no supera el ancho del control.</span><span class="sxs-lookup"><span data-stu-id="3d244-118">The scroll bar appears dimmed when text does not exceed the width of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|<span data-ttu-id="3d244-119">Siempre muestra una barra de desplazamiento vertical.</span><span class="sxs-lookup"><span data-stu-id="3d244-119">Always displays a vertical scroll bar.</span></span> <span data-ttu-id="3d244-120">La barra de desplazamiento aparece atenuada cuando el texto no supera la longitud del control.</span><span class="sxs-lookup"><span data-stu-id="3d244-120">The scroll bar appears dimmed when text does not exceed the length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|<span data-ttu-id="3d244-121">Siempre muestra una barra de desplazamiento vertical.</span><span class="sxs-lookup"><span data-stu-id="3d244-121">Always displays a vertical scrollbar.</span></span> <span data-ttu-id="3d244-122">Muestra si la barra de desplazamiento horizontal del <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> propiedad está establecida en `false`.</span><span class="sxs-lookup"><span data-stu-id="3d244-122">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="3d244-123">Las barras de desplazamiento aparecen en gris cuando el texto no supera el ancho o el alto del control.</span><span class="sxs-lookup"><span data-stu-id="3d244-123">The scroll bars appear grayed when text does not exceed the width or length of the control.</span></span>|  
  
3.  <span data-ttu-id="3d244-124">Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="3d244-124">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="3d244-125">Valor</span><span class="sxs-lookup"><span data-stu-id="3d244-125">Value</span></span>|<span data-ttu-id="3d244-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d244-126">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="3d244-127">Texto en el control no se ajusta automáticamente para ajustarse al ancho del control, por lo que se desplazará a la derecha hasta que se alcance un salto de línea.</span><span class="sxs-lookup"><span data-stu-id="3d244-127">Text in the control is not automatically adjusted to fit the width of the control, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="3d244-128">Utilice este valor si eligió barras de desplazamiento horizontal o ambas cosas, por encima.</span><span class="sxs-lookup"><span data-stu-id="3d244-128">Use this value if you chose horizontal scroll bars or both, above.</span></span>|  
    |<span data-ttu-id="3d244-129">`true` (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="3d244-129">`true` (default)</span></span>|<span data-ttu-id="3d244-130">Texto en el control se ajusta automáticamente para ajustarse al ancho del control.</span><span class="sxs-lookup"><span data-stu-id="3d244-130">Text in the control is automatically adjusted to fit the width of the control.</span></span> <span data-ttu-id="3d244-131">No se mostrará la barra de desplazamiento horizontal.</span><span class="sxs-lookup"><span data-stu-id="3d244-131">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="3d244-132">Utilice este valor si eligió barras de desplazamiento vertical o ninguno, anteriormente, para mostrar uno o varios párrafos.</span><span class="sxs-lookup"><span data-stu-id="3d244-132">Use this value if you chose vertical scroll bars or none, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d244-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d244-133">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="3d244-134">RichTextBox (control)</span><span class="sxs-lookup"><span data-stu-id="3d244-134">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="3d244-135">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d244-135">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
