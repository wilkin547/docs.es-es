---
title: Funcionalidad para imprimir en formularios Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 029d5ed424061807cf04446cbb10424ae20afba2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="f6dea-102">Funcionalidad para imprimir en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6dea-102">Windows Forms Print Support</span></span>
<span data-ttu-id="f6dea-103">Impresión en formularios Windows Forms consiste principalmente en utilizar el [PrintDocument (componente)](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) componente para permitir al usuario imprimir y el [PrintPreviewDialog Control](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Componente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) y [PageSetupDialog (componente)](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) componentes para proporcionar una interfaz gráfica familiar a los usuarios acostumbrados al sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="f6dea-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="f6dea-104">Normalmente, se crea una nueva instancia de la <xref:System.Drawing.Printing.PrintDocument> componente, establecer las propiedades que describen qué imprimir con la <xref:System.Drawing.Printing.PrinterSettings> y <xref:System.Drawing.Printing.PageSettings> clases y llame a la <xref:System.Drawing.Printing.PrintDocument.Print%2A> método realmente imprimir el documento.</span><span class="sxs-lookup"><span data-stu-id="f6dea-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="f6dea-105">En el transcurso de impresión desde una aplicación basada en Windows, la <xref:System.Drawing.Printing.PrintDocument> componente mostrará un cuadro de diálogo de impresión de anulación alertar a los usuarios al hecho de que se está produciendo la impresión y para permitir que el trabajo de impresión se cancele.</span><span class="sxs-lookup"><span data-stu-id="f6dea-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6dea-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f6dea-106">In This Section</span></span>  
 [<span data-ttu-id="f6dea-107">Crear trabajos de impresión estándar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6dea-107">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="f6dea-108">Explica cómo utilizar el <xref:System.Drawing.Printing.PrintDocument> componente imprimir desde un formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f6dea-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="f6dea-109">Capturar datos proporcionados por el usuario de un componente PrintDialog en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f6dea-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="f6dea-110">Explica cómo modificar opciones de impresión seleccionadas mediante programación con el <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="f6dea-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="f6dea-111">Seleccionar las impresoras conectadas al equipo de un usuario en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6dea-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="f6dea-112">Describe cómo cambiar la impresora para imprimir en usando el <xref:System.Windows.Forms.PrintDialog> componente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f6dea-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="f6dea-113">Cómo: Imprimir gráficos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6dea-113">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="f6dea-114">Describe cómo enviar gráficos a la impresora.</span><span class="sxs-lookup"><span data-stu-id="f6dea-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="f6dea-115">Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6dea-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="f6dea-116">Describe cómo enviar texto a la impresora.</span><span class="sxs-lookup"><span data-stu-id="f6dea-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="f6dea-117">Completar trabajos de impresión de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6dea-117">How to: Complete Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="f6dea-118">Explica cómo alertar a los usuarios hasta la finalización de un trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="f6dea-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="f6dea-119">Imprimir Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6dea-119">How to: Print a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 <span data-ttu-id="f6dea-120">Muestra cómo imprimir una copia del formulario actual.</span><span class="sxs-lookup"><span data-stu-id="f6dea-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="f6dea-121">Imprimir en Windows Forms a través de la vista previa de impresión</span><span class="sxs-lookup"><span data-stu-id="f6dea-121">How to: Print in Windows Forms Using Print Preview</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="f6dea-122">Muestra cómo utilizar un <xref:System.Windows.Forms.PrintPreviewDialog> para imprimir un documento.</span><span class="sxs-lookup"><span data-stu-id="f6dea-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f6dea-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f6dea-123">Related Sections</span></span>  
 [<span data-ttu-id="f6dea-124">PrintDocument (Componente, Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f6dea-124">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="f6dea-125">Explica el uso de la <xref:System.Drawing.Printing.PrintDocument> componente.</span><span class="sxs-lookup"><span data-stu-id="f6dea-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="f6dea-126">PrintDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="f6dea-126">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="f6dea-127">Explica el uso de la <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="f6dea-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="f6dea-128">PrintPreviewDialog (control)</span><span class="sxs-lookup"><span data-stu-id="f6dea-128">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="f6dea-129">Explica el uso de la <xref:System.Windows.Forms.PrintPreviewDialog> control.</span><span class="sxs-lookup"><span data-stu-id="f6dea-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="f6dea-130">PageSetupDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="f6dea-130">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="f6dea-131">Explica el uso de la <xref:System.Windows.Forms.PageSetupDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="f6dea-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="f6dea-132">Describe las clases en el <xref:System.Drawing.Printing> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f6dea-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
