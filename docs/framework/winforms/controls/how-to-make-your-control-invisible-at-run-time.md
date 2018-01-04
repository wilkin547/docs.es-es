---
title: "Cómo: Hacer un control no visible en tiempo de ejecución"
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
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e28a682c6f3bfc52a293daebeade960c1875bb5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="f00ee-102">Cómo: Hacer un control no visible en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f00ee-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="f00ee-103">Hay ocasiones cuando desea crear un control de usuario que sea invisible en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f00ee-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="f00ee-104">Por ejemplo, un control que es un reloj de alarma podría ser invisible excepto cuando suene la alarma.</span><span class="sxs-lookup"><span data-stu-id="f00ee-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="f00ee-105">Esto se consigue fácilmente estableciendo la <xref:System.Windows.Forms.Control.Visible%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f00ee-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="f00ee-106">Si el <xref:System.Windows.Forms.Control.Visible%2A> propiedad es `true`, el control aparecerá como normal.</span><span class="sxs-lookup"><span data-stu-id="f00ee-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="f00ee-107">Si `false`, se ocultará el control.</span><span class="sxs-lookup"><span data-stu-id="f00ee-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="f00ee-108">Aunque todavía puede ejecutar código en el control al invisible, no podrá interactuar con el control a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f00ee-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="f00ee-109">Si desea crear un control invisible que responda a la entrada (por ejemplo, clics del mouse) del usuario, debe crear un control transparente.</span><span class="sxs-lookup"><span data-stu-id="f00ee-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="f00ee-110">Para obtener más información, consulte [que proporciona el Control de un fondo transparente](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).</span><span class="sxs-lookup"><span data-stu-id="f00ee-110">For more information, see [Giving Your Control a Transparent Background](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="f00ee-111">Para hacer que el control sea invisible en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f00ee-111">To make your control invisible at run time</span></span>  
  
1.  <span data-ttu-id="f00ee-112">Establezca la propiedad <xref:System.Windows.Forms.Control.Visible%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="f00ee-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f00ee-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f00ee-113">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Visible%2A>  
 [<span data-ttu-id="f00ee-114">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f00ee-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="f00ee-115">Proporcionar un fondo transparente a un control</span><span class="sxs-lookup"><span data-stu-id="f00ee-115">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
