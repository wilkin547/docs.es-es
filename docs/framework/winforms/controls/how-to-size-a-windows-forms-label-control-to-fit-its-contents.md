---
title: Procedimiento Tamaño de un Control de etiqueta de Windows Forms para ajustar su contenido
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 74947e529a472c9e9a681fcb436ce8aff990c0af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640412"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Procedimiento Tamaño de un Control de etiqueta de Windows Forms para ajustar su contenido
Los formularios de Windows <xref:System.Windows.Forms.Label> control puede ser una línea o varias líneas y se tamaño fijo o cambiar automáticamente de tamaño para adaptarse al título. El <xref:System.Windows.Forms.Label.AutoSize%2A> propiedad le ayuda a cambiar el tamaño de los controles para ajustarse a los títulos mayores o menores, que es especialmente útil si el título cambia en tiempo de ejecución.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Para realizar un control de etiqueta de tamaño dinámicamente para ajustarse a su contenido  
  
1.  Establezca su <xref:System.Windows.Forms.Label.AutoSize%2A> propiedad `true`.  
  
 Si <xref:System.Windows.Forms.Label.AutoSize%2A> está establecido en `false`, las palabras especificadas en el <xref:System.Windows.Forms.Label.Text%2A> propiedad se ajustará a la siguiente línea si es posible, pero no puede crecer el control.  
  
## <a name="see-also"></a>Vea también
- [Cómo: Crear teclas de acceso con controles Label de formularios de Windows](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Información general sobre el control Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)
- [Etiqueta (control)](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
