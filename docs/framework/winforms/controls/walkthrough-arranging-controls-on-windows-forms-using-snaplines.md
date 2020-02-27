---
title: Organizar controles mediante líneas de ajuste
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0b68a70b55cbf03d480fd388a637a4caf78b6eaa
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628805"
---
# <a name="walkthrough-arrange-controls-on-windows-forms-using-snaplines"></a>Tutorial: organizar controles en Windows Forms mediante líneas de ajuste

La posición precisa de los controles del formulario es de alta prioridad para muchas aplicaciones. El Diseñador de Windows Forms ofrece muchas herramientas de diseño para lograr esto. Una de las más importantes es la característica <xref:System.Windows.Forms.Design.Behavior.SnapLine>.

Las guías de alineación muestran exactamente dónde alinear los controles con otros controles. También se muestran las distancias recomendadas para los márgenes entre controles, como se especifica en las instrucciones de la [interfaz de usuario de Windows](/windows/win32/uxguide/guidelines).

Las guías de alineación facilitan la alineación de los controles, para una apariencia y un comportamiento más nítidos y profesionales (aspecto y funcionamiento).

## <a name="create-the-project"></a>Creación del proyecto

1. En Visual Studio, cree un proyecto de aplicación basado en Windows denominado "SnaplineExample".

2. Seleccione el formulario en el Diseñador de Windows Forms.

## <a name="space-and-align-controls"></a>Controlar espacio y alinear controles

Las guías de alineación proporcionan una manera precisa e intuitiva de alinear los controles en el formulario. Aparecen al mover un control o controles seleccionados cerca de una posición que se alinearía con otro control o conjunto de controles. La selección se "ajustará" a la posición sugerida cuando la mueva más allá de los demás controles.

### <a name="to-arrange-controls-using-snaplines"></a>Para organizar los controles mediante las guías de alineación

1. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.

2. Mueva el control <xref:System.Windows.Forms.Button> a la esquina inferior derecha del formulario. Tenga en cuenta que las líneas de ajuste que aparecen como control <xref:System.Windows.Forms.Button> se aproximan a los bordes inferior y derecho del formulario. Estas guías de alineación muestran la distancia recomendada entre los bordes del control y el formulario.

3. Mueva el control de <xref:System.Windows.Forms.Button> alrededor de los bordes del formulario y observe dónde aparecen las guías de alineación. Cuando haya terminado, mueva el control <xref:System.Windows.Forms.Button> cerca del centro del formulario.

4. Arrastre otro control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** hasta el formulario.

5. Mueva el segundo control <xref:System.Windows.Forms.Button> hasta que esté casi nivelado con el primero. Observe la línea de ajuste que aparece en la línea de base de texto de ambos botones y tenga en cuenta que el control que está moviendo se ajusta a una posición que está exactamente nivelada con el otro control.

6. Mueva el segundo control <xref:System.Windows.Forms.Button> hasta que se coloque directamente encima de la primera. Observe las líneas de ajuste que aparecen a lo largo de los bordes izquierdo y derecho de ambos botones y tenga en cuenta que el control que está moviendo se ajusta a una posición que está exactamente alineada con el otro control.

7. Seleccione uno de los controles de <xref:System.Windows.Forms.Button> y muévalo cerca del otro, hasta que estén casi tocando. Tenga en cuenta la línea de ajuste que aparece entre ellas. Esta distancia es la distancia recomendada entre los bordes de los controles. Tenga en cuenta también que el control que está moviendo se ajusta a esta posición.

8. Arrastre dos controles <xref:System.Windows.Forms.Panel> desde el **cuadro de herramientas** hasta el formulario.

9. Mueva uno de los controles de <xref:System.Windows.Forms.Panel> hasta que esté casi nivelado con el primero. Observe las líneas de ajuste que aparecen a lo largo de los bordes superior e inferior de ambos controles y tenga en cuenta que el control que está moviendo se ajusta a una posición que está exactamente nivelada con el otro control.

## <a name="align-to-form-and-container-margins"></a>Alinear con los márgenes de formulario y contenedor

Las guías de alineación le ayudan a alinear los controles con los márgenes de formulario y contenedor de una manera coherente.

1. Seleccione uno de los controles de <xref:System.Windows.Forms.Button> y muévalo cerca del borde derecho del formulario hasta que aparezca una guía de alineación. La distancia de la guía de alineación desde el borde derecho es la suma de la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control y los valores de propiedad <xref:System.Windows.Forms.Control.Padding%2A> del formulario.

   > [!NOTE]
   > Si la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del formulario se establece en 0, 0, 0, el Diseñador de Windows Forms proporciona al formulario un valor de <xref:System.Windows.Forms.Control.Padding%2A> sombreado de 9, 9, 9, 9. Para invalidar este comportamiento, asigne un valor distinto de 0, 0, 0,0.

2. Para cambiar el valor de la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control <xref:System.Windows.Forms.Button>, expanda la entrada <xref:System.Windows.Forms.Control.Margin%2A> en la ventana **propiedades** y establezca la propiedad <xref:System.Windows.Forms.Padding.All%2A> en 0. Para obtener más información, vea [Tutorial: diseñar Windows Forms controles con relleno, márgenes y la propiedad AutoSize](windows-forms-controls-padding-autosize.md).

3. Mueva el control <xref:System.Windows.Forms.Button> cerca del borde derecho del formulario hasta que aparezca una guía de alineación. Esta distancia se proporciona ahora mediante el valor de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del formulario.

4. Arrastre un control <xref:System.Windows.Forms.GroupBox> del **cuadro de herramientas** al formulario.

5. Para cambiar el valor de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control <xref:System.Windows.Forms.GroupBox>, expanda la entrada <xref:System.Windows.Forms.Control.Padding%2A> en la ventana **propiedades** y establezca la propiedad <xref:System.Windows.Forms.Padding.All%2A> en 10.

6. Arrastre un control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** al control <xref:System.Windows.Forms.GroupBox>.

7. Mueva el control <xref:System.Windows.Forms.Button> cerca del borde derecho del control <xref:System.Windows.Forms.GroupBox> hasta que aparezca una guía de alineación. Mueva el control <xref:System.Windows.Forms.Button> dentro del control <xref:System.Windows.Forms.GroupBox> y observe dónde aparecen las guías de alineación.

## <a name="align-to-grouped-controls"></a>Alinear con controles agrupados

Puede usar las líneas de ajuste para alinear los controles agrupados, así como los controles de un control de <xref:System.Windows.Forms.GroupBox>.

1. Seleccione dos de los controles en el formulario. Mueva la selección alrededor de y observe las guías de alineación que aparecen entre su selección y los demás controles.

2. Arrastre un control <xref:System.Windows.Forms.GroupBox> del **cuadro de herramientas** al formulario.

3. Arrastre un control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** al control <xref:System.Windows.Forms.GroupBox>.

4. Seleccione uno de los controles de <xref:System.Windows.Forms.Button> y muévalo alrededor del control <xref:System.Windows.Forms.GroupBox>. Observe las líneas de ajuste que aparecen en los bordes del control <xref:System.Windows.Forms.GroupBox>. Tenga en cuenta también las líneas de ajuste que aparecen en los bordes del control <xref:System.Windows.Forms.Button> que contiene el control <xref:System.Windows.Forms.GroupBox>. Los controles que son elementos secundarios de un control contenedor también admiten las guías de alineación.

## <a name="use-snaplines-to-place-a-control-by-outlining-its-size"></a>Usar líneas de ajuste para colocar un control Esquematizando su tamaño

1. En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.Button> . No lo arrastre hasta el formulario.

2. Mueva el puntero del mouse sobre la superficie de diseño del formulario. Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.Button> agregado. Tenga en cuenta también las líneas de ajuste que aparecen para sugerir las posiciones alineadas del control <xref:System.Windows.Forms.Button>.

3. Haga clic y mantenga presionado el botón del mouse.

4. Arrastre el puntero del mouse alrededor del formulario. Observe que se dibuja un esquema, que indica la posición y el tamaño del control.

5. Arrastre el puntero hasta que se alinee con otro control del formulario. Observe que aparece una guía de alineación para indicar la alineación.

6. Suelte el botón del mouse (ratón). El control se crea en la posición y el tamaño indicados por el esquema.

## <a name="use-snaplines-when-dragging-a-control-from-the-toolbox"></a>Usar líneas de ajuste al arrastrar un control desde el cuadro de herramientas

1. Arrastre un control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** hasta el formulario, pero no suelte el botón del mouse.

2. Mueva el puntero del mouse sobre la superficie de diseño del formulario. Tenga en cuenta que el puntero cambia para indicar la posición en la que se creará el nuevo control de <xref:System.Windows.Forms.Button>.

3. Arrastre el puntero del mouse alrededor del formulario. Observe las líneas de ajuste que aparecen para sugerir las posiciones alineadas del control <xref:System.Windows.Forms.Button>. Buscar una posición que está alineada con otros controles.

4. Suelte el botón del mouse (ratón). El control se crea en la posición indicada por las líneas de ajuste.

## <a name="resize-a-control-using-snaplines"></a>Cambiar el tamaño de un control mediante las guías de alineación

1. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.

2. Cambie el tamaño del control de <xref:System.Windows.Forms.Button> mediante la captura de uno de los controladores de tamaño de esquina y arrastre. Para obtener más información, consulte [Cómo: cambiar el tamaño de los controles en Windows Forms](how-to-resize-controls-on-windows-forms.md).

3. Arrastre el controlador de tamaño hasta que uno de los bordes del control <xref:System.Windows.Forms.Button> esté alineado con otro control. Observe que aparece una guía de alineación. Tenga en cuenta también que el controlador de tamaño se ajusta a la posición indicada por la línea de ajuste.

4. Cambiar el tamaño del control de <xref:System.Windows.Forms.Button> en distintas direcciones y alinear el controlador de tamaño con diferentes controles. Observe cómo las guías de alineación aparecen en diversas orientaciones para indicar la alineación.

## <a name="align-a-label-to-a-controls-text"></a>Alinear una etiqueta con el texto de un control

1. Arrastre un control <xref:System.Windows.Forms.TextBox> del **cuadro de herramientas** al formulario. Cuando coloque el control <xref:System.Windows.Forms.TextBox> en el formulario, haga clic en el glifo de etiqueta inteligente y seleccione la opción **establecer texto en TextBox1** . Para obtener más información, vea [Tutorial: realizar tareas comunes con las acciones del diseñador](perform-common-tasks-design-actions.md).

2. Arrastre un control <xref:System.Windows.Forms.Label> del **cuadro de herramientas** al formulario.

3. Cambie el valor de la propiedad <xref:System.Windows.Forms.Label> del control <xref:System.Windows.Forms.Control.AutoSize%2A> a `true`. Tenga en cuenta que los bordes del control se ajustan para ajustarse al texto que se va a mostrar.

4. Mueva el control <xref:System.Windows.Forms.Label> a la izquierda del control <xref:System.Windows.Forms.TextBox>, de modo que se alinee con el borde inferior del control <xref:System.Windows.Forms.TextBox>. Observe la guía de alineación que aparece a lo largo de los bordes inferiores de los dos controles.

5. Mueva el control de <xref:System.Windows.Forms.Label> ligeramente hacia arriba, hasta que el texto de la <xref:System.Windows.Forms.Label> y el texto de <xref:System.Windows.Forms.TextBox> estén alineados. Observe la línea de ajuste de estilo diferente que aparece, que indica cuándo se alinean los campos de texto de ambos controles.

## <a name="use-snaplines-with-keyboard-navigation"></a>Usar líneas de ajuste con la navegación mediante el teclado

1. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario. Colóquelo en la esquina superior izquierda del formulario.

2. Presione **Ctrl**+**flecha abajo**. Tenga en cuenta que el control baja el formulario hasta la primera posición de alineación horizontal disponible.

3. Presione **Ctrl**+**flecha abajo** hasta que el control llegue a la parte inferior del formulario. Tenga en cuenta las posiciones que ocupa a medida que baja el formulario.

4. Presione **Ctrl**+**flecha derecha**. Tenga en cuenta que el control se desplaza por el formulario hasta la primera posición de alineación vertical disponible.

5. Presione **Ctrl**+**flecha derecha** hasta que el control llegue al lado del formulario. Tenga en cuenta las posiciones que ocupa a medida que se mueve por el formulario.

6. Mueva el control alrededor del formulario con una combinación de teclas de dirección. Tenga en cuenta las posiciones que ocupa el control y las guías de alineación que las acompañan.

7. Presione **mayús**+**teclas de dirección** para cambiar el tamaño del control de <xref:System.Windows.Forms.Button> por incrementos de un píxel.

8. Presione **Ctrl**+**MAYÚS**+**teclas de flecha** para cambiar el tamaño del control <xref:System.Windows.Forms.Button> en incrementos de la línea de ajuste.

## <a name="selectively-disable-snaplines"></a>Deshabilitar de forma selectiva las líneas de ajuste

1. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.

2. Haga doble clic en el icono del control <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas**. Observe que aparece un nuevo control de botón en la primera celda del control <xref:System.Windows.Forms.TableLayoutPanel>.

3. Haga doble clic en el icono control de <xref:System.Windows.Forms.Button> en el **cuadro de herramientas** dos veces más. Esto deja una celda vacía en el control <xref:System.Windows.Forms.TableLayoutPanel>.

4. Arrastre un control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** a la celda vacía del control <xref:System.Windows.Forms.TableLayoutPanel>. Tenga en cuenta que no aparece ninguna alineación.

5. Arrastre el control <xref:System.Windows.Forms.Button> fuera del control <xref:System.Windows.Forms.TableLayoutPanel> y muévalo alrededor del control <xref:System.Windows.Forms.TableLayoutPanel>. Tenga en cuenta que las líneas de ajuste vuelven a aparecer.

## <a name="disable-snaplines"></a>Deshabilitar líneas de ajuste

Presione la tecla **Alt** y mueva un control alrededor del formulario.

No aparecen las líneas de ajuste y el control no se ajusta a ninguna de las posibles posiciones de alineación.

### <a name="to-disable-snaplines-in-the-design-environment"></a>Para deshabilitar las líneas de ajuste en el entorno de diseño

1. En el menú **herramientas** , abra el cuadro de diálogo **Opciones** . Seleccione **Diseñador de Windows Forms**.

2. Seleccione el nodo **General** . En la sección **modo de diseño** , cambie la selección de las líneas de **ajuste** a **SnapToGrid**.

3. Seleccione **Aceptar** para aplicar la configuración.

4. Seleccione un control en el formulario y muévalo alrededor de los demás controles. Tenga en cuenta que las líneas de ajuste no aparecen.

## <a name="next-steps"></a>Pasos siguientes

Las guías de alineación ofrecen un medio intuitivo de alinear los controles en el formulario. Algunas sugerencias de investigación adicional son:

- Intente anidar un control <xref:System.Windows.Forms.GroupBox> dentro de otro control <xref:System.Windows.Forms.GroupBox>. Coloque un control <xref:System.Windows.Forms.Button> dentro del control secundario <xref:System.Windows.Forms.GroupBox> y otro dentro del control <xref:System.Windows.Forms.GroupBox> primario. Mueva los controles del <xref:System.Windows.Forms.Button> para ver cómo las guías de alineación cruzan los límites del contenedor.

- Cree una columna de controles de <xref:System.Windows.Forms.TextBox> y una columna correspondiente de controles de <xref:System.Windows.Forms.Label>. Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> de los controles <xref:System.Windows.Forms.Label> en `true`. Use las líneas de ajuste para desplazar los controles de <xref:System.Windows.Forms.Label> de modo que el texto que se muestra se alinee con el texto de los controles de <xref:System.Windows.Forms.TextBox>.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Diseñar controles de Windows Forms con relleno, márgenes y la propiedad AutoSize](windows-forms-controls-padding-autosize.md)
