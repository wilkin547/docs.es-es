---
title: Procedimiento Mostrar botones de opción en un MenuStrip (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: 94d683369edd6583ad8b01c2ce3f393567a5ed75
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971935"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Procedimiento Mostrar botones de opción en un MenuStrip (Windows Forms)

Los botones de opción, también conocidos como botones de radio, son similares a las casillas, salvo que los usuarios solo pueden seleccionar uno cada vez. Aunque de forma predeterminada <xref:System.Windows.Forms.ToolStripMenuItem> , la clase no proporciona el comportamiento del botón de opción, la clase proporciona un comportamiento de casilla que se puede personalizar para implementar el comportamiento del botón de opción para <xref:System.Windows.Forms.MenuStrip> los elementos de menú en un control.

Cuando la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad de un elemento de menú `true`es, los usuarios pueden hacer clic en el elemento para alternar la presentación de una marca de verificación. La <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad indica el estado actual del elemento. Para implementar el comportamiento básico de los botones de opción, debe asegurarse de que cuando se selecciona un elemento, <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> establezca la propiedad del elemento seleccionado anteriormente `false`en.

En los procedimientos siguientes se describe cómo implementar esta y la funcionalidad adicional en una clase que hereda <xref:System.Windows.Forms.ToolStripMenuItem> la clase. La `ToolStripRadioButtonMenuItem` clase invalida miembros <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> como y <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para proporcionar el comportamiento de selección y la apariencia de los botones de opción. Además, esta clase invalida la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad para que las opciones de un submenú estén deshabilitadas a menos que se seleccione el elemento primario.

## <a name="to-implement-option-button-selection-behavior"></a>Para implementar el comportamiento de la selección de botones de opción

1. Inicialice la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad en `true` para habilitar la selección de elementos.

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. Invalide el <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> método para borrar la selección del elemento seleccionado anteriormente cuando se selecciona un nuevo elemento.

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. Invalide el <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> método para asegurarse de que al hacer clic en un elemento que ya se ha seleccionado no se borrará la selección.

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a>Para modificar la apariencia de los elementos de botón de opción

1. Invalide el <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> método para reemplazar la marca de verificación predeterminada por un botón de opción <xref:System.Windows.Forms.RadioButtonRenderer> mediante la clase.

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>Invalide los <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>métodos, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, y <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> para realizar un seguimiento del estado del mouse y asegurarse <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> de que el método pinta el estado correcto del botón de opción.

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Para deshabilitar las opciones de un submenú cuando no se selecciona el elemento primario

1. Invalide la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad para que el elemento se deshabilite cuando tenga un elemento primario con <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> un valor `true` de y <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> un valor `false`de.

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. Invalide el <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> método para suscribirse <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> al evento del elemento primario.

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. En el controlador del evento de elemento <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> primario, invalide el elemento para actualizar la presentación con el nuevo estado habilitado.

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se `ToolStripRadioButtonMenuItem` proporciona la clase completa <xref:System.Windows.Forms.Form> y una `Program` clase y clase para mostrar el comportamiento del botón de opción.

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a>Compilar el código

Para este ejemplo se necesita:

- Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.

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
- [Procedimientos: Implementar un ToolStripRenderer personalizado](how-to-implement-a-custom-toolstriprenderer.md)
