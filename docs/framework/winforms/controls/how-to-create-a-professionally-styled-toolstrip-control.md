---
title: Procedimiento para crear un control ToolStrip de estilo profesional
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 4e4e899d583eb87b3ced7161f1fd274c0bcc591c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586555"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="9150b-102">Procedimiento para crear un control ToolStrip de estilo profesional</span><span class="sxs-lookup"><span data-stu-id="9150b-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="9150b-103">Puede dar a los controles <xref:System.Windows.Forms.ToolStrip> de la aplicación un aspecto y comportamiento profesional escribiendo su propia clase derivada del tipo <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span><span class="sxs-lookup"><span data-stu-id="9150b-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="9150b-104">Hay una amplia compatibilidad para esta característica en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9150b-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="9150b-105">Vea [Tutorial: Crear un Control ToolStrip de estilo profesional](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="9150b-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9150b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9150b-106">Example</span></span>  
 <span data-ttu-id="9150b-107">En el ejemplo de código siguiente se muestra cómo usar <xref:System.Windows.Forms.ToolStrip> controles para crear un control compuesto que imite el **panel de navegación** proporcionado por Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="9150b-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9150b-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9150b-108">Compiling the Code</span></span>  
 <span data-ttu-id="9150b-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9150b-109">This example requires:</span></span>  
  
- <span data-ttu-id="9150b-110">Referencias a los ensamblados System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9150b-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9150b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9150b-111">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="9150b-112">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9150b-112">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="9150b-113">Cómo: Proporcionar elementos de menú estándar a un formulario</span><span class="sxs-lookup"><span data-stu-id="9150b-113">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
