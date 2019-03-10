---
title: Filtrar Deshabilitar ToolStripMenuItems mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: a185fe4421b5b5d7846c7d8cacbfc1cae5f805eb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704449"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a>Procedimiento Deshabilitar ToolStripMenuItems mediante el diseñador
Puede limitar o ampliar los comandos que un usuario puede realizar mediante la habilitación y deshabilitación de los elementos de menú en respuesta a las actividades del usuario. Los elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede ajustar mediante el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad. Puede manipular esta propiedad en tiempo de diseño en el **propiedades** ventana o mediante programación si se establece en el código. Para obtener más información, vea [Cómo: Deshabilitar ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-disable-a-menu-item-at-design-time"></a>Para deshabilitar un elemento de menú en tiempo de diseño  
  
1.  Con el elemento de menú seleccionado en el formulario, establezca la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad `false`.  
  
    > [!TIP]
    >  Al deshabilitar el elemento de menú de primer o de nivel superior en un menú, deshabilitan todos los elementos de menú contenidos en el menú. Del mismo modo, la deshabilitación de un elemento de menú que tiene elementos de submenú deshabilita los elementos de submenú. Si todos los comandos de un menú no están disponibles para el usuario, se considera buena práctica de programación para ocultar y deshabilitar todo el menú, como esto presenta una interfaz de usuario limpia. Se debe ocultar y deshabilitar el menú, como oculta por sí solo no impide el acceso a un comando de menú a través de una tecla de método abreviado. Establecer el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de un elemento de menú de nivel superior para `false` para ocultar todo el menú.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Cómo: Ocultar ToolStripMenuItems](how-to-hide-toolstripmenuitems.md)
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
