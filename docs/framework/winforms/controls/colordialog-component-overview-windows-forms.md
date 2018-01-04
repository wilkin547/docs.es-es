---
title: "Información general sobre el componente ColorDialog (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5df0d7ddd16de5bd8bb052c09731df6583ca4903
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="colordialog-component-overview-windows-forms"></a>Información general sobre el componente ColorDialog (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.ColorDialog> componente es un cuadro de diálogo preconfigurado que permite al usuario seleccionar un color de una paleta y agregue colores personalizados a la paleta. Es el mismo cuadro de diálogo que se ve en otras aplicaciones basadas en Windows para seleccionar colores. Utilícelo en la aplicación basada en Windows como una solución sencilla, en lugar de configurar su propio cuadro de diálogo.  
  
 El color seleccionado en el cuadro de diálogo se devuelve en el <xref:System.Windows.Forms.ColorDialog.Color%2A> propiedad. Si el <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> propiedad está establecida en `false`, el botón "Definir colores personalizados" está deshabilitado y el usuario está restringido a los colores predefinidos en la paleta. Si el <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> propiedad está establecida en `true`, el usuario no puede seleccionar colores interpolados. Para mostrar el cuadro de diálogo, debe llamar a su <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ColorDialog>  
 [ColorDialog (componente)](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [Controles y componentes de cuadros de diálogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 [Cómo: Cambiar la apariencia del componente ColorDialog de Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
