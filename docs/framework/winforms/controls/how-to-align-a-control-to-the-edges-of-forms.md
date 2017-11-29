---
title: "Cómo: Alinear un control con los bordes de los formularios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a55212ac4d770848355ace1b0ef3fff3cc50f871
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a><span data-ttu-id="c3059-102">Cómo: Alinear un control con los bordes de los formularios</span><span class="sxs-lookup"><span data-stu-id="c3059-102">How to: Align a Control to the Edges of Forms</span></span>
<span data-ttu-id="c3059-103">Puede alinear el control con el borde de los formularios estableciendo la propiedad <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="c3059-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="c3059-104">Esta propiedad designa el lugar en el que se encuentra el control en el formulario.</span><span class="sxs-lookup"><span data-stu-id="c3059-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="c3059-105">La propiedad <xref:System.Windows.Forms.Control.Dock%2A> puede establecerse en los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3059-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>  
  
|<span data-ttu-id="c3059-106">Configuración</span><span class="sxs-lookup"><span data-stu-id="c3059-106">Setting</span></span>|<span data-ttu-id="c3059-107">Efecto en el control</span><span class="sxs-lookup"><span data-stu-id="c3059-107">Effect on your control</span></span>|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="c3059-108">Lo acopla en la parte inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="c3059-108">Docks to the bottom of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="c3059-109">Llena todo el espacio restante del formulario.</span><span class="sxs-lookup"><span data-stu-id="c3059-109">Fills all remaining space in the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="c3059-110">Lo acopla en el lado izquierdo del formulario.</span><span class="sxs-lookup"><span data-stu-id="c3059-110">Docks to the left side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="c3059-111">No lo acopla en ningún lugar y aparece en la ubicación especificada por su propiedad <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="c3059-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="c3059-112">Lo acopla en el lado derecho del formulario.</span><span class="sxs-lookup"><span data-stu-id="c3059-112">Docks to the right side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="c3059-113">Lo acopla en la parte superior del formulario.</span><span class="sxs-lookup"><span data-stu-id="c3059-113">Docks to the top of the form.</span></span>|  
  
 <span data-ttu-id="c3059-114">Hay compatibilidad en tiempo de diseño para esta característica en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c3059-114">There is design-time support for this feature in Visual Studio.</span></span>  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a><span data-ttu-id="c3059-115">Para establecer la propiedad Dock en su control en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c3059-115">To set the Dock property for your control at run time</span></span>  
  
1.  <span data-ttu-id="c3059-116">Establezca un valor adecuado en el código para la propiedad <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="c3059-116">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to the appropriate value in code.</span></span>  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c3059-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3059-117">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="c3059-118">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c3059-118">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="c3059-119">Delimitar y acoplar controles secundarios en un control FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c3059-119">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="c3059-120">Delimitar y acoplar controles secundarios en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c3059-120">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="c3059-121">Información general sobre la propiedad AutoSize</span><span class="sxs-lookup"><span data-stu-id="c3059-121">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
