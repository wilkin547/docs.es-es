---
title: "Información general sobre el control PrintPreviewControl (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d50e772cf870d47314a25347f4909367062ffb94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="86b6e-102">Información general sobre el control PrintPreviewControl (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="86b6e-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="86b6e-103">Los formularios Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> se usa para mostrar un [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) tal y como aparecerá cuando se imprima.</span><span class="sxs-lookup"><span data-stu-id="86b6e-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="86b6e-104">Este control no tiene botones ni otros elementos de la interfaz de usuario, por lo que normalmente utiliza <xref:System.Windows.Forms.PrintPreviewControl> solo si desea volver a escribir su propia interfaz de usuario de vista previa de impresión.</span><span class="sxs-lookup"><span data-stu-id="86b6e-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="86b6e-105">Si desea que la interfaz de usuario estándar, utilice un <xref:System.Windows.Forms.PrintPreviewDialog> el control; vea [información general del Control PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) para obtener información general.</span><span class="sxs-lookup"><span data-stu-id="86b6e-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="86b6e-106">Propiedades clave</span><span class="sxs-lookup"><span data-stu-id="86b6e-106">Key Properties</span></span>  
 <span data-ttu-id="86b6e-107">Ninguna propiedad clave del control <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, que establece el documento en una vista previa.</span><span class="sxs-lookup"><span data-stu-id="86b6e-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="86b6e-108">El documento debe ser un <xref:System.Drawing.Printing.PrintDocument> objeto.</span><span class="sxs-lookup"><span data-stu-id="86b6e-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="86b6e-109">Para obtener información general de creación de documentos para la impresión, consulte [general sobre el componente PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) y [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).</span><span class="sxs-lookup"><span data-stu-id="86b6e-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="86b6e-110">El <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> propiedades determinan el número de páginas que se muestran horizontal y verticalmente en el control.</span><span class="sxs-lookup"><span data-stu-id="86b6e-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="86b6e-111">Suavizado de contorno puede hacer que el texto aparezca más suave, pero también puede hacer que la pantalla sea más lenta; para utilizarla, establezca la <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="86b6e-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86b6e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="86b6e-112">See Also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewControl>  
 [<span data-ttu-id="86b6e-113">Información general del control PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="86b6e-113">PrintPreviewDialog Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)  
 [<span data-ttu-id="86b6e-114">PrintPreviewControl (control)</span><span class="sxs-lookup"><span data-stu-id="86b6e-114">PrintPreviewControl Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)  
 [<span data-ttu-id="86b6e-115">Controles y componentes de cuadros de diálogo</span><span class="sxs-lookup"><span data-stu-id="86b6e-115">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
