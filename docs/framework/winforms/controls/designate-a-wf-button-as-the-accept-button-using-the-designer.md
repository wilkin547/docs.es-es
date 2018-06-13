---
title: 'Cómo: Designar un botón de formularios Windows Forms como botón para aceptar mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: aade1b6e988fc4b43f7ad9cfb58382302c875d37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527048"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="0cd1e-102">Cómo: Designar un botón de formularios Windows Forms como botón para aceptar mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="0cd1e-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="0cd1e-103">En cualquier formulario Windows Forms, puede designar un <xref:System.Windows.Forms.Button> que sea el botón Aceptar, también conocido como el botón predeterminado del control.</span><span class="sxs-lookup"><span data-stu-id="0cd1e-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="0cd1e-104">Cada vez que el usuario presiona la tecla ENTRAR, hacer clic en el botón predeterminado, sin tener en cuenta que otro control en el formulario tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="0cd1e-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="0cd1e-105">Las excepciones a esto son cuando el control tiene el foco es otro botón, en ese caso, se hace clic en el botón con el foco, o un cuadro de texto multilínea o un control personalizado que intercepta la tecla ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="0cd1e-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cd1e-106">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="0cd1e-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0cd1e-107">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="0cd1e-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0cd1e-108">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="0cd1e-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="0cd1e-109">Para designar el botón Aceptar</span><span class="sxs-lookup"><span data-stu-id="0cd1e-109">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="0cd1e-110">Seleccione el formulario en el que reside el botón.</span><span class="sxs-lookup"><span data-stu-id="0cd1e-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="0cd1e-111">En el **propiedades** ventana, establezca el formato <xref:System.Windows.Forms.Form.AcceptButton%2A> propiedad a la <xref:System.Windows.Forms.Button> nombre del control.</span><span class="sxs-lookup"><span data-stu-id="0cd1e-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd1e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cd1e-112">See Also</span></span>  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [<span data-ttu-id="0cd1e-113">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="0cd1e-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="0cd1e-114">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0cd1e-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="0cd1e-115">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0cd1e-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="0cd1e-116">Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="0cd1e-116">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [<span data-ttu-id="0cd1e-117">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="0cd1e-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
