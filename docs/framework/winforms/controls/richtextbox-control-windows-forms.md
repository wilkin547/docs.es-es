---
title: RichTextBox (Control, formularios Windows Forms)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 80621a12a4ccd5008a0331af005629d45f60abdf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="32c09-102">RichTextBox (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="32c09-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="32c09-103">Los formularios Windows Forms `RichTextBox` control se utiliza para mostrar, escribir y manipular texto con formato.</span><span class="sxs-lookup"><span data-stu-id="32c09-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="32c09-104">El `RichTextBox` control hace todo lo que el <xref:System.Windows.Forms.TextBox> no de control, pero también puede mostrar las fuentes, colores y vínculos; Cargar texto e imágenes incrustadas desde un archivo; Deshacer y rehacer operaciones; de edición y buscar caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="32c09-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="32c09-105">El `RichTextBox` control se utiliza normalmente para manipular texto y proporcionar funciones de presentación similares a las aplicaciones de procesamiento de textos como Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="32c09-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="32c09-106">Como el <xref:System.Windows.Forms.TextBox> (control), el `RichTextBox` control puede mostrar barras de desplazamiento; pero a diferencia del <xref:System.Windows.Forms.TextBox> control, muestra barras de desplazamiento horizontal y vertical de forma predeterminada y tiene una configuración adicional de la barra de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="32c09-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32c09-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="32c09-107">In This Section</span></span>  
 [<span data-ttu-id="32c09-108">Información general sobre el control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="32c09-108">RichTextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="32c09-109">Presenta los conceptos generales de la `RichTextBox` control, lo que permite a los usuarios escribir, mostrar y manipular texto con opciones de formato.</span><span class="sxs-lookup"><span data-stu-id="32c09-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="32c09-110">Determinar cuándo cambian los atributos de formato en el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32c09-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="32c09-111">Explica cómo realizar un seguimiento de cambios en la fuente y el formato de párrafo en el `RichTextBox` control.</span><span class="sxs-lookup"><span data-stu-id="32c09-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="32c09-112">Mostrar barras de desplazamiento en el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32c09-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="32c09-113">Describe las diversas opciones disponibles para las barras de desplazamiento en el `RichTextBox` control.</span><span class="sxs-lookup"><span data-stu-id="32c09-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="32c09-114">Mostrar vínculos de estilo Web con el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32c09-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="32c09-115">Explica cómo vincular a sitios Web desde el `RichTextBox` control.</span><span class="sxs-lookup"><span data-stu-id="32c09-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="32c09-116">Habilitar operaciones de arrastrar y colocar con el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32c09-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="32c09-117">Proporciona instrucciones para arrastrar datos a la `RichTextBox` control.</span><span class="sxs-lookup"><span data-stu-id="32c09-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="32c09-118">Cargar archivos en el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32c09-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="32c09-119">Proporciona instrucciones para cargar un archivo existente en el `RichTextBox` control.</span><span class="sxs-lookup"><span data-stu-id="32c09-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="32c09-120">Guardar archivos con el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32c09-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="32c09-121">Proporciona instrucciones para guardar el contenido de la `RichTextBox` control a un archivo.</span><span class="sxs-lookup"><span data-stu-id="32c09-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="32c09-122">Establecer atributos de fuente para el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32c09-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="32c09-123">Describe cómo establecer la familia de fuentes, el tamaño, el estilo y el color del texto de la `RichTextBox` control.</span><span class="sxs-lookup"><span data-stu-id="32c09-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="32c09-124">Establecer sangrías, sangrías francesas y párrafos con viñetas con el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32c09-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="32c09-125">Describe cómo dar formato a párrafos en el `RichTextBox` control.</span><span class="sxs-lookup"><span data-stu-id="32c09-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="32c09-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="32c09-126">Reference</span></span>  
 <span data-ttu-id="32c09-127">Clase <xref:System.Windows.Forms.RichTextBox></span><span class="sxs-lookup"><span data-stu-id="32c09-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="32c09-128">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="32c09-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="32c09-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="32c09-129">Related Sections</span></span>  
 [<span data-ttu-id="32c09-130">Controles que se usan en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32c09-130">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="32c09-131">Proporciona una lista completa de controles de Windows Forms, con vínculos a información sobre su uso.</span><span class="sxs-lookup"><span data-stu-id="32c09-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="32c09-132">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="32c09-132">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)  
 <span data-ttu-id="32c09-133">Presenta los conceptos generales de la <xref:System.Windows.Forms.TextBox> control, lo que permite varias líneas, puede editar entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="32c09-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
