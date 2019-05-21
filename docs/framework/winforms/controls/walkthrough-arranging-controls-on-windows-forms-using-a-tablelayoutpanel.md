---
title: 'Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: cbd0eb3dfc8f4494bf9a8e96ff7c472622f135d8
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960341"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel

Algunas aplicaciones requieren un formulario con un diseño que se organice de manera adecuada y automática a medida que el formulario o el contenido cambien de tamaño. Si necesita un diseño dinámico y no desea controlar los eventos <xref:System.Windows.Forms.Control.Layout> de forma explícita en el código, considere la posibilidad de usar un panel de diseño.

El control <xref:System.Windows.Forms.FlowLayoutPanel> y el control <xref:System.Windows.Forms.TableLayoutPanel> proporcionan formas intuitivas para organizar los controles en el formulario. Ambos proporcionan una capacidad automática y configurable para controlar las posiciones relativas de los controles secundarios que contienen, y ambos ofrecen características de diseño dinámico en tiempo de ejecución, lo que permite cambiar el tamaño y la posición de los controles secundarios a medida que las dimensiones del formulario primario cambian. Los paneles de diseño se pueden anidar dentro de paneles de diseño para habilitar la creación de interfaces de usuario sofisticadas.

El control <xref:System.Windows.Forms.FlowLayoutPanel> organiza su contenido en una dirección de flujo específica: horizontal o vertical. Su contenido puede ajustarse desde una fila a la siguiente o desde una columna a la siguiente. Además, el contenido puede recortarse en lugar de ajustarse. Para obtener más información, vea [Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

El <xref:System.Windows.Forms.TableLayoutPanel> organiza su contenido en una cuadrícula, que proporciona funcionalidad similar a HTML \<tabla > elemento. El <xref:System.Windows.Forms.TableLayoutPanel> control le permite colocar los controles en un diseño de cuadrícula sin necesidad de especificar con precisión la posición de cada control individual. Las celdas se organizan en filas y columnas, y pueden tener distintos tamaños. Las celdas se pueden combinar en filas y columnas. Las celdas pueden contener cualquier cosa un formulario puede contener y se comportan de la mayoría de los casos como contenedores.

El <xref:System.Windows.Forms.TableLayoutPanel> control también proporciona una funcionalidad de cambio de tamaño proporcional en tiempo de ejecución, por lo que su diseño puede cambiar fácilmente cuando se cambia el tamaño del formulario. Esto hace que el <xref:System.Windows.Forms.TableLayoutPanel> control adecuado para fines, como formularios de entrada de datos y las aplicaciones localizadas. Para obtener más información, vea [Tutorial: Creación de un formulario de Windows puede cambiar el tamaño de entrada de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)) y [Tutorial: Creación de un formulario Windows Localizable](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).

En general, no debe usar un <xref:System.Windows.Forms.TableLayoutPanel> control como un contenedor para todo el diseño. Use <xref:System.Windows.Forms.TableLayoutPanel> controles para proporcionar capacidades de cambio de tamaño proporcionales a las partes del diseño.

Las tareas ilustradas en este tutorial incluyen:

- Crear un proyecto de Windows Forms

- Organizar controles en filas y columnas

- Propiedades de columna y fila de valores

- Abarcar filas y columnas con un Control

- Control automático de desbordamientos

- Insertar controles mediante un doble clic en estos en el cuadro de herramientas

- Insertar un control dibujando su contorno

- Reasignar controles existentes en un elemento primario diferente

Cuando termine, comprenderá el rol de estas importantes características de diseño.

> [!NOTE]
> Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="creating-the-project"></a>Crear el proyecto

El primer paso es crear el proyecto y configurar el formulario.

#### <a name="to-create-the-project"></a>Para crear el proyecto

1. Cree un proyecto de aplicación de Windows denominado "TableLayoutPanelExample". Para obtener más información, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) .

2. Seleccione el formulario en el **Windows** **Diseñador de formularios**.

## <a name="arranging-controls-in-rows-and-columns"></a>Organizar controles en filas y columnas

El <xref:System.Windows.Forms.TableLayoutPanel> control le permite organizar fácilmente los controles en filas y columnas.

#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>Para organizar los controles en filas y columnas con un control TableLayoutPanel

1. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario. Tenga en cuenta que, de forma predeterminada, el <xref:System.Windows.Forms.TableLayoutPanel> control tiene cuatro celdas.

2. Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en el <xref:System.Windows.Forms.TableLayoutPanel> controlar y colóquelo en una de las celdas. Tenga en cuenta que el <xref:System.Windows.Forms.Button> control se crea dentro de la celda seleccionada.

3. Arrastre tres más <xref:System.Windows.Forms.Button> controla desde el **cuadro de herramientas** en el <xref:System.Windows.Forms.TableLayoutPanel> control, de modo que cada celda contiene un botón.

4. Agarre el controlador de cambio de tamaño vertical entre las dos columnas y muévalo a la izquierda. Tenga en cuenta que el <xref:System.Windows.Forms.Button> controles en la primera columna cambian de tamaño a un ancho menor al tamaño de la <xref:System.Windows.Forms.Button> controles en la segunda columna se ha modificado.

5. Agarre el controlador de cambio de tamaño vertical entre las dos columnas y muévalo a la derecha. Tenga en cuenta que el <xref:System.Windows.Forms.Button> controles en la primera columna se devuelven a su tamaño original, mientras el <xref:System.Windows.Forms.Button> controles en la segunda columna se mueven a la derecha.

6. Mueva el controlador de tamaño horizontal hacia arriba y abajo para ver el efecto en los controles en el panel.

## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Colocar controles en celdas mediante el acoplamiento y delimitación

El comportamiento de anclaje de controles secundarios en un <xref:System.Windows.Forms.TableLayoutPanel> difiere del comportamiento de otros controles contenedor. El comportamiento de acoplamiento de controles secundarios es igual que otros controles contenedor.

#### <a name="positioning-controls-within-cells"></a>Colocar controles en celdas

1. Seleccione el primer <xref:System.Windows.Forms.Button> control. Cambie el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> a <xref:System.Windows.Forms.DockStyle.Fill>. Tenga en cuenta que el <xref:System.Windows.Forms.Button> control se expande para rellenar la celda.

2. Seleccione uno de los otros <xref:System.Windows.Forms.Button> controles. Cambie el valor de su propiedad <xref:System.Windows.Forms.Control.Anchor%2A> a <xref:System.Windows.Forms.AnchorStyles.Right>. Tenga en cuenta que se mueve para que el borde derecho esté cerca del borde derecho de la celda. La distancia entre los bordes es la suma de los <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Margin%2A> propiedad y el panel <xref:System.Windows.Forms.Control.Padding%2A> propiedad.

3. Cambie el valor de la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> propiedad <xref:System.Windows.Forms.AnchorStyles.Right> y <xref:System.Windows.Forms.AnchorStyles.Left>. Tenga en cuenta que el control de tamaño se ajusta al ancho de la celda, con el <xref:System.Windows.Forms.Control.Margin%2A> y <xref:System.Windows.Forms.Control.Padding%2A> valores computados.

4. Repita los pasos 2 y 3 con el <xref:System.Windows.Forms.AnchorStyles.Top> y <xref:System.Windows.Forms.AnchorStyles.Bottom> estilos.

## <a name="setting-row-and-column-properties"></a>Propiedades de columna y fila de valores

Puede establecer las propiedades individuales de filas y columnas mediante el <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> y <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> colecciones.

#### <a name="to-set-row-and-column-properties"></a>Para establecer las propiedades de columna y fila

1. Seleccione el <xref:System.Windows.Forms.TableLayoutPanel> en controlar la **Diseñador de Windows Forms**.

2. En el **propiedades** windows, abra el <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> colección haciendo clic en el botón de puntos suspensivos (![los puntos suspensivos (...) en la ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la  **Columnas** entrada.

3. Seleccione la primera columna y cambie el valor de su <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> propiedad <xref:System.Windows.Forms.SizeType.AutoSize>. Haga clic en **Aceptar** para aceptar el cambio. Tenga en cuenta que el ancho de la primera columna se reduce para ajustarse a la <xref:System.Windows.Forms.Button> control. Tenga en cuenta también que el ancho de la columna no es de tamaño variable.

4. En el **propiedades** ventana, abra el <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> colección y seleccione la primera columna. Cambie el valor de su propiedad <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> a <xref:System.Windows.Forms.SizeType.Percent>. Haga clic en **Aceptar** para aceptar el cambio. Cambiar el tamaño de la <xref:System.Windows.Forms.TableLayoutPanel> el control a un mayor ancho y tenga en cuenta que el ancho de la primera columna se expande. Cambiar el tamaño de la <xref:System.Windows.Forms.TableLayoutPanel> el control a un ancho menor y tenga en cuenta que el tamaño de los botones de la primera columna se ajusta para ajustarse a la celda. Tenga en cuenta también que el ancho de la columna es de tamaño ajustable.

5. En el **propiedades** ventana, abra el <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> colección y seleccione todas las columnas enumeradas. Establezca el valor de cada <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> propiedad <xref:System.Windows.Forms.SizeType.Percent>. Haga clic en **Aceptar** para aceptar el cambio. Repita con los <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> colección.

6. Tomar uno de los controladores de tamaño de esquina y cambiar el tamaño del ancho y alto de la <xref:System.Windows.Forms.TableLayoutPanel> control. Tenga en cuenta que las filas y columnas cambian de tamaño como el <xref:System.Windows.Forms.TableLayoutPanel> los cambios de tamaño del control. Tenga en cuenta también que las filas y columnas son puede cambiar el tamaño horizontal y vertical de controladores de tamaño.

## <a name="spanning-rows-and-columns-with-a-control"></a>Abarcar filas y columnas con un Control

El <xref:System.Windows.Forms.TableLayoutPanel> control agrega nuevas propiedades a controles en tiempo de diseño. Dos de estas propiedades son `RowSpan` y `ColumnSpan`. Puede usar estas propiedades para realizar un intervalo de control más de una fila o columna.

#### <a name="to-span-rows-and-columns-with-a-control"></a>Para abarcar filas y columnas con un control

1. Seleccione el <xref:System.Windows.Forms.Button> control en la primera fila y primera columna.

2. En el **propiedades** windows, cambie el valor de la `ColumnSpan` propiedad **2**. Tenga en cuenta que el <xref:System.Windows.Forms.Button> control rellena la primera columna y la segunda columna. Tenga en cuenta también que se ha agregado una fila adicional para dar cabida a este cambio.

3. Repita el paso 2 para el `RowSpan` propiedad.

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Insertar controles mediante un doble clic en estos en el cuadro de herramientas

Para rellenar el control <xref:System.Windows.Forms.TableLayoutPanel> puede hacer doble clic en los controles del **cuadro de herramientas**.

#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>Para insertar controles mediante un doble clic en el cuadro de herramientas

1. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.

2. Haga doble clic en el icono del control <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas**. Tenga en cuenta que aparece un nuevo control de botón en el <xref:System.Windows.Forms.TableLayoutPanel> primera celda del control.

3. Haga doble clic en algunos controles más en el **cuadro de herramientas**. Tenga en cuenta que los nuevos controles aparecen de manera consecutiva en el <xref:System.Windows.Forms.TableLayoutPanel> celdas desocupadas del control. Tenga en cuenta también que el <xref:System.Windows.Forms.TableLayoutPanel> control se expande para dar cabida a los nuevos controles si no hay ninguna celda abierta está disponible.

## <a name="automatic-handling-of-overflows"></a>Control automático de desbordamientos

Cuando se insertan los controles en el <xref:System.Windows.Forms.TableLayoutPanel> control, puede quedarse sin celdas vacías para los nuevos controles. El <xref:System.Windows.Forms.TableLayoutPanel> control controla automáticamente esta situación si aumenta el número de celdas.

#### <a name="to-observe-automatic-handling-of-overflows"></a>Para observar el control automático de desbordamientos

1. Si hay celdas vacías todavía en el <xref:System.Windows.Forms.TableLayoutPanel> controlar, continuar insertándolo como nuevo <xref:System.Windows.Forms.Button> controla hasta el <xref:System.Windows.Forms.TableLayoutPanel> control está lleno.

2. Una vez el <xref:System.Windows.Forms.TableLayoutPanel> control está lleno, haga doble clic en el <xref:System.Windows.Forms.Button> icono en el **cuadro de herramientas** para insertar otro <xref:System.Windows.Forms.Button> control. Tenga en cuenta que el <xref:System.Windows.Forms.TableLayoutPanel> control crea las nuevas celdas para alojar el nuevo control. Inserte algunos controles más y observar el comportamiento de cambio de tamaño.

3. Cambie el valor de la propiedad <xref:System.Windows.Forms.TableLayoutPanel> del control <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> a <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Haga doble clic en el <xref:System.Windows.Forms.Button> icono en el **cuadro de herramientas** para insertar <xref:System.Windows.Forms.Button> controla hasta el <xref:System.Windows.Forms.TableLayoutPanel> control está lleno. Haga doble clic en el <xref:System.Windows.Forms.Button> icono en el **cuadro de herramientas** nuevo. Tenga en cuenta que recibe un mensaje de error desde el **Diseñador de Windows Forms** que le informa de que no se puede crear otras filas y columnas.

## <a name="inserting-a-control-by-drawing-its-outline"></a>Insertar un control dibujando su contorno

Puede insertar un control en un control <xref:System.Windows.Forms.TableLayoutPanel> y dibujar su contorno en una celda para especificar el tamaño.

#### <a name="to-insert-a-control-by-drawing-its-outline"></a>Para insertar un control dibujando su contorno

1. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.

2. En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.Button> . No lo arrastre hasta el formulario.

3. Mueva el puntero del mouse sobre el control <xref:System.Windows.Forms.TableLayoutPanel> . Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.Button> agregado.

4. Haga clic y mantenga presionado el botón del mouse.

5. Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.Button> . Cuando esté satisfecho con el tamaño, suelte el botón del mouse. Tenga en cuenta que el <xref:System.Windows.Forms.Button> control se crea en la celda en la que ha dibujado el esquema.

## <a name="multiple-controls-within-cells-are-not-permitted"></a>No se permiten varios controles en celdas

El <xref:System.Windows.Forms.TableLayoutPanel> control puede contener sólo un control secundario por celda.

#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>Para demostrar que no se permiten varios controles en celdas

- Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en el <xref:System.Windows.Forms.TableLayoutPanel> controlar y colóquelo en una de las celdas ocupadas. Tenga en cuenta que el <xref:System.Windows.Forms.TableLayoutPanel> control no permite quitar el <xref:System.Windows.Forms.Button> control en la celda ocupada.

## <a name="swapping-controls"></a>Intercambiar los controles

El <xref:System.Windows.Forms.TableLayoutPanel> control le permite intercambiar los controles que ocupan las dos celdas diferentes.

#### <a name="to-swap-controls"></a>Para intercambiar los controles

- Arrastre uno de los <xref:System.Windows.Forms.Button> controles de una celda ocupada y colocar en a otra celda ocupada. Tenga en cuenta que los dos controles se mueven de una celda en el otro.

## <a name="next-steps"></a>Pasos siguientes

Puede lograr un diseño complejo mediante una combinación de controles y paneles de diseño. Estas son otras sugerencias para seguir con la exploración:

- Intente cambiar el tamaño de uno de los <xref:System.Windows.Forms.Button> controles a un tamaño mayor y observe el efecto en el diseño.

- Pegue una selección de varios controles en el <xref:System.Windows.Forms.TableLayoutPanel> controlar y tenga en cuenta cómo se insertan los controles.

- Los paneles de diseño pueden contener otros paneles de diseño. Experimente colocando un control <xref:System.Windows.Forms.TableLayoutPanel> en el control existente.

- Acople el control <xref:System.Windows.Forms.TableLayoutPanel> al formulario primario. Cambie el tamaño del formulario y observe el efecto en el diseño.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Experiencia de usuario de Microsoft Windows, Official Guidelines for diseñadores y desarrolladores de interfaz de usuario. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
- [Tutorial: Creación de un formulario de Windows puede cambiar el tamaño de entrada de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))
- [Tutorial: Creación de un formulario Windows Localizable](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))
- [Procedimientos recomendados para el control TableLayoutPanel](best-practices-for-the-tablelayoutpanel-control.md)
- [Información general sobre la propiedad AutoSize](autosize-property-overview.md)
- [Cómo: Acoplar controles en Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Cómo: Delimitar controles en Windows Forms](how-to-anchor-controls-on-windows-forms.md)
- [Tutorial: Diseñar Windows controles Forms con relleno, márgenes y la propiedad AutoSize](windows-forms-controls-padding-autosize.md)
