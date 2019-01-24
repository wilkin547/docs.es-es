---
title: Procedimiento Acoplar controles en Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: f4a9d3bcf7f9db1634da2b2f06177c05061af28e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733550"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Procedimiento Acoplar controles en Windows Forms
Puede acoplar controles a los bordes del formulario o hacer que rellene el contenedor del control (un formulario o un control contenedor). Por ejemplo, en el Explorador de Windows se acopla su <xref:System.Windows.Forms.TreeView> control a la izquierda de la ventana y su <xref:System.Windows.Forms.ListView> control a la derecha de la ventana. Use el <xref:System.Windows.Forms.Control.Dock%2A> propiedad para todos los controles de Windows Forms visibles definir el modo de acoplamiento.  
  
> [!NOTE]
>  Los controles se acoplan en orden z inverso.  
  
 El <xref:System.Windows.Forms.Control.Dock%2A> propiedad interactúa con el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad. Para obtener más información, consulte [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
### <a name="to-dock-a-control"></a>Para acoplar un control  
  
1.  Seleccione el control que desee acoplar.  
  
2.  En la ventana Propiedades, haga clic en la flecha situada a la derecha de la <xref:System.Windows.Forms.Control.Dock%2A> propiedad.  
  
     Se muestra un editor que muestra una serie de cuadros que representan los bordes y el centro del formulario.  
  
3.  Haga clic en el botón que representa el borde del formulario donde desea acoplar el control. Para rellenar el contenido del control de contenedor o el formulario del control, haga clic en el cuadro del centro. Haga clic en **(ninguno)** para deshabilitar el acoplamiento.  
  
     El control cambia automáticamente de tamaño para ajustarse a los límites del borde acoplado.  
  
    > [!NOTE]
    >  Los controles heredados deben estar `Protected` que puedan estar acoplada. Para cambiar el nivel de acceso de un control, establezca su **modificador** propiedad en la ventana Propiedades.  
  
## <a name="see-also"></a>Vea también
- [Controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md)
- [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
- [Cómo: Delimitar y acoplar controles secundarios en un Control FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Cómo: Delimitar y acoplar controles secundarios en un Control TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
- [Cómo: Delimitar controles en Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
