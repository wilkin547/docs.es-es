---
title: 'Cómo: Delimitar y acoplar controles secundarios en un control FlowLayoutPanel'
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: b53547e8e61e69834f262407de490422e6b6bb00
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44082166"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Cómo: Delimitar y acoplar controles secundarios en un control FlowLayoutPanel
El control <xref:System.Windows.Forms.FlowLayoutPanel> admite las propiedades <xref:System.Windows.Forms.Control.Anchor%2A> y <xref:System.Windows.Forms.Control.Dock%2A> en sus controles secundarios.  
  
### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Para delimitar y acoplar controles secundarios en un control FlowLayoutPanel  
  
1.  Cree un control <xref:System.Windows.Forms.FlowLayoutPanel> en el formulario.  
  
2.  Establecer el <xref:System.Windows.Forms.Control.Width%2A> de la <xref:System.Windows.Forms.FlowLayoutPanel> el control a **300**y establezca su <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> a <xref:System.Windows.Forms.FlowDirection.TopDown>.  
  
3.  Cree dos controles <xref:System.Windows.Forms.Button> y colóquelos en el control <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
4.  Establecer el <xref:System.Windows.Forms.Control.Width%2A> del primer botón en **200**.  
  
5.  Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del segundo botón en <xref:System.Windows.Forms.DockStyle.Fill>.  
  
    > [!NOTE]
    >  El segundo botón toma el mismo ancho que el primer botón. No se ajusta a lo ancho del control <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
6.  Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del segundo botón en `None`. Esto hace que el botón tome su ancho original.  
  
7.  Establezca la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del segundo botón en `Left, Right`.  
  
    > [!IMPORTANT]
    >  El segundo botón toma el mismo ancho que el primer botón. No se ajusta a lo ancho del control <xref:System.Windows.Forms.FlowLayoutPanel>. Esta es la regla general para delimitar y acoplar en el control <xref:System.Windows.Forms.FlowLayoutPanel>: para direcciones de flujo verticales, el control <xref:System.Windows.Forms.FlowLayoutPanel> calcula el ancho de una columna implícita a partir del control secundario más ancho de la columna. Todos los demás controles de esta columna con propiedades <xref:System.Windows.Forms.Control.Anchor%2A> o <xref:System.Windows.Forms.Control.Dock%2A> se alinean o cambian de tamaño para ajustarse a esta columna implícita. El comportamiento funciona de forma similar para las direcciones de flujo horizontales. El control <xref:System.Windows.Forms.FlowLayoutPanel> calcula el alto de una fila implícita a partir del control secundario más alto de la fila, y todos los controles secundarios delimitados o acoplados de esta fila se alinean o cambian de tamaño para ajustarse a la fila implícita.  
  
## <a name="example"></a>Ejemplo  
 La ilustración siguiente muestra cuatro botones que se delimitan y se acoplan con relación al botón azul en un <xref:System.Windows.Forms.FlowLayoutPanel>. El valor de <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> es <xref:System.Windows.Forms.FlowDirection.LeftToRight>.  
  
 ![Delimitación de FlowLayoutPanel](../../../../docs/framework/winforms/controls/media/net-flpanchorexp.gif "NET_FLPanchorExp")  
  
 La ilustración siguiente muestra cuatro botones que se delimitan y se acoplan con relación al botón azul en un <xref:System.Windows.Forms.FlowLayoutPanel>. El valor de <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> es <xref:System.Windows.Forms.FlowDirection.TopDown>.  
  
 ![Delimitación de FlowLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-flpanchor2.gif "VS_FLPanchor2")  
  
 En el ejemplo de código siguiente se muestran varios valores de propiedad <xref:System.Windows.Forms.Control.Anchor%2A> para un control <xref:System.Windows.Forms.Button> en un control <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
 [!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [Información general sobre el control FlowLayoutPanel](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-overview.md)
