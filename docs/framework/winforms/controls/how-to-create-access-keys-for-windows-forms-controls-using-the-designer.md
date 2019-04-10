---
title: Filtrar para crear teclas de acceso para controles de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 410fc0134046c5fa7e05bfcd38ce6818244a0a54
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307878"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="4d89b-102">Filtrar para crear teclas de acceso para controles de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="4d89b-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="4d89b-103">Un *clave de acceso* es un carácter subrayado en el texto de un menú, elemento de menú o la etiqueta de un control como un botón.</span><span class="sxs-lookup"><span data-stu-id="4d89b-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="4d89b-104">Permite al usuario "haga clic en" un botón presionando la tecla ALT en combinación con la clave de acceso predefinidas.</span><span class="sxs-lookup"><span data-stu-id="4d89b-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="4d89b-105">Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y por lo tanto, su `Text` propiedad se establece en "Imprimir" Agregar una y comercial (&) delante de la letra "P" hace que la letra "P" estar subrayados en el texto del botón en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4d89b-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="4d89b-106">El usuario puede ejecutar el comando asociado con el botón presionando ALT + P.</span><span class="sxs-lookup"><span data-stu-id="4d89b-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="4d89b-107">No puede tener una clave de acceso para un control que no se puede recibir el foco.</span><span class="sxs-lookup"><span data-stu-id="4d89b-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d89b-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="4d89b-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4d89b-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="4d89b-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4d89b-110">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="4d89b-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="4d89b-111">Para crear una clave de acceso para un control</span><span class="sxs-lookup"><span data-stu-id="4d89b-111">To create an access key for a control</span></span>  
  
1. <span data-ttu-id="4d89b-112">En el **propiedades** ventana, establezca el `Text` en una cadena que incluye una y comercial (&) delante de la letra que será la clave de acceso de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4d89b-112">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="4d89b-113">Por ejemplo, para establecer la letra "P" como la clave de acceso, escriba **& impresión** en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4d89b-113">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d89b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d89b-114">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="4d89b-115">Filtrar para responder a clics de botones en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d89b-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="4d89b-116">Filtrar para establecer el texto mostrado por un control de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d89b-116">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="4d89b-117">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="4d89b-117">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
