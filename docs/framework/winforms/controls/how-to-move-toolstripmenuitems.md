---
title: Procedimiento para mover elementos ToolStripMenuItems
ms.date: 03/30/2017
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
ms.openlocfilehash: adf25973fde790937461007bd0106cca02dd83be
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039795"
---
# <a name="how-to-move-toolstripmenuitems"></a>Procedimiento para mover elementos ToolStripMenuItems
En tiempo de diseño, puede desplazar los menús de nivel superior completos y sus elementos de menú a un <xref:System.Windows.Forms.MenuStrip>lugar diferente en el. También puede mover elementos de menú individuales entre los menús de nivel superior o cambiar la posición de los elementos de menú dentro de un menú.

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>Para desplace un menú de nivel superior y sus elementos de menú a otra ubicación de nivel superior

1. Haga clic y mantenga presionado el botón primario del mouse en el menú que desea desplace.

2. Arrastre el punto de inserción hasta el menú de nivel superior que está antes de la nueva ubicación deseada y suelte el botón primario del mouse.

     El menú seleccionado se mueve a la derecha del punto de inserción.

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>Para trasladar un menú de nivel superior y sus elementos de menú a una ubicación desplegable

1. Haga clic en el menú que desea desplace y presione CTRL + X o haga clic con el botón derecho en el menú y seleccione **cortar** en el menú contextual.

2. En el menú de nivel superior de destino, haga clic con el botón primario en el elemento de menú situado encima de la nueva ubicación deseada y presione CTRL + V, o haga clic con el botón derecho en el elemento de menú situado encima de la nueva ubicación deseada y seleccione **pegar** en el menú contextual.

     El menú que corte se insertará después del elemento de menú seleccionado.

## <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>Para desplace un elemento de menú dentro de un menú mediante el editor de la colección de elementos

1. Haga clic con el botón secundario en el menú que contiene el elemento de menú que desea desplace.

2. En el menú contextual, elija **Editar DropDownItems**.

3. En el **Editor**de la colección de elementos, haga clic con el botón primario en el elemento de menú que desea desplace.

4. Haga clic en las teclas de flecha arriba y abajo para colocar el elemento de menú en el menú.

5. Haga clic en **OK**.

## <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>Para desplace un elemento de menú dentro de un menú mediante el teclado

1. Presione y mantenga presionada la tecla ALT.

2. Haga clic y mantenga presionado el botón primario del mouse en el elemento de menú que desea desplace.

3. Arrastre el elemento de menú a la nueva ubicación y suelte el botón primario del mouse.

## <a name="to-move-a-menu-item-to-another-menu"></a>Para colocar un elemento de menú en otro menú

1. Haga clic con el botón primario en el elemento de menú que desea desplace y presione CTRL + X o haga clic con el botón derecho en el elemento de menú y elija **cortar** en el menú contextual.

2. Haga clic con el botón primario en el menú que contendrá el elemento de menú que ha cortado.

3. Haga clic con el botón primario en el elemento de menú que está antes de la nueva ubicación deseada y presione CTRL + V, o haga clic con el botón derecho en el elemento de menú que se encuentra antes de la nueva ubicación deseada y seleccione **pegar** en el menú contextual.

     El elemento de menú que corte se insertará después del elemento de menú seleccionado.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
