---
title: 'Cómo: Mostrar botones de opción en un control MenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: f3010e71396ce562e9dbdefd4b75b36f3a81ffb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735528"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Cómo: Mostrar botones de opción en un control MenuStrip (Windows Forms)

Los botones de opción, también conocidos como botones de radio, son similares a las casillas, salvo que los usuarios solo pueden seleccionar uno cada vez. Aunque de forma predeterminada la clase <xref:System.Windows.Forms.ToolStripMenuItem> no proporciona el comportamiento del botón de opción, la clase proporciona un comportamiento de casilla que se puede personalizar para implementar el comportamiento de los botones de opción para los elementos de menú en un control <xref:System.Windows.Forms.MenuStrip>.

Cuando se `true`la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> de un elemento de menú, los usuarios pueden hacer clic en el elemento para alternar la presentación de una marca de verificación. La propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> indica el estado actual del elemento. Para implementar el comportamiento básico de los botones de opción, debe asegurarse de que cuando se selecciona un elemento, establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> del elemento seleccionado anteriormente en `false`.

En los procedimientos siguientes se describe cómo implementar esta y la funcionalidad adicional en una clase que hereda la clase <xref:System.Windows.Forms.ToolStripMenuItem>. La clase `ToolStripRadioButtonMenuItem` invalida miembros como <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> y <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para proporcionar el comportamiento de la selección y la apariencia de los botones de opción. Además, esta clase invalida la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> de modo que las opciones de un submenú estén deshabilitadas a menos que se seleccione el elemento primario.

## <a name="to-implement-option-button-selection-behavior"></a>Para implementar el comportamiento de la selección de botones de opción

1. Inicialice la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> en `true` para habilitar la selección de elementos.

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. Invalide el método <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> para borrar la selección del elemento seleccionado anteriormente cuando se selecciona un nuevo elemento.

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. Invalide el método <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> para asegurarse de que al hacer clic en un elemento que ya se ha seleccionado no se borrará la selección.

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a>Para modificar la apariencia de los elementos de botón de opción

1. Invalide el método <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para reemplazar la marca de verificación predeterminada por un botón de opción mediante la clase <xref:System.Windows.Forms.RadioButtonRenderer>.

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. Invalide los métodos <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>y <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> para realizar el seguimiento del estado del mouse y asegurarse de que el método <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> dibuje el estado correcto del botón de opción.

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Para deshabilitar las opciones de un submenú cuando no se selecciona el elemento primario

1. Invalide la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> de modo que el elemento esté deshabilitado cuando tenga un elemento primario con un valor <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> de `true` y un valor <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> de `false`.

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. Invalide el método <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> para suscribirse al evento de <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> del elemento primario.

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. En el controlador del evento de <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> de elemento primario, invalide el elemento para actualizar la presentación con el nuevo estado habilitado.

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se proporciona la clase `ToolStripRadioButtonMenuItem` completa y una clase <xref:System.Windows.Forms.Form> y `Program` clase para mostrar el comportamiento del botón de opción.

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
- [Implementar un control ToolStripRenderer personalizado](how-to-implement-a-custom-toolstriprenderer.md)
