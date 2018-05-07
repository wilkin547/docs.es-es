---
title: 'Cómo: Mostrar pestañas alineadas a la izquierda con TabControl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tab pages [Windows Forms], displaying side-aligned tabs
- tabs [Windows Forms], displaying side-aligned tabs
- TabControl control [Windows Forms], displaying side-aligned tabs
ms.assetid: 110d5abd-3ae3-4ded-95bf-778aaac798a0
ms.openlocfilehash: e145547ba4c8648a765e9507b7f35e50cb15fd82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-side-aligned-tabs-with-tabcontrol"></a>Cómo: Mostrar pestañas alineadas a la izquierda con TabControl
La propiedad <xref:System.Windows.Forms.TabControl.Alignment%2A> de <xref:System.Windows.Forms.TabControl> permite mostrar pestañas verticalmente (a lo largo del borde izquierdo o derecho del control) en lugar de horizontalmente (en la parte superior o inferior del control). De forma predeterminada, esta presentación vertical produce una mala experiencia de usuario porque la propiedad <xref:System.Windows.Forms.TabPage.Text%2A> del objeto <xref:System.Windows.Forms.TabPage> no se muestra en la pestaña cuando se habilitan estilos visuales. Tampoco hay una manera directa de controlar la dirección del texto dentro de la pestaña. Puede usar la característica «dibujado por el propietario» en <xref:System.Windows.Forms.TabControl> para mejorar la experiencia.  
  
 El procedimiento siguiente muestra cómo representar pestañas alineadas a la derecha, con el texto de la pestaña escrito de izquierda a derecha usando la característica "dibujado por el propietario".  
  
### <a name="to-display-right-aligned-tabs"></a>Para mostrar pestañas alineadas a la derecha  
  
1.  Agregue un <xref:System.Windows.Forms.TabControl> al formulario.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.TabControl.Alignment%2A> en <xref:System.Windows.Forms.TabAlignment.Right>.  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.TabControl.SizeMode%2A> en <xref:System.Windows.Forms.TabSizeMode.Fixed> para que todas las pestañas tengan el mismo ancho.  
  
4.  Establezca la propiedad <xref:System.Windows.Forms.TabControl.ItemSize%2A> en el tamaño fijo preferido para las pestañas. Tenga en cuenta que la propiedad <xref:System.Windows.Forms.TabControl.ItemSize%2A> se comporta como si las pestañas estuvieran en la parte superior, aunque estén alineadas a la derecha. Como resultado, para hacer que las pestañas sean más anchas, debe cambiar la propiedad <xref:System.Drawing.Size.Height%2A> y, para que sean más altas, debe cambiar la propiedad <xref:System.Drawing.Size.Width%2A>.  
  
     Para obtener los mejores resultados con el siguiente ejemplo de código, establezca el valor de <xref:System.Drawing.Size.Width%2A> en 25 y el valor de <xref:System.Drawing.Size.Height%2A> en 100.  
  
5.  Establezca la propiedad <xref:System.Windows.Forms.TabControl.DrawMode%2A> en <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.  
  
6.  Defina un controlador para el evento <xref:System.Windows.Forms.TabControl.DrawItem> de <xref:System.Windows.Forms.TabControl> que representa el texto de izquierda a derecha.  
  
     [!code-csharp[TabControl.RightAlignedTabs#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/TabControl.RightAlignedTabs/CS/Form1.cs#1)]
     [!code-vb[TabControl.RightAlignedTabs#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/TabControl.RightAlignedTabs/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [TabControl (control)](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)
