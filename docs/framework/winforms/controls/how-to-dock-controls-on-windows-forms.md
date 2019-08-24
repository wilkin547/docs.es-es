---
title: Procedimiento para acoplar controles en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 58b61af306385a245bedf16e370e6830c370a622
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987479"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Procedimiento Acoplar controles en Windows Forms

Puede acoplar controles a los bordes del formulario o hacer que rellenen el contenedor del control (ya sea un formulario o un control contenedor). Por ejemplo, el explorador de Windows acopla <xref:System.Windows.Forms.TreeView> su control en el lado izquierdo de la ventana y <xref:System.Windows.Forms.ListView> su control en el lado derecho de la ventana. Use la <xref:System.Windows.Forms.Control.Dock%2A> propiedad para todos los controles de Windows Forms visibles para definir el modo de acoplamiento.

> [!NOTE]
> Los controles se acoplan en orden z inverso.

La <xref:System.Windows.Forms.Control.Dock%2A> propiedad interactúa con la <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad. Para obtener más información, vea [información general sobre la propiedad AutoSize](autosize-property-overview.md).

## <a name="to-dock-a-control"></a>Para acoplar un control

1. En Visual Studio, seleccione el control que desea acoplar.

2. En la ventana **propiedades** , haga clic en la flecha situada a la <xref:System.Windows.Forms.Control.Dock%2A> derecha de la propiedad.

   Se muestra un editor que muestra una serie de cuadros que representan los bordes y el centro del formulario.

3. Haga clic en el botón que representa el borde del formulario en el que desea acoplar el control. Para rellenar el contenido del control de formulario o contenedor del control, haga clic en el cuadro central. Haga clic en **(ninguno)** para deshabilitar el acoplamiento.

   El control cambia automáticamente de tamaño para ajustarse a los límites del borde acoplado.

   > [!NOTE]
   > Los controles heredados `Protected` deben ser capaces de acoplarse. Para cambiar el nivel de acceso de un control, establezca su propiedad modificador en la ventana **propiedades** .

## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
- [Procedimientos: Delimitar y acoplar controles secundarios en un control FlowLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Procedimientos: Delimitar y acoplar controles secundarios en un control TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Información general sobre la propiedad AutoSize](autosize-property-overview.md)
- [Procedimientos: Delimitar controles en Windows Forms](how-to-anchor-controls-on-windows-forms.md)
