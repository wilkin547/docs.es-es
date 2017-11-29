---
title: "Cómo: Disponer objetos en capas en formularios Windows Forms"
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
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bda4cb3641ff890646614af35d38ff13621cc16b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="df452-102">Cómo: Disponer objetos en capas en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df452-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="df452-103">Al crear una interfaz de usuario complejas o trabajar con un formulario de múltiples documentos (MDI) de la interfaz, que a menudo desea capas controles y formularios secundarios para crear interfaces de usuario (UI) más complejas.</span><span class="sxs-lookup"><span data-stu-id="df452-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="df452-104">Para mover y realizar un seguimiento de los controles y ventanas en el contexto de un grupo, manipular su orden z.</span><span class="sxs-lookup"><span data-stu-id="df452-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="df452-105">*Orden Z* constituye las capas visuales de controles en un formulario de eje z del formulario (profundidad).</span><span class="sxs-lookup"><span data-stu-id="df452-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="df452-106">La ventana en la parte superior del orden z superpone a todas las demás ventanas.</span><span class="sxs-lookup"><span data-stu-id="df452-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="df452-107">Todas las demás ventanas superponen a la ventana en la parte inferior del orden z.</span><span class="sxs-lookup"><span data-stu-id="df452-107">All other windows overlap the window at the bottom of the z-order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df452-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="df452-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="df452-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="df452-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="df452-110">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="df452-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="df452-111">Para superponer los controles en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="df452-111">To layer controls at design time</span></span>  
  
1.  <span data-ttu-id="df452-112">Seleccione un control que desee disponer en capas.</span><span class="sxs-lookup"><span data-stu-id="df452-112">Select a control that you want to layer.</span></span>  
  
2.  <span data-ttu-id="df452-113">En el **formato** menú, elija **orden**y, a continuación, haga clic en **Traer al frente** o **hacia atrás**.</span><span class="sxs-lookup"><span data-stu-id="df452-113">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>  
  
### <a name="to-layer-controls-programmatically"></a><span data-ttu-id="df452-114">Disponer en capas los controles mediante programación</span><span class="sxs-lookup"><span data-stu-id="df452-114">To layer controls programmatically</span></span>  
  
-   <span data-ttu-id="df452-115">Use la <xref:System.Windows.Forms.Control.BringToFront%2A> y <xref:System.Windows.Forms.Control.SendToBack%2A> métodos para manipular el orden z de los controles.</span><span class="sxs-lookup"><span data-stu-id="df452-115">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>  
  
     <span data-ttu-id="df452-116">Por ejemplo, si un <xref:System.Windows.Forms.TextBox> control `txtFirstName`, está debajo de la directiva otro control y desea tener en la parte superior, utilice el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="df452-116">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="df452-117">Formularios Windows Forms admiten *contención de controles*.</span><span class="sxs-lookup"><span data-stu-id="df452-117">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="df452-118">Contención de controles permite colocar una serie de controles dentro de un control contenedor, como un número de <xref:System.Windows.Forms.RadioButton> controla dentro de un <xref:System.Windows.Forms.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="df452-118">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="df452-119">A continuación, puede crear niveles en los controles en el control contenedor.</span><span class="sxs-lookup"><span data-stu-id="df452-119">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="df452-120">Mover el cuadro de grupo mueve a los controles, porque están contenidos dentro de él.</span><span class="sxs-lookup"><span data-stu-id="df452-120">Moving the group box moves the controls as well, because they are contained inside it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df452-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="df452-121">See Also</span></span>  
 [<span data-ttu-id="df452-122">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df452-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="df452-123">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df452-123">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="df452-124">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="df452-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="df452-125">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df452-125">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="df452-126">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="df452-126">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
