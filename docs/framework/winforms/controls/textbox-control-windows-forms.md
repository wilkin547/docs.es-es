---
title: Control TextBox
description: Obtenga información sobre los distintos aspectos del control de cuadro de texto Windows Forms, incluido su uso para texto editable y convertirlo en de solo lectura.
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- TextBox control [Windows Forms]
ms.assetid: e5a06987-8aec-4271-b196-2245ba992d62
ms.openlocfilehash: 026f6d2653e41dabd3db7490660b6ce19846d397
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174450"
---
# <a name="textbox-control-windows-forms"></a><span data-ttu-id="38b71-103">TextBox (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="38b71-103">TextBox Control (Windows Forms)</span></span>
<span data-ttu-id="38b71-104">Windows Forms cuadros de texto se utilizan para obtener la entrada del usuario o para mostrar texto.</span><span class="sxs-lookup"><span data-stu-id="38b71-104">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="38b71-105">`TextBox`Normalmente, el control se utiliza para texto editable, aunque también se puede convertir en de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="38b71-105">The `TextBox` control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="38b71-106">Los cuadros de texto pueden mostrar varias líneas, ajustar el texto al tamaño del control y agregar formato básico.</span><span class="sxs-lookup"><span data-stu-id="38b71-106">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="38b71-107">El `TextBox` control permite un único formato para el texto que se muestra o se escribe en el control.</span><span class="sxs-lookup"><span data-stu-id="38b71-107">The `TextBox` control allows a single format for text displayed or entered in the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38b71-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="38b71-108">In This Section</span></span>  
 [<span data-ttu-id="38b71-109">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="38b71-109">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)  
 <span data-ttu-id="38b71-110">Explica qué es este control y sus propiedades y características clave.</span><span class="sxs-lookup"><span data-stu-id="38b71-110">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="38b71-111">Procedimiento para controlar el punto de inserción en un control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38b71-111">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 <span data-ttu-id="38b71-112">Proporciona instrucciones para especificar dónde aparece el punto de inserción cuando un control de edición obtiene el foco por primera vez.</span><span class="sxs-lookup"><span data-stu-id="38b71-112">Gives directions for specifying where the insertion point appears when an edit control first gets the focus.</span></span>  
  
 [<span data-ttu-id="38b71-113">Procedimiento para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38b71-113">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="38b71-114">Explica cómo ocultar lo que se escribe en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="38b71-114">Explains how to conceal what is typed into a text box.</span></span>  
  
 [<span data-ttu-id="38b71-115">Procedimiento para crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="38b71-115">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)  
 <span data-ttu-id="38b71-116">Describe cómo evitar que se cambie el contenido de un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="38b71-116">Describes how to prevent the contents of a text box from being changed.</span></span>  
  
 [<span data-ttu-id="38b71-117">Procedimiento para insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="38b71-117">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 <span data-ttu-id="38b71-118">Explica cómo agregar comillas a una cadena en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="38b71-118">Explains adding quotation marks to a string in a text box.</span></span>  
  
 [<span data-ttu-id="38b71-119">Procedimiento para seleccionar texto en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38b71-119">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="38b71-120">Explica cómo resaltar texto en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="38b71-120">Explains how to highlight text in a text box.</span></span>  
  
 [<span data-ttu-id="38b71-121">Procedimiento para ver varias líneas en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38b71-121">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="38b71-122">Describe cómo hacer que un cuadro de texto se pueda desplazar.</span><span class="sxs-lookup"><span data-stu-id="38b71-122">Describes how to make a text box scrollable.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="38b71-123">Referencia</span><span class="sxs-lookup"><span data-stu-id="38b71-123">Reference</span></span>  
 <span data-ttu-id="38b71-124">Clase <xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="38b71-124"><xref:System.Windows.Forms.TextBox> class</span></span>  
 <span data-ttu-id="38b71-125">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="38b71-125">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="38b71-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="38b71-126">Related Sections</span></span>  
 [<span data-ttu-id="38b71-127">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38b71-127">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="38b71-128">Proporciona una lista completa de controles de Windows Forms, con vínculos a información sobre su uso.</span><span class="sxs-lookup"><span data-stu-id="38b71-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
