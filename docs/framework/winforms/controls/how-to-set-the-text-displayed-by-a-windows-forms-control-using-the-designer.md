---
title: Procedimiento para establecer el texto mostrado por un control de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: a0f567befb1e0c323dd16fffedec279ff836cbf8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013223"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="6a864-102">Procedimiento para establecer el texto mostrado por un control de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="6a864-102">How to: Set the Text Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="6a864-103">Controles de formularios Windows Forms normalmente muestran algún texto relacionado con la función principal del control.</span><span class="sxs-lookup"><span data-stu-id="6a864-103">Windows Forms controls typically display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="6a864-104">Por ejemplo, un <xref:System.Windows.Forms.Button> control normalmente muestra un título que indica qué acción se realizará cuando se hace clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="6a864-104">For example, a <xref:System.Windows.Forms.Button> control typically displays a caption that indicates what action will be performed when the button is clicked.</span></span> <span data-ttu-id="6a864-105">Para todos los controles, puede establecer o devolver el texto usando la propiedad <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a864-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="6a864-106">Puede cambiar la fuente usando la propiedad <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a864-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a><span data-ttu-id="6a864-107">Para establecer el texto y la fuente con el diseñador</span><span class="sxs-lookup"><span data-stu-id="6a864-107">To set the text and font with the designer</span></span>  
  
1. <span data-ttu-id="6a864-108">En la ventana Propiedades, establezca el <xref:System.Windows.Forms.Control.Text%2A> propiedad del control en una cadena adecuada.</span><span class="sxs-lookup"><span data-stu-id="6a864-108">In the Properties window, set the <xref:System.Windows.Forms.Control.Text%2A> property of the control to an appropriate string.</span></span>  
  
     <span data-ttu-id="6a864-109">Para crear una tecla de método abreviado subrayada, incluya una y comercial (&) delante de la letra que será la tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="6a864-109">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>  
  
2. <span data-ttu-id="6a864-110">En la ventana Propiedades, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.Control.Font%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="6a864-110">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
     <span data-ttu-id="6a864-111">En el cuadro de diálogo Fuente estándar, seleccione la fuente, estilo de fuente, tamaño, efectos (por ejemplo, tachado o subrayado) y secuencias de comandos que desee.</span><span class="sxs-lookup"><span data-stu-id="6a864-111">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a864-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a864-112">See also</span></span>

- [<span data-ttu-id="6a864-113">Cómo: Establecer el texto mostrado por un Windows Forms Control</span><span class="sxs-lookup"><span data-stu-id="6a864-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="6a864-114">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="6a864-114">Using Fonts and Text</span></span>](../advanced/using-fonts-and-text.md)
- [<span data-ttu-id="6a864-115">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="6a864-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
