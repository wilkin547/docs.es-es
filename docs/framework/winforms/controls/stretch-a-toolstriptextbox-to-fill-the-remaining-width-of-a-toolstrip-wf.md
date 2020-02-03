---
title: 'Cómo: Ajustar un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742843"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="9ef50-102">Cómo: Ajustar un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9ef50-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="9ef50-103">Cuando se establece la propiedad <xref:System.Windows.Forms.ToolStrip.Stretch%2A> de un control <xref:System.Windows.Forms.ToolStrip> en `true`, el control rellena su contenedor de un extremo a otro y cambia de tamaño cuando se cambia el tamaño de su contenedor.</span><span class="sxs-lookup"><span data-stu-id="9ef50-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="9ef50-104">En esta configuración, puede que le resulte útil expandir un elemento del control, como un <xref:System.Windows.Forms.ToolStripTextBox>, para rellenar el espacio disponible y cambiar el tamaño cuando el control cambia de tamaño.</span><span class="sxs-lookup"><span data-stu-id="9ef50-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="9ef50-105">Esta ampliación es útil, por ejemplo, si desea lograr la apariencia y el comportamiento similares a la barra de direcciones de Microsoft® Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="9ef50-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ef50-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ef50-106">Example</span></span>  
 <span data-ttu-id="9ef50-107">En el ejemplo de código siguiente se proporciona una clase derivada de <xref:System.Windows.Forms.ToolStripTextBox> denominada `ToolStripSpringTextBox`.</span><span class="sxs-lookup"><span data-stu-id="9ef50-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="9ef50-108">Esta clase invalida el método <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> para calcular el ancho disponible del control primario <xref:System.Windows.Forms.ToolStrip> una vez que se ha restado el ancho combinado de todos los demás elementos.</span><span class="sxs-lookup"><span data-stu-id="9ef50-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="9ef50-109">En este ejemplo de código también se proporciona una clase <xref:System.Windows.Forms.Form> y una clase `Program` para mostrar el nuevo comportamiento.</span><span class="sxs-lookup"><span data-stu-id="9ef50-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ef50-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9ef50-110">Compiling the Code</span></span>  
 <span data-ttu-id="9ef50-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9ef50-111">This example requires:</span></span>  
  
- <span data-ttu-id="9ef50-112">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9ef50-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ef50-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ef50-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9ef50-114">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9ef50-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="9ef50-115">Utilizar la propiedad Spring de manera interactiva en un control StatusStrip</span><span class="sxs-lookup"><span data-stu-id="9ef50-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
