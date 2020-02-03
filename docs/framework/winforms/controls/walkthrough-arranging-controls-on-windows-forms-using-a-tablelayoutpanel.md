---
title: Organizar controles mediante un control TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 803a56f6416cf3b718890e96cf9f36ae6c4ee471
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740320"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel

Algunas aplicaciones requieren un formulario con un diseño que se organice de manera adecuada y automática a medida que el formulario o el contenido cambien de tamaño. Si necesita un diseño dinámico y no desea controlar los eventos <xref:System.Windows.Forms.Control.Layout> de forma explícita en el código, considere la posibilidad de usar un panel de diseño.

El control <xref:System.Windows.Forms.FlowLayoutPanel> y el control <xref:System.Windows.Forms.TableLayoutPanel> proporcionan formas intuitivas para organizar los controles en el formulario. Ambos proporcionan una capacidad automática y configurable para controlar las posiciones relativas de los controles secundarios que contienen, y ambos ofrecen características de diseño dinámico en tiempo de ejecución, lo que permite cambiar el tamaño y la posición de los controles secundarios a medida que las dimensiones del formulario primario cambian. Los paneles de diseño se pueden anidar dentro de paneles de diseño para habilitar la creación de interfaces de usuario sofisticadas.

El control <xref:System.Windows.Forms.FlowLayoutPanel> organiza su contenido en una dirección de flujo específica: horizontal o vertical. Su contenido puede ajustarse desde una fila a la siguiente o desde una columna a la siguiente. Además, el contenido puede recortarse en lugar de ajustarse. Para obtener más información, vea [Tutorial: organizar controles en Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

El <xref:System.Windows.Forms.TableLayoutPanel> organiza su contenido en una cuadrícula, lo que proporciona una funcionalidad similar a la de la tabla del \<HTML > elemento. El control <xref:System.Windows.Forms.TableLayoutPanel> permite colocar controles en un diseño de cuadrícula sin necesidad de especificar con precisión la posición de cada control individual. Las celdas se organizan en filas y columnas, y pueden tener distintos tamaños. Las celdas se pueden combinar en filas y columnas. Las celdas pueden contener cualquier elemento que un formulario pueda contener y comportarse en la mayoría de los demás aspectos como contenedores.

El control <xref:System.Windows.Forms.TableLayoutPanel> también proporciona una función de cambio de tamaño proporcional en tiempo de ejecución, por lo que el diseño puede cambiar sin problemas a medida que se cambia el tamaño del formulario. Esto hace que el control de <xref:System.Windows.Forms.TableLayoutPanel> sea adecuado para propósitos como los formularios de entrada de datos y las aplicaciones localizadas. Para obtener más información, vea [Tutorial: crear un formulario de Windows Forms de tamaño variable para la entrada de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)) y [Tutorial: crear un Windows Form localizable](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).

En general, no debe usar un control <xref:System.Windows.Forms.TableLayoutPanel> como contenedor para todo el diseño. Utilice <xref:System.Windows.Forms.TableLayoutPanel> controles para proporcionar funciones de cambio de tamaño proporcional a las partes del diseño.

Las tareas ilustradas en este tutorial incluyen:

- Crear un proyecto de Windows Forms

- Organizar controles en filas y columnas

- Establecer propiedades de filas y columnas

- Expandir filas y columnas con un control

- Control automático de los desbordamientos

- Insertar controles mediante un doble clic en estos en el cuadro de herramientas

- Insertar un control dibujando su contorno

- Reasignar controles existentes en un elemento primario diferente

Cuando termine, comprenderá el rol de estas importantes características de diseño.

## <a name="creating-the-project"></a>Crear el proyecto

El primer paso es crear el proyecto y configurar el formulario.

#### <a name="to-create-the-project"></a>Para crear el proyecto

1. Cree un proyecto de aplicación para Windows denominado "TableLayoutPanelExample". Para obtener más información, vea [Cómo: crear un proyecto de aplicación Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) .

2. Seleccione el formulario en el diseñador de **Windows** **Forms**.

## <a name="arranging-controls-in-rows-and-columns"></a>Organizar controles en filas y columnas

El control <xref:System.Windows.Forms.TableLayoutPanel> permite organizar fácilmente los controles en filas y columnas.

#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>Para organizar los controles en filas y columnas mediante TableLayoutPanel

1. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario. Tenga en cuenta que, de forma predeterminada, el control <xref:System.Windows.Forms.TableLayoutPanel> tiene cuatro celdas.

2. Arrastre un control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** al control <xref:System.Windows.Forms.TableLayoutPanel> y colóquelo en una de las celdas. Tenga en cuenta que el control de <xref:System.Windows.Forms.Button> se crea dentro de la celda seleccionada.

3. Arrastre tres controles <xref:System.Windows.Forms.Button> del cuadro de **herramientas** al control <xref:System.Windows.Forms.TableLayoutPanel>, de modo que cada celda contenga un botón.

4. Agarre el controlador de tamaño vertical entre las dos columnas y muévala hacia la izquierda. Tenga en cuenta que se cambia el tamaño de los controles <xref:System.Windows.Forms.Button> de la primera columna a un ancho menor, mientras que el tamaño de los controles <xref:System.Windows.Forms.Button> de la segunda columna no cambia.

5. Agarre el controlador de tamaño vertical entre las dos columnas y muévalo a la derecha. Tenga en cuenta que los controles <xref:System.Windows.Forms.Button> de la primera columna vuelven a su tamaño original, mientras que los controles <xref:System.Windows.Forms.Button> de la segunda columna se mueven a la derecha.

6. Mueva el controlador de tamaño horizontal hacia arriba y hacia abajo para ver el efecto en los controles del panel.

## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Colocar controles dentro de las celdas mediante el acoplamiento y la delimitación

El comportamiento de delimitación de los controles secundarios en un <xref:System.Windows.Forms.TableLayoutPanel> difiere del comportamiento de otros controles contenedor. El comportamiento de acoplamiento de los controles secundarios es el mismo que el de otros controles contenedor.

#### <a name="positioning-controls-within-cells"></a>Colocar controles dentro de las celdas

1. Seleccione el primer control de <xref:System.Windows.Forms.Button>. Cambie el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> a <xref:System.Windows.Forms.DockStyle.Fill>. Tenga en cuenta que el control <xref:System.Windows.Forms.Button> se expande para rellenar su celda.

2. Seleccione uno de los otros controles de <xref:System.Windows.Forms.Button>. Cambie el valor de su propiedad <xref:System.Windows.Forms.Control.Anchor%2A> a <xref:System.Windows.Forms.AnchorStyles.Right>. Tenga en cuenta que se mueve para que el borde derecho esté cerca del borde derecho de la celda. La distancia entre los bordes es la suma de la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control <xref:System.Windows.Forms.Button> y la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del panel.

3. Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a <xref:System.Windows.Forms.AnchorStyles.Right> y <xref:System.Windows.Forms.AnchorStyles.Left>. Tenga en cuenta que el tamaño del control se ajusta al ancho de la celda, con los valores <xref:System.Windows.Forms.Control.Margin%2A> y <xref:System.Windows.Forms.Control.Padding%2A> que se tienen en cuenta.

4. Repita los pasos 2 y 3 con los estilos <xref:System.Windows.Forms.AnchorStyles.Top> y <xref:System.Windows.Forms.AnchorStyles.Bottom>.

## <a name="setting-row-and-column-properties"></a>Establecer propiedades de filas y columnas

Puede establecer propiedades individuales de filas y columnas mediante las colecciones <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> y <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>.

#### <a name="to-set-row-and-column-properties"></a>Para establecer las propiedades de filas y columnas

1. Seleccione el control <xref:System.Windows.Forms.TableLayoutPanel> en el **Diseñador de Windows Forms**.

2. En las ventanas **propiedades** , abra la colección de <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> haciendo clic en los puntos suspensivos (![botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la entrada **columnas** .

3. Seleccione la primera columna y cambie el valor de su propiedad <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> a <xref:System.Windows.Forms.SizeType.AutoSize>. Haga clic en **Aceptar** para aceptar el cambio. Tenga en cuenta que el ancho de la primera columna se reduce para ajustarse al control <xref:System.Windows.Forms.Button>. Tenga en cuenta también que no se puede cambiar el ancho de la columna.

4. En la ventana **propiedades** , abra la colección de <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> y seleccione la primera columna. Cambie el valor de su propiedad <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> a <xref:System.Windows.Forms.SizeType.Percent>. Haga clic en **Aceptar** para aceptar el cambio. Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un ancho mayor y observe que el ancho de la primera columna se expande. Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un ancho menor y observe que los botones de la primera columna tienen el tamaño para ajustarse a la celda. Tenga en cuenta también que se puede cambiar el ancho de la columna.

5. En la ventana **propiedades** , abra la colección de <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> y seleccione todas las columnas de la lista. Establezca el valor de cada propiedad <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> en <xref:System.Windows.Forms.SizeType.Percent>. Haga clic en **Aceptar** para aceptar el cambio. Repita el procedimiento con la colección de <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A>.

6. Arrastre uno de los controladores de cambio de tamaño de las esquinas y cambie el ancho y el alto del control de <xref:System.Windows.Forms.TableLayoutPanel>. Tenga en cuenta que se cambia el tamaño de las filas y las columnas a medida que cambia el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel>. Tenga en cuenta también que se puede cambiar el tamaño de las filas y las columnas con los controladores de tamaño horizontal y vertical.

## <a name="spanning-rows-and-columns-with-a-control"></a>Expandir filas y columnas con un control

El control <xref:System.Windows.Forms.TableLayoutPanel> agrega varias propiedades nuevas a los controles en tiempo de diseño. Dos de estas propiedades son `RowSpan` y `ColumnSpan`. Puede usar estas propiedades para hacer que un control abarque más de una fila o columna.

#### <a name="to-span-rows-and-columns-with-a-control"></a>Para abarcar filas y columnas con un control

1. Seleccione el control <xref:System.Windows.Forms.Button> en la primera fila y primera columna.

2. En las ventanas de **propiedades** , cambie el valor de la propiedad `ColumnSpan` a **2**. Tenga en cuenta que el control <xref:System.Windows.Forms.Button> rellena la primera columna y la segunda columna. Tenga en cuenta también que se ha agregado una fila adicional para dar cabida a este cambio.

3. Repita el paso 2 para la propiedad `RowSpan`.

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Insertar controles mediante un doble clic en estos en el cuadro de herramientas

Para rellenar el control <xref:System.Windows.Forms.TableLayoutPanel> puede hacer doble clic en los controles del **cuadro de herramientas**.

#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>Para insertar controles mediante un doble clic en el cuadro de herramientas

1. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.

2. Haga doble clic en el icono del control <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas**. Observe que aparece un nuevo control de botón en la primera celda del control <xref:System.Windows.Forms.TableLayoutPanel>.

3. Haga doble clic en algunos controles más en el **cuadro de herramientas**. Tenga en cuenta que los nuevos controles aparecen sucesivamente en las celdas no ocupadas del control <xref:System.Windows.Forms.TableLayoutPanel>. Tenga en cuenta también que el control <xref:System.Windows.Forms.TableLayoutPanel> se expande para dar cabida a los nuevos controles si no hay ninguna celda abierta disponible.

## <a name="automatic-handling-of-overflows"></a>Control automático de los desbordamientos

Al insertar controles en el control <xref:System.Windows.Forms.TableLayoutPanel>, puede quedarse sin celdas vacías para los nuevos controles. El control <xref:System.Windows.Forms.TableLayoutPanel> controla esta situación automáticamente aumentando el número de celdas.

#### <a name="to-observe-automatic-handling-of-overflows"></a>Para observar el control automático de los desbordamientos

1. Si todavía hay celdas vacías en el control <xref:System.Windows.Forms.TableLayoutPanel>, siga insertando nuevos controles de <xref:System.Windows.Forms.Button> hasta que el control de <xref:System.Windows.Forms.TableLayoutPanel> esté lleno.

2. Una vez que el control de <xref:System.Windows.Forms.TableLayoutPanel> está lleno, haga doble clic en el icono de <xref:System.Windows.Forms.Button> del **cuadro de herramientas** para insertar otro control de <xref:System.Windows.Forms.Button>. Tenga en cuenta que el control <xref:System.Windows.Forms.TableLayoutPanel> crea nuevas celdas para alojar el nuevo control. Inserte algunos controles más y observe el comportamiento de cambio de tamaño.

3. Cambie el valor de la propiedad <xref:System.Windows.Forms.TableLayoutPanel> del control <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> a <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Haga doble clic en el icono de <xref:System.Windows.Forms.Button> en el **cuadro de herramientas** para insertar <xref:System.Windows.Forms.Button> controles hasta que el control de <xref:System.Windows.Forms.TableLayoutPanel> esté lleno. Haga doble clic en el icono de <xref:System.Windows.Forms.Button> en el **cuadro de herramientas** de nuevo. Tenga en cuenta que recibe un mensaje de error de la **Diseñador de Windows Forms** que le informa de que no se pueden crear más filas y columnas.

## <a name="inserting-a-control-by-drawing-its-outline"></a>Insertar un control dibujando su contorno

Puede insertar un control en un control <xref:System.Windows.Forms.TableLayoutPanel> y dibujar su contorno en una celda para especificar el tamaño.

#### <a name="to-insert-a-control-by-drawing-its-outline"></a>Para insertar un control dibujando su contorno

1. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.

2. En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.Button> . No lo arrastre hasta el formulario.

3. Mueva el puntero del mouse sobre el control <xref:System.Windows.Forms.TableLayoutPanel> . Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.Button> agregado.

4. Haga clic y mantenga presionado el botón del mouse.

5. Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.Button> . Cuando esté satisfecho con el tamaño, suelte el botón del mouse. Tenga en cuenta que el control <xref:System.Windows.Forms.Button> se crea en la celda en la que dibujó el contorno del control.

## <a name="multiple-controls-within-cells-are-not-permitted"></a>No se permiten varios controles dentro de las celdas

El control <xref:System.Windows.Forms.TableLayoutPanel> solo puede contener un control secundario por celda.

#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>Para demostrar que no se permiten varios controles dentro de las celdas

- Arrastre un control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** al control <xref:System.Windows.Forms.TableLayoutPanel> y colóquelo en una de las celdas ocupadas. Tenga en cuenta que el control <xref:System.Windows.Forms.TableLayoutPanel> no permite colocar el control <xref:System.Windows.Forms.Button> en la celda ocupada.

## <a name="swapping-controls"></a>Intercambiar controles

El control <xref:System.Windows.Forms.TableLayoutPanel> permite intercambiar los controles que ocupan dos celdas diferentes.

#### <a name="to-swap-controls"></a>Para intercambiar controles

- Arrastre uno de los controles <xref:System.Windows.Forms.Button> desde una celda ocupada y colóquelo en otra celda ocupada. Tenga en cuenta que los dos controles se mueven de una celda al otro.

## <a name="next-steps"></a>Pasos siguientes

Puede lograr un diseño complejo mediante una combinación de controles y paneles de diseño. Algunas sugerencias de investigación adicional son:

- Intente cambiar el tamaño de uno de los controles <xref:System.Windows.Forms.Button> a un tamaño mayor y observe el efecto en el diseño.

- Pegue una selección de varios controles en el control <xref:System.Windows.Forms.TableLayoutPanel> y observe cómo se insertan los controles.

- Los paneles de diseño pueden contener otros paneles de diseño. Experimente colocando un control <xref:System.Windows.Forms.TableLayoutPanel> en el control existente.

- Acople el control <xref:System.Windows.Forms.TableLayoutPanel> al formulario primario. Cambie el tamaño del formulario y observe el efecto en el diseño.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Tutorial: Crear Windows Forms de entrada de datos de tamaño variable](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))
- [Tutorial: crear un Windows Form localizable](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))
- [Procedimientos recomendados para el control TableLayoutPanel](best-practices-for-the-tablelayoutpanel-control.md)
- [Información general sobre la propiedad AutoSize](autosize-property-overview.md)
- [Procedimiento para acoplar controles en formularios Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Procedimiento para delimitar controles en formularios Windows Forms](how-to-anchor-controls-on-windows-forms.md)
- [Tutorial: Diseñar controles de Windows Forms con relleno, márgenes y la propiedad AutoSize](windows-forms-controls-padding-autosize.md)
