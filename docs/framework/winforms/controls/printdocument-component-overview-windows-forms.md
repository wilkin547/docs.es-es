---
title: "Información general sobre el componente PrintDocument (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 414a7972550558b40403b7f4cbfd9a49194666be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="5e8c4-102">Información general sobre el componente PrintDocument (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5e8c4-102">PrintDocument Component Overview (Windows Forms)</span></span>
<span data-ttu-id="5e8c4-103">El componente [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) de Windows Forms se usa para establecer las propiedades que describen lo que desea imprimir y la capacidad de imprimir el documento en aplicaciones basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="5e8c4-103">The Windows Forms [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="5e8c4-104">Se puede utilizar junto con el componente [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) para controlar todos los aspectos de la impresión del documento.</span><span class="sxs-lookup"><span data-stu-id="5e8c4-104">It can be used in conjunction with the [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>  
  
## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="5e8c4-105">Trabajo con el componente PrintDocument</span><span class="sxs-lookup"><span data-stu-id="5e8c4-105">Working with the PrintDocument Component</span></span>  
 <span data-ttu-id="5e8c4-106">Dos de los principales escenarios que implican la <xref:System.Drawing.Printing.PrintDocument> componente son:</span><span class="sxs-lookup"><span data-stu-id="5e8c4-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>  
  
-   <span data-ttu-id="5e8c4-107">Trabajos de impresión sencillos, tales como la impresión de un archivo de texto individual.</span><span class="sxs-lookup"><span data-stu-id="5e8c4-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="5e8c4-108">En tal caso agregaría el <xref:System.Drawing.Printing.PrintDocument> componente a un formulario Windows Forms, a continuación, agregar lógica de programación que imprime un archivo en el <xref:System.Drawing.Printing.PrintDocument.PrintPage> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="5e8c4-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="5e8c4-109">La lógica de programación debe culminan con la <xref:System.Drawing.Printing.PrintDocument.Print%2A> método para imprimir el documento.</span><span class="sxs-lookup"><span data-stu-id="5e8c4-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="5e8c4-110">Este método envía un <xref:System.Drawing.Graphics> objeto, incluido en el <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> propiedad de la <xref:System.Drawing.Printing.PrintPageEventArgs> (clase), a la impresora.</span><span class="sxs-lookup"><span data-stu-id="5e8c4-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="5e8c4-111">Para obtener un ejemplo que muestra cómo imprimir un documento de texto utilizando la <xref:System.Drawing.Printing.PrintDocument> componente, vea [Cómo: imprimir un archivo de texto de varias páginas en formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5e8c4-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="5e8c4-112">Trabajos de impresión más complejos como, por ejemplo, una situación en la que se desee reutilizar la lógica de impresión escrita.</span><span class="sxs-lookup"><span data-stu-id="5e8c4-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="5e8c4-113">En tal caso, deberá derivar un nuevo componente de la <xref:System.Drawing.Printing.PrintDocument> componente e invalide (vea [invalida](~/docs/visual-basic/language-reference/modifiers/overrides.md) para Visual Basic o [invalidar](~/docs/csharp/language-reference/keywords/override.md) en C#) el <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventos.</span><span class="sxs-lookup"><span data-stu-id="5e8c4-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](~/docs/visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](~/docs/csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
 <span data-ttu-id="5e8c4-114">Cuando se agrega a un formulario, el <xref:System.Drawing.Printing.PrintDocument> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5e8c4-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e8c4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e8c4-115">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Printing.PrintDocument>  
 <span data-ttu-id="5e8c4-116">[Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5e8c4-116">[Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)</span></span>  
 [<span data-ttu-id="5e8c4-117">PrintDocument (Componente, Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5e8c4-117">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)
