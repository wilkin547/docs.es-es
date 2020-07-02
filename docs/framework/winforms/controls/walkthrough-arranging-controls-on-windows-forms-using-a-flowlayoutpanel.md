---
title: Organizar controles mediante FlowLayoutPanel
description: Aprenda a usar el control FlowLayoutPanel y el control TableLayoutPanel para proporcionar formas intuitivas de organizar los controles en el proyecto de Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- FlowLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
- controls [Windows Forms], arranging with FlowLayoutPanel
- layout [Windows Forms], walkthroughs
ms.assetid: a1744323-0316-49c2-992e-ebfc0a976b85
ms.openlocfilehash: efcb38275be7b0cf94afb6b68aa139876f7cf5fd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619291"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel"></a>Tutorial: Organizar controles en formularios Windows Forms mediante FlowLayoutPanel

Algunas aplicaciones requieren un formulario con un diseño que se organice de manera adecuada y automática a medida que el formulario o el contenido cambien de tamaño. Si necesita un diseño dinámico y no desea controlar los eventos <xref:System.Windows.Forms.Control.Layout> de forma explícita en el código, considere la posibilidad de usar un panel de diseño.

El control <xref:System.Windows.Forms.FlowLayoutPanel> y el control <xref:System.Windows.Forms.TableLayoutPanel> proporcionan formas intuitivas para organizar los controles en el formulario. Ambos proporcionan una capacidad automática y configurable para controlar las posiciones relativas de los controles secundarios que contienen, y ambos ofrecen características de diseño dinámico en tiempo de ejecución, lo que permite cambiar el tamaño y la posición de los controles secundarios a medida que las dimensiones del formulario primario cambian. Los paneles de diseño se pueden anidar dentro de paneles de diseño para habilitar la creación de interfaces de usuario sofisticadas.

El <xref:System.Windows.Forms.TableLayoutPanel> organiza su contenido en una cuadrícula, lo que proporciona una funcionalidad similar a la del \<table> elemento HTML. Las celdas se organizan en filas y columnas, y pueden tener distintos tamaños. Para obtener más información, consulta [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).

El control <xref:System.Windows.Forms.FlowLayoutPanel> organiza su contenido en una dirección de flujo específica: horizontal o vertical. Su contenido puede ajustarse desde una fila a la siguiente o desde una columna a la siguiente. Además, el contenido puede recortarse en lugar de ajustarse. Las tareas ilustradas en este tutorial incluyen:

- Crear un proyecto de Windows Forms

- Organizar los controles horizontal y verticalmente

- Cambiar la dirección del flujo

- Insertar saltos de flujo

- Organizar los controles mediante Padding y Margin

- Insertar controles mediante un doble clic en estos en el cuadro de herramientas

- Insertar un control dibujando su contorno

- Insertar controles mediante el símbolo de intercalación

- Reasignar controles existentes en un elemento primario diferente

Cuando haya terminado, tendrá conocimientos sobre el rol que desempeñan estas características de diseño importantes.

## <a name="create-the-project"></a>Crear el proyecto

1. En Visual Studio, cree un proyecto de aplicación basado en Windows denominado "FlowLayoutPanelExample" (**archivo**  >  **nuevo**  >  **proyecto**  >  **Visual C#** o **Visual Basic**  >  aplicación**clásica de escritorio**  >  **Windows Forms**).

2. Seleccione el formulario en el **Diseñador de Windows Forms**.

## <a name="arranging-controls-horizontally-and-vertically"></a>Organizar los controles horizontal y verticalmente
 El control <xref:System.Windows.Forms.FlowLayoutPanel> permite colocar controles en filas o columnas sin necesidad de especificar con precisión la posición de cada control individual.

 El control <xref:System.Windows.Forms.FlowLayoutPanel> puede cambiar el tamaño de sus controles secundarios o redistribuirlos a medida que las dimensiones del formulario primario cambian.

### <a name="to-arrange-controls-horizontally-and-vertically-using-a-flowlayoutpanel"></a>Para organizar controles horizontal y verticalmente mediante un control FlowLayoutPanel

1. Arrastre un control <xref:System.Windows.Forms.FlowLayoutPanel> del **cuadro de herramientas** al formulario.

2. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al control <xref:System.Windows.Forms.FlowLayoutPanel>. Tenga en cuenta que se mueve automáticamente a la esquina superior izquierda del control <xref:System.Windows.Forms.FlowLayoutPanel> .

3. Arrastre otro control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al control <xref:System.Windows.Forms.FlowLayoutPanel>. Tenga en cuenta que el control <xref:System.Windows.Forms.Button> se mueve automáticamente a una posición junto al primer control <xref:System.Windows.Forms.Button> . Si el control <xref:System.Windows.Forms.FlowLayoutPanel> es demasiado estrecho para ajustar los dos controles en la misma fila, el nuevo control <xref:System.Windows.Forms.Button> se mueve automáticamente a la fila siguiente.

4. Arrastre algunos controles <xref:System.Windows.Forms.Button> más del **cuadro de herramientas** al control <xref:System.Windows.Forms.FlowLayoutPanel>. Siga colocando controles <xref:System.Windows.Forms.Button> hasta que uno se ajuste a la fila siguiente.

5. Cambie el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel> del control <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> a `false`. Tenga en cuenta que los controles secundarios ya no fluyen a la fila siguiente. En su lugar, se mueven a la primera fila y se recortan.

6. Cambie el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel> del control <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> a `true`. Tenga en cuenta que los controles secundarios se ajustan de nuevo a la fila siguiente.

7. Reduzca el ancho del control <xref:System.Windows.Forms.FlowLayoutPanel> hasta que todos los controles <xref:System.Windows.Forms.Button> se muevan a la primera columna.

8. Aumente el ancho del control <xref:System.Windows.Forms.FlowLayoutPanel> hasta que todos los controles <xref:System.Windows.Forms.Button> se muevan a la primera fila. Es posible que deba cambiar el tamaño del formulario para alojar el ancho mayor.

## <a name="changing-flow-direction"></a>Cambiar la dirección del flujo
 La propiedad <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> permite cambiar la dirección en la que se organizan los controles. Puede organizar los controles secundarios de izquierda a derecha, de derecha a izquierda, de arriba abajo o de abajo arriba.

### <a name="to-change-the-flow-direction-in-a-flowlayoutpanel"></a>Para cambiar la dirección del flujo en un control FlowLayoutPanel

1. Cambie el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel> del control <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> a <xref:System.Windows.Forms.FlowDirection.TopDown>. Tenga en cuenta que los controles secundarios se reorganizan en una o más columnas, según el alto del control.

2. Cambie el tamaño del control <xref:System.Windows.Forms.FlowLayoutPanel> de modo que el alto sea menor que la columna de controles <xref:System.Windows.Forms.Button> . Tenga en cuenta que el control <xref:System.Windows.Forms.FlowLayoutPanel> reorganiza los controles secundarios para que fluyan a la columna siguiente. Siga disminuyendo el alto y observe que los controles secundarios fluyen a las columnas consecutivas. Cambie el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel> del control <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> a <xref:System.Windows.Forms.FlowDirection.RightToLeft>. Observe que las posiciones de los controles secundarios están invertidas. Observe el diseño al cambiar el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> a <xref:System.Windows.Forms.FlowDirection.BottomUp>.

## <a name="inserting-flow-breaks"></a>Insertar saltos de flujo
 El control <xref:System.Windows.Forms.FlowLayoutPanel> proporciona una propiedad FlowBreak a sus controles secundarios. Al establecer el valor de la propiedad FlowBreak en `true` , el control <xref:System.Windows.Forms.FlowLayoutPanel> deja de distribuir los controles en la dirección del flujo actual y ajusta a la siguiente fila o columna.

### <a name="to-insert-flow-breaks"></a>Para insertar saltos de flujo

1. Cambie el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel> del control <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> a <xref:System.Windows.Forms.FlowDirection.TopDown>.

2. Seleccione uno de los controles <xref:System.Windows.Forms.Button> en el centro de la primera columna de la izquierda.

3. Establezca el valor de la propiedad FlowBreak del control <xref:System.Windows.Forms.Button> en `true`. Observe que la columna está rota y que los controles que siguen al control <xref:System.Windows.Forms.Button> seleccionado fluyen a la columna siguiente. Establezca el valor de la propiedad FlowBreak del control <xref:System.Windows.Forms.Button> en `false` para volver al comportamiento original.

## <a name="positioning-controls-using-docking-and-anchoring"></a>Colocar controles mediante el acoplamiento y la delimitación
 Los comportamientos de acoplamiento y delimitación de los controles secundarios difieren de los comportamientos de otros controles contenedor. El acoplamiento y la delimitación están relacionados con el control mayor en la dirección del flujo.

### <a name="to-position-controls-using-docking-and-anchoring"></a>Para colocar controles mediante el acoplamiento y la delimitación

1. Aumente el tamaño del control <xref:System.Windows.Forms.FlowLayoutPanel> hasta que los controles <xref:System.Windows.Forms.Button> estén organizados en una columna.

2. Seleccione el control <xref:System.Windows.Forms.Button> superior. Aumente su ancho hasta que doble el ancho de los demás controles <xref:System.Windows.Forms.Button> .

3. Seleccione el segundo control <xref:System.Windows.Forms.Button> . Cambie el valor de su propiedad <xref:System.Windows.Forms.Control.Anchor%2A> a <xref:System.Windows.Forms.AnchorStyles.Right>. Observe que se mueve hasta que el borde derecho queda alineado con el borde derecho del primer control <xref:System.Windows.Forms.Button> .

4. Cambie el valor de su propiedad <xref:System.Windows.Forms.Control.Anchor%2A> a <xref:System.Windows.Forms.AnchorStyles.Right> y <xref:System.Windows.Forms.AnchorStyles.Left>. Observe que su tamaño se ajusta al ancho del primer control <xref:System.Windows.Forms.Button> .

5. Seleccione el tercer control <xref:System.Windows.Forms.Button> . Cambie el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> a <xref:System.Windows.Forms.DockStyle.Fill>. Observe que su tamaño se ajusta al ancho del primer control <xref:System.Windows.Forms.Button> .

## <a name="arranging-controls-using-padding-and-margins"></a>Organizar los controles mediante Padding y Margin
 También puede organizar los controles del control <xref:System.Windows.Forms.FlowLayoutPanel> cambiando las propiedades <xref:System.Windows.Forms.Control.Padding%2A> y <xref:System.Windows.Forms.Control.Margin%2A> .

 La propiedad <xref:System.Windows.Forms.Control.Padding%2A> permite controlar la colocación de controles dentro de una celda del control <xref:System.Windows.Forms.FlowLayoutPanel> . Especifica el espaciado entre los controles secundarios y el borde del control <xref:System.Windows.Forms.FlowLayoutPanel> .

 La propiedad <xref:System.Windows.Forms.Control.Margin%2A> permite controlar el espaciado entre los controles.

### <a name="to-arrange-controls-using-the-padding-and-margin-properties"></a>Para organizar los controles mediante las propiedades Padding y Margin

1. Cambie el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel> del control <xref:System.Windows.Forms.Control.Dock%2A> a <xref:System.Windows.Forms.DockStyle.Fill>. Si el formulario es suficientemente grande, los controles <xref:System.Windows.Forms.Button> se moverán a la primera columna del control <xref:System.Windows.Forms.FlowLayoutPanel> .

2. Cambie el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel> del control <xref:System.Windows.Forms.Control.Padding%2A> mediante la expansión de la entrada <xref:System.Windows.Forms.Control.Padding%2A> en la ventana **Propiedades** y la configuración de la propiedad <xref:System.Windows.Forms.Padding.All%2A> en **20**. Para obtener más información, vea [Tutorial: diseñar Windows Forms controles con relleno, márgenes y la propiedad AutoSize](windows-forms-controls-padding-autosize.md). Tenga en cuenta que los controles secundarios se mueven hacia el centro del control <xref:System.Windows.Forms.FlowLayoutPanel> . El valor aumentado de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> inserta los controles secundarios fuera de los bordes del control <xref:System.Windows.Forms.FlowLayoutPanel> .

3. Seleccione todos los controles <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.FlowLayoutPanel> y establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Margin%2A> en **20**. Observe que el espaciado entre los controles <xref:System.Windows.Forms.Button> aumenta, por lo que se separan más. Puede que necesite cambiar el tamaño del control <xref:System.Windows.Forms.FlowLayoutPanel> para aumentarlo y ver todos los controles secundarios.

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Insertar controles mediante un doble clic en estos en el cuadro de herramientas
 Para rellenar el control <xref:System.Windows.Forms.FlowLayoutPanel> puede hacer doble clic en los controles del **cuadro de herramientas**.

### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>Para insertar controles mediante un doble clic en el cuadro de herramientas

1. Haga doble clic en el icono del control <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas**. Observe que aparece un nuevo control <xref:System.Windows.Forms.Button> en el control <xref:System.Windows.Forms.FlowLayoutPanel> .

2. Haga doble clic en algunos controles más en el **cuadro de herramientas**. Observe que los nuevos controles aparecen de manera consecutiva en el control <xref:System.Windows.Forms.FlowLayoutPanel> .

## <a name="inserting-a-control-by-drawing-its-outline"></a>Insertar un control dibujando su contorno
 Puede insertar un control en un control <xref:System.Windows.Forms.FlowLayoutPanel> y dibujar su contorno en una celda para especificar el tamaño.

### <a name="to-insert-a-control-by-drawing-its-outline"></a>Para insertar un control dibujando su contorno

1. En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.Button> . No lo arrastre hasta el formulario.

2. Mueva el puntero del mouse sobre el control <xref:System.Windows.Forms.FlowLayoutPanel> . Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.Button> agregado.

3. Haga clic y mantenga presionado el botón del mouse.

4. Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.Button> . Cuando esté satisfecho con el tamaño, suelte el botón del mouse. Tenga en cuenta que el control <xref:System.Windows.Forms.Button> se crea en la siguiente ubicación abierta del control <xref:System.Windows.Forms.FlowLayoutPanel> .

## <a name="inserting-controls-using-the-insertion-bar"></a>Insertar controles mediante la barra de inserción
 Puede insertar controles en una posición específica de un control <xref:System.Windows.Forms.FlowLayoutPanel> . Cuando se arrastra un control en el área de cliente del control <xref:System.Windows.Forms.FlowLayoutPanel> , aparece una barra de inserción para indicar la ubicación donde se insertará el control.

### <a name="to-insert-a-control-using-the-caret"></a>Para insertar un control mediante el símbolo de intercalación

1. Arrastre un control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** al control <xref:System.Windows.Forms.FlowLayoutPanel> y señale el espacio entre los dos controles <xref:System.Windows.Forms.Button> . Observe que se dibuja una barra de inserción, que indica dónde se <xref:System.Windows.Forms.Button> colocará cuando se coloque en el <xref:System.Windows.Forms.FlowLayoutPanel> control. Antes de colocar el nuevo control <xref:System.Windows.Forms.Button> en el control <xref:System.Windows.Forms.FlowLayoutPanel> , mueva el puntero del mouse para observar cómo se mueve la barra de inserción.

2. Coloque el nuevo control <xref:System.Windows.Forms.Button> en el control <xref:System.Windows.Forms.FlowLayoutPanel> . Tenga en cuenta que el nuevo control <xref:System.Windows.Forms.Button> no está alineado con los demás, porque su propiedad <xref:System.Windows.Forms.Control.Margin%2A> tiene un valor diferente.

## <a name="reassigning-existing-controls-to-a-different-parent"></a>Reasignar controles existentes en un elemento primario diferente
 Puede asignar controles que existen en el formulario a un nuevo control <xref:System.Windows.Forms.FlowLayoutPanel> .

### <a name="to-reparent-existing-controls"></a>Para cambiar el primario de los controles existentes

1. Arrastre tres controles <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario. Colóquelos cerca entre sí, pero sin alinearlos.

2. En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> . No lo arrastre hasta el formulario.

3. Mueva el puntero del mouse cerca de los tres controles <xref:System.Windows.Forms.Button> . Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> agregado.

4. Haga clic y mantenga presionado el botón del mouse.

5. Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.FlowLayoutPanel> . Dibuje el contorno alrededor de los tres controles <xref:System.Windows.Forms.Button> .

6. Suelte el botón del mouse (ratón). Observe que los tres controles <xref:System.Windows.Forms.Button> se insertan en el control <xref:System.Windows.Forms.FlowLayoutPanel> .

## <a name="next-steps"></a>Pasos siguientes
 Puede lograr un diseño complejo mediante una combinación de controles y paneles de diseño. Algunas sugerencias de investigación adicional son:

- Cambie el tamaño de uno de los controles <xref:System.Windows.Forms.Button> para aumentarlo y observe el efecto en el diseño.

- Los paneles de diseño pueden contener otros paneles de diseño. Experimente colocando un control <xref:System.Windows.Forms.TableLayoutPanel> en el control existente.

- Acople el control <xref:System.Windows.Forms.FlowLayoutPanel> al formulario primario. Cambie el tamaño del formulario y observe el efecto en el diseño.

- Establezca la propiedad <xref:System.Windows.Forms.Control.Visible%2A> de uno de los controles en `false` y observe cómo se distribuye <xref:System.Windows.Forms.FlowLayoutPanel> en respuesta.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Información general sobre la propiedad AutoSize](autosize-property-overview.md)
- [Procedimiento para acoplar controles en formularios Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Cómo: Delimitar controles en formularios Windows Forms](how-to-anchor-controls-on-windows-forms.md)
- [Tutorial: Diseñar controles de formularios Windows Forms con relleno, márgenes y la propiedad AutoSize](windows-forms-controls-padding-autosize.md)
