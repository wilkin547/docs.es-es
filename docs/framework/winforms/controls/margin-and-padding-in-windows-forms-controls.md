---
title: Márgenes y relleno en controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
ms.openlocfilehash: be5d1ae308b9412f914f1cde91d1cc5834212df8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570556"
---
# <a name="margin-and-padding-in-windows-forms-controls"></a><span data-ttu-id="ffab0-102">Márgenes y relleno en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ffab0-102">Margin and Padding in Windows Forms Controls</span></span>
<span data-ttu-id="ffab0-103">La posición precisa de los controles del formulario es de alta prioridad para muchas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ffab0-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="ffab0-104">El espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> le ofrece muchas características de diseño para lograrlo.</span><span class="sxs-lookup"><span data-stu-id="ffab0-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout features to accomplish this.</span></span> <span data-ttu-id="ffab0-105">Dos de las más importantes son las propiedades <xref:System.Windows.Forms.Control.Margin%2A> y <xref:System.Windows.Forms.Control.Padding%2A>.</span><span class="sxs-lookup"><span data-stu-id="ffab0-105">Two of the most important are the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties.</span></span>  
  
 <span data-ttu-id="ffab0-106">La propiedad <xref:System.Windows.Forms.Control.Margin%2A> define el espacio alrededor del control que mantiene a los demás controles a una distancia especificada de los bordes del control.</span><span class="sxs-lookup"><span data-stu-id="ffab0-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="ffab0-107">La propiedad <xref:System.Windows.Forms.Control.Padding%2A> define el espacio en el interior de un control que mantiene el contenido del control (por ejemplo, el valor de su propiedad <xref:System.Windows.Forms.Control.Text%2A>) a una distancia especificada de los bordes del control.</span><span class="sxs-lookup"><span data-stu-id="ffab0-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="ffab0-108">La siguiente ilustración muestra las propiedades <xref:System.Windows.Forms.Control.Padding%2A> y <xref:System.Windows.Forms.Control.Margin%2A> de un control.</span><span class="sxs-lookup"><span data-stu-id="ffab0-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="ffab0-109">![Relleno y margen de Windows Forms controles](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="ffab0-109">![Padding And Margin for Windows Forms Controls](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="ffab0-110">Hay compatibilidad en tiempo de diseño para esta característica en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ffab0-110">There is design-time support for this feature in Visual Studio.</span></span>  <span data-ttu-id="ffab0-111">Consulte también [Tutorial: Diseño de Windows Forms con relleno, márgenes y la propiedad AutoSize los controles](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="ffab0-111">Also see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffab0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffab0-112">See also</span></span>
- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
