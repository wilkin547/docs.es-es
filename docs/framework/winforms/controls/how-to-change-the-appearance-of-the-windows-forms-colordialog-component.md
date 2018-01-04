---
title: "Cómo: Cambiar la apariencia del componente ColorDialog de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af3a9ec6ba301a27a7940bc752ffaf12f345abec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>Cómo: Cambiar la apariencia del componente ColorDialog de formularios Windows Forms
Puede configurar la apariencia de los formularios Windows Forms <xref:System.Windows.Forms.ColorDialog> componente con un número de sus propiedades. El cuadro de diálogo tiene dos secciones: una que muestra colores básicos y otra que permite al usuario definir colores personalizados.  
  
 La mayoría de las propiedades restringen los colores que el usuario puede seleccionar en el cuadro de diálogo. Si el <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> propiedad está establecida en `true`, el usuario puede definir colores personalizados. El <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> propiedad es `true` si se expande el cuadro de diálogo para definir colores personalizados; en caso contrario, el usuario debe hacer clic en un botón "Definir colores personalizados". Cuando el <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> propiedad está establecida en `true`, el cuadro de diálogo muestra todos los colores disponibles en el conjunto de colores básicos. Si el <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> propiedad está establecida en `true`, el usuario no puede seleccionar colores interpolados; están disponibles para seleccionar únicamente colores sólidos.  
  
 Si el <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> propiedad está establecida en `true`, aparece un botón de ayuda en el cuadro de diálogo. Cuando el usuario hace clic en el botón de ayuda, el <xref:System.Windows.Forms.ColorDialog> del componente <xref:System.Windows.Forms.CommonDialog.HelpRequest> evento se desencadena.  
  
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
 <xref:System.Windows.Forms.ColorDialog>  
 [ColorDialog (componente)](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [Información general del componente ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)
