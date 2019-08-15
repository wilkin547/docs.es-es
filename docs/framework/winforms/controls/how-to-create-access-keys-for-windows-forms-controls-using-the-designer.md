---
title: Procedimiento para crear teclas de acceso para controles de formularios Windows Forms mediante el diseñador
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
ms.openlocfilehash: 01bed04483702ba2e62162b675aa1138bc1b0e01
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039520"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="6c19d-102">Procedimiento para crear teclas de acceso para controles de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="6c19d-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="6c19d-103">Una *tecla de acceso* es un carácter subrayado en el texto de un menú, un elemento de menú o la etiqueta de un control, como un botón.</span><span class="sxs-lookup"><span data-stu-id="6c19d-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="6c19d-104">Permite al usuario "hacer clic" en un botón presionando la tecla ALT en combinación con la tecla de acceso predefinida.</span><span class="sxs-lookup"><span data-stu-id="6c19d-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="6c19d-105">Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y, por tanto `Text` , su propiedad se establece en "Imprimir", agregar un símbolo de y comercial (&) antes de la letra "p" hace que la letra "p" esté subrayada en el texto del botón en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6c19d-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="6c19d-106">El usuario puede ejecutar el comando asociado al botón presionando ALT + P.</span><span class="sxs-lookup"><span data-stu-id="6c19d-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="6c19d-107">No puede tener una tecla de acceso para un control que no puede recibir el foco.</span><span class="sxs-lookup"><span data-stu-id="6c19d-107">You cannot have an access key for a control that cannot receive focus.</span></span>

## <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="6c19d-108">Para crear una tecla de acceso para un control</span><span class="sxs-lookup"><span data-stu-id="6c19d-108">To create an access key for a control</span></span>

1. <span data-ttu-id="6c19d-109">En la ventana **propiedades** , establezca la `Text` propiedad en una cadena que incluya una y comercial (&) delante de la letra que será la tecla de acceso.</span><span class="sxs-lookup"><span data-stu-id="6c19d-109">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="6c19d-110">Por ejemplo, para establecer la letra "P" como tecla de acceso, escriba **& imprimir** en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6c19d-110">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c19d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c19d-111">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="6c19d-112">Cómo: Responder a clics de botón de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6c19d-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="6c19d-113">Cómo: Establecer el texto mostrado por un control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6c19d-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="6c19d-114">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="6c19d-114">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
