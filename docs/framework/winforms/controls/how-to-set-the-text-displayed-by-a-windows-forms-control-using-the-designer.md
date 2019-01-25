---
title: Procedimiento Establecer el texto mostrado por un Windows Forms mediante el Diseñador de Control
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: cea2bcdb973e1deb5e0e6cf7fcc31b7c084dc446
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510590"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="eeac0-102">Procedimiento Establecer el texto mostrado por un Windows Forms mediante el Diseñador de Control</span><span class="sxs-lookup"><span data-stu-id="eeac0-102">How to: Set the Text Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="eeac0-103">Controles de formularios Windows Forms normalmente muestran algún texto relacionado con la función principal del control.</span><span class="sxs-lookup"><span data-stu-id="eeac0-103">Windows Forms controls typically display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="eeac0-104">Por ejemplo, un <xref:System.Windows.Forms.Button> control normalmente muestra un título que indica qué acción se realizará cuando se hace clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="eeac0-104">For example, a <xref:System.Windows.Forms.Button> control typically displays a caption that indicates what action will be performed when the button is clicked.</span></span> <span data-ttu-id="eeac0-105">Para todos los controles, puede establecer o devolver el texto usando la propiedad <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="eeac0-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="eeac0-106">Puede cambiar la fuente usando la propiedad <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="eeac0-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a><span data-ttu-id="eeac0-107">Para establecer el texto y la fuente con el diseñador</span><span class="sxs-lookup"><span data-stu-id="eeac0-107">To set the text and font with the designer</span></span>  
  
1.  <span data-ttu-id="eeac0-108">En la ventana Propiedades, establezca el <xref:System.Windows.Forms.Control.Text%2A> propiedad del control en una cadena adecuada.</span><span class="sxs-lookup"><span data-stu-id="eeac0-108">In the Properties window, set the <xref:System.Windows.Forms.Control.Text%2A> property of the control to an appropriate string.</span></span>  
  
     <span data-ttu-id="eeac0-109">Para crear una tecla de método abreviado subrayada, incluya una y comercial (&) delante de la letra que será la tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="eeac0-109">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>  
  
2.  <span data-ttu-id="eeac0-110">En la ventana Propiedades, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.Control.Font%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="eeac0-110">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
     <span data-ttu-id="eeac0-111">En el cuadro de diálogo Fuente estándar, seleccione la fuente, estilo de fuente, tamaño, efectos (por ejemplo, tachado o subrayado) y secuencias de comandos que desee.</span><span class="sxs-lookup"><span data-stu-id="eeac0-111">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeac0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="eeac0-112">See also</span></span>
- [<span data-ttu-id="eeac0-113">Cómo: Establecer el texto mostrado por un Windows Forms Control</span><span class="sxs-lookup"><span data-stu-id="eeac0-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="eeac0-114">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="eeac0-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [<span data-ttu-id="eeac0-115">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="eeac0-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
