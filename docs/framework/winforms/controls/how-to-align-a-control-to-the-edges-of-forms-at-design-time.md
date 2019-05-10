---
title: Procedimiento para alinear un control con los bordes de los formularios en tiempo de diseño
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b08e01eb9adb984a32a8fc435cf1f3b93b159a14
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210378"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a>Procedimiento para alinear un control con los bordes de los formularios en tiempo de diseño

Puede hacer que el control se alinea el elemento en el borde de los formularios estableciendo el valor de la <xref:System.Windows.Forms.Control.Dock%2A> propiedad. Esta propiedad designa el lugar en el que se encuentra el control en el formulario. La propiedad <xref:System.Windows.Forms.Control.Dock%2A> puede establecerse en los valores siguientes:

|Parámetro|Efecto en el control|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|Lo acopla en la parte inferior del formulario.|
|<xref:System.Windows.Forms.DockStyle.Fill>|Llena todo el espacio restante del formulario.|
|<xref:System.Windows.Forms.DockStyle.Left>|Lo acopla en el lado izquierdo del formulario.|
|<xref:System.Windows.Forms.DockStyle.None>|No lo acopla en cualquier lugar y aparece en la ubicación especificada por su <xref:System.Windows.Forms.Control.Location%2A>.|
|<xref:System.Windows.Forms.DockStyle.Right>|Lo acopla en el lado derecho del formulario.|
|<xref:System.Windows.Forms.DockStyle.Top>|Lo acopla en la parte superior del formulario.|

Estos valores también se pueden establecer en el código. Para obtener más información, vea [Cómo: Alinear un Control con los bordes de formularios](how-to-align-a-control-to-the-edges-of-forms.md).

## <a name="set-the-dock-property-for-your-control-at-design-time"></a>Establezca la propiedad Dock en su control en tiempo de diseño

1. En el Diseñador de Windows Forms en Visual Studio, seleccione el control.

2. En el **propiedades** ventana, haga clic en cuadro de lista desplegable situado junto a la <xref:System.Windows.Forms.Control.Dock%2A> propiedad.

     Una interfaz gráfica que representa los seis posibles <xref:System.Windows.Forms.Control.Dock%2A> se muestra la configuración.

3. Elija la configuración apropiada.

4. El control se acoplará la manera especificada por la configuración.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [Cómo: Alinear un Control con los bordes de formularios](how-to-align-a-control-to-the-edges-of-forms.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Cómo: Delimitar controles en Windows Forms](how-to-anchor-controls-on-windows-forms.md)
- [Cómo: Delimitar y acoplar controles secundarios en un Control TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Cómo: Delimitar y acoplar controles secundarios en un Control FlowLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Desarrollar controles de Windows Forms en tiempo de diseño](developing-windows-forms-controls-at-design-time.md)
