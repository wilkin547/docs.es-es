---
title: "Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be514f435b787c770eca114d42bee5c1424a40c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a>Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste
La posición precisa de los controles del formulario es de alta prioridad para muchas aplicaciones. El Diseñador de Windows Forms ofrece muchas herramientas de diseño para lograr esto. Uno de los más importantes es la <xref:System.Windows.Forms.Design.Behavior.SnapLine> característica.  
  
 Las guías de alineación muestran exactamente dónde alinear controles con otros controles. También muestran las distancias recomendadas para los márgenes entre los controles, como se especifica en las instrucciones para la interfaz de usuario de Windows. Para obtener más información, consulte [desarrollo y diseño de la interfaz de usuario](http://go.microsoft.com/FWLink/?LinkId=83878).  
  
 Las guías de alineación facilitan a alinear los controles, precisos y profesionales apariencia y el comportamiento (apariencia y funcionamiento).  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de Windows Forms  
  
-   Espaciar y alinear controles mediante las guías de alineación  
  
-   Alinear al formulario y los márgenes de contenedor  
  
-   Alinear a controles agrupados  
  
-   Usar las guías de alineación para colocar un Control mediante su tamaño de esquematización  
  
-   Usar líneas de ajuste al arrastrar un Control desde el cuadro de herramientas  
  
-   Cambiar el tamaño de los controles mediante las guías de alineación  
  
-   Alinear una etiqueta de texto de un Control  
  
-   Uso de las guías de alineación con navegación mediante el teclado  
  
-   Líneas de ajuste y paneles de diseño  
  
-   Deshabilitar las guías de alineación  
  
 Cuando haya terminado, tendrá un conocimiento de la función de diseño desempeñada por la característica de las guías de alineación.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
1.  Cree un proyecto de aplicación basada en Windows llamado a "SnaplineExample". Para ver detalles, consulte [Cómo: Crear un nuevo proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Seleccione el formulario en el Diseñador de formularios.  
  
## <a name="spacing-and-aligning-controls-using-snaplines"></a>Espaciar y alinear controles mediante las guías de alineación  
 Las guías de alineación proporcionan una manera precisa e intuitiva para alinear los controles del formulario. Aparecen cuando se están moviendo un control o controles seleccionados cerca de una posición que se alinee con otro control o conjunto de controles. La selección se "ajustará" a la posición sugerida cuando mueve más allá de los demás controles.  
  
#### <a name="to-arrange-controls-using-snaplines"></a>Para organizar los controles mediante las guías de alineación  
  
1.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** al formulario.  
  
2.  Mover el <xref:System.Windows.Forms.Button> control a la esquina inferior derecha del formulario. Tenga en cuenta las líneas de ajuste que aparecen como el <xref:System.Windows.Forms.Button> control acerca de los bordes inferior y derecho del formulario. Estas guías de alineación muestran la distancia recomendada entre los bordes del control y el formulario.  
  
3.  Mover el <xref:System.Windows.Forms.Button> control alrededor de los bordes del formulario y tenga en cuenta dónde deben aparecer las líneas de ajuste. Cuando haya terminado, mueva el <xref:System.Windows.Forms.Button> control cerca del centro del formulario.  
  
4.  Arrastre otra <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** al formulario.  
  
5.  Mover el segundo <xref:System.Windows.Forms.Button> controlar hasta que esté casi nivel con la primera. Tenga en cuenta la Guía de alineación que aparece en la línea base del texto de ambos botones y observe que el control que está moviendo se ajusta a una posición que está exactamente al mismo nivel que el otro control.  
  
6.  Mover el segundo <xref:System.Windows.Forms.Button> controlar hasta que se coloca directamente encima de la primera. Tenga en cuenta las líneas de ajuste que aparecen a lo largo de los bordes izquierdos y derecho de ambos botones y tenga en cuenta que el control que está moviendo se ajusta a una posición que está alineada exactamente con el otro control.  
  
7.  Seleccione uno de los <xref:System.Windows.Forms.Button> controla y muévalo cerca del otro, hasta que tocan casi. Tenga en cuenta la Guía de alineación que aparece entre ellos. Esta es la distancia recomendada entre los bordes de los controles. Tenga en cuenta que el control que está moviendo se ajusta a esta posición.  
  
8.  Arrastre dos <xref:System.Windows.Forms.Panel> controla desde el **cuadro de herramientas** al formulario.  
  
9. Mueva una de las <xref:System.Windows.Forms.Panel> controla hasta que esté casi nivel con la primera. Tenga en cuenta las líneas de ajuste que aparecen a lo largo de los bordes superior e inferior de los dos controles y tenga en cuenta que el control que está moviendo se ajusta a una posición que está exactamente al mismo nivel que el otro control.  
  
## <a name="aligning-to-form-and-container-margins"></a>Alinear al formulario y los márgenes de contenedor  
 Las guías de alineación le ayudan a alinear los controles a los márgenes del contenedor y del formulario de una manera coherente.  
  
#### <a name="to-align-controls-to-form-and-container-margins"></a>Para alinear los controles a los márgenes del contenedor y del formulario  
  
1.  Seleccione uno de los <xref:System.Windows.Forms.Button> controla y muévalo cerca del borde derecho del formulario hasta que aparezca una línea de ajuste. Distancia de la Guía de alineación desde el borde derecho es la suma del control <xref:System.Windows.Forms.Control.Margin%2A> propiedad y el formulario <xref:System.Windows.Forms.Control.Padding%2A> valores de propiedad.  
  
> [!NOTE]
>  Si el formulario <xref:System.Windows.Forms.Control.Padding%2A> propiedad está establecida en 0,0,0,0, el Diseñador de Windows Forms proporciona un sombreado al formulario <xref:System.Windows.Forms.Control.Padding%2A> valor de 9,9,9,9. Para invalidar este comportamiento, asigne un valor distinto de 0,0,0,0.  
  
1.  Cambie el valor de la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Margin%2A> propiedad expandiendo el <xref:System.Windows.Forms.Control.Margin%2A> entrada en el **propiedades** ventana y estableciendo el <xref:System.Windows.Forms.Padding.All%2A> propiedad en 0. Para obtener más información, consulte [Tutorial: diseñar controles de Windows Forms con relleno, márgenes y la propiedad AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md).  
  
2.  Mover el <xref:System.Windows.Forms.Button> control cerca del borde derecho del formulario hasta que aparezca una línea de ajuste. Esta distancia ahora viene dada por el valor de la forma <xref:System.Windows.Forms.Control.Padding%2A> propiedad.  
  
3.  Arrastre un <xref:System.Windows.Forms.GroupBox> controlar desde la **cuadro de herramientas** al formulario.  
  
4.  Cambie el valor de la <xref:System.Windows.Forms.GroupBox> del control <xref:System.Windows.Forms.Control.Padding%2A> propiedad expandiendo el <xref:System.Windows.Forms.Control.Padding%2A> entrada en el **propiedades** ventana y estableciendo el <xref:System.Windows.Forms.Padding.All%2A> propiedad a 10.  
  
5.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en el <xref:System.Windows.Forms.GroupBox> control.  
  
6.  Mover el <xref:System.Windows.Forms.Button> control cerca del borde derecho de la <xref:System.Windows.Forms.GroupBox> controlar hasta que aparezca una línea de ajuste. Mover el <xref:System.Windows.Forms.Button> control dentro de la <xref:System.Windows.Forms.GroupBox> control y tenga en cuenta dónde deben aparecer las líneas de ajuste.  
  
## <a name="aligning-to-grouped-controls"></a>Alinear a controles agrupados  
 Puede utilizar las líneas de ajuste para alinear controles agrupados así como controles dentro de un <xref:System.Windows.Forms.GroupBox> control.  
  
#### <a name="to-align-to-grouped-controls"></a>Para alinear los controles agrupados  
  
1.  Seleccione dos de los controles en el formulario. Mover la selección y tenga en cuenta las líneas de ajuste que aparecen entre la selección y los demás controles.  
  
2.  Arrastre un <xref:System.Windows.Forms.GroupBox> controlar desde la **cuadro de herramientas** al formulario.  
  
3.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en el <xref:System.Windows.Forms.GroupBox> control.  
  
4.  Seleccione uno de los <xref:System.Windows.Forms.Button> controla y para desplazarse por el <xref:System.Windows.Forms.GroupBox> control. Tenga en cuenta las líneas de ajuste que aparecen en los bordes de la <xref:System.Windows.Forms.GroupBox> control. Tenga en cuenta las líneas de ajuste que aparecen en los bordes de la <xref:System.Windows.Forms.Button> control que está contenida en el <xref:System.Windows.Forms.GroupBox> control. Controles que son elementos secundarios de un control contenedor también admiten las guías de alineación.  
  
## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a>Usar las guías de alineación para colocar un Control mediante su tamaño de esquematización  
 Ayuda de las guías de alineación de alineación de los controles cuando se coloca por primera vez en un formulario.  
  
#### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a>Utilizar las guías de alineación para colocar un control mediante su tamaño de esquematización  
  
1.  En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.Button> . No lo arrastre hasta el formulario.  
  
2.  Mueva el puntero del mouse sobre la superficie de diseño del formulario. Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.Button> agregado. Tenga en cuenta las líneas de ajuste que sugieren las posiciones alineadas para el <xref:System.Windows.Forms.Button> control.  
  
3.  Haga clic y mantenga presionado el botón del mouse.  
  
4.  Arrastre el puntero del mouse alrededor del formulario. Tenga en cuenta que se dibuja un esquema, que indica la posición y el tamaño del control.  
  
5.  Arrastre el puntero hasta que quede alineado con otro control en el formulario. Tenga en cuenta que una guía de alineación aparece para indicar la alineación.  
  
6.  Suelte el botón del mouse. El control se crea en la posición y el tamaño indicado por el esquema.  
  
## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a>Usar líneas de ajuste al arrastrar un Control desde el cuadro de herramientas  
 Ayuda de las guías de alineación de alineación de los controles cuando se arrastra desde el **cuadro de herramientas** al formulario.  
  
#### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a>Para usar las guías de alineación al arrastrar un control desde el cuadro de herramientas  
  
1.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en el formulario, pero no suelte el botón del mouse.  
  
2.  Mueva el puntero del mouse sobre la superficie de diseño del formulario. Tenga en cuenta que el puntero cambia para indicar la posición en la que el nuevo <xref:System.Windows.Forms.Button> se creará el control.  
  
3.  Arrastre el puntero del mouse alrededor del formulario. Tenga en cuenta las líneas de ajuste que sugieren las posiciones alineadas para el <xref:System.Windows.Forms.Button> control. Buscar una posición que se alinea con otros controles.  
  
4.  Suelte el botón del mouse. El control se crea en la posición indicada por las líneas de ajuste.  
  
## <a name="resizing-controls-using-snaplines"></a>Cambiar el tamaño de los controles mediante las guías de alineación  
 Las guías de alineación le ayudan a alinear los controles cuando cambia el tamaño de ellos.  
  
#### <a name="to-resize-a-control-using-snaplines"></a>Para cambiar el tamaño de un control mediante las guías de alineación  
  
1.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** al formulario.  
  
2.  Cambiar el tamaño de la <xref:System.Windows.Forms.Button> control manteniendo sujeto uno de la esquina controladores de tamaño y arrastrar. Para obtener más información, consulte [Cómo: cambiar el tamaño de controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md).  
  
3.  Arrastre el controlador de tamaño hasta que uno de los <xref:System.Windows.Forms.Button> bordes del control se alinee con otro control. Tenga en cuenta que aparece una guía de alineación. Tenga en cuenta también que el controlador de tamaño se ajusta a la posición indicada por la Guía de alineación.  
  
4.  Cambiar el tamaño de la <xref:System.Windows.Forms.Button> controlar en diferentes direcciones y alinee el controlador de tamaño a los distintos controles. Tenga en cuenta cómo aparecen las líneas de ajuste en distintas orientaciones para indicar la alineación.  
  
## <a name="aligning-a-label-to-a-controls-text"></a>Alinear una etiqueta de texto de un Control  
 Algunos controles proporcionan una línea de ajuste para alinear otros controles al texto mostrado.  
  
#### <a name="to-align-a-label-to-a-controls-text"></a>Para alinear una etiqueta al texto de un control  
  
1.  Arrastre un <xref:System.Windows.Forms.TextBox> controlar desde la **cuadro de herramientas** al formulario. Al colocar el <xref:System.Windows.Forms.TextBox> controlar hasta el formulario, haga clic en el glifo de etiqueta inteligente y seleccione el **establece el texto en textBox1** opción. Para obtener más información, consulte [Tutorial: realizar comunes tareas utilizando etiquetas inteligentes en controles de Windows Forms](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md).  
  
2.  Arrastre un <xref:System.Windows.Forms.Label> controlar desde la **cuadro de herramientas** al formulario.  
  
3.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Label> a `true`. Tenga en cuenta que los bordes del control se ajustan para adaptarse al texto de presentación.  
  
4.  Mover el <xref:System.Windows.Forms.Label> control a la izquierda de la <xref:System.Windows.Forms.TextBox> controlar, por lo que se alinea con el borde inferior de la <xref:System.Windows.Forms.TextBox> control. Tenga en cuenta la Guía de alineación que aparece a lo largo de los bordes de la parte inferior de los dos controles.  
  
5.  Mover el <xref:System.Windows.Forms.Label> control ligeramente hacia arriba, hasta que el <xref:System.Windows.Forms.Label> texto y <xref:System.Windows.Forms.TextBox> se alinea el texto. Tenga en cuenta la Guía de alineación con estilo diferente que aparece, que indica cuándo se alinean los campos de texto de los dos controles.  
  
## <a name="using-snaplines-with-keyboard-navigation"></a>Uso de las guías de alineación con navegación mediante el teclado  
 Ayuda de las guías de alineación de alineación de los controles cuando está organizándolos mediante las teclas de desplazamiento.  
  
#### <a name="to-use-snaplines-with-keyboard-navigation"></a>Para usar las guías de alineación con navegación mediante el teclado  
  
1.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** al formulario. Colóquelo en la esquina superior izquierda del formulario.  
  
2.  Presione CTRL + flecha abajo. Tenga en cuenta que el control se desplaza hacia abajo en el formulario a la primera posición de alineación horizontal disponible.  
  
3.  Presione CTRL + flecha abajo hasta que el control alcanza la parte inferior del formulario. Tenga en cuenta las posiciones que ocupa cuando se desplaza hacia abajo en el formulario.  
  
4.  Presione CTRL + flecha derecha. Tenga en cuenta que el control se desplace por el formulario a la primera posición de alineación vertical disponible.  
  
5.  Presione CTRL + flecha derecha hasta que el control alcance el lado del formulario. Tenga en cuenta las posiciones que ocupa cuando se desplaza horizontalmente por el formulario.  
  
6.  Mueva el control alrededor del formulario con una combinación de teclas de dirección. Tenga en cuenta las posiciones que ocupa el control y las líneas de ajuste que lo acompañan.  
  
7.  Presione MAYÚS + cualquier tecla de dirección para cambiar el tamaño de la <xref:System.Windows.Forms.Button> control en incrementos de un píxel.  
  
8.  Presione CTRL + MAYÚS + cualquier tecla de dirección para cambiar el tamaño de la <xref:System.Windows.Forms.Button> control en incrementos de guía de alineación.  
  
## <a name="snaplines-and-layout-panels"></a>Líneas de ajuste y paneles de diseño  
 Las guías de alineación se deshabilitan dentro de los paneles de diseño.  
  
#### <a name="to-selectively-disable-snaplines"></a>Para deshabilitar de forma selectiva las guías de alineación  
  
1.  Arrastre un <xref:System.Windows.Forms.TableLayoutPanel> controlar desde la **cuadro de herramientas** al formulario.  
  
2.  Haga doble clic en el icono del control <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas**. Tenga en cuenta que aparece un nuevo control de botón en el <xref:System.Windows.Forms.TableLayoutPanel> primera celda del control.  
  
3.  Haga doble clic en el <xref:System.Windows.Forms.Button> icono de control en el **cuadro de herramientas** dos veces más. Esto deja una celda vacía en el <xref:System.Windows.Forms.TableLayoutPanel> control.  
  
4.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en la celda vacía de la <xref:System.Windows.Forms.TableLayoutPanel> control. Tenga en cuenta que no las guías de alineación aparecen.  
  
5.  Arrastre el <xref:System.Windows.Forms.Button> controlar fuera de la <xref:System.Windows.Forms.TableLayoutPanel> controlar y para desplazarse por el <xref:System.Windows.Forms.TableLayoutPanel> control. Tenga en cuenta que las guías de alineación aparecen de nuevo.  
  
## <a name="disabling-snaplines"></a>Deshabilitar las guías de alineación  
 Las guías de alineación están activados de forma predeterminada. Puede deshabilitar las guías de alineación de forma selectiva o puede deshabilitar en el entorno de diseño.  
  
#### <a name="to-selectively-disable-snaplines"></a>Para deshabilitar de forma selectiva las guías de alineación  
  
-   Presione la tecla ALT y mientras mueve un control alrededor del formulario.  
  
     Tenga en cuenta que no las guías de alineación aparecen y el control no se ajusta a ninguna posible posición de alineación.  
  
#### <a name="to-disable-snaplines-in-the-design-environment"></a>Para deshabilitar las guías de alineación en el entorno de diseño  
  
1.  Desde el **herramientas** menú, abra el **opciones** cuadro de diálogo. Abra el cuadro de diálogo del Diseñador de Windows Forms. Para obtener más información, consulte [General, el Diseñador de Windows Forms, el cuadro de diálogo Opciones](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834).  
  
2.  Seleccione el **General** nodo. En el **modo de diseño** sección, cambie la selección de **las guías de alineación** a **SnapToGrid**.  
  
3.  Haga clic en Aceptar para aplicar la configuración.  
  
4.  Seleccione un control en el formulario y para desplazarse por los demás controles. Tenga en cuenta que no aparecen las guías de alineación.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Las guías de alineación proporcionan una forma intuitiva de alinear controles en el formulario. Estas son otras sugerencias para seguir con la exploración:  
  
-   Intente anidamiento un <xref:System.Windows.Forms.GroupBox> control dentro de otra <xref:System.Windows.Forms.GroupBox> control. Lugar un <xref:System.Windows.Forms.Button> control dentro del elemento secundario <xref:System.Windows.Forms.GroupBox> control y otro dentro del elemento primario <xref:System.Windows.Forms.GroupBox> control. Mover el <xref:System.Windows.Forms.Button> controles alrededor para ver cómo las líneas de ajuste cruzan los límites del contenedor.  
  
-   Crear una columna de <xref:System.Windows.Forms.TextBox> controles y una columna correspondiente de <xref:System.Windows.Forms.Label> controles. Establezca el valor de la <xref:System.Windows.Forms.Label> controles <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad `true`. Usar las guías de alineación para mover el <xref:System.Windows.Forms.Label> controla de manera que su texto mostrado se alinee con el texto en el <xref:System.Windows.Forms.TextBox> controles.  
  
 Para obtener información acerca del diseño de interfaz de usuario de Windows, consulte el libro *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and diseñadores* Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>  
 [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Tutorial: Diseñar controles de Windows Forms con relleno, márgenes y la propiedad AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)  
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
