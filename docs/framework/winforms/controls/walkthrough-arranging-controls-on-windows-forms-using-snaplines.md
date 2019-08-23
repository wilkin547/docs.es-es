---
title: 'Tutorial: Organizar controles en formularios Windows Forms mediante guías de alineación'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: 8ac1ba6b8121aabea3c992ca5b943f231fc19ce2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950071"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a>Tutorial: Organizar controles en formularios Windows Forms mediante guías de alineación
La posición precisa de los controles del formulario es de alta prioridad para muchas aplicaciones. El Diseñador de Windows Forms ofrece muchas herramientas de diseño para lograr esto. Una de las más importantes es la <xref:System.Windows.Forms.Design.Behavior.SnapLine> característica.

 Las guías de alineación muestran exactamente dónde alinear los controles con otros controles. También se muestran las distancias recomendadas para los márgenes entre controles, como se especifica en las instrucciones de la interfaz de usuario de Windows. Para obtener más información, consulte [diseño y desarrollo](https://go.microsoft.com/FWLink/?LinkId=83878)de la interfaz de usuario.

 Las guías de alineación facilitan la alineación de los controles, para una apariencia y un comportamiento más nítidos y profesionales (aspecto y funcionamiento).

 Las tareas ilustradas en este tutorial incluyen:

- Crear un proyecto de Windows Forms

- Espaciado y alineación de controles mediante las guías de alineación

- Alinear a los márgenes de formulario y contenedor

- Alinear con controles agrupados

- Usar líneas de ajuste para colocar un control Esquematizando su tamaño

- Usar líneas de ajuste al arrastrar un control desde el cuadro de herramientas

- Cambiar el tamaño de los controles mediante líneas de ajuste

- Alinear una etiqueta con el texto de un control

- Usar líneas de ajuste con la navegación mediante el teclado

- Guías de alineación y paneles de diseño

- Deshabilitar las guías de alineación

 Cuando haya terminado, tendrá conocimientos sobre el rol de diseño que desempeña la característica de guías de alineación.

## <a name="creating-the-project"></a>Crear el proyecto
 El primer paso es crear el proyecto y configurar el formulario.

### <a name="to-create-the-project"></a>Para crear el proyecto

1. Cree un proyecto de aplicación basada en Windows llamado "SnaplineExample" (**archivo** > **nuevo** > **proyecto** >  **C# visual** o **Visual Basic** > **clásico**  > **Aplicación de Windows Forms**de escritorio).

2. Seleccione el formulario en el diseñador de formularios.

## <a name="spacing-and-aligning-controls-using-snaplines"></a>Espaciado y alineación de controles mediante las guías de alineación
 Las guías de alineación proporcionan una manera precisa e intuitiva de alinear los controles en el formulario. Aparecen al mover un control o controles seleccionados cerca de una posición que se alinearía con otro control o conjunto de controles. La selección se "ajustará" a la posición sugerida cuando la mueva más allá de los demás controles.

### <a name="to-arrange-controls-using-snaplines"></a>Para organizar los controles mediante las guías de alineación

1. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.

2. Mueva el <xref:System.Windows.Forms.Button> control a la esquina inferior derecha del formulario. Tenga en cuenta que las líneas de <xref:System.Windows.Forms.Button> ajuste que aparecen como control se aproximan a los bordes inferior y derecho del formulario. Estas guías de alineación muestran la distancia recomendada entre los bordes del control y el formulario.

3. Mueva el <xref:System.Windows.Forms.Button> control alrededor de los bordes del formulario y observe dónde aparecen las guías de alineación. Cuando haya terminado, mueva el <xref:System.Windows.Forms.Button> control cerca del centro del formulario.

4. Arrastre otro <xref:System.Windows.Forms.Button> control desde el **cuadro de herramientas** hasta el formulario.

5. Mueva el segundo <xref:System.Windows.Forms.Button> control hasta que esté casi nivelado con el primero. Observe la línea de ajuste que aparece en la línea de base de texto de ambos botones y tenga en cuenta que el control que está moviendo se ajusta a una posición que está exactamente nivelada con el otro control.

6. Mueva el segundo <xref:System.Windows.Forms.Button> control hasta que se coloque directamente encima de la primera. Observe las líneas de ajuste que aparecen a lo largo de los bordes izquierdo y derecho de ambos botones y tenga en cuenta que el control que está moviendo se ajusta a una posición que está exactamente alineada con el otro control.

7. Seleccione uno de los <xref:System.Windows.Forms.Button> controles y muévalo cerca del otro, hasta que estén casi tocando. Tenga en cuenta la línea de ajuste que aparece entre ellas. Esta distancia es la distancia recomendada entre los bordes de los controles. Tenga en cuenta también que el control que está moviendo se ajusta a esta posición.

8. Arrastre dos <xref:System.Windows.Forms.Panel> controles desde el **cuadro de herramientas** hasta el formulario.

9. Mueva uno de los <xref:System.Windows.Forms.Panel> controles hasta que esté casi nivelado con el primero. Observe las líneas de ajuste que aparecen a lo largo de los bordes superior e inferior de ambos controles y tenga en cuenta que el control que está moviendo se ajusta a una posición que está exactamente nivelada con el otro control.

## <a name="aligning-to-form-and-container-margins"></a>Alinear a los márgenes de formulario y contenedor
 Las guías de alineación le ayudan a alinear los controles con los márgenes de formulario y contenedor de una manera coherente.

### <a name="to-align-controls-to-form-and-container-margins"></a>Para alinear controles a los márgenes de formulario y contenedor

1. Seleccione uno de los <xref:System.Windows.Forms.Button> controles y muévalo cerca del borde derecho del formulario hasta que aparezca una guía de alineación. La distancia de la guía de alineación desde el borde derecho es la suma de <xref:System.Windows.Forms.Control.Margin%2A> la propiedad del control y <xref:System.Windows.Forms.Control.Padding%2A> los valores de propiedad del formulario.

> [!NOTE]
> Si el <xref:System.Windows.Forms.Control.Padding%2A> valor de <xref:System.Windows.Forms.Control.Padding%2A> la propiedad del formulario se establece en 0, 0, 0, 0, el diseñador de Windows Forms proporciona el formato con el que se ha prevalecido 9, 9, 9, 9. Para invalidar este comportamiento, asigne un valor distinto de 0, 0, 0,0.

1. Para cambiar el valor de <xref:System.Windows.Forms.Button> la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control, expanda la <xref:System.Windows.Forms.Control.Margin%2A> entrada en la ventana **propiedades** y <xref:System.Windows.Forms.Padding.All%2A> establezca la propiedad en 0. Para obtener más información [, consulte Tutorial: Diseñar Windows Forms controles con relleno, márgenes y la propiedad](windows-forms-controls-padding-autosize.md)AutoSize.

2. Mueva el <xref:System.Windows.Forms.Button> control cerca del borde derecho del formulario hasta que aparezca una guía de alineación. Esta distancia se proporciona ahora mediante el valor de la propiedad del <xref:System.Windows.Forms.Control.Padding%2A> formulario.

3. Arrastre un control <xref:System.Windows.Forms.GroupBox> del **cuadro de herramientas** al formulario.

4. Para cambiar el valor de <xref:System.Windows.Forms.GroupBox> la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control, expanda la <xref:System.Windows.Forms.Control.Padding%2A> entrada en la ventana **propiedades** y <xref:System.Windows.Forms.Padding.All%2A> establezca la propiedad en 10.

5. Arrastre un <xref:System.Windows.Forms.Button> control del <xref:System.Windows.Forms.GroupBox> **cuadro de herramientas** al control.

6. Mueva el <xref:System.Windows.Forms.Button> control cerca del borde derecho <xref:System.Windows.Forms.GroupBox> del control hasta que aparezca una guía de alineación. Mueva el <xref:System.Windows.Forms.Button> control dentro del <xref:System.Windows.Forms.GroupBox> control y observe dónde aparecen las guías de alineación.

## <a name="aligning-to-grouped-controls"></a>Alinear con controles agrupados
 Puede usar las líneas de ajuste para alinear los controles agrupados, así <xref:System.Windows.Forms.GroupBox> como los controles de un control.

### <a name="to-align-to-grouped-controls"></a>Para alinear los controles agrupados

1. Seleccione dos de los controles en el formulario. Mueva la selección alrededor de y observe las guías de alineación que aparecen entre su selección y los demás controles.

2. Arrastre un control <xref:System.Windows.Forms.GroupBox> del **cuadro de herramientas** al formulario.

3. Arrastre un <xref:System.Windows.Forms.Button> control del <xref:System.Windows.Forms.GroupBox> **cuadro de herramientas** al control.

4. Seleccione uno de los <xref:System.Windows.Forms.Button> controles y muévalo alrededor del <xref:System.Windows.Forms.GroupBox> control. Observe las líneas de ajuste que aparecen en los bordes <xref:System.Windows.Forms.GroupBox> del control. Tenga en cuenta también las líneas de ajuste que aparecen en <xref:System.Windows.Forms.Button> los bordes del control que contiene <xref:System.Windows.Forms.GroupBox> el control. Los controles que son elementos secundarios de un control contenedor también admiten las guías de alineación.

## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a>Usar líneas de ajuste para colocar un control Esquematizando su tamaño
 Las guías de alineación le ayudan a alinear los controles la primera vez que se colocan en un formulario.

### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a>Usar líneas de ajuste para colocar un control Esquematizando su tamaño

1. En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.Button> . No lo arrastre hasta el formulario.

2. Mueva el puntero del mouse sobre la superficie de diseño del formulario. Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.Button> agregado. Tenga en cuenta también las líneas de ajuste que aparecen para sugerir <xref:System.Windows.Forms.Button> las posiciones alineadas del control.

3. Haga clic y mantenga presionado el botón del mouse.

4. Arrastre el puntero del mouse alrededor del formulario. Observe que se dibuja un esquema, que indica la posición y el tamaño del control.

5. Arrastre el puntero hasta que se alinee con otro control del formulario. Observe que aparece una guía de alineación para indicar la alineación.

6. Suelte el botón del mouse. El control se crea en la posición y el tamaño indicados por el esquema.

## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a>Usar líneas de ajuste al arrastrar un control desde el cuadro de herramientas
 Las guías de alineación le ayudan a alinear los controles al arrastrarlos desde el **cuadro de herramientas** hasta el formulario.

### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a>Para usar las líneas de ajuste al arrastrar un control desde el cuadro de herramientas

1. Arrastre un <xref:System.Windows.Forms.Button> control desde el **cuadro de herramientas** hasta el formulario, pero no suelte el botón del mouse.

2. Mueva el puntero del mouse sobre la superficie de diseño del formulario. Tenga en cuenta que el puntero cambia para indicar la posición en la <xref:System.Windows.Forms.Button> que se creará el nuevo control.

3. Arrastre el puntero del mouse alrededor del formulario. Observe las líneas de ajuste que aparecen para sugerir las posiciones <xref:System.Windows.Forms.Button> alineadas del control. Buscar una posición que está alineada con otros controles.

4. Suelte el botón del mouse. El control se crea en la posición indicada por las líneas de ajuste.

## <a name="resizing-controls-using-snaplines"></a>Cambiar el tamaño de los controles mediante líneas de ajuste
 Las guías de alineación le ayudan a alinear los controles a medida que cambia su tamaño.

### <a name="to-resize-a-control-using-snaplines"></a>Para cambiar el tamaño de un control mediante las guías de alineación

1. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.

2. Cambie el tamaño <xref:System.Windows.Forms.Button> del control mediante la captura de uno de los controladores de tamaño de esquina y arrastre. Para obtener más detalles, vea [Cómo: Cambiar el tamaño de los](how-to-resize-controls-on-windows-forms.md)controles en Windows Forms.

3. Arrastre el controlador de tamaño hasta que uno <xref:System.Windows.Forms.Button> de los bordes del control se alinee con otro control. Observe que aparece una guía de alineación. Tenga en cuenta también que el controlador de tamaño se ajusta a la posición indicada por la línea de ajuste.

4. Cambiar el tamaño <xref:System.Windows.Forms.Button> del control en diferentes direcciones y alinear el controlador de tamaño con diferentes controles. Observe cómo las guías de alineación aparecen en diversas orientaciones para indicar la alineación.

## <a name="aligning-a-label-to-a-controls-text"></a>Alinear una etiqueta con el texto de un control
 Algunos controles ofrecen una línea de ajuste para alinear otros controles con el texto mostrado.

### <a name="to-align-a-label-to-a-controls-text"></a>Para alinear una etiqueta con el texto de un control

1. Arrastre un control <xref:System.Windows.Forms.TextBox> del **cuadro de herramientas** al formulario. Al colocar el <xref:System.Windows.Forms.TextBox> control en el formulario, haga clic en el glifo de etiqueta inteligente y seleccione la opción **establecer texto en TextBox1** . Para obtener más información [, consulte Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles](performing-common-tasks-using-smart-tags-on-wf-controls.md)de Windows Forms.

2. Arrastre un control <xref:System.Windows.Forms.Label> del **cuadro de herramientas** al formulario.

3. Cambie el valor de la propiedad <xref:System.Windows.Forms.Label> del control <xref:System.Windows.Forms.Control.AutoSize%2A> a `true`. Tenga en cuenta que los bordes del control se ajustan para ajustarse al texto que se va a mostrar.

4. Mueve el <xref:System.Windows.Forms.Label> control a la izquierda <xref:System.Windows.Forms.TextBox> del control, por lo que está alineado con <xref:System.Windows.Forms.TextBox> el borde inferior del control. Observe la guía de alineación que aparece a lo largo de los bordes inferiores de los dos controles.

5. Mueva el <xref:System.Windows.Forms.Label> control ligeramente hacia arriba, hasta <xref:System.Windows.Forms.Label> que el texto <xref:System.Windows.Forms.TextBox> y el texto estén alineados. Observe la línea de ajuste de estilo diferente que aparece, que indica cuándo se alinean los campos de texto de ambos controles.

## <a name="using-snaplines-with-keyboard-navigation"></a>Usar líneas de ajuste con la navegación mediante el teclado
 Las guías de alineación le ayudan a alinear los controles cuando los organiza con las teclas de dirección del teclado.

### <a name="to-use-snaplines-with-keyboard-navigation"></a>Para usar líneas de ajuste con la navegación mediante el teclado

1. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario. Colóquelo en la esquina superior izquierda del formulario.

2. Presione CTRL + flecha abajo. Tenga en cuenta que el control baja el formulario hasta la primera posición de alineación horizontal disponible.

3. Presione CTRL + flecha abajo hasta que el control llegue a la parte inferior del formulario. Tenga en cuenta las posiciones que ocupa a medida que baja el formulario.

4. Presione CTRL + flecha derecha. Tenga en cuenta que el control se desplaza por el formulario hasta la primera posición de alineación vertical disponible.

5. Presione CTRL + flecha derecha hasta que el control llegue al lado del formulario. Tenga en cuenta las posiciones que ocupa a medida que se mueve por el formulario.

6. Mueva el control alrededor del formulario con una combinación de teclas de dirección. Tenga en cuenta las posiciones que ocupa el control y las guías de alineación que las acompañan.

7. Presione Mayús + cualquier tecla de dirección para cambiar el <xref:System.Windows.Forms.Button> tamaño del control en incrementos de un píxel.

8. Presione Ctrl + Mayús + cualquier tecla de dirección para cambiar el <xref:System.Windows.Forms.Button> tamaño del control en incrementos de la línea de ajuste.

## <a name="snaplines-and-layout-panels"></a>Guías de alineación y paneles de diseño
 Las guías de alineación están deshabilitadas dentro de los paneles de diseño.

### <a name="to-selectively-disable-snaplines"></a>Para deshabilitar de forma selectiva las guías de alineación

1. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.

2. Haga doble clic en el icono del control <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas**. Observe que aparece un nuevo control de botón en <xref:System.Windows.Forms.TableLayoutPanel> la primera celda del control.

3. Haga doble clic en <xref:System.Windows.Forms.Button> el icono de control en el **cuadro de herramientas** dos veces más. Esto deja una celda vacía en el <xref:System.Windows.Forms.TableLayoutPanel> control.

4. Arrastre un <xref:System.Windows.Forms.Button> control del **cuadro de herramientas** a la celda <xref:System.Windows.Forms.TableLayoutPanel> vacía del control. Tenga en cuenta que no aparece ninguna alineación.

5. Arrastre el <xref:System.Windows.Forms.Button> control fuera <xref:System.Windows.Forms.TableLayoutPanel> del control y muévalo alrededor del <xref:System.Windows.Forms.TableLayoutPanel> control. Tenga en cuenta que las líneas de ajuste vuelven a aparecer.

## <a name="disabling-snaplines"></a>Deshabilitar las guías de alineación
 Las guías de alineación están activadas de forma predeterminada. Puede deshabilitar las líneas de ajuste de forma selectiva o deshabilitarlas en el entorno de diseño.

### <a name="to-selectively-disable-snaplines"></a>Para deshabilitar de forma selectiva las guías de alineación

- Presione la tecla ALT y mueva un control alrededor del formulario.

     Tenga en cuenta que no aparecen las líneas de ajuste y el control no se ajusta a ninguna de las posibles posiciones de alineación.

### <a name="to-disable-snaplines-in-the-design-environment"></a>Para deshabilitar las líneas de ajuste en el entorno de diseño

1. En el menú **herramientas** , abra el cuadro de diálogo **Opciones** . Abra el cuadro de diálogo Diseñador de Windows Forms. Para obtener más información, consulte [General, diseñador de Windows Forms, opciones (cuadro de diálogo)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).

2. Seleccione el nodo **General** . En la sección **modo de diseño** , cambie la selección de las líneas de **ajuste** a **SnapToGrid**.

3. Haga clic en Aceptar para aplicar la configuración.

4. Seleccione un control en el formulario y muévalo alrededor de los demás controles. Tenga en cuenta que las líneas de ajuste no aparecen.

## <a name="next-steps"></a>Pasos siguientes
 Las guías de alineación ofrecen un medio intuitivo de alinear los controles en el formulario. Estas son otras sugerencias para seguir con la exploración:

- Intente anidar un <xref:System.Windows.Forms.GroupBox> control dentro de <xref:System.Windows.Forms.GroupBox> otro control. Coloque un <xref:System.Windows.Forms.Button> control dentro del control <xref:System.Windows.Forms.GroupBox> secundario y otro dentro del control primario <xref:System.Windows.Forms.GroupBox> . Mueva los <xref:System.Windows.Forms.Button> controles para ver cómo las líneas de ajuste cruzan los límites del contenedor.

- Cree una columna de <xref:System.Windows.Forms.TextBox> controles y una columna de <xref:System.Windows.Forms.Label> controles correspondiente. Establezca el valor de la <xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad de los controles `true`en. Use las líneas de ajuste <xref:System.Windows.Forms.Label> para desplazar los controles de modo que el texto que <xref:System.Windows.Forms.TextBox> se muestra esté alineado con el texto de los controles.

 Para obtener información sobre el diseño de la interfaz de usuario de Windows, vea el libro *experiencia del usuario de Microsoft Windows, directrices oficiales para desarrolladores y diseñadores de la interfaz de usuario* Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Diseñar Windows Forms controles con relleno, márgenes y la propiedad AutoSize](windows-forms-controls-padding-autosize.md)
- [Organizar controles en formularios Windows Forms](arranging-controls-on-windows-forms.md)
