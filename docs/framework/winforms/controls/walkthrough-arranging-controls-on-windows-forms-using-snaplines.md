---
title: "Tutorial: Organizar controles en formularios Windows Forms mediante l&#237;neas de ajuste | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], organizar con líneas de ajuste"
  - "SnapLine (clase), tutoriales"
  - "líneas de ajuste, organizar controles de formularios Windows Forms"
  - "controles de Windows Forms, organizar"
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Tutorial: Organizar controles en formularios Windows Forms mediante l&#237;neas de ajuste
La posición precisa de los controles en el formulario es de alta prioridad para muchas aplicaciones.  El Diseñador de Windows Forms ofrece muchas herramientas de diseño para realizarlo.  Una de las más importantes es la característica <xref:System.Windows.Forms.Design.Behavior.SnapLine>.  
  
 Las líneas de ajuste muestran precisamente dónde alinear controles con otros controles.  También le muestran las distancias recomendadas para los márgenes entre los controles, tal como está especificado en las Instrucciones de la interfaz de usuario de Windows.  Para obtener información detallada, vea [User Interface Design and Development](http://go.microsoft.com/FWLink/?LinkId=83878).  
  
 Las líneas de ajuste facilitan la alineación de los controles, para obtener una apariencia y comportamiento nítido y profesional.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de formularios Windows Forms  
  
-   Espaciar y alinear controles mediante guías de alineación  
  
-   Alinear a márgenes del contenedor y formulario  
  
-   Alinear a controles agrupados  
  
-   Utilizar líneas de ajuste para colocar un control esquematizando el tamaño  
  
-   Utilizar líneas de ajuste al arrastrar un control en el Cuadro de herramientas  
  
-   Cambiar el tamaño de los controles utilizando guías de alineación  
  
-   Alinear una etiqueta a un texto de control  
  
-   Utilizar líneas de ajuste con la navegación con el teclado  
  
-   Líneas de ajuste y paneles de diseño  
  
-   Deshabilitar líneas de ajuste  
  
 Al finalizar, podrá entender el rol que desempeña esta importante característica de líneas de ajuste en el diseño.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### Para crear el proyecto  
  
1.  Cree un proyecto de aplicación basada en Windows llamado a "SnaplineExample."  Para obtener información detallada, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Seleccione el formulario en el diseñador de formularios.  
  
## Espaciar y alinear controles mediante guías de alineación  
 Las líneas de ajuste ofrecen una manera precisa e intuitiva de alinear controles en el formulario.  Aparecen cuando está moviendo un control o controles seleccionados cerca de una posición que podría alinear con otro control o conjunto de controles.  La selección se "ajustará" a la posición sugerida cuando la mueve más allá de los demás controles.  
  
#### Para organizar controles mediante las líneas de ajuste  
  
1.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al formulario.  
  
2.  Mueva el control <xref:System.Windows.Forms.Button> a la esquina inferior derecha del formulario.  Observe las líneas de ajuste que aparecen cuando el control <xref:System.Windows.Forms.Button> se acerca los bordes inferior y derecho del control.  Estas líneas de ajuste muestran la distancia recomendada entre los bordes del control y el formulario.  
  
3.  Mueva el control <xref:System.Windows.Forms.Button> alrededor de los bordes del formulario y observe dónde aparecen las líneas de ajuste.  Cuando finalice, mueva el control <xref:System.Windows.Forms.Button> cerca del centro del formulario.  
  
4.  Arrastre otro control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al formulario.  
  
5.  Mueva el segundo control <xref:System.Windows.Forms.Button> hasta que esté casi al mismo nivel que el primero.  Observe la línea de ajuste que aparece en la línea base del texto de ambos botones, y observe que el control que está moviendo se ajusta a la posición que está exactamente al mismo nivel que el otro control.  
  
6.  Mueva el segundo control <xref:System.Windows.Forms.Button> hasta que se coloque directamente sobre el primero.  Observe la línea de ajuste que aparece en los bodes derecho e izquierdo de ambos botones, y observe que el control que está moviendo se ajusta a la posición que está alineada exactamente con el otro control.  
  
7.  Seleccione uno de los controles <xref:System.Windows.Forms.Button> y muévalo cerca del otro, hasta que casi se toquen.  Observe la línea de ajuste que aparece entre ellos.  Ésta es la distancia recomendada entre los bordes de los controles.  También tenga en cuenta que el control que está moviendo se ajusta a esta posición.  
  
8.  Arrastre dos controles <xref:System.Windows.Forms.Panel> desde el **Cuadro de herramientas** al formulario.  
  
9. Mueva uno de los controles <xref:System.Windows.Forms.Panel> hasta que esté prácticamente al mismo nivel que el primero.  Observe la línea de ajuste que aparece junto a los bordes superior e inferior de ambos botones, y observe que el control que está moviendo se ajusta a la posición que está exactamente al mismo nivel que el otro control.  
  
## Alinear a márgenes del contenedor y formulario  
 Las líneas de ajuste le ayudan a alinear los controles a los márgenes del contenedor y del formulario de una manera coherente.  
  
#### Para alinear controles a los márgenes del contenedor y del formulario  
  
1.  Seleccione uno de los controles <xref:System.Windows.Forms.Button> y muévalo cerca del borde derecho del formulario hasta que aparezca una línea de ajuste.  La distancia de la línea de ajuste del borde derecho es la suma de los valores de propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control y los valores de propiedad <xref:System.Windows.Forms.Control.Padding%2A> del formulario.  
  
> [!NOTE]
>  Si la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del formulario se establece en 0,0,0,0, el Diseñador de Windows Forms proporciona al formulario el valor 9,9,9,9 de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> sombreada.  Para invalidar este comportamiento, asigne un valor distinto de 0,0,0,0.  
  
1.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control <xref:System.Windows.Forms.Button> expandiendo la entrada <xref:System.Windows.Forms.Control.Margin%2A> en la ventana **Propiedades** y estableciendo la propiedad <xref:System.Windows.Forms.Padding.All%2A> en 0.  Para obtener información detallada, vea [Tutorial: Diseñar controles de formularios Windows Forms con relleno, márgenes y la propiedad AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md).  
  
2.  Mueva el control <xref:System.Windows.Forms.Button> cerca del borde derecho del formulario hasta que aparezca una línea de ajuste.  El valor de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del formulario proporciona ahora esta distancia.  
  
3.  Arrastre un control <xref:System.Windows.Forms.GroupBox> desde el **Cuadro de herramientas** al formulario.  
  
4.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control <xref:System.Windows.Forms.GroupBox> expandiendo la entrada <xref:System.Windows.Forms.Control.Padding%2A> en la ventana **Propiedades** y estableciendo la propiedad <xref:System.Windows.Forms.Padding.All%2A> en 10.  
  
5.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al control <xref:System.Windows.Forms.GroupBox>.  
  
6.  Mueva el control <xref:System.Windows.Forms.Button> cerca del borde derecho del formulario del control <xref:System.Windows.Forms.GroupBox> hasta que aparezca una línea de ajuste.  Mueva el control <xref:System.Windows.Forms.Button> dentro del control <xref:System.Windows.Forms.GroupBox> y observe dónde aparecen las líneas de ajuste.  
  
## Alinear a controles agrupados  
 Puede utilizar las líneas de ajuste para alinear controles agrupados así como a controles dentro de un control <xref:System.Windows.Forms.GroupBox>.  
  
#### Para alinear a los controles agrupados  
  
1.  Seleccione dos de los controles en el formulario.  Mueva la selección alrededor y observe las líneas de ajuste que aparecen entre la selección y los demás controles.  
  
2.  Arrastre un control <xref:System.Windows.Forms.GroupBox> desde el **Cuadro de herramientas** al formulario.  
  
3.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al control <xref:System.Windows.Forms.GroupBox>.  
  
4.  Seleccione uno de los controles <xref:System.Windows.Forms.Button> y muévalo alrededor del control <xref:System.Windows.Forms.GroupBox>.  Observe las líneas de ajuste que aparecen en los bordes del control <xref:System.Windows.Forms.GroupBox>.  También observe las líneas de ajuste que aparecen en los bordes del control <xref:System.Windows.Forms.Button> contenido en el control <xref:System.Windows.Forms.GroupBox>.  Los controles secundarios de un control contenedor también admiten líneas de ajuste.  
  
## Utilizar líneas de ajuste para colocar un control esquematizando el tamaño  
 Las líneas de ajuste le ayudan a alinear los controles cuando los coloca por primera vez en un formulario.  
  
#### Para utilizar líneas de ajuste para colocar un control esquematizando su tamaño  
  
1.  En el **Cuadro de herramientas**, haga clic en el icono de control <xref:System.Windows.Forms.Button>.  No lo arrastre hacia el formulario.  
  
2.  Mueva el puntero del mouse sobre la superficie de diseño del formulario.  Observe que el puntero cambia a una forma de cruz con el icono de control <xref:System.Windows.Forms.Button> adjuntado.  Observe también las líneas de ajuste que sugieren las posiciones alineadas para el control <xref:System.Windows.Forms.Button>.  
  
3.  Haga clic y mantenga presionado el botón del mouse.  
  
4.  Arrastre el puntero del mouse alrededor del formulario.  Observe que se dibuja un contorno, indicando la posición y el tamaño del control.  
  
5.  Arrastre el puntero hasta que alinee con otro control en el formulario.  Observe que aparece una línea de ajuste para indicar la alineación.  
  
6.  Suelte el botón del mouse.  Se crea el control en la posición y el tamaño indicado por el contorno.  
  
## Utilizar líneas de ajuste al arrastrar un control en el Cuadro de herramientas  
 Las líneas de ajuste le ayudan a alinear los controles cuando los arrastra del **Cuadro de herramientas** al formulario.  
  
#### Para utilizar las líneas de ajuste al arrastrar un control desde el Cuadro de herramientas  
  
1.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al formulario, pero no suelte el botón del mouse.  
  
2.  Mueva el puntero del mouse sobre la superficie de diseño del formulario.  Observe que el puntero cambia para indicar la posición en la que se creará el nuevo control <xref:System.Windows.Forms.Button>.  
  
3.  Arrastre el puntero del mouse alrededor del formulario.  Observe las líneas de ajuste que sugieren las posiciones alineadas para el control <xref:System.Windows.Forms.Button>.  Encuentre una posición que se alinee con otros controles.  
  
4.  Suelte el botón del mouse.  El control se crea en la posición indicada por las líneas de ajuste.  
  
## Cambiar el tamaño de los controles utilizando guías de alineación  
 Las guías de alineación le ayudan a alinear los controles cuando cambia su tamaño.  
  
#### Para cambiar el tamaño de un control mediante las líneas de ajuste  
  
1.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al formulario.  
  
2.  Cambie el tamaño del control <xref:System.Windows.Forms.Button> manteniendo sujeto uno de los cuadros de tamaño de esquina y arrastrándolo.  Para obtener información detallada, vea [Cómo: Cambiar el tamaño de los controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md).  
  
3.  Arrastre el cuadro de tamaño hasta que uno de los bordes de control <xref:System.Windows.Forms.Button> se alinee con otro control.  Observe que aparece una línea de ajuste.  También observe que el cuadro de tamaño se ajusta a la posición indicada por la línea de ajuste.  
  
4.  Cambie el tamaño del control <xref:System.Windows.Forms.Button> en diferentes direcciones y alinee el cuadro de tamaño a los distintos controles.  Observe cómo aparecen las guías de alineación en distintas orientaciones para indicar la alineación.  
  
## Alinear una etiqueta a un texto de control  
 Algunos controles proporcionan una línea de ajuste para alinear otros controles al texto mostrado.  
  
#### Para alinear una etiqueta al texto de un control  
  
1.  Arrastre un control <xref:System.Windows.Forms.TextBox> desde el **Cuadro de herramientas** hasta el formulario.  Cuando coloca el control <xref:System.Windows.Forms.TextBox> en el formulario, haga clic en el glifo de la etiqueta inteligente y seleccione la opción **Establecer el texto en textBox1**.  Para obtener información detallada, vea [Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md).  
  
2.  Arrastre un control <xref:System.Windows.Forms.Label> desde el **Cuadro de herramientas** hasta el formulario.  
  
3.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Label> a `true`.  Observe que los bordes de control se ajustan para adaptarse el texto de la presentación.  
  
4.  Mueva el control <xref:System.Windows.Forms.Label> a la izquierda del control <xref:System.Windows.Forms.TextBox>, para que se alinee con el borde inferior del control <xref:System.Windows.Forms.TextBox>.  Observe la línea de ajuste que aparece a lo largo del borde inferior de los dos controles.  
  
5.  Mueva el control <xref:System.Windows.Forms.Label> ligeramente hacia arriba, hasta que el texto <xref:System.Windows.Forms.Label> y el texto <xref:System.Windows.Forms.TextBox> estén alineados.  Observe la línea de ajuste con estilo diferente que aparece, que indica cuándo se alinean los campos de texto de ambos controles.  
  
## Utilizar líneas de ajuste con la navegación con el teclado  
 Las líneas de ajuste le ayudan a alinear los controles cuando está organizándolos mediante las teclas de dirección del teclado.  
  
#### Para utilizar las líneas de ajuste con navegación mediante el teclado  
  
1.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al formulario.  Colóquelo en la esquina superior izquierda del formulario.  
  
2.  Presione CTRL\+FLECHA ABAJO.  Observe que el control se desplaza hacia abajo por el formulario hasta la primera posición de la alineación horizontal disponible.  
  
3.  Presione CTRL\+FLECHA ABAJO hasta que el control alcance la parte inferior del formulario.  Observe la posición que ocupa cuando se desplaza hacia abajo por el formulario.  
  
4.  Presione CTRL\+FLECHA DERECHA.  Observe que el control se desplaza horizontalmente por el formulario hasta la primera posición de la alineación vertical disponible.  
  
5.  Presione CTRL\+FLECHA DERECHA hasta que el control alcance el lado del formulario.  Observe la posición que ocupa cuando se desplaza horizontalmente por el formulario.  
  
6.  Mueva el control alrededor del formulario con una combinación de teclas de dirección.  Tenga en cuenta las posiciones que ocupa el control así como las de las líneas de ajuste que lo acompañan.  
  
7.  Presione cualquier tecla de dirección \+ MAYÚS para cambiar el tamaño del control <xref:System.Windows.Forms.Button> mediante incrementos de un píxel.  
  
8.  Presione la tecla de dirección de CTRL\+MAYÚS \+cualquier tecla de dirección para cambiar el tamaño del control <xref:System.Windows.Forms.Button> en incrementos de línea de ajuste.  
  
## Líneas de ajuste y paneles de diseño  
 Las líneas de ajuste se deshabilitan dentro de los paneles de diseño.  
  
#### Para deshabilitar selectivamente las líneas de ajuste  
  
1.  Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> desde el **Cuadro de herramientas** al formulario.  
  
2.  Haga doble clic en el icono de control <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas**.  Observe que aparece un nuevo control de botón en la primera celda del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
3.  Haga doble clic dos veces más en el icono del control <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas**.  Esta opción deja una celda vacía en el control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
4.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** a la celda vacía del control <xref:System.Windows.Forms.TableLayoutPanel>.  Observe que no aparece ninguna línea de ajuste.  
  
5.  Arrastre el control <xref:System.Windows.Forms.Button> fuera del control <xref:System.Windows.Forms.TableLayoutPanel> y muévalo alrededor del control <xref:System.Windows.Forms.TableLayoutPanel>.  Observe que las líneas de ajuste aparecen de nuevo.  
  
## Deshabilitar líneas de ajuste  
 Las líneas de ajuste están activadas de manera predeterminada.  Puede deshabilitar selectivamente las líneas de ajuste o deshabilitarlas en el entorno de diseño.  
  
#### Para deshabilitar selectivamente las líneas de ajuste  
  
-   Presione la tecla ALT mientras mueve un control alrededor del formulario.  
  
     Observe que no aparece ninguna línea de ajuste y que el control no se ajusta a ninguna posible posición de alineación.  
  
#### Para deshabilitar las líneas de ajuste en el entorno de diseño  
  
1.  En el menú **Herramientas**, abra el cuadro de diálogo **Opciones**.  Abra el cuadro de diálogo Diseñador de Windows Forms.  Para obtener información detallada, vea [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/es-es/8dd170af-72f0-4212-b04b-034ceee92834).  
  
2.  Seleccione el nodo **General**.  En la sección **Modo diseño**, cambie la selección de **Líneas de ajuste** a **AjustarALaCuadrícula**.  
  
3.  Haga clic en Aceptar para aplicar la configuración.  
  
4.  Seleccione un control en su formulario y muévalo alrededor de los demás controles.  Observe que las líneas de ajuste no aparecen.  
  
## Pasos siguientes  
 Las líneas de ajuste proporcionan una forma intuitiva de alinear los controles en el formulario.  Para una exploración más a fondo, pruebe estas sugerencias:  
  
-   Pruebe a anidar un control <xref:System.Windows.Forms.GroupBox> dentro de otro control <xref:System.Windows.Forms.GroupBox>.  Coloque un control <xref:System.Windows.Forms.Button> dentro del control <xref:System.Windows.Forms.GroupBox> secundario y otro dentro del control <xref:System.Windows.Forms.GroupBox> principal.  Mueva los controles <xref:System.Windows.Forms.Button> para ver cómo se cruzan las líneas de ajuste con los límites del contenedor.  
  
-   Cree una columna de controles <xref:System.Windows.Forms.TextBox> y una columna correspondiente de controles <xref:System.Windows.Forms.Label>.  Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> de los controles <xref:System.Windows.Forms.Label> en `true`.  Utilice las líneas de ajuste para mover los <xref:System.Windows.Forms.Label>controles para que el texto mostrado se alinee con el texto en los controles <xref:System.Windows.Forms.TextBox>.  
  
 Para obtener información sobre el diseño de la interfaz de usuario de Windows, vea el libro *Microsoft Windows User Experience: Official Guidelines for User Interface Developers and Designers*, Redmond, WA: Microsoft Press, 1999.  \(USBN: 0\-7356\-0566\-1\).  
  
## Vea también  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>   
 [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Tutorial: Diseñar controles de formularios Windows Forms con relleno, márgenes y la propiedad AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)   
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)