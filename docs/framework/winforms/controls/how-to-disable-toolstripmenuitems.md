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
ms.openlocfilehash: a480cd29eef1a79a69f702eed7cd02c28d7ea3de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954237"
---
# <a name="how-to-disable-toolstripmenuitems"></a>Procedimiento para deshabilitar ToolStripMenuItems
Puede limitar o ampliar los comandos que un usuario puede realizar mediante la habilitación y deshabilitación de los elementos de menú en respuesta a las actividades del usuario. Los elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede ajustar mediante el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad. Puede manipular esta propiedad en tiempo de diseño en el **propiedades** ventana o mediante programación si se establece en el código.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>Para deshabilitar un elemento de menú mediante programación  
  
- Dentro del método donde estableció las propiedades del elemento de menú, agregue código para establecer el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad `false`.  
  
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
    >  Deshabilitar el elemento de menú de primer o de nivel superior en un menú oculta todos los elementos de menú contenidos en el menú, pero no deshabilita. Del mismo modo, la deshabilitación de un elemento de menú que tiene elementos de submenú oculta los elementos de submenú, pero deshabilitarlas. Si todos los comandos de un menú no están disponibles para el usuario, se considera buena práctica de programación para ocultar y deshabilitar todo el menú, como esto presenta una interfaz de usuario limpia. Se debe ocultar y deshabilite el menú y cada elemento y el elemento de submenú en el menú, porque oculta por sí solo no impide el acceso a un comando de menú a través de una tecla de método abreviado. Establecer el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de un elemento de menú de nivel superior para `false` para ocultar todo el menú.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Cómo: Ocultar ToolStripMenuItems](how-to-hide-toolstripmenuitems.md)
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
