---
title: Información general sobre el componente PrintDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0b0e516364277133efc83e7324345ccea8328690
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535494"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="18fe3-102">Información general sobre el componente PrintDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="18fe3-102">PrintDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="18fe3-103">Los formularios Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) componente es un cuadro de diálogo preconfigurado que se utiliza para seleccionar una impresora, elegir las páginas que se va a imprimir y determinar otra configuración relacionada con la impresión en aplicaciones basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="18fe3-103">The Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="18fe3-104">Utilizar como una solución sencilla para la impresora y la selección de configuración relacionada con la impresión en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="18fe3-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="18fe3-105">Puede permitir que los usuarios impriman diversas partes de sus documentos: imprimir todo, imprimir un intervalo de páginas seleccionado o imprimir una selección.</span><span class="sxs-lookup"><span data-stu-id="18fe3-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="18fe3-106">Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="18fe3-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="18fe3-107">El <xref:System.Windows.Forms.PrintDialog> componente hereda de la <xref:System.Windows.Forms.CommonDialog> clase.</span><span class="sxs-lookup"><span data-stu-id="18fe3-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-component"></a><span data-ttu-id="18fe3-108">Trabajar con el componente</span><span class="sxs-lookup"><span data-stu-id="18fe3-108">Working with the Component</span></span>  
 <span data-ttu-id="18fe3-109">Use la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="18fe3-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="18fe3-110">Este componente tiene propiedades relacionadas con un único trabajo de impresión (<xref:System.Drawing.Printing.PrintDocument> clase) o la configuración de una impresora individual (<xref:System.Drawing.Printing.PrinterSettings> clase).</span><span class="sxs-lookup"><span data-stu-id="18fe3-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="18fe3-111">Cualquiera de estos, a su vez, pueden estar compartido por varias impresoras.</span><span class="sxs-lookup"><span data-stu-id="18fe3-111">Either of these, in turn, may be shared by multiple printers.</span></span>  
  
 <span data-ttu-id="18fe3-112">Cuando se agrega a un formulario, el <xref:System.Windows.Forms.PrintDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="18fe3-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18fe3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="18fe3-113">See Also</span></span>  
 <xref:System.Windows.Forms.PrintDialog>  
 [<span data-ttu-id="18fe3-114">PrintDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="18fe3-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
