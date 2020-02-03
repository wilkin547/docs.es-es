---
title: Crear claves de acceso para controles
ms.date: 08/20/2019
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
ms.openlocfilehash: 7f6b0a5838cacfc1189fba819a54b3423d567ea0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731170"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="1ebfa-102">Cómo: crear teclas de acceso para controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1ebfa-102">How to: Create access keys for Windows Forms controls</span></span>

<span data-ttu-id="1ebfa-103">Una *tecla de acceso* es un carácter subrayado en el texto de un menú, un elemento de menú o la etiqueta de un control, como un botón.</span><span class="sxs-lookup"><span data-stu-id="1ebfa-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="1ebfa-104">Con una tecla de acceso, el usuario puede hacer clic en un botón presionando la tecla Alt junto con la tecla de acceso predefinida.</span><span class="sxs-lookup"><span data-stu-id="1ebfa-104">With an access key, the user can "click" a button by pressing the Alt key in combination with the predefined access key.</span></span> <span data-ttu-id="1ebfa-105">Por ejemplo, si un botón ejecuta un procedimiento para imprimir un formulario y, por tanto, su propiedad `Text` está establecida en "Imprimir", agregar un símbolo de y comercial antes de la letra "P" hace que la letra "P" esté subrayada en el texto del botón en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ebfa-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="1ebfa-106">El usuario puede ejecutar el comando asociado al botón presionando Alt + P.</span><span class="sxs-lookup"><span data-stu-id="1ebfa-106">The user can run the command associated with the button by pressing Alt+P.</span></span>

<span data-ttu-id="1ebfa-107">Los controles que no pueden recibir el foco no pueden tener claves de acceso.</span><span class="sxs-lookup"><span data-stu-id="1ebfa-107">Controls that cannot receive focus can't have access keys.</span></span>

## <a name="programmatic"></a><span data-ttu-id="1ebfa-108">Programático</span><span class="sxs-lookup"><span data-stu-id="1ebfa-108">Programmatic</span></span>

<span data-ttu-id="1ebfa-109">Establezca la propiedad `Text` en una cadena que incluya una y comercial (&) delante de la letra que será el método abreviado.</span><span class="sxs-lookup"><span data-stu-id="1ebfa-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>

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
> <span data-ttu-id="1ebfa-110">Para usar una y comercial en un título sin crear una tecla de acceso, incluya dos símbolos de y comercial (& &).</span><span class="sxs-lookup"><span data-stu-id="1ebfa-110">To use an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="1ebfa-111">Se muestra un carácter de y comercial único en el título y no hay ningún carácter subrayado.</span><span class="sxs-lookup"><span data-stu-id="1ebfa-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>

## <a name="designer"></a><span data-ttu-id="1ebfa-112">Diseñador</span><span class="sxs-lookup"><span data-stu-id="1ebfa-112">Designer</span></span>

<span data-ttu-id="1ebfa-113">En la ventana **propiedades** de Visual Studio, establezca la propiedad **texto** en una cadena que incluya una y comercial (' & ') delante de la letra que será la tecla de acceso.</span><span class="sxs-lookup"><span data-stu-id="1ebfa-113">In the **Properties** window of Visual Studio, set the **Text** property to a string that includes an ampersand ('&') before the letter that will be the access key.</span></span> <span data-ttu-id="1ebfa-114">Por ejemplo, para establecer la letra "P" como tecla de acceso, escriba **& imprimir**.</span><span class="sxs-lookup"><span data-stu-id="1ebfa-114">For example, to set the letter "P" as the access key, enter **&Print**.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ebfa-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ebfa-115">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="1ebfa-116">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1ebfa-116">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="1ebfa-117">Establecer el texto mostrado por un control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1ebfa-117">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="1ebfa-118">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="1ebfa-118">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
