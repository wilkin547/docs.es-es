---
title: 'Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: 513029c1bd5cc4af52fcee97f7fab961729e613c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44039600"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a>Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño
Puede hacer que el control se alinea el elemento en el borde de los formularios estableciendo la <xref:System.Windows.Forms.Control.Dock%2A>. Esta propiedad designa el lugar en el que se encuentra el control en el formulario. La propiedad <xref:System.Windows.Forms.Control.Dock%2A> puede establecerse en los valores siguientes:  
  
|Parámetro|Efecto en el control|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|Lo acopla en la parte inferior del formulario.|  
|<xref:System.Windows.Forms.DockStyle.Fill>|Llena todo el espacio restante del formulario.|  
|<xref:System.Windows.Forms.DockStyle.Left>|Lo acopla en el lado izquierdo del formulario.|  
|<xref:System.Windows.Forms.DockStyle.None>|No lo acopla en cualquier lugar y aparece en la ubicación especificada por su <xref:System.Windows.Forms.Control.Location%2A>.|  
|<xref:System.Windows.Forms.DockStyle.Right>|Lo acopla en el lado derecho del formulario.|  
|<xref:System.Windows.Forms.DockStyle.Top>|Lo acopla en la parte superior del formulario.|  
  
 Estos valores también se pueden establecer en el código. Para obtener más información, consulte [Cómo: alinear un Control con los bordes de formularios](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-dock-property-for-your-control-at-design-time"></a>Para establecer la propiedad Dock en su control en tiempo de diseño  
  
1.  En el Diseñador de formularios de Windows, seleccione el control.  
  
2.  En el **propiedades** ventana, haga clic en cuadro de lista desplegable situado junto a la <xref:System.Windows.Forms.Control.Dock%2A> propiedad.  
  
     Una interfaz gráfica que representa los seis posibles <xref:System.Windows.Forms.Control.Dock%2A> se muestra la configuración.  
  
3.  Elija la configuración apropiada.  
  
4.  El control se acoplará la manera especificada por la configuración.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [Alinear un control con los bordes de los formularios](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)  
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Procedimiento para delimitar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)  
 [Delimitar y acoplar controles secundarios en un control TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Delimitar y acoplar controles secundarios en un control FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Desarrollar controles de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
