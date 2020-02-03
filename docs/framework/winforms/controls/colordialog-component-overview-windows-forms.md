---
title: Información general sobre el componente ColorDialog
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 48d9d5072335908f85e65933dadafb1b69f28528
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736968"
---
# <a name="colordialog-component-overview-windows-forms"></a>Información general sobre el componente ColorDialog (formularios Windows Forms)
El componente de <xref:System.Windows.Forms.ColorDialog> de Windows Forms es un cuadro de diálogo preconfigurado que permite al usuario seleccionar un color de una paleta y agregar colores personalizados a la paleta. Es el mismo cuadro de diálogo que se ve en otras aplicaciones basadas en Windows para seleccionar colores. Utilícelo en la aplicación basada en Windows como una solución sencilla, en lugar de configurar su propio cuadro de diálogo.  
  
 El color seleccionado en el cuadro de diálogo se devuelve en la propiedad <xref:System.Windows.Forms.ColorDialog.Color%2A>. Si la propiedad <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> está establecida en `false`, el botón "definir colores personalizados" está deshabilitado y el usuario está restringido a los colores predefinidos de la paleta. Si la propiedad <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> está establecida en `true`, el usuario no puede seleccionar colores propuestos. Para mostrar el cuadro de diálogo, debe llamar a su método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog (componente)](colordialog-component-windows-forms.md)
- [Controles y componentes de cuadros de diálogo](dialog-box-controls-and-components-windows-forms.md)
- [Cómo: Cambiar la apariencia del componente ColorDialog de Windows Forms](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
