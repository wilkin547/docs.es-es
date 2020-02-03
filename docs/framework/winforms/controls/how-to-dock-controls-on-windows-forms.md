---
title: para controles de acoplamiento
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 02f1c26dcb322a39c41781c83d8c820bd2fd27e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745525"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Cómo: acoplar controles en Windows Forms

Puede acoplar controles a los bordes del formulario o hacer que rellenen el contenedor del control (ya sea un formulario o un control contenedor). Por ejemplo, el explorador de Windows acopla su control <xref:System.Windows.Forms.TreeView> al lado izquierdo de la ventana y su control <xref:System.Windows.Forms.ListView> al lado derecho de la ventana. Use la propiedad <xref:System.Windows.Forms.Control.Dock%2A> de todos los controles de Windows Forms visibles para definir el modo de acoplamiento.

> [!NOTE]
> Los controles se acoplan en orden z inverso.

La propiedad <xref:System.Windows.Forms.Control.Dock%2A> interactúa con la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>. Para obtener más información, vea [información general sobre la propiedad AutoSize](autosize-property-overview.md).

## <a name="to-dock-a-control"></a>Para acoplar un control

1. En Visual Studio, seleccione el control que desea acoplar.

2. En la ventana **propiedades** , haga clic en la flecha situada a la derecha de la propiedad <xref:System.Windows.Forms.Control.Dock%2A>.

   Se muestra un editor que muestra una serie de cuadros que representan los bordes y el centro del formulario.

3. Haga clic en el botón que representa el borde del formulario en el que desea acoplar el control. Para rellenar el contenido del control de formulario o contenedor del control, haga clic en el cuadro central. Haga clic en **(ninguno)** para deshabilitar el acoplamiento.

   El control cambia automáticamente de tamaño para ajustarse a los límites del borde acoplado.

   > [!NOTE]
   > Los controles heredados deben estar `Protected` para poder acoplarse. Para cambiar el nivel de acceso de un control, establezca su propiedad **modificador** en la ventana **propiedades** .

## <a name="see-also"></a>Consulte también

- [Controles de Windows Forms](index.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
- [Delimitar y acoplar controles secundarios en un control FlowLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Delimitar y acoplar controles secundarios en un control TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Información general sobre la propiedad AutoSize](autosize-property-overview.md)
- [Procedimiento para delimitar controles en formularios Windows Forms](how-to-anchor-controls-on-windows-forms.md)
