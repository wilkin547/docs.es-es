---
title: Filtrar para cambiar la apariencia del componente ColorDialog de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: d79139ac3d11d3cd9a7d1bbe1f12e14df83530e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094650"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>Filtrar para cambiar la apariencia del componente ColorDialog de formularios Windows Forms
Puede configurar la apariencia de los formularios de Windows <xref:System.Windows.Forms.ColorDialog> componente con un número de sus propiedades. El cuadro de diálogo tiene dos secciones: una que muestra los colores básicos y otra que permite al usuario definir colores personalizados.  
  
 La mayoría de las propiedades restringen los colores que el usuario puede seleccionar desde el cuadro de diálogo. Si el <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> propiedad está establecida en `true`, el usuario puede definir colores personalizados. El <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> propiedad es `true` si se expande el cuadro de diálogo para definir colores personalizados; en caso contrario, el usuario debe hacer clic en un botón "Definir colores personalizados". Cuando el <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> propiedad está establecida en `true`, el cuadro de diálogo muestra todos los colores disponibles en el conjunto de colores básicos. Si el <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> propiedad está establecida en `true`, el usuario no puede seleccionar colores interpolados; están disponibles para seleccionar sólo colores sólidos.  
  
 Si el <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> propiedad está establecida en `true`, aparece un botón de ayuda en el cuadro de diálogo. Cuando el usuario hace clic en el botón Ayuda, el <xref:System.Windows.Forms.ColorDialog> del componente <xref:System.Windows.Forms.CommonDialog.HelpRequest> provoca el evento.  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a>Para configurar la apariencia del cuadro de diálogo color  
  
1.  Establecer el <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, y <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> propiedades en los valores deseados.  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ColorDialog>
- [Componente ColorDialog](colordialog-component-windows-forms.md)
- [Información general sobre el componente ColorDialog](colordialog-component-overview-windows-forms.md)
