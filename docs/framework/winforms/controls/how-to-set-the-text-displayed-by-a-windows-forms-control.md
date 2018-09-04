---
title: 'Cómo: Establecer el texto mostrado por un control de formularios Windows Forms'
ms.date: 03/30/2017
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
ms.openlocfilehash: d9c9bea26cfc3d5b2cfc4484173a7680ff2fc34d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525040"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="925b6-102">Cómo: Establecer el texto mostrado por un control de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="925b6-102">How to: Set the Text Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="925b6-103">Normalmente, los controles de Windows Forms muestran algún texto relacionado con la función principal del control.</span><span class="sxs-lookup"><span data-stu-id="925b6-103">Windows Forms controls usually display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="925b6-104">Por ejemplo, un control <xref:System.Windows.Forms.Button> suele mostrar un título que indica qué acción se realizará al hacer clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="925b6-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed when the button is clicked.</span></span> <span data-ttu-id="925b6-105">Para todos los controles, puede establecer o devolver el texto usando la propiedad <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="925b6-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="925b6-106">Puede cambiar la fuente usando la propiedad <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="925b6-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span> <span data-ttu-id="925b6-107">También puede establecer el texto mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="925b6-107">You can also set the text using the designer.</span></span>  <span data-ttu-id="925b6-108">Consulte también [Cómo: crear acceso a las claves para Windows Forms controles mediante el diseñador](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [Cómo: establecer el texto que se muestra mediante un Control de Windows Forms mediante el diseñador](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [Cómo: establecer la imagen Muestra un Windows Forms mediante el Diseñador de Control](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="925b6-108">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).</span></span>  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a><span data-ttu-id="925b6-109">Para establecer mediante programación el texto que un control muestra</span><span class="sxs-lookup"><span data-stu-id="925b6-109">To set the text displayed by a control programmatically</span></span>  
  
1.  <span data-ttu-id="925b6-110">Establezca la propiedad <xref:System.Windows.Forms.Control.Text%2A> en una cadena.</span><span class="sxs-lookup"><span data-stu-id="925b6-110">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>  
  
     <span data-ttu-id="925b6-111">Para crear una tecla de acceso subrayada, incluya un signo de Y comercial (&) antes de la letra que será la tecla de acceso.</span><span class="sxs-lookup"><span data-stu-id="925b6-111">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>  
  
2.  <span data-ttu-id="925b6-112">Establezca la propiedad <xref:System.Windows.Forms.Control.Font%2A> en un objeto del tipo <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="925b6-112">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="925b6-113">Puede usar un carácter de escape para mostrar un carácter especial en elementos de la interfaz de usuario que normalmente interpretarían de forma distinta, por ejemplo, elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="925b6-113">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="925b6-114">Por ejemplo, la siguiente línea de código establece el texto del elemento de menú en "& Now For Something Completely Different":</span><span class="sxs-lookup"><span data-stu-id="925b6-114">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="925b6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="925b6-115">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="925b6-116">Crear teclas de acceso para controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="925b6-116">How to: Create Access Keys for Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [<span data-ttu-id="925b6-117">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="925b6-117">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
