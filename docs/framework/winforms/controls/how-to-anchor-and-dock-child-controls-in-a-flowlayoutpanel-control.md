---
title: Procedimiento para delimitar y acoplar controles secundarios en un control FlowLayoutPanel
description: Obtenga información sobre cómo delimitar y acoplar controles secundarios mediante programación en un Windows Forms control FlowLayoutPanel.
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: b4fb3bf6d148a526a75926bd67c1f967286332bf
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174541"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Procedimiento para delimitar y acoplar controles secundarios en un control FlowLayoutPanel

El control <xref:System.Windows.Forms.FlowLayoutPanel> admite las propiedades <xref:System.Windows.Forms.Control.Anchor%2A> y <xref:System.Windows.Forms.Control.Dock%2A> en sus controles secundarios.

### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Para delimitar y acoplar controles secundarios en un control FlowLayoutPanel

1. Cree un control <xref:System.Windows.Forms.FlowLayoutPanel> en el formulario.

2. Establezca el valor <xref:System.Windows.Forms.Control.Width%2A> del <xref:System.Windows.Forms.FlowLayoutPanel> control en **300**y establezca su <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> en <xref:System.Windows.Forms.FlowDirection.TopDown> .

3. Cree dos controles <xref:System.Windows.Forms.Button> y colóquelos en el control <xref:System.Windows.Forms.FlowLayoutPanel>.

4. Establezca el valor <xref:System.Windows.Forms.Control.Width%2A> del primer botón en **200**.

5. Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del segundo botón en <xref:System.Windows.Forms.DockStyle.Fill>.

    > [!NOTE]
    > El segundo botón toma el mismo ancho que el primer botón. No se ajusta a lo ancho del control <xref:System.Windows.Forms.FlowLayoutPanel>.

6. Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del segundo botón en `None`. Esto hace que el botón tome su ancho original.

7. Establezca la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del segundo botón en `Left, Right`.

    > [!IMPORTANT]
    > El segundo botón toma el mismo ancho que el primer botón. No se ajusta a lo ancho del control <xref:System.Windows.Forms.FlowLayoutPanel>. Esta es la regla general para delimitar y acoplar en el control <xref:System.Windows.Forms.FlowLayoutPanel>: para direcciones de flujo verticales, el control <xref:System.Windows.Forms.FlowLayoutPanel> calcula el ancho de una columna implícita a partir del control secundario más ancho de la columna. Todos los demás controles de esta columna con propiedades <xref:System.Windows.Forms.Control.Anchor%2A> o <xref:System.Windows.Forms.Control.Dock%2A> se alinean o cambian de tamaño para ajustarse a esta columna implícita. El comportamiento funciona de forma similar para las direcciones de flujo horizontales. El control <xref:System.Windows.Forms.FlowLayoutPanel> calcula el alto de una fila implícita a partir del control secundario más alto de la fila, y todos los controles secundarios delimitados o acoplados de esta fila se alinean o cambian de tamaño para ajustarse a la fila implícita.

## <a name="example"></a>Ejemplo

La ilustración siguiente muestra cuatro botones que se delimitan y se acoplan con relación al botón azul en un <xref:System.Windows.Forms.FlowLayoutPanel>. El valor de <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> es <xref:System.Windows.Forms.FlowDirection.LeftToRight>.

![Delimitación de FlowLayoutPanel](./media/net-flpanchorexp.gif "NET_FLPanchorExp")

La ilustración siguiente muestra cuatro botones que se delimitan y se acoplan con relación al botón azul en un <xref:System.Windows.Forms.FlowLayoutPanel>. El valor de <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> es <xref:System.Windows.Forms.FlowDirection.TopDown>.

![Delimitación de FlowLayoutPanel](./media/vs-flpanchor2.gif "VS_FLPanchor2")

En el ejemplo de código siguiente se muestran varios valores de propiedad <xref:System.Windows.Forms.Control.Anchor%2A> para un control <xref:System.Windows.Forms.Button> en un control <xref:System.Windows.Forms.FlowLayoutPanel>.

[!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
[!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]

## <a name="compiling-the-code"></a>Compilar el código

Para este ejemplo se necesita:

- Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FlowLayoutPanel>
- [Información general sobre el control FlowLayoutPanel](flowlayoutpanel-control-overview.md)
