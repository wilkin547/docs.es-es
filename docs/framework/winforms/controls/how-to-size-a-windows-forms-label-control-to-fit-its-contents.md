---
title: Filtrar Tamaño de un Control de etiqueta de Windows Forms para ajustar su contenido
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 5771b232d77e3e5a792b179ebffd3fa0edda7c9b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702199"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="9939f-102">Filtrar Tamaño de un Control de etiqueta de Windows Forms para ajustar su contenido</span><span class="sxs-lookup"><span data-stu-id="9939f-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="9939f-103">Los formularios de Windows <xref:System.Windows.Forms.Label> control puede ser una línea o varias líneas y se tamaño fijo o cambiar automáticamente de tamaño para adaptarse al título.</span><span class="sxs-lookup"><span data-stu-id="9939f-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="9939f-104">El <xref:System.Windows.Forms.Label.AutoSize%2A> propiedad le ayuda a cambiar el tamaño de los controles para ajustarse a los títulos mayores o menores, que es especialmente útil si el título cambia en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9939f-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="9939f-105">Para realizar un control de etiqueta de tamaño dinámicamente para ajustarse a su contenido</span><span class="sxs-lookup"><span data-stu-id="9939f-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1.  <span data-ttu-id="9939f-106">Establezca su <xref:System.Windows.Forms.Label.AutoSize%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="9939f-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="9939f-107">Si <xref:System.Windows.Forms.Label.AutoSize%2A> está establecido en `false`, las palabras especificadas en el <xref:System.Windows.Forms.Label.Text%2A> propiedad se ajustará a la siguiente línea si es posible, pero no puede crecer el control.</span><span class="sxs-lookup"><span data-stu-id="9939f-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9939f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="9939f-108">See also</span></span>
- [<span data-ttu-id="9939f-109">Cómo: Crear teclas de acceso con controles Label de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="9939f-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="9939f-110">Información general sobre el control Label</span><span class="sxs-lookup"><span data-stu-id="9939f-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="9939f-111">Etiqueta (control)</span><span class="sxs-lookup"><span data-stu-id="9939f-111">Label Control</span></span>](label-control-windows-forms.md)
