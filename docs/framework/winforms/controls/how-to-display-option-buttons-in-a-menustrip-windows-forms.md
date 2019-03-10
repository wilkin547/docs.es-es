---
title: Procedimiento Mostrar los botones de opción en un control MenuStrip (formularios Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: c64dd88915fdd17deee415b4d6c3fd088fbcfbfd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718875"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Filtrar Mostrar los botones de opción en un control MenuStrip (formularios Windows Forms)
Botones de opción, también conocido como botones de radio, son similares a las casillas excepto en que los usuarios pueden seleccionar solo uno en uno. Aunque de forma predeterminada el <xref:System.Windows.Forms.ToolStripMenuItem> clase no proporciona el comportamiento del botón de opción, la clase proporciona el comportamiento de la casilla de verificación que se puede personalizar para implementar el comportamiento del botón de opción para los elementos de menú en un <xref:System.Windows.Forms.MenuStrip> control.  
  
 Cuando el <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> es propiedad de un elemento de menú `true`, los usuarios hacer clic en el elemento para alternar la presentación de una marca de verificación. El <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad indica el estado actual del elemento. Para implementar el comportamiento del botón de opción básico, debe asegurarse de que cuando se selecciona un elemento, establecen el <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad del elemento seleccionado anteriormente para `false`.  
  
 Los procedimientos siguientes describen cómo realizar la implementación y funcionalidad adicional en una clase que hereda la <xref:System.Windows.Forms.ToolStripMenuItem> clase. El `ToolStripRadioButtonMenuItem` clase reemplaza a los miembros como <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> y <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para proporcionar el comportamiento de la selección y la apariencia de botones de opción. Además, esta clase invalida el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad, por lo que las opciones de un submenú están deshabilitadas a menos que el elemento primario está seleccionado.  
  
### <a name="to-implement-option-button-selection-behavior"></a>Para implementar el comportamiento de selección de botón de opción  
  
1.  Inicializar el <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad `true` para habilitar la selección de elementos.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> método para borrar la selección del elemento seleccionado previamente cuando se selecciona un nuevo elemento.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> método para asegurarse de que al hacer clic en un elemento que se ha seleccionado ya no borra la selección.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a>Para modificar la apariencia de los elementos de botón de opción  
  
1.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> método para reemplazar la marca de verificación de forma predeterminada con un botón de opción mediante el <xref:System.Windows.Forms.RadioButtonRenderer> clase.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, y <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> métodos para realizar un seguimiento del estado del mouse y asegúrese de que el <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> método pinta el estado del botón de opción correctos.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Para deshabilitar las opciones de un submenú al elemento primario no está seleccionado  
  
1.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad para que el elemento está deshabilitado cuando tiene un elemento primario con ambos un <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> valor `true` y un <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> valor de `false`.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> método para suscribirse a la <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> eventos del elemento primario.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  En el controlador para el elemento principal <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> eventos, invalide el elemento para actualizar la pantalla con el nuevo estado habilitado.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se proporciona la completa `ToolStripRadioButtonMenuItem` (clase) y un <xref:System.Windows.Forms.Form> clase y `Program` clase para demostrar el comportamiento del botón de opción.  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [Control MenuStrip](menustrip-control-windows-forms.md)
- [Cómo: Implementar un control ToolStripRenderer personalizado](how-to-implement-a-custom-toolstriprenderer.md)
