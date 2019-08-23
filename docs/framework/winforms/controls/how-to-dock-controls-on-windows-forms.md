---
title: Procedimiento para acoplar controles en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: dc514fd8b9b7a17bf07a878e42729db4187d2b82
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963626"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Procedimiento para acoplar controles en formularios Windows Forms
Puede acoplar controles a los bordes del formulario o hacer que rellenen el contenedor del control (ya sea un formulario o un control contenedor). Por ejemplo, el explorador de Windows acopla <xref:System.Windows.Forms.TreeView> su control en el lado izquierdo de la ventana y <xref:System.Windows.Forms.ListView> su control en el lado derecho de la ventana. Use la <xref:System.Windows.Forms.Control.Dock%2A> propiedad para todos los controles de Windows Forms visibles para definir el modo de acoplamiento.  
  
> [!NOTE]
> Los controles se acoplan en orden z inverso.  
  
 La <xref:System.Windows.Forms.Control.Dock%2A> propiedad interactúa con la <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad. Para obtener más información, vea [información general sobre la propiedad AutoSize](autosize-property-overview.md).  
  
### <a name="to-dock-a-control"></a>Para acoplar un control  
  
1. Seleccione el control que desea acoplar.  
  
2. En el ventana Propiedades, haga clic en la flecha situada a la <xref:System.Windows.Forms.Control.Dock%2A> derecha de la propiedad.  
  
     Se muestra un editor que muestra una serie de cuadros que representan los bordes y el centro del formulario.  
  
3. Haga clic en el botón que representa el borde del formulario en el que desea acoplar el control. Para rellenar el contenido del control de formulario o contenedor del control, haga clic en el cuadro central. Haga clic en **(ninguno)** para deshabilitar el acoplamiento.  
  
     El control cambia automáticamente de tamaño para ajustarse a los límites del borde acoplado.  
  
    > [!NOTE]
    > Los controles heredados `Protected` deben ser capaces de acoplarse. Para cambiar el nivel de acceso de un control, establezca su propiedad modificador en el ventana Propiedades.  
  
## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Organizar controles en formularios Windows Forms](arranging-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
- [Procedimientos: Delimitar y acoplar controles secundarios en un control FlowLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Cómo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Información general sobre la propiedad AutoSize](autosize-property-overview.md)
- [Cómo: Delimitar controles en Windows Forms](how-to-anchor-controls-on-windows-forms.md)
