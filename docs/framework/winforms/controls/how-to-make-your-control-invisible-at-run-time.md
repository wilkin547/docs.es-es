---
title: Procedimiento para hacer un control invisible en tiempo de ejecución
ms.date: 03/30/2017
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
ms.openlocfilehash: e9af529541a40a951d6defea180dbbef04c8f3be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913710"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="2ba90-102">Procedimiento para hacer un control invisible en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2ba90-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="2ba90-103">Hay veces cuando desee crear un control de usuario que sea invisible en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2ba90-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="2ba90-104">Por ejemplo, un control que sea un reloj despertador podría ser invisible excepto cuando suene la alarma.</span><span class="sxs-lookup"><span data-stu-id="2ba90-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="2ba90-105">Esto se consigue estableciendo la <xref:System.Windows.Forms.Control.Visible%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2ba90-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="2ba90-106">Si el <xref:System.Windows.Forms.Control.Visible%2A> propiedad es `true`, el control aparecerá con normalidad.</span><span class="sxs-lookup"><span data-stu-id="2ba90-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="2ba90-107">Si `false`, se ocultará el control.</span><span class="sxs-lookup"><span data-stu-id="2ba90-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="2ba90-108">Aunque todavía puede ejecutar código en el control aunque sea invisible, no podrá interactuar con el control a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="2ba90-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="2ba90-109">Si desea crear un control invisible que responda a los usuarios de entrada (por ejemplo, clics del mouse), debe crear un control transparente.</span><span class="sxs-lookup"><span data-stu-id="2ba90-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="2ba90-110">Para obtener más información, consulte [proporcionar un fondo transparente Control](how-to-give-your-control-a-transparent-background.md).</span><span class="sxs-lookup"><span data-stu-id="2ba90-110">For more information, see [Giving Your Control a Transparent Background](how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="2ba90-111">Para que el control sea invisible en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2ba90-111">To make your control invisible at run time</span></span>  
  
1. <span data-ttu-id="2ba90-112">Establezca la propiedad <xref:System.Windows.Forms.Control.Visible%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="2ba90-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2ba90-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ba90-113">See also</span></span>

- <xref:System.Windows.Forms.Control.Visible%2A>
- [<span data-ttu-id="2ba90-114">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ba90-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="2ba90-115">Cómo: Proporcionar un fondo transparente a un Control</span><span class="sxs-lookup"><span data-stu-id="2ba90-115">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)
