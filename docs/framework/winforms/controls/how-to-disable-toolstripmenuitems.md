---
title: 'Cómo: Deshabilitar ToolStripMenuItems'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: 20d0e13642aac3004a31ff416318cf6723207379
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532033"
---
# <a name="how-to-disable-toolstripmenuitems"></a>Cómo: Deshabilitar ToolStripMenuItems
Puede limitar o ampliar los comandos que un usuario puede realizar para habilitar y deshabilitar elementos de menú en respuesta a las actividades del usuario. Elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede ajustar mediante el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad. Puede manipular esta propiedad en tiempo de diseño en el **propiedades** ventana o mediante programación si se establece en el código.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>Para deshabilitar un elemento de menú mediante programación  
  
-   Dentro del método donde estableció las propiedades del elemento de menú, agregue código para establecer el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad `false`.  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  Deshabilitar el elemento de menú de primer o de nivel superior en un menú oculta todos los elementos de menú contenidos en el menú, pero no deshabilitará. Del mismo modo, al deshabilitar un elemento de menú que tiene elementos de submenú oculta los elementos de submenú, pero no deshabilitará. Si todos los comandos de un menú no están disponibles para el usuario, se considera buena práctica de programación ocultar y deshabilitar todo el menú, tal y como se presenta una interfaz de usuario limpia. Debe ocultar y deshabilitar el menú y deshabilitar cada elemento y el elemento de submenú en el menú, ya que oculta por sí solo no impide el acceso a un comando de menú a través de una tecla de método abreviado. Establecer el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de un elemento de menú de nivel superior para `false` para ocultar todo el menú.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Ocultar ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
