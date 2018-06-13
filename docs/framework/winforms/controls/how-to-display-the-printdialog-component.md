---
title: 'Cómo: Mostrar el componente PrintDialog'
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: d8765187522f8becf24b519434b7c170c1c755b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532192"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="7752a-102">Cómo: Mostrar el componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="7752a-102">How to: Display the PrintDialog Component</span></span>
<span data-ttu-id="7752a-103">El <xref:System.Windows.Forms.PrintDialog> componente es el cuadro de diálogo de impresión de Windows estándar que muchos de los usuarios estarán familiarizados con.</span><span class="sxs-lookup"><span data-stu-id="7752a-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="7752a-104">Dado que los usuarios cómodos con él, sería beneficioso para su uso la <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="7752a-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
### <a name="to-display-the-printdialog-component"></a><span data-ttu-id="7752a-105">Mostrar el componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="7752a-105">To display the PrintDialog component</span></span>  
  
-   <span data-ttu-id="7752a-106">Llame a la <xref:System.Windows.Forms.Form.ShowDialog%2A> método desde el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7752a-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>  
  
     <span data-ttu-id="7752a-107">Una vez que se muestre el componente, los usuarios interactuarán con él y establecerán las propiedades del trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="7752a-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="7752a-108">Éstas se guardan en el <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` clase (y el <xref:System.Drawing.Printing.PageSettings> de la clase, si el usuario tiene acceso a la [PageSetupDialog (componente)](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) a través de la <xref:System.Windows.Forms.PrintDialog> componente) asociados a ese trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="7752a-108">These are saved in the <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="7752a-109">A continuación, puede realizar llamadas a las propiedades que establecen para determinar los detalles del trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="7752a-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7752a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7752a-110">See Also</span></span>  
 [<span data-ttu-id="7752a-111">Crear trabajos de impresión estándar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7752a-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [<span data-ttu-id="7752a-112">Capturar datos proporcionados por el usuario de un componente PrintDialog en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7752a-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [<span data-ttu-id="7752a-113">PrintPreviewDialog (control)</span><span class="sxs-lookup"><span data-stu-id="7752a-113">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="7752a-114">PrintDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="7752a-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="7752a-115">[Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7752a-115">[Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)</span></span>  
 [<span data-ttu-id="7752a-116">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7752a-116">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
