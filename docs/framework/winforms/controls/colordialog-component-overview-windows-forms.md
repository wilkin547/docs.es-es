---
title: Información general sobre el componente ColorDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 9ef7d667b582d3b227f0f0e8af5e7e0335cd4860
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570114"
---
# <a name="colordialog-component-overview-windows-forms"></a>Información general sobre el componente ColorDialog (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.ColorDialog> componente es un cuadro de diálogo preconfigurado que permite al usuario seleccionar un color de una paleta y agregar colores personalizados a la paleta. Es el mismo cuadro de diálogo que se ve en otras aplicaciones basadas en Windows para seleccionar colores. Utilícelo en la aplicación basada en Windows como una solución sencilla, en lugar de configurar su propio cuadro de diálogo.  
  
 Se devuelve el color seleccionado en el cuadro de diálogo en el <xref:System.Windows.Forms.ColorDialog.Color%2A> propiedad. Si el <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> propiedad está establecida en `false`, el botón "Definir colores personalizados" está deshabilitado y el usuario está restringido a los colores predefinidos en la paleta. Si el <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> propiedad está establecida en `true`, el usuario no puede seleccionar colores interpolados. Para mostrar el cuadro de diálogo, debe llamar a su <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog (componente)](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)
- [Controles y componentes de cuadros de diálogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
- [Cómo: Cambiar la apariencia del componente ColorDialog de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
