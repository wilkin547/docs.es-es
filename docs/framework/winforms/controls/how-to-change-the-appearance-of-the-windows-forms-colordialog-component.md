---
title: Cambiar la apariencia del componente ColorDialog
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
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746632"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>Cómo: Cambiar la apariencia del componente ColorDialog de formularios Windows Forms
Puede configurar la apariencia del componente de <xref:System.Windows.Forms.ColorDialog> de Windows Forms con una serie de sus propiedades. El cuadro de diálogo tiene dos secciones: una que muestra los colores básicos y otra que permite al usuario definir colores personalizados.  
  
 La mayoría de las propiedades restringen qué colores puede seleccionar el usuario en el cuadro de diálogo. Si la propiedad <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> está establecida en `true`, el usuario puede definir colores personalizados. La propiedad <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> se `true` si se expande el cuadro de diálogo para definir colores personalizados. de lo contrario, el usuario debe hacer clic en el botón "definir colores personalizados". Cuando la propiedad <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> está establecida en `true`, el cuadro de diálogo muestra todos los colores disponibles en el conjunto de colores básicos. Si la propiedad <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> está establecida en `true`, el usuario no puede seleccionar colores propuestos; solo están disponibles para seleccionar los colores sólidos.  
  
 Si la propiedad <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> está establecida en `true`, aparece un botón ayuda en el cuadro de diálogo. Cuando el usuario hace clic en el botón ayuda, se genera el evento <xref:System.Windows.Forms.CommonDialog.HelpRequest> del componente de <xref:System.Windows.Forms.ColorDialog>.  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a>Para configurar la apariencia del cuadro de diálogo color  
  
1. Establezca las propiedades <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>y <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> en los valores deseados.  
  
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
- [ColorDialog (componente)](colordialog-component-windows-forms.md)
- [Información general del componente ColorDialog](colordialog-component-overview-windows-forms.md)
