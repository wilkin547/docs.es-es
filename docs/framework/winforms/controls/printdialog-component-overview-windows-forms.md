---
title: Información general sobre el componente PrintDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 982c52dbe9243e69bbb0452513e78798f4d1fd0d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072446"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="97a14-102">Información general sobre el componente PrintDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="97a14-102">PrintDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="97a14-103">Los formularios de Windows [PrintDialog](printdialog-component-windows-forms.md) componente es un cuadro de diálogo preconfigurado que se utiliza para seleccionar una impresora, elegir las páginas para imprimir y determinar otra configuración relacionada con la impresión en aplicaciones basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="97a14-103">The Windows Forms [PrintDialog](printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="97a14-104">Utilizar como una solución sencilla para la impresora y la selección de configuración relacionada con la impresión en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="97a14-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="97a14-105">Puede permitir que los usuarios impriman diversas partes de sus documentos: imprimir todo, imprimir un intervalo de páginas seleccionado o imprimir una selección.</span><span class="sxs-lookup"><span data-stu-id="97a14-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="97a14-106">Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="97a14-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="97a14-107">El <xref:System.Windows.Forms.PrintDialog> componente hereda de la <xref:System.Windows.Forms.CommonDialog> clase.</span><span class="sxs-lookup"><span data-stu-id="97a14-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-component"></a><span data-ttu-id="97a14-108">Trabajar con el componente</span><span class="sxs-lookup"><span data-stu-id="97a14-108">Working with the Component</span></span>  
 <span data-ttu-id="97a14-109">Use el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="97a14-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="97a14-110">Este componente tiene propiedades relacionadas con un único trabajo de impresión (<xref:System.Drawing.Printing.PrintDocument> clase) o la configuración de una impresora individual (<xref:System.Drawing.Printing.PrinterSettings> clase).</span><span class="sxs-lookup"><span data-stu-id="97a14-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="97a14-111">Cualquiera de estos, a su vez, pueden compartirse entre varias impresoras.</span><span class="sxs-lookup"><span data-stu-id="97a14-111">Either of these, in turn, may be shared by multiple printers.</span></span>  
  
 <span data-ttu-id="97a14-112">Cuando se agrega a un formulario, el <xref:System.Windows.Forms.PrintDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="97a14-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a14-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="97a14-113">See also</span></span>

- <xref:System.Windows.Forms.PrintDialog>
- [<span data-ttu-id="97a14-114">PrintDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="97a14-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
