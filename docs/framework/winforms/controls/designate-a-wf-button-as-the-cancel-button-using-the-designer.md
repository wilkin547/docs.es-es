---
title: Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: f127a1a74643c975aea73b24896c098b365aa327
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972307"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="624cb-102">Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="624cb-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="624cb-103">En cualquier formulario de Windows, se puede designar un <xref:System.Windows.Forms.Button> que sea el botón Cancelar del control.</span><span class="sxs-lookup"><span data-stu-id="624cb-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="624cb-104">Cada vez que el usuario presiona la tecla ESC, independientemente de que otro control en el formulario tiene el foco, se hace clic en un botón Cancelar.</span><span class="sxs-lookup"><span data-stu-id="624cb-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="624cb-105">Habitualmente se programa un botón para permitir que el usuario salga rápidamente de una operación sin confirmar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="624cb-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="624cb-106">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="624cb-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="624cb-107">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="624cb-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="624cb-108">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="624cb-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="624cb-109">Para designar el botón Cancelar</span><span class="sxs-lookup"><span data-stu-id="624cb-109">To designate the cancel button</span></span>  
  
1. <span data-ttu-id="624cb-110">Seleccione el formulario en el que reside el botón.</span><span class="sxs-lookup"><span data-stu-id="624cb-110">Select the form on which the button resides.</span></span>  
  
2. <span data-ttu-id="624cb-111">En el **propiedades** ventana, establezca el formulario <xref:System.Windows.Forms.Form.CancelButton%2A> propiedad a la <xref:System.Windows.Forms.Button> nombre del control.</span><span class="sxs-lookup"><span data-stu-id="624cb-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="624cb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="624cb-112">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="624cb-113">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="624cb-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="624cb-114">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="624cb-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="624cb-115">Cómo: Responder a clics de botón de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="624cb-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="624cb-116">Cómo: Designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="624cb-116">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="624cb-117">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="624cb-117">Button Control</span></span>](button-control-windows-forms.md)
