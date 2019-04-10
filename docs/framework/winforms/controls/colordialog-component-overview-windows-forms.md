---
title: Información general sobre el componente ColorDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 284d42218fb4fbce873325b1e45c883d51eefab8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222359"
---
# <a name="colordialog-component-overview-windows-forms"></a>Información general sobre el componente ColorDialog (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.ColorDialog> componente es un cuadro de diálogo preconfigurado que permite al usuario seleccionar un color de una paleta y agregar colores personalizados a la paleta. Es el mismo cuadro de diálogo que se ve en otras aplicaciones basadas en Windows para seleccionar colores. Utilícelo en la aplicación basada en Windows como una solución sencilla, en lugar de configurar su propio cuadro de diálogo.  
  
 Se devuelve el color seleccionado en el cuadro de diálogo en el <xref:System.Windows.Forms.ColorDialog.Color%2A> propiedad. Si el <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> propiedad está establecida en `false`, el botón "Definir colores personalizados" está deshabilitado y el usuario está restringido a los colores predefinidos en la paleta. Si el <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> propiedad está establecida en `true`, el usuario no puede seleccionar colores interpolados. Para mostrar el cuadro de diálogo, debe llamar a su <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ColorDialog>
- [Componente ColorDialog](colordialog-component-windows-forms.md)
- [Controles y componentes de cuadros de diálogo](dialog-box-controls-and-components-windows-forms.md)
- [Filtrar para cambiar la apariencia del componente ColorDialog de formularios Windows Forms](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
