---
title: "C&#243;mo: Delimitar y acoplar controles secundarios en un control FlowLayoutPanel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles secundarios, delimitar y acoplar"
  - "controles [Windows Forms], secundarios"
  - "FlowLayoutPanel (control) [Windows Forms], controles secundarios"
  - "diseño [Windows Forms], controles secundarios"
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Delimitar y acoplar controles secundarios en un control FlowLayoutPanel
El control <xref:System.Windows.Forms.FlowLayoutPanel> admite las propiedades <xref:System.Windows.Forms.Control.Anchor%2A> y <xref:System.Windows.Forms.Control.Dock%2A> en sus controles secundarios.  
  
### Para delimitar y acoplar controles secundarios en un control FlowLayoutPanel  
  
1.  Cree un control <xref:System.Windows.Forms.FlowLayoutPanel> en el formulario.  
  
2.  Establezca el valor de <xref:System.Windows.Forms.Control.Width%2A> del control <xref:System.Windows.Forms.FlowLayoutPanel> en 300 y establezca el valor de <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> en <xref:System.Windows.Forms.FlowDirection>.  
  
3.  Cree dos controles <xref:System.Windows.Forms.Button> y colóquelos en el control <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
4.  Establezca el valor de <xref:System.Windows.Forms.Control.Width%2A> del primer botón en 200.  
  
5.  Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del segundo botón en <xref:System.Windows.Forms.DockStyle>.  
  
    > [!NOTE]
    >  El segundo botón toma el mismo ancho que el primer botón.  No se ajusta a lo ancho del control <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
6.  Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del segundo botón en `Ninguno`.  Esto hace que el botón tome su ancho original.  
  
7.  Establezca la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del segundo botón en `Izquierda, Derecha`.  
  
    > [!IMPORTANT]
    >  El segundo botón toma el mismo ancho que el primer botón.  No se ajusta a lo ancho del control <xref:System.Windows.Forms.FlowLayoutPanel>.  Esta es la regla general para delimitar y acoplar en el control <xref:System.Windows.Forms.FlowLayoutPanel>: para direcciones de flujo verticales, el control <xref:System.Windows.Forms.FlowLayoutPanel> calcula el ancho de una columna implícita a partir del control secundario más ancho de la columna.  Todos los demás controles de esta columna con propiedades <xref:System.Windows.Forms.Control.Anchor%2A> o <xref:System.Windows.Forms.Control.Dock%2A> se alinean o cambian de tamaño para ajustarse a esta columna implícita.  El comportamiento funciona de forma similar para las direcciones de flujo horizontales.  El control <xref:System.Windows.Forms.FlowLayoutPanel> calcula el alto de una fila implícita a partir del control secundario más alto de la fila, y todos los controles secundarios delimitados o acoplados de esta fila se alinean o cambian de tamaño para ajustarse a la fila implícita.  
  
## Ejemplo  
 La ilustración siguiente muestra cuatro botones que se delimitan y se acoplan con relación al botón azul en un <xref:System.Windows.Forms.FlowLayoutPanel>.  El valor de <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> es <xref:System.Windows.Forms.FlowDirection>.  
  
 ![Delimitación de FlowLayoutPanel](../../../../docs/framework/winforms/controls/media/net-flpanchorexp.png "NET\_FLPanchorExp")  
  
 La ilustración siguiente muestra cuatro botones que se delimitan y se acoplan con relación al botón azul en un <xref:System.Windows.Forms.FlowLayoutPanel>.  El valor de <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> es <xref:System.Windows.Forms.FlowDirection>.  
  
 ![Delimitación de FlowLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-flpanchor2.png "VS\_FLPanchor2")  
  
 En el ejemplo de código siguiente se muestran varios valores de propiedad <xref:System.Windows.Forms.Control.Anchor%2A> para un control <xref:System.Windows.Forms.Button> en un control <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
 [!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 [Información general sobre el control FlowLayoutPanel](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-overview.md)