---
title: Cambiar el tamaño de un control de etiqueta para ajustar su contenido
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 6a563693feaa5074f5d13f0b82cc4d0305a79c23
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743774"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="0790f-102">Cómo: Cambiar el tamaño de un control Label de formularios Windows Forms para ajustar su contenido</span><span class="sxs-lookup"><span data-stu-id="0790f-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="0790f-103">El control <xref:System.Windows.Forms.Label> de Windows Forms puede tener una sola línea o varias líneas, y puede tener un tamaño fijo o cambiar su tamaño automáticamente para dar cabida a su título.</span><span class="sxs-lookup"><span data-stu-id="0790f-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="0790f-104">La propiedad <xref:System.Windows.Forms.Label.AutoSize%2A> ayuda a cambiar el tamaño de los controles para ajustarse a títulos mayores o más pequeños, lo que resulta especialmente útil si el título cambia en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0790f-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="0790f-105">Para hacer que un control de etiqueta cambie de tamaño dinámicamente para ajustarse a su contenido</span><span class="sxs-lookup"><span data-stu-id="0790f-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1. <span data-ttu-id="0790f-106">Establezca su propiedad <xref:System.Windows.Forms.Label.AutoSize%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="0790f-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="0790f-107">Si <xref:System.Windows.Forms.Label.AutoSize%2A> se establece en `false`, las palabras especificadas en la propiedad <xref:System.Windows.Forms.Label.Text%2A> se ajustarán a la línea siguiente, si es posible, pero el control no aumentará.</span><span class="sxs-lookup"><span data-stu-id="0790f-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0790f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="0790f-108">See also</span></span>

- [<span data-ttu-id="0790f-109">Crear teclas de acceso con controles Label de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0790f-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="0790f-110">Información general sobre el control Label</span><span class="sxs-lookup"><span data-stu-id="0790f-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="0790f-111">Etiqueta (control)</span><span class="sxs-lookup"><span data-stu-id="0790f-111">Label Control</span></span>](label-control-windows-forms.md)
