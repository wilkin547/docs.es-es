---
title: Compatibilidad con impresión
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732495"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="e4987-102">Funcionalidad para imprimir en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4987-102">Windows Forms Print Support</span></span>
<span data-ttu-id="e4987-103">La impresión en Windows Forms consiste principalmente en el uso del componente de [componente PrintDocument](../controls/printdocument-component-windows-forms.md) para permitir que el usuario imprima, y el control de [control PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md) , los componentes de [componente PrintDialog](../controls/printdialog-component-windows-forms.md) y [componente PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) para proporcionar una interfaz gráfica familiar a los usuarios acostumbrados al sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="e4987-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="e4987-104">Normalmente, se crea una nueva instancia del componente <xref:System.Drawing.Printing.PrintDocument>, se establecen las propiedades que describen lo que se va a imprimir mediante las clases <xref:System.Drawing.Printing.PrinterSettings> y <xref:System.Drawing.Printing.PageSettings> y se llama al método <xref:System.Drawing.Printing.PrintDocument.Print%2A> para imprimir realmente el documento.</span><span class="sxs-lookup"><span data-stu-id="e4987-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="e4987-105">Durante el transcurso de la impresión desde una aplicación basada en Windows, el componente de <xref:System.Drawing.Printing.PrintDocument> mostrará un cuadro de diálogo anular impresión para avisar a los usuarios del hecho de que se está produciendo la impresión y permitir que se cancele el trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="e4987-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4987-106">Esta sección</span><span class="sxs-lookup"><span data-stu-id="e4987-106">In This Section</span></span>  
 [<span data-ttu-id="e4987-107">Crear trabajos de impresión estándar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4987-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="e4987-108">Explica cómo utilizar el componente de <xref:System.Drawing.Printing.PrintDocument> para imprimir desde un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="e4987-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="e4987-109">Capturar datos proporcionados por el usuario de un componente PrintDialog en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e4987-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="e4987-110">Explica cómo modificar las opciones de impresión seleccionadas mediante programación con el <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="e4987-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="e4987-111">Seleccionar las impresoras conectadas al equipo de un usuario en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4987-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="e4987-112">Describe el cambio de la impresora que se va a imprimir con el componente de <xref:System.Windows.Forms.PrintDialog> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e4987-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="e4987-113">Cómo: Imprimir gráficos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4987-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="e4987-114">Describe el envío de gráficos a la impresora.</span><span class="sxs-lookup"><span data-stu-id="e4987-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="e4987-115">Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4987-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="e4987-116">Describe el envío de texto a la impresora.</span><span class="sxs-lookup"><span data-stu-id="e4987-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="e4987-117">Completar trabajos de impresión de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4987-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="e4987-118">Explica cómo avisar a los usuarios de la finalización de un trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="e4987-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="e4987-119">Imprimir Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4987-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="e4987-120">Muestra cómo imprimir una copia del formulario actual.</span><span class="sxs-lookup"><span data-stu-id="e4987-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="e4987-121">Imprimir en Windows Forms a través de la vista previa de impresión</span><span class="sxs-lookup"><span data-stu-id="e4987-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="e4987-122">Muestra cómo utilizar un <xref:System.Windows.Forms.PrintPreviewDialog> para imprimir un documento.</span><span class="sxs-lookup"><span data-stu-id="e4987-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e4987-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e4987-123">Related Sections</span></span>  
 [<span data-ttu-id="e4987-124">PrintDocument (Componente, Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e4987-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="e4987-125">Explica el uso del componente <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="e4987-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="e4987-126">PrintDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="e4987-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="e4987-127">Explica el uso del componente <xref:System.Windows.Forms.PrintDialog>.</span><span class="sxs-lookup"><span data-stu-id="e4987-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="e4987-128">PrintPreviewDialog (control)</span><span class="sxs-lookup"><span data-stu-id="e4987-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="e4987-129">Explica el uso del control <xref:System.Windows.Forms.PrintPreviewDialog>.</span><span class="sxs-lookup"><span data-stu-id="e4987-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="e4987-130">PageSetupDialog Component</span><span class="sxs-lookup"><span data-stu-id="e4987-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="e4987-131">Explica el uso del componente <xref:System.Windows.Forms.PageSetupDialog>.</span><span class="sxs-lookup"><span data-stu-id="e4987-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="e4987-132">Describe las clases en el espacio de nombres <xref:System.Drawing.Printing>.</span><span class="sxs-lookup"><span data-stu-id="e4987-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
