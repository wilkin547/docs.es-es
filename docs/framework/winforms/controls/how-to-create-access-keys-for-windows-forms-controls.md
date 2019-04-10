---
title: Filtrar para crear teclas de acceso para controles de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: e6c829553163359301bad2cd896fc43562ee8069
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334463"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="6039d-102">Filtrar para crear teclas de acceso para controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6039d-102">How to: Create Access Keys for Windows Forms Controls</span></span>
<span data-ttu-id="6039d-103">Un *clave de acceso* es un carácter subrayado en el texto de un menú, elemento de menú o la etiqueta de un control como un botón.</span><span class="sxs-lookup"><span data-stu-id="6039d-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="6039d-104">Con una clave de acceso, el usuario puede "haga clic en" un botón presionando la tecla ALT en combinación con la clave de acceso predefinidas.</span><span class="sxs-lookup"><span data-stu-id="6039d-104">With an access key, the user can "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="6039d-105">Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y por lo tanto, su `Text` propiedad está establecida en "Print", agregar una y comercial antes de la letra "P" hace que la letra "P" para subrayada en el texto del botón en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6039d-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="6039d-106">El usuario puede ejecutar el comando asociado con el botón presionando ALT + P.</span><span class="sxs-lookup"><span data-stu-id="6039d-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="6039d-107">No puede tener una clave de acceso para un control que no se puede recibir el foco.</span><span class="sxs-lookup"><span data-stu-id="6039d-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="6039d-108">Para crear una clave de acceso para un control</span><span class="sxs-lookup"><span data-stu-id="6039d-108">To create an access key for a control</span></span>  
  
1. <span data-ttu-id="6039d-109">Establecer el `Text` propiedad en una cadena que incluye una y comercial (&) delante de la letra que será el acceso directo.</span><span class="sxs-lookup"><span data-stu-id="6039d-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="6039d-110">Para incluir una y comercial en un título sin crear una clave de acceso, incluya dos símbolos de y comercial (& &).</span><span class="sxs-lookup"><span data-stu-id="6039d-110">To include an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="6039d-111">Un solo carácter & se muestra en la leyenda y no está subrayados ningún carácter.</span><span class="sxs-lookup"><span data-stu-id="6039d-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6039d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6039d-112">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="6039d-113">Filtrar para responder a clics de botones en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6039d-113">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="6039d-114">Filtrar para establecer el texto mostrado por un control de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6039d-114">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="6039d-115">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="6039d-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
