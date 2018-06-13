---
title: 'Cómo: Crear teclas de acceso para controles de formularios Windows Forms mediante el Diseñador'
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
ms.openlocfilehash: 023973e7fa4ab1e8b802d8c7cd8abef8201ed720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532556"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="81ed0-102">Cómo: Crear teclas de acceso para controles de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="81ed0-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="81ed0-103">Un *clave de acceso* es un carácter subrayado en el texto de un menú, elemento de menú o la etiqueta de un control como un botón.</span><span class="sxs-lookup"><span data-stu-id="81ed0-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="81ed0-104">Permite al usuario "haga clic" en un botón al presionar la tecla ALT en combinación con la clave de acceso predefinidas.</span><span class="sxs-lookup"><span data-stu-id="81ed0-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="81ed0-105">Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y por tanto su `Text` propiedad se establece en "Imprimir" Agregar una y comercial (&) delante de la letra "P" hace que la letra "P" aparecerá subrayada en el texto del botón en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="81ed0-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="81ed0-106">El usuario puede ejecutar el comando asociado con el botón presionando ALT + P.</span><span class="sxs-lookup"><span data-stu-id="81ed0-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="81ed0-107">No puede tener una tecla de acceso para un control que no se puede recibir el foco.</span><span class="sxs-lookup"><span data-stu-id="81ed0-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81ed0-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="81ed0-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="81ed0-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="81ed0-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="81ed0-110">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="81ed0-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="81ed0-111">Para crear una clave de acceso para un control</span><span class="sxs-lookup"><span data-stu-id="81ed0-111">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="81ed0-112">En el **propiedades** ventana, establezca el `Text` propiedad a una cadena que incluye una y comercial (&) delante de la letra que será la tecla de acceso.</span><span class="sxs-lookup"><span data-stu-id="81ed0-112">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="81ed0-113">Por ejemplo, para establecer la letra "P" como la clave de acceso, escriba **& impresión** en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="81ed0-113">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81ed0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="81ed0-114">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="81ed0-115">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="81ed0-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="81ed0-116">Establecer el texto mostrado por un control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="81ed0-116">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="81ed0-117">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="81ed0-117">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
