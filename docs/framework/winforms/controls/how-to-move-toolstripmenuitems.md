---
title: "Cómo: Mover elementos ToolStripMenuItems"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfc1cb718b3738ac93b284b0b438b08d1e721349
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-move-toolstripmenuitems"></a>Cómo: Mover elementos ToolStripMenuItems
En tiempo de diseño, puede mover los menús de nivel superior completos y sus elementos de menú en un lugar diferente el <xref:System.Windows.Forms.MenuStrip>. También puede mover elementos de menú individuales entre los menús de nivel superior o cambiar la posición de los elementos de menú dentro de un menú.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>Para mover un menú de nivel superior y sus elementos de menú a otra ubicación de nivel superior  
  
1.  Haga clic y mantenga presionado el botón primario del mouse en el menú que desea mover.  
  
2.  Arrastre el punto de inserción en el menú de nivel superior que está antes de la nueva ubicación deseada y suelte el botón primario del mouse.  
  
     El menú seleccionado se mueve a la derecha del punto de inserción.  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>Para mover un menú de nivel superior y sus elementos de menú a una ubicación desplegable  
  
1.  Haga clic en el menú que desea mover y presione CTRL + X, o haga clic en el menú y seleccione **cortar** en el menú contextual.  
  
2.  En el menú de nivel superior de destino, haga clic en el elemento de menú por encima de la nueva ubicación deseada y presione CTRL+V, o haga clic en el elemento de menú por encima de la nueva ubicación deseada y seleccione **pegar** en el menú contextual.  
  
     El menú que ha cortado se inserta después del elemento de menú seleccionado.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>Para mover un elemento de menú dentro de un menú mediante el Editor de la colección de elementos  
  
1.  Haga clic en el menú que contiene el elemento de menú que desea mover.  
  
2.  En el menú contextual, elija **Editar DropDownItems**.  
  
3.  En el **Editor de la colección de elementos**, haga clic en el elemento de menú que desea mover.  
  
4.  Haga clic en las teclas de dirección arriba y abajo para mover el elemento de menú en el menú.  
  
5.  Haga clic en **Aceptar**.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>Para mover un elemento de menú dentro de un menú mediante el teclado  
  
1.  Presione y mantenga presionada la tecla ALT.  
  
2.  Mantenga presionado el botón primario del mouse en el elemento de menú que desea mover.  
  
3.  Arrastre el elemento de menú a la nueva ubicación y suelte el botón primario del mouse.  
  
### <a name="to-move-a-menu-item-to-another-menu"></a>Para mover un elemento de menú a otro menú  
  
1.  Haga clic en el elemento de menú que desea mover y presione CTRL + X, o haga clic en el elemento de menú y elija **cortar** en el menú contextual.  
  
2.  Haga clic en el menú que contendrá el elemento de menú que ha cortado.  
  
3.  Haga clic en el elemento de menú que está antes de la nueva ubicación deseada y presione CTRL+V o haga clic en el elemento de menú que es anterior a la nueva ubicación deseada y seleccione **pegar** en el menú contextual.  
  
     El elemento de menú que ha cortado se inserta después del elemento de menú seleccionado.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
