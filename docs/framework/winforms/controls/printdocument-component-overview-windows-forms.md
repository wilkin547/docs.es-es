---
title: '{1}'
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: a82cc0cdcb8cfae796c9c6bf60ab73873f85a291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728543"
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="1cabe-102">Información general sobre el componente PrintDocument (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1cabe-102">PrintDocument Component Overview (Windows Forms)</span></span>

<span data-ttu-id="1cabe-103">El componente [PrintDocument](printdocument-component-windows-forms.md) de Windows Forms se usa para establecer las propiedades que describen lo que desea imprimir y la capacidad de imprimir el documento en aplicaciones basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="1cabe-103">The Windows Forms [PrintDocument](printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="1cabe-104">Se puede utilizar junto con el componente [PrintDialog](printdialog-component-windows-forms.md) para controlar todos los aspectos de la impresión del documento.</span><span class="sxs-lookup"><span data-stu-id="1cabe-104">It can be used in conjunction with the [PrintDialog](printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>

## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="1cabe-105">Trabajo con el componente PrintDocument</span><span class="sxs-lookup"><span data-stu-id="1cabe-105">Working with the PrintDocument Component</span></span>

<span data-ttu-id="1cabe-106">Dos de los principales escenarios que implican el componente <xref:System.Drawing.Printing.PrintDocument> son:</span><span class="sxs-lookup"><span data-stu-id="1cabe-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>

- <span data-ttu-id="1cabe-107">Trabajos de impresión sencillos, tales como la impresión de un archivo de texto individual.</span><span class="sxs-lookup"><span data-stu-id="1cabe-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="1cabe-108">En tal caso, agregaría el componente <xref:System.Drawing.Printing.PrintDocument> a Windows Forms y, a continuación, agregaría lógica de programación que imprime un archivo en el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage>.</span><span class="sxs-lookup"><span data-stu-id="1cabe-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="1cabe-109">La lógica de programación debe culminar con el método <xref:System.Drawing.Printing.PrintDocument.Print%2A> para imprimir el documento.</span><span class="sxs-lookup"><span data-stu-id="1cabe-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="1cabe-110">Este método envía a la impresora un objeto <xref:System.Drawing.Graphics>, contenido en la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> de la clase <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="1cabe-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="1cabe-111">Para obtener un ejemplo en el que se muestra cómo imprimir un documento de texto mediante el componente de <xref:System.Drawing.Printing.PrintDocument>, vea [Cómo: imprimir un archivo de texto de varias páginas en Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="1cabe-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>

- <span data-ttu-id="1cabe-112">Trabajos de impresión más complejos como, por ejemplo, una situación en la que se desee reutilizar la lógica de impresión escrita.</span><span class="sxs-lookup"><span data-stu-id="1cabe-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="1cabe-113">En tal caso, debe derivar un nuevo componente del componente <xref:System.Drawing.Printing.PrintDocument> e invalidar (vea [invalidaciones](../../../visual-basic/language-reference/modifiers/overrides.md) para Visual Basic o [invalidar](../../../csharp/language-reference/keywords/override.md) para C#) el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.</span><span class="sxs-lookup"><span data-stu-id="1cabe-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](../../../csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>

<span data-ttu-id="1cabe-114">Cuando se agrega a un formulario, el componente de <xref:System.Drawing.Printing.PrintDocument> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1cabe-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="1cabe-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1cabe-115">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- <span data-ttu-id="1cabe-116">[Windows Forms Print Support](../advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1cabe-116">[Windows Forms Print Support](../advanced/windows-forms-print-support.md)</span></span>
- [<span data-ttu-id="1cabe-117">PrintDocument (componente)</span><span class="sxs-lookup"><span data-stu-id="1cabe-117">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
