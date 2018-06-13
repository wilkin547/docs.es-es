---
title: 'Cómo: Mostrar botones de opción en un control MenuStrip (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: da2bb7edceaf83aa5178618fd4098631d65a7d49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538034"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Cómo: Mostrar botones de opción en un control MenuStrip (Windows Forms)
Botones de opción, también conocidos como botones de radio, son similares a las casillas excepto en que los usuarios pueden seleccionar sólo uno en uno. Aunque de forma predeterminada el <xref:System.Windows.Forms.ToolStripMenuItem> clase no proporciona el comportamiento de botón de opción, la clase proporcionar un comportamiento de casilla de verificación que se puede personalizar para implementar el comportamiento de botón de opción para elementos de menú en un <xref:System.Windows.Forms.MenuStrip> control.  
  
 Cuando el <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> la propiedad de un elemento de menú es `true`, los usuarios puedan seleccionar el elemento para alternar la presentación de una marca de verificación. El <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad indica el estado actual del elemento. Para implementar el comportamiento de botón de opción básico, debe asegurarse de que, al que se selecciona un elemento, establezca la <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad del elemento seleccionado anteriormente para `false`.  
  
 Los procedimientos siguientes describen cómo implementar esto y funciones adicionales en una clase que hereda la <xref:System.Windows.Forms.ToolStripMenuItem> clase. El `ToolStripRadioButtonMenuItem` clase reemplaza a los miembros como <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> y <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para proporcionar el comportamiento de la selección y la apariencia de los botones de opción. Además, esta clase reemplaza el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad para que las opciones de un submenú están deshabilitados a menos que se selecciona el elemento primario.  
  
### <a name="to-implement-option-button-selection-behavior"></a>Para implementar el comportamiento de selección de botón de opción  
  
1.  Inicializar el <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad `true` para habilitar la selección de elementos.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> método para borrar la selección del elemento seleccionado anteriormente cuando se selecciona un nuevo elemento.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> método para asegurarse de que al hacer clic en un elemento que ya se ha seleccionado no borrará la selección.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a>Para modificar la apariencia de los elementos de botón de opción  
  
1.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> método para reemplazar la marca de verificación de forma predeterminada con un botón de opción mediante el <xref:System.Windows.Forms.RadioButtonRenderer> clase.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, y <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> métodos para hacer un seguimiento del estado del mouse y asegúrese de que el <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> método pinta el estado del botón de opción correctos.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Para deshabilitar las opciones en un submenú cuando no se selecciona el elemento primario  
  
1.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad para que el elemento está deshabilitado cuando tiene un elemento primario con ambos un <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> valo `true` y un <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> valo `false`.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> método para suscribirse a las <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> eventos del elemento primario.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  En el controlador para el elemento principal <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> eventos, invalide el elemento para actualizar la pantalla con el nuevo estado habilitado.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se proporciona la sección completa `ToolStripRadioButtonMenuItem` (clase) y un <xref:System.Windows.Forms.Form> clase y `Program` clase para demostrar el comportamiento de botón de opción.  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RadioButtonRenderer>  
 [Control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [Implementar un control ToolStripRenderer personalizado](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)
