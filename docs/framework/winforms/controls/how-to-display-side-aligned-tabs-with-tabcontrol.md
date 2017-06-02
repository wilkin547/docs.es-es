---
title: "C&#243;mo: Mostrar pesta&#241;as alineadas a la izquierda con TabControl | Microsoft Docs"
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
  - "páginas de fichas, mostrar pestañas alineadas a la izquierda"
  - "TabControl (control) [Windows Forms], mostrar pestañas alineadas a la izquierda"
  - "pestañas, mostrar pestañas alineadas a la izquierda"
ms.assetid: 110d5abd-3ae3-4ded-95bf-778aaac798a0
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Mostrar pesta&#241;as alineadas a la izquierda con TabControl
La propiedad <xref:System.Windows.Forms.TabControl.Alignment%2A> de <xref:System.Windows.Forms.TabControl> permite mostrar pestañas verticalmente \(a lo largo del borde izquierdo o derecho del control\) en lugar de horizontalmente \(en la parte superior o inferior del control\).  De forma predeterminada, esta presentación vertical produce una mala experiencia de usuario porque la propiedad <xref:System.Windows.Forms.TabPage.Text%2A> del objeto <xref:System.Windows.Forms.TabPage> no se muestra en la pestaña cuando se habilitan estilos visuales.  Tampoco hay una manera directa de controlar la dirección del texto dentro de la pestaña.  Puede usar la característica «dibujado por el propietario» en <xref:System.Windows.Forms.TabControl> para mejorar la experiencia.  
  
 El procedimiento siguiente muestra cómo representar pestañas alineadas a la derecha, con el texto de la pestaña escrito de izquierda a derecha usando la característica "dibujado por el propietario".  
  
### Para mostrar pestañas alineadas a la derecha  
  
1.  Agregue un <xref:System.Windows.Forms.TabControl> al formulario.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.TabControl.Alignment%2A> en <xref:System.Windows.Forms.TabAlignment>.  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.TabControl.SizeMode%2A> en <xref:System.Windows.Forms.TabSizeMode> para que todas las pestañas tengan el mismo ancho.  
  
4.  Establezca la propiedad <xref:System.Windows.Forms.TabControl.ItemSize%2A> en el tamaño fijo preferido para las pestañas.  Tenga en cuenta que la propiedad <xref:System.Windows.Forms.TabControl.ItemSize%2A> se comporta como si las pestañas estuvieran en la parte superior, aunque estén alineadas a la derecha.  Como resultado, para hacer que las pestañas sean más anchas, debe cambiar la propiedad <xref:System.Drawing.Size.Height%2A> y, para que sean más altas, debe cambiar la propiedad <xref:System.Drawing.Size.Width%2A>.  
  
     Para obtener los mejores resultados con el siguiente ejemplo de código, establezca el valor de <xref:System.Drawing.Size.Width%2A> en 25 y el valor de <xref:System.Drawing.Size.Height%2A> en 100.  
  
5.  Establezca la propiedad <xref:System.Windows.Forms.TabControl.DrawMode%2A> en <xref:System.Windows.Forms.TabDrawMode>.  
  
6.  Defina un controlador para el evento <xref:System.Windows.Forms.TabControl.DrawItem> de <xref:System.Windows.Forms.TabControl> que representa el texto de izquierda a derecha.  
  
     [!code-csharp[TabControl.RightAlignedTabs#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/TabControl.RightAlignedTabs/CS/Form1.cs#1)]
     [!code-vb[TabControl.RightAlignedTabs#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/TabControl.RightAlignedTabs/VB/Form1.vb#1)]  
  
## Vea también  
 [TabControl \(Control\)](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)