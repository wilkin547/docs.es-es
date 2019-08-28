---
title: Procedimiento para deshabilitar ToolStripMenuItems
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
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046223"
---
# <a name="how-to-disable-toolstripmenuitems"></a>Procedimiento para deshabilitar ToolStripMenuItems
Puede limitar o ampliar los comandos que puede realizar un usuario habilitando y deshabilitando los elementos de menú en respuesta a las actividades del usuario. Los elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> ajustar a través de la propiedad. Puede manipular esta propiedad en tiempo de diseño en la ventana **propiedades** o mediante programación estableciéndolo en código.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>Para deshabilitar un elemento de menú mediante programación  
  
- Dentro del método donde se establecen las propiedades del elemento de menú, agregue código para establecer la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad en `false`.  
  
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
    > Al deshabilitar el primer elemento de menú de nivel superior de un menú, se ocultan todos los elementos de menú incluidos en el menú, pero no se deshabilitan. Del mismo modo, al deshabilitar un elemento de menú que tiene elementos de submenú, se ocultan los elementos de submenú, pero no se deshabilitan. Si todos los comandos de un menú determinado no están disponibles para el usuario, se considera una buena práctica de programación para ocultar y deshabilitar todo el menú, ya que esto presenta una interfaz de usuario limpia. Debe ocultar y deshabilitar el menú, y deshabilitar todos los elementos y elementos de submenú en el menú, ya que ocultar solo no impide el acceso a un comando de menú mediante una tecla de método abreviado. Establezca la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de un elemento de menú de nivel superior `false` en para ocultar todo el menú.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Procedimientos: Ocultar ToolStripMenuItems](how-to-hide-toolstripmenuitems.md)
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
