---
title: Procedimiento Un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip (formularios Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: 707fd2e470a9be1d61d2878eeff845b3cad270db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223581"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="aa24e-102">Procedimiento Un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="aa24e-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="aa24e-103">Al establecer el <xref:System.Windows.Forms.ToolStrip.Stretch%2A> propiedad de un <xref:System.Windows.Forms.ToolStrip> el control a `true`, el control rellena su contenedor de extremo a extremo y cambia de tamaño cuando cambia el tamaño de su contenedor.</span><span class="sxs-lookup"><span data-stu-id="aa24e-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="aa24e-104">En esta configuración, le resultará útil para ajustar un elemento en el control, como un <xref:System.Windows.Forms.ToolStripTextBox>, para rellenar el espacio disponible y para cambiar el tamaño cuando el control cambia de tamaño.</span><span class="sxs-lookup"><span data-stu-id="aa24e-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="aa24e-105">Este ajuste es útil, por ejemplo, si desea obtener una apariencia y comportamiento similar a la barra de direcciones en Microsoft® Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="aa24e-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa24e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa24e-106">Example</span></span>  
 <span data-ttu-id="aa24e-107">En el ejemplo de código siguiente se proporciona una clase derivada de <xref:System.Windows.Forms.ToolStripTextBox> llamado `ToolStripSpringTextBox`.</span><span class="sxs-lookup"><span data-stu-id="aa24e-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="aa24e-108">Esta clase invalida el <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> método para calcular el ancho disponible del elemento primario <xref:System.Windows.Forms.ToolStrip> controlar una vez restado el ancho combinado de todos los demás elementos.</span><span class="sxs-lookup"><span data-stu-id="aa24e-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="aa24e-109">Este ejemplo de código también proporciona un <xref:System.Windows.Forms.Form> clase y un `Program` clase para mostrar el nuevo comportamiento.</span><span class="sxs-lookup"><span data-stu-id="aa24e-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aa24e-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="aa24e-110">Compiling the Code</span></span>  
 <span data-ttu-id="aa24e-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="aa24e-111">This example requires:</span></span>  
  
-   <span data-ttu-id="aa24e-112">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="aa24e-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa24e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa24e-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="aa24e-114">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="aa24e-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="aa24e-115">Cómo: Utilizar la propiedad Spring de manera interactiva en un control StatusStrip</span><span class="sxs-lookup"><span data-stu-id="aa24e-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
