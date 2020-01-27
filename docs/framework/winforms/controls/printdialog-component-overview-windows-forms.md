---
title: Información general sobre el componente PrintDialog
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728669"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="7dde6-102">Información general sobre el componente PrintDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7dde6-102">PrintDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="7dde6-103">El Windows Forms componente [PrintDialog](printdialog-component-windows-forms.md) es un cuadro de diálogo preconfigurado que se usa para seleccionar una impresora, elegir las páginas que se van a imprimir y determinar otros valores de configuración relacionados con la impresión en aplicaciones basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="7dde6-103">The Windows Forms [PrintDialog](printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="7dde6-104">Utilizar como una solución sencilla para la impresora y la selección de configuración relacionada con la impresión en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7dde6-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="7dde6-105">Puede permitir que los usuarios impriman muchas partes de sus documentos: Imprimir todo, imprimir un intervalo de páginas seleccionado o imprimir una selección.</span><span class="sxs-lookup"><span data-stu-id="7dde6-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="7dde6-106">Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7dde6-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="7dde6-107">El componente de <xref:System.Windows.Forms.PrintDialog> hereda de la clase <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="7dde6-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-component"></a><span data-ttu-id="7dde6-108">Trabajar con el componente</span><span class="sxs-lookup"><span data-stu-id="7dde6-108">Working with the Component</span></span>

<span data-ttu-id="7dde6-109">Utilice el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7dde6-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="7dde6-110">Este componente tiene propiedades relacionadas con un solo trabajo de impresión (clase<xref:System.Drawing.Printing.PrintDocument>) o con la configuración de una impresora individual (clase<xref:System.Drawing.Printing.PrinterSettings>).</span><span class="sxs-lookup"><span data-stu-id="7dde6-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="7dde6-111">Cualquiera de ellas, a su vez, se puede compartir entre varias impresoras.</span><span class="sxs-lookup"><span data-stu-id="7dde6-111">Either of these, in turn, may be shared by multiple printers.</span></span>

<span data-ttu-id="7dde6-112">Cuando se agrega a un formulario, el componente de <xref:System.Windows.Forms.PrintDialog> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7dde6-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="7dde6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dde6-113">See also</span></span>

- <xref:System.Windows.Forms.PrintDialog>
- [<span data-ttu-id="7dde6-114">PrintDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="7dde6-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
