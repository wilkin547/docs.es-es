---
title: "Cómo: Cambiar el tamaño de un control Label de formularios Windows Forms para ajustar su contenido"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd89d72264e5837d2c41fcb0ab024a7b16f4205b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="2e7e3-102">Cómo: Cambiar el tamaño de un control Label de formularios Windows Forms para ajustar su contenido</span><span class="sxs-lookup"><span data-stu-id="2e7e3-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="2e7e3-103">Los formularios Windows Forms <xref:System.Windows.Forms.Label> control puede ser una línea o varias líneas, y ser tamaño fijo o cambiar automáticamente de tamaño para adaptarse al título.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="2e7e3-104">El <xref:System.Windows.Forms.Label.AutoSize%2A> propiedad ayuda a cambiar el tamaño de los controles para que se ajuste a títulos mayores o menores, lo que es especialmente útil si va a cambiar el título en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="2e7e3-105">Para crear un control de etiqueta de tamaño dinámicamente para ajustarse a su contenido</span><span class="sxs-lookup"><span data-stu-id="2e7e3-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1.  <span data-ttu-id="2e7e3-106">Establecer su <xref:System.Windows.Forms.Label.AutoSize%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="2e7e3-107">Si <xref:System.Windows.Forms.Label.AutoSize%2A> está establecido en `false`, las palabras especificadas en el <xref:System.Windows.Forms.Label.Text%2A> propiedad se ajustará a la línea siguiente si es posible, pero el control no crecerán.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e7e3-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e7e3-108">See Also</span></span>  
 [<span data-ttu-id="2e7e3-109">Crear teclas de acceso con controles Label de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2e7e3-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [<span data-ttu-id="2e7e3-110">Información general sobre el control Label</span><span class="sxs-lookup"><span data-stu-id="2e7e3-110">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="2e7e3-111">Etiqueta (control)</span><span class="sxs-lookup"><span data-stu-id="2e7e3-111">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
