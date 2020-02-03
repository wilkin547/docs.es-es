---
title: Establecer el texto mostrado por un control
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: eb02cbc3b335b0d5856f786b21d1d202cf444211
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738420"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="53f08-102">Cómo: establecer el texto mostrado por un control Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53f08-102">How to: Set the text displayed by a Windows Forms control</span></span>

<span data-ttu-id="53f08-103">Windows Forms controles suelen mostrar algún texto relacionado con la función principal del control.</span><span class="sxs-lookup"><span data-stu-id="53f08-103">Windows Forms controls usually display some text that's related to the primary function of the control.</span></span> <span data-ttu-id="53f08-104">Por ejemplo, un control de <xref:System.Windows.Forms.Button> normalmente muestra un título que indica la acción que se realizará si se hace clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="53f08-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed if the button is clicked.</span></span> <span data-ttu-id="53f08-105">Para todos los controles, puede establecer o devolver el texto usando la propiedad <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="53f08-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="53f08-106">Puede cambiar la fuente usando la propiedad <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="53f08-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>

<span data-ttu-id="53f08-107">También puede establecer el texto mediante el [Diseñador](#designer).</span><span class="sxs-lookup"><span data-stu-id="53f08-107">You can also set the text by using the [designer](#designer).</span></span>

## <a name="programmatic"></a><span data-ttu-id="53f08-108">Programático</span><span class="sxs-lookup"><span data-stu-id="53f08-108">Programmatic</span></span>

1. <span data-ttu-id="53f08-109">Establezca la propiedad <xref:System.Windows.Forms.Control.Text%2A> en una cadena.</span><span class="sxs-lookup"><span data-stu-id="53f08-109">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>

   <span data-ttu-id="53f08-110">Para crear una tecla de acceso subrayada, incluye una y comercial (&) delante de la letra que será la tecla de acceso.</span><span class="sxs-lookup"><span data-stu-id="53f08-110">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>

2. <span data-ttu-id="53f08-111">Establezca la propiedad <xref:System.Windows.Forms.Control.Font%2A> en un objeto del tipo <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="53f08-111">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > <span data-ttu-id="53f08-112">Puede usar un carácter de escape para mostrar un carácter especial en elementos de la interfaz de usuario que normalmente interpretarían de forma distinta, por ejemplo, elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="53f08-112">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="53f08-113">Por ejemplo, la siguiente línea de código establece el texto del elemento de menú para que se lea "& Now para algo completamente diferente":</span><span class="sxs-lookup"><span data-stu-id="53f08-113">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a><span data-ttu-id="53f08-114">Diseñador</span><span class="sxs-lookup"><span data-stu-id="53f08-114">Designer</span></span>

1. <span data-ttu-id="53f08-115">En la ventana **propiedades** de Visual Studio, establezca la propiedad **texto** del control en una cadena adecuada.</span><span class="sxs-lookup"><span data-stu-id="53f08-115">In the **Properties** window in Visual Studio, set the **Text** property of the control to an appropriate string.</span></span>

   <span data-ttu-id="53f08-116">Para crear una tecla de método abreviado subrayada, incluye una y comercial (&) delante de la letra que será la tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="53f08-116">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>

2. <span data-ttu-id="53f08-117">En la ventana **propiedades** , seleccione el botón de puntos suspensivos (![botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio](./media/visual-studio-ellipsis-button.png)) junto a la propiedad **Font** .</span><span class="sxs-lookup"><span data-stu-id="53f08-117">In the **Properties** window, select the ellipsis button (![Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) next to the **Font** property.</span></span>

   <span data-ttu-id="53f08-118">En el cuadro de diálogo fuente estándar, seleccione la fuente, el estilo de fuente, el tamaño, los efectos (como tachado o subrayado) y el script que desee.</span><span class="sxs-lookup"><span data-stu-id="53f08-118">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="53f08-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53f08-119">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="53f08-120">Crear teclas de acceso para controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53f08-120">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)
- [<span data-ttu-id="53f08-121">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53f08-121">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
