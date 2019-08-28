---
title: Procedimiento para deshabilitar ToolStripMenuItems mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 692b6c11f6d58c52a0af29ed04ada45c48cae058
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046238"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a>Procedimiento para deshabilitar ToolStripMenuItems mediante el diseñador
Puede limitar o ampliar los comandos que puede realizar un usuario habilitando y deshabilitando los elementos de menú en respuesta a las actividades del usuario. Los elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> ajustar a través de la propiedad. Puede manipular esta propiedad en tiempo de diseño en la ventana **propiedades** o mediante programación estableciéndolo en código. Para obtener más información, consulte [Cómo Deshabilite](how-to-disable-toolstripmenuitems.md)ToolStripMenuItems.

## <a name="to-disable-a-menu-item-at-design-time"></a>Para deshabilitar un elemento de menú en tiempo de diseño

1. Con el elemento de menú seleccionado en el formulario, establezca <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> la propiedad `false`en.

    > [!TIP]
    > Al deshabilitar el primer elemento de menú de nivel superior de un menú, se deshabilitan todos los elementos de menú incluidos en el menú. Del mismo modo, al deshabilitar un elemento de menú que tiene elementos de submenú, se deshabilitan los elementos de submenú. Si todos los comandos de un menú determinado no están disponibles para el usuario, se considera una buena práctica de programación para ocultar y deshabilitar todo el menú, ya que esto presenta una interfaz de usuario limpia. Debe ocultar y deshabilitar el menú, ya que ocultar solo no impide el acceso a un comando de menú mediante una tecla de método abreviado. Establezca la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de un elemento de menú de nivel superior `false` en para ocultar todo el menú.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Cómo: Ocultar ToolStripMenuItems](how-to-hide-toolstripmenuitems.md)
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
