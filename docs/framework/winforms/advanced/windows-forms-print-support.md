---
title: Funcionalidad para imprimir en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: 8e008f2cb4b2f32cdba676e68d9fd790530e2b06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011858"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="7435e-102">Funcionalidad para imprimir en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7435e-102">Windows Forms Print Support</span></span>
<span data-ttu-id="7435e-103">Impresión en Windows Forms consiste principalmente en usar el [PrintDocument (componente)](../controls/printdocument-component-windows-forms.md) componente para permitir al usuario a imprimir y el [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Componente](../controls/printdialog-component-windows-forms.md) y [componente PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) componentes que ofrecen una interfaz gráfica conocida para los usuarios acostumbrados al sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="7435e-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="7435e-104">Normalmente, se crea una nueva instancia de la <xref:System.Drawing.Printing.PrintDocument> componente, establecer las propiedades que describen qué imprimir con la <xref:System.Drawing.Printing.PrinterSettings> y <xref:System.Drawing.Printing.PageSettings> clases y llame a la <xref:System.Drawing.Printing.PrintDocument.Print%2A> método para imprimir el documento.</span><span class="sxs-lookup"><span data-stu-id="7435e-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="7435e-105">Durante el transcurso de impresión desde una aplicación basada en Windows, la <xref:System.Drawing.Printing.PrintDocument> componente mostrará un cuadro de diálogo de impresión de anulación alertar a los usuarios al hecho de que se está produciendo la impresión y para permitir que el trabajo de impresión se puede cancelar.</span><span class="sxs-lookup"><span data-stu-id="7435e-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7435e-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7435e-106">In This Section</span></span>  
 [<span data-ttu-id="7435e-107">Cómo: Crear trabajos de impresión estándar de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7435e-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="7435e-108">Explica cómo utilizar el <xref:System.Drawing.Printing.PrintDocument> componente para imprimir desde un formulario de Windows.</span><span class="sxs-lookup"><span data-stu-id="7435e-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="7435e-109">Cómo: Captura de datos de usuario de un componente PrintDialog en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7435e-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="7435e-110">Explica cómo modificar opciones de impresión seleccionadas mediante programación con el <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="7435e-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="7435e-111">Cómo: Seleccionar las impresoras conectadas al equipo de un usuario en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7435e-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="7435e-112">Describe cómo cambiar la impresora para imprimir en usando el <xref:System.Windows.Forms.PrintDialog> componente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7435e-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="7435e-113">Cómo: Imprimir gráficos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7435e-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="7435e-114">Describe cómo enviar gráficos a la impresora.</span><span class="sxs-lookup"><span data-stu-id="7435e-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="7435e-115">Cómo: Imprimir un archivo de texto de varias páginas en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7435e-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="7435e-116">Describe cómo enviar texto a la impresora.</span><span class="sxs-lookup"><span data-stu-id="7435e-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="7435e-117">Cómo: Los trabajos de impresión de formularios de Windows completo</span><span class="sxs-lookup"><span data-stu-id="7435e-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="7435e-118">Explica cómo alertar a los usuarios a la finalización de un trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="7435e-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="7435e-119">Cómo: Imprimir un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="7435e-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="7435e-120">Muestra cómo imprimir una copia del formulario actual.</span><span class="sxs-lookup"><span data-stu-id="7435e-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="7435e-121">Cómo: Imprimir en Windows Forms a través de la vista previa de impresión</span><span class="sxs-lookup"><span data-stu-id="7435e-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="7435e-122">Se muestra cómo usar un <xref:System.Windows.Forms.PrintPreviewDialog> para imprimir un documento.</span><span class="sxs-lookup"><span data-stu-id="7435e-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7435e-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7435e-123">Related Sections</span></span>  
 [<span data-ttu-id="7435e-124">PrintDocument (Componente, Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7435e-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="7435e-125">Explica el uso de la <xref:System.Drawing.Printing.PrintDocument> componente.</span><span class="sxs-lookup"><span data-stu-id="7435e-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="7435e-126">PrintDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="7435e-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="7435e-127">Explica el uso de la <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="7435e-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="7435e-128">PrintPreviewDialog (control)</span><span class="sxs-lookup"><span data-stu-id="7435e-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="7435e-129">Explica el uso de la <xref:System.Windows.Forms.PrintPreviewDialog> control.</span><span class="sxs-lookup"><span data-stu-id="7435e-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="7435e-130">PageSetupDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="7435e-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="7435e-131">Explica el uso de la <xref:System.Windows.Forms.PageSetupDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="7435e-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="7435e-132">Describe las clases en el <xref:System.Drawing.Printing> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7435e-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
