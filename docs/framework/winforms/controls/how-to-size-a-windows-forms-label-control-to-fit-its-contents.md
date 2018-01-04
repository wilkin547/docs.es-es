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
ms.workload: dotnet
ms.openlocfilehash: a2c34506ca33af80b83f365893e56a5a9d437b89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Cómo: Cambiar el tamaño de un control Label de formularios Windows Forms para ajustar su contenido
Los formularios Windows Forms <xref:System.Windows.Forms.Label> control puede ser una línea o varias líneas, y ser tamaño fijo o cambiar automáticamente de tamaño para adaptarse al título. El <xref:System.Windows.Forms.Label.AutoSize%2A> propiedad ayuda a cambiar el tamaño de los controles para que se ajuste a títulos mayores o menores, lo que es especialmente útil si va a cambiar el título en tiempo de ejecución.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Para crear un control de etiqueta de tamaño dinámicamente para ajustarse a su contenido  
  
1.  Establecer su <xref:System.Windows.Forms.Label.AutoSize%2A> propiedad `true`.  
  
 Si <xref:System.Windows.Forms.Label.AutoSize%2A> está establecido en `false`, las palabras especificadas en el <xref:System.Windows.Forms.Label.Text%2A> propiedad se ajustará a la línea siguiente si es posible, pero el control no crecerán.  
  
## <a name="see-also"></a>Vea también  
 [Crear teclas de acceso con controles Label de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [Información general sobre el control Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Etiqueta (control)](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
