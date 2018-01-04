---
title: "Cómo: Deshabilitar ToolStripMenuItems mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6f60976ffd42c63307a0fe476cb3dc36a7c657e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a>Cómo: Deshabilitar ToolStripMenuItems mediante el Diseñador
Puede limitar o ampliar los comandos que un usuario puede realizar para habilitar y deshabilitar elementos de menú en respuesta a las actividades del usuario. Elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede ajustar mediante el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad. Puede manipular esta propiedad en tiempo de diseño en el **propiedades** ventana o mediante programación si se establece en el código. Para obtener más información, consulte [Cómo: Deshabilitar ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-disable-a-menu-item-at-design-time"></a>Para deshabilitar un elemento de menú en tiempo de diseño  
  
1.  Con el elemento de menú seleccionado en el formulario, establezca la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad `false`.  
  
    > [!TIP]
    >  Si se deshabilita el elemento de menú de primer o de nivel superior en un menú, deshabilitan todos los elementos de menú contenidos en el menú. Del mismo modo, si se deshabilita un elemento de menú que tiene elementos de submenú, deshabilitan los elementos de submenú. Si todos los comandos de un menú no están disponibles para el usuario, se considera buena práctica de programación ocultar y deshabilitar todo el menú, tal y como se presenta una interfaz de usuario limpia. Se debe ocultar y deshabilitar el menú, como si sólo se oculta no impide el acceso a un comando de menú a través de una tecla de método abreviado. Establecer el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de un elemento de menú de nivel superior para `false` para ocultar todo el menú.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Ocultar ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
