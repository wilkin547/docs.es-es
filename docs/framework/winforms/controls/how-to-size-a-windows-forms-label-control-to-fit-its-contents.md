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
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Cómo: Cambiar el tamaño de un control Label de formularios Windows Forms para ajustar su contenido
El control <xref:System.Windows.Forms.Label> de Windows Forms puede tener una sola línea o varias líneas, y puede tener un tamaño fijo o cambiar su tamaño automáticamente para dar cabida a su título. La propiedad <xref:System.Windows.Forms.Label.AutoSize%2A> ayuda a cambiar el tamaño de los controles para ajustarse a títulos mayores o más pequeños, lo que resulta especialmente útil si el título cambia en tiempo de ejecución.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Para hacer que un control de etiqueta cambie de tamaño dinámicamente para ajustarse a su contenido  
  
1. Establezca su propiedad <xref:System.Windows.Forms.Label.AutoSize%2A> en `true`.  
  
 Si <xref:System.Windows.Forms.Label.AutoSize%2A> se establece en `false`, las palabras especificadas en la propiedad <xref:System.Windows.Forms.Label.Text%2A> se ajustarán a la línea siguiente, si es posible, pero el control no aumentará.  
  
## <a name="see-also"></a>Consulte también

- [Crear teclas de acceso con controles Label de formularios Windows Forms](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Información general sobre el control Label](label-control-overview-windows-forms.md)
- [Etiqueta (control)](label-control-windows-forms.md)
