---
title: "Información general sobre el componente PrintDialog (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b90d94165de6985b43d47809ae57bfcae204f0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="aa282-102">Información general sobre el componente PrintDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="aa282-102">PrintDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="aa282-103">Los formularios Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) componente es un cuadro de diálogo preconfigurado que se utiliza para seleccionar una impresora, elegir las páginas que se va a imprimir y determinar otra configuración relacionada con la impresión en aplicaciones basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="aa282-103">The Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="aa282-104">Utilizar como una solución sencilla para la impresora y la selección de configuración relacionada con la impresión en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aa282-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="aa282-105">Puede permitir que los usuarios impriman diversas partes de sus documentos: imprimir todo, imprimir un intervalo de páginas seleccionado o imprimir una selección.</span><span class="sxs-lookup"><span data-stu-id="aa282-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="aa282-106">Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="aa282-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="aa282-107">El <xref:System.Windows.Forms.PrintDialog> componente hereda de la <xref:System.Windows.Forms.CommonDialog> clase.</span><span class="sxs-lookup"><span data-stu-id="aa282-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-component"></a><span data-ttu-id="aa282-108">Trabajar con el componente</span><span class="sxs-lookup"><span data-stu-id="aa282-108">Working with the Component</span></span>  
 <span data-ttu-id="aa282-109">Use la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa282-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="aa282-110">Este componente tiene propiedades relacionadas con un único trabajo de impresión (<xref:System.Drawing.Printing.PrintDocument> clase) o la configuración de una impresora individual (<xref:System.Drawing.Printing.PrinterSettings> clase).</span><span class="sxs-lookup"><span data-stu-id="aa282-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="aa282-111">Cualquiera de estos, a su vez, pueden estar compartido por varias impresoras.</span><span class="sxs-lookup"><span data-stu-id="aa282-111">Either of these, in turn, may be shared by multiple printers.</span></span>  
  
 <span data-ttu-id="aa282-112">Cuando se agrega a un formulario, el <xref:System.Windows.Forms.PrintDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="aa282-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa282-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa282-113">See Also</span></span>  
 <xref:System.Windows.Forms.PrintDialog>  
 [<span data-ttu-id="aa282-114">PrintDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="aa282-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
