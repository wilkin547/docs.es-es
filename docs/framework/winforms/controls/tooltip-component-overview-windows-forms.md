---
title: "Información general sobre el componente ToolTip (formularios Windows Forms)"
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
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fce1cb5750197e52461b4883f1238325fa10fc5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="tooltip-component-overview-windows-forms"></a><span data-ttu-id="c1a90-102">Información general sobre el componente ToolTip (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c1a90-102">ToolTip Component Overview (Windows Forms)</span></span>
<span data-ttu-id="c1a90-103">El componente <xref:System.Windows.Forms.ToolTip> de Windows Forms muestra texto cuando el usuario apunta a otros controles.</span><span class="sxs-lookup"><span data-stu-id="c1a90-103">The Windows Forms <xref:System.Windows.Forms.ToolTip> component displays text when the user points at controls.</span></span> <span data-ttu-id="c1a90-104">Un componente Tooltip se puede asociar con cualquier control.</span><span class="sxs-lookup"><span data-stu-id="c1a90-104">A ToolTip can be associated with any control.</span></span> <span data-ttu-id="c1a90-105">Un ejemplo del uso de este componente: para ahorrar espacio en un formulario, puede mostrar un pequeño icono en un botón y utilizar un componente ToolTip para explicar la función del botón.</span><span class="sxs-lookup"><span data-stu-id="c1a90-105">An example use of this component: to save space on a form, you can display a small icon on a button and use a ToolTip to explain the button's function.</span></span>  
  
## <a name="working-with-the-tooltip-component"></a><span data-ttu-id="c1a90-106">Trabajar con el componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="c1a90-106">Working with the ToolTip Component</span></span>  
 <span data-ttu-id="c1a90-107">A <xref:System.Windows.Forms.ToolTip> componente proporciona un `ToolTip` propiedad para varios controles en un formulario Windows Forms o en otro contenedor.</span><span class="sxs-lookup"><span data-stu-id="c1a90-107">A <xref:System.Windows.Forms.ToolTip> component provides a `ToolTip` property to multiple controls on a Windows Form or other container.</span></span> <span data-ttu-id="c1a90-108">Por ejemplo, si coloca uno <xref:System.Windows.Forms.ToolTip> componente en un formulario, puede mostrar "Escriba aquí el nombre" para un <xref:System.Windows.Forms.TextBox> controlar y "Haga clic aquí para guardar los cambios" para un <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="c1a90-108">For example, if you place one <xref:System.Windows.Forms.ToolTip> component on a form, you can display "Type your name here" for a <xref:System.Windows.Forms.TextBox> control and "Click here to save changes" for a <xref:System.Windows.Forms.Button> control.</span></span>  
  
 <span data-ttu-id="c1a90-109">Los métodos principales de la <xref:System.Windows.Forms.ToolTip> componente <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> y <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span><span class="sxs-lookup"><span data-stu-id="c1a90-109">The key methods of the <xref:System.Windows.Forms.ToolTip> component are <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> and <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span></span> <span data-ttu-id="c1a90-110">Puede usar el <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método para establecer la información sobre herramientas muestra para los controles.</span><span class="sxs-lookup"><span data-stu-id="c1a90-110">You can use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method to set the ToolTips displayed for controls.</span></span> <span data-ttu-id="c1a90-111">Para obtener más información, consulte [Cómo: establecer información sobre herramientas para controles en un formulario Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="c1a90-111">For more information, see [How to: Set ToolTips for Controls on a Windows Form at Design Time](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span></span> <span data-ttu-id="c1a90-112">Las propiedades claves son <xref:System.Windows.Forms.ToolTip.Active%2A>, que debe establecerse en `true` para la información sobre herramientas que se muestre y <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, que establece el período de tiempo que se muestra la cadena de información sobre herramientas, cuánto tiempo debe apuntar el usuario en el control de la información sobre herramientas que se muestre y cómo tiempo que toma de la siguiente ventana de información sobre herramientas que aparezca.</span><span class="sxs-lookup"><span data-stu-id="c1a90-112">The key properties are <xref:System.Windows.Forms.ToolTip.Active%2A>, which must be set to `true` for the ToolTip to appear, and <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, which sets the length of time that the ToolTip string is shown, how long the user must point at the control for the ToolTip to appear, and how long it takes for subsequent ToolTip windows to appear.</span></span> <span data-ttu-id="c1a90-113">Para obtener más información, consulte [Cómo: cambiar el retardo del componente ToolTip de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span><span class="sxs-lookup"><span data-stu-id="c1a90-113">For more information, see [How to: Change the Delay of the Windows Forms ToolTip Component](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a90-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1a90-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolTip>  
 [<span data-ttu-id="c1a90-115">Establecer información sobre herramientas en controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="c1a90-115">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [<span data-ttu-id="c1a90-116">Cambiar el retardo del componente ToolTip de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1a90-116">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
