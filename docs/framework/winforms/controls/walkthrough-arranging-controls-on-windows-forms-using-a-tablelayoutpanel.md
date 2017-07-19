---
title: "Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel | Microsoft Docs"
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
  - "controles [Windows Forms], organizar con TableLayoutPanel"
  - "TableLayoutPanel (control) [Windows Forms], tutoriales"
  - "controles de Windows Forms, organizar"
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel
Algunas aplicaciones precisan un formulario con un diseño que se organice a sí mismo apropiadamente a medida que cambia de tamaño o cuando el contenido cambia de tamaño.  Cuando necesita un diseño dinámico y no desea controlar explícitamente los eventos <xref:System.Windows.Forms.Control.Layout> en el código, considere utilizar un panel de diseño.  
  
 El control <xref:System.Windows.Forms.FlowLayoutPanel> y el control <xref:System.Windows.Forms.TableLayoutPanel> proporcionan formas intuitivas de organizar los controles en el formulario.  Ambos controles proporcionan una capacidad automática y configurable de controlar las posiciones relativas de los controles secundarios contenidos en ellos, y ambos ofrecen características de diseño dinámicas en tiempo de ejecución, de tal forma que puede cambiar el tamaño y la posición de los controles secundarios a medida que cambian las dimensiones del formulario principal.  Los paneles de diseño se pueden anidar dentro de paneles de diseño, para habilitar la realización de interfaces de usuario más complejas.  
  
 El control <xref:System.Windows.Forms.FlowLayoutPanel> organiza su contenido en una dirección específica de flujo horizontal o vertical.  Su contenido puede ajustarse desde una fila o una columna a la siguiente.  Como alternativa, su contenido puede recortarse en lugar de ajustarse.  Para obtener más información, vea [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
 <xref:System.Windows.Forms.TableLayoutPanel> organiza su contenido en una cuadrícula, proporcionando una funcionalidad similar al elemento \<table\> de HTML.  El control <xref:System.Windows.Forms.TableLayoutPanel> permite colocar los controles en una cuadrícula de diseño sin exigirle la especificación precisa de la posición de cada control individual.  Las celdas se organizan en filas y columnas y éstas pueden tener distintos tamaños.  Las celdas se pueden combinar en las filas y columnas.  Las celdas pueden contener cualquier elemento que contenga un formulario y comportarse en la mayoría de los casos como contenedores.  
  
 El control <xref:System.Windows.Forms.TableLayoutPanel> también proporciona en tiempo de ejecución una función de cambio de tamaño proporcional, por lo que su diseño puede cambiar fácilmente cuando se cambia el tamaño del formulario.  De esta forma, el control <xref:System.Windows.Forms.TableLayoutPanel> está muy bien adaptado a propósitos tales como formularios de entrada de datos y aplicaciones localizadas.  Para obtener más información, vea [Walkthrough: Creating a Resizable Windows Form for Data Entry](http://msdn.microsoft.com/es-es/e193b4fc-912a-4917-b036-b76c7a6f58ab) y [Walkthrough: Creating a Localizable Windows Form](http://msdn.microsoft.com/es-es/c5240b6e-aaca-4286-9bae-778a416edb9c).  
  
 En general, no debería utilizar un control <xref:System.Windows.Forms.TableLayoutPanel> como un contenedor para todo el diseño.  Utilice los controles <xref:System.Windows.Forms.TableLayoutPanel> para proporcionar las funciones de cambio el tamaño proporcional a las distintas partes del diseño.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de formularios Windows Forms  
  
-   Organizar los controles en filas y columnas  
  
-   Configurar las propiedades de las filas y columnas  
  
-   Abarcar filas y columnas con un control  
  
-   Control automático de desbordamientos  
  
-   Insertar controles haciendo doble clic en ellos en el Cuadro de herramientas  
  
-   Insertar un control dibujando su contorno  
  
-   Reasignar los controles existentes a un elemento primario diferente  
  
 Al finalizar, podrá entender el rol que desempeñan estas importantes características de diseño.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### Para crear el proyecto  
  
1.  Cree un proyecto de aplicación para Windows denominado "TableLayoutPanelExample."  Para obtener más información, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Seleccione el formulario en el **Diseñador de Windows** **Forms**.  
  
## Organizar los controles en filas y columnas  
 El control <xref:System.Windows.Forms.TableLayoutPanel> le permite organizar fácilmente los controles en filas y columnas.  
  
#### Para organizar los controles en filas y columnas mediante TableLayoutPanel  
  
1.  Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> desde el **Cuadro de herramientas** al formulario.  Observe que, de forma predeterminada, el control <xref:System.Windows.Forms.TableLayoutPanel> tiene cuatro celdas.  
  
2.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al control <xref:System.Windows.Forms.TableLayoutPanel> y colóquelo en una de las celdas.  Observe que el control <xref:System.Windows.Forms.Button> se crea dentro de la celda que ha seleccionado.  
  
3.  Arrastre tres controles <xref:System.Windows.Forms.Button> más desde el **Cuadro de herramientas** al control <xref:System.Windows.Forms.TableLayoutPanel>, para que cada celda contenga un botón.  
  
4.  Mantenga sujeto el cuadro de tamaño vertical entre las dos columnas y muévalo a la izquierda.  Observe que los controles <xref:System.Windows.Forms.Button> de la primera columna cambian su tamaño a un ancho menor, mientras que el tamaño de los controles <xref:System.Windows.Forms.Button> de la segunda columna no se ha modificado.  
  
5.  Mantenga sujeto el cuadro de tamaño vertical entre las dos columnas y muévalo a la derecha.  Observe que los controles <xref:System.Windows.Forms.Button> de la primera columna vuelven a su tamaño original, mientras que los controles <xref:System.Windows.Forms.Button> de la segunda columna se mueven a la derecha.  
  
6.  Mueva de arriba abajo el cuadro de tamaño horizontal para ver su efecto sobre los controles del panel.  
  
## Colocar los controles dentro de las celdas utilizando el acoplamiento y el anclaje  
 El comportamiento del anclaje de los controles secundarios en un control <xref:System.Windows.Forms.TableLayoutPanel> difiere del comportamiento de otros controles contenedor.  El comportamiento del acoplamiento de los controles secundarios es igual al de los otros controles contenedor.  
  
#### Colocar controles dentro de celdas  
  
1.  Seleccione el primer control <xref:System.Windows.Forms.Button>.  Cambie el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> a <xref:System.Windows.Forms.DockStyle>.  Observe que el control <xref:System.Windows.Forms.Button> se expande para rellenar la celda.  
  
2.  Seleccione cualquiera de los demás controles <xref:System.Windows.Forms.Button>.  Cambie el valor de su propiedad <xref:System.Windows.Forms.Control.Anchor%2A> a <xref:System.Windows.Forms.AnchorStyles>.  Observe que se desplaza para que el borde derecho esté cerca del borde derecho de la celda.  La distancia entre los bordes es la suma de la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control <xref:System.Windows.Forms.Button> y la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del panel.  
  
3.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a <xref:System.Windows.Forms.AnchorStyles> y <xref:System.Windows.Forms.AnchorStyles>.  Observe que el control cambia el tamaño al ancho de la celda, teniendo en cuenta los valores de la propiedad <xref:System.Windows.Forms.Control.Margin%2A> y <xref:System.Windows.Forms.Control.Padding%2A>.  
  
4.  Repita los pasos 2 y 3 con los estilos <xref:System.Windows.Forms.AnchorStyles> y <xref:System.Windows.Forms.AnchorStyles>.  
  
## Configurar las propiedades de las filas y columnas  
 Puede establecer propiedades individuales de filas y columnas mediante las colecciones <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> y <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>.  
  
#### Para establecer propiedades de filas y columnas  
  
1.  Seleccione el control <xref:System.Windows.Forms.TableLayoutPanel> en el **Diseñador de Windows Forms**.  
  
2.  En las ventanas **Propiedades**, abra la colección <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> haciendo clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) al lado de la entrada **Columnas**.  
  
3.  Seleccione la primera columna y cambie el valor de su propiedad <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> a <xref:System.Windows.Forms.SizeType>.  Haga clic en **Aceptar** para aceptar el cambio.  Observe que el ancho de la primera columna se reduce para ajustar el control <xref:System.Windows.Forms.Button>.  También observe que el tamaño del ancho de la columna no se puede cambiar.  
  
4.  En la ventana **Propiedades**, abra la colección <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> y seleccione la primera columna.  Cambie el valor de su propiedad <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> a <xref:System.Windows.Forms.SizeType>.  Haga clic en **Aceptar** para aceptar el cambio.  Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un ancho mayor y observe que el ancho de la primera columna se expande.  Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un ancho menor y observe que el tamaño de los botones de la primera columna cambian para ajustarse a la celda.  También observe que el tamaño del ancho de la columna se puede cambiar.  
  
5.  En la ventana **Propiedades**, abra la colección <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> y seleccione todas las columnas listadas.  Establezca el valor de cada propiedad <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> en <xref:System.Windows.Forms.SizeType>.  Haga clic en **Aceptar** para aceptar el cambio.  Repita con la colección <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A>.  
  
6.  Mantenga sujeto uno de los cuadros de tamaño de esquina y cambie el tamaño del ancho y alto del control <xref:System.Windows.Forms.TableLayoutPanel>.  Observe que el tamaño de las filas y columnas se cambia cuando cambia el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel>.  También observe que el tamaño de las filas y columnas se puede cambiar con los cuadros de tamaño horizontal y vertical.  
  
## Abarcar filas y columnas con un control  
 El control <xref:System.Windows.Forms.TableLayoutPanel> agrega en tiempo de diseño nuevas propiedades a los controles.  Dos de estas propiedades son `RowSpan` y `ColumnSpan`.  Puede utilizar estas propiedades que un control abarque más que una fila o columna.  
  
#### Para abarcar filas y columnas con un control  
  
1.  Seleccione el control <xref:System.Windows.Forms.Button> en la primera fila y primera columna.  
  
2.  En la ventana **Propiedades**, cambie el valor de la propiedad `ColumnSpan` a 2.  Observe que el control <xref:System.Windows.Forms.Button> rellena la primera columna y la segunda columna.  También observe que se ha agregado una fila adicional para adaptarse a este cambio.  
  
3.  Repita el paso 2 para la propiedad `RowSpan`.  
  
## Insertar controles haciendo doble clic en ellos en el Cuadro de herramientas  
 Puede rellenar el control <xref:System.Windows.Forms.TableLayoutPanel> haciendo doble clic en los controles en el **Cuadro de herramientas**.  
  
#### Para insertar controles haciendo doble clic en el Cuadro de herramientas  
  
1.  Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> desde el **Cuadro de herramientas** al formulario.  
  
2.  Haga doble clic en el icono de control <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas**.  Observe que aparece un nuevo control de botón en la primera celda del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
3.  Haga doble clic en otros controles en el **Cuadro de herramientas**.  Observe que los nuevos controles aparecen consecutivamente en las celdas desocupadas del control <xref:System.Windows.Forms.TableLayoutPanel>.  También observe que el control <xref:System.Windows.Forms.TableLayoutPanel> se expande para adaptarse a los nuevos controles si no está disponible ninguna celda abierta.  
  
## Control automático de desbordamientos  
 Cuando está insertando controles en el control <xref:System.Windows.Forms.TableLayoutPanel>, se puede quedarse sin celdas vacías para los nuevos controles.  El control <xref:System.Windows.Forms.TableLayoutPanel> controla automáticamente esta situación y aumenta en consecuencia el número de celdas.  
  
#### Para observar el control automático de los desbordamientos  
  
1.  Si todavía hay celdas vacías en el control <xref:System.Windows.Forms.TableLayoutPanel>, siga insertando los nuevos controles <xref:System.Windows.Forms.Button> hasta que el control <xref:System.Windows.Forms.TableLayoutPanel> esté lleno.  
  
2.  Cuando el control <xref:System.Windows.Forms.TableLayoutPanel> esté completo, haga doble clic en el icono <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas** para insertar otro control <xref:System.Windows.Forms.Button>.  Observe que el control <xref:System.Windows.Forms.TableLayoutPanel> crea nuevas celdas para adaptar el nuevo control.  Inserte algunos controles más y observe el comportamiento de cambio de tamaño.  
  
3.  Cambie el valor de la propiedad <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> del control <xref:System.Windows.Forms.TableLayoutPanel> a <xref:System.Windows.Forms.TableLayoutPanelGrowStyle>.  Haga doble clic en el icono <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas** para insertar controles <xref:System.Windows.Forms.Button> hasta que el control <xref:System.Windows.Forms.TableLayoutPanel> esté lleno.  Haga doble clic de nuevo en el icono del control <xref:System.Windows.Forms.Button> en el **Cuadro de herramientas**.  Observe que recibe un mensaje de error del **Diseñador de Windows Forms** que le informa que ya no se pueden crear filas columnas adicionales.  
  
## Insertar un control dibujando su contorno  
 Puede insertar un control en un control <xref:System.Windows.Forms.TableLayoutPanel> y especificar su tamaño dibujando su contorno en una celda.  
  
#### Para insertar un control dibujando su contorno  
  
1.  Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> desde el **Cuadro de herramientas** al formulario.  
  
2.  En el **Cuadro de herramientas**, haga clic en el icono de control <xref:System.Windows.Forms.Button>.  No lo arrastre hacia el formulario.  
  
3.  Coloque el puntero del mouse sobre el control <xref:System.Windows.Forms.TableLayoutPanel>.  Observe que el puntero cambia a una forma de cruz con el icono de control <xref:System.Windows.Forms.Button> adjuntado.  
  
4.  Haga clic y mantenga presionado el botón del mouse.  
  
5.  Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.Button>.  Cuando alcance el tamaño deseado, suelte el botón del mouse.  Observe que el control <xref:System.Windows.Forms.Button> se crea en la celda en la que dibujó el contorno de control.  
  
## No permiten varios controles dentro de las celdas  
 El control <xref:System.Windows.Forms.TableLayoutPanel> puede contener sólo un control secundario por celda.  
  
#### Para demostrar que no se permiten varios controles dentro de las celdas  
  
-   Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al control <xref:System.Windows.Forms.TableLayoutPanel> y colóquelo en una de las celdas ocupadas.  Observe que el control <xref:System.Windows.Forms.TableLayoutPanel> no le permite colocar el control <xref:System.Windows.Forms.Button> en la celda ocupada.  
  
## Intercambiar los controles  
 El control <xref:System.Windows.Forms.TableLayoutPanel> le permite intercambiar los controles que ocupan dos celdas diferentes.  
  
#### Para intercambiar los controles  
  
-   Arrastre uno de los controles <xref:System.Windows.Forms.Button> de una celda ocupada y colóquelo en otra celda ocupada.  Observe que los dos controles se intercambian.  
  
## Pasos siguientes  
 Puede lograr un diseño complejo mediante una combinación de paneles de diseño y controles.  Para una exploración más a fondo, pruebe estas sugerencias:  
  
-   Pruebe a cambiar el tamaño de uno de los controles <xref:System.Windows.Forms.Button> a un tamaño mayor y observe el efecto en el diseño.  
  
-   Pegue una selección de varios controles en el control <xref:System.Windows.Forms.TableLayoutPanel> y observe cómo se insertan los controles.  
  
-   Los paneles de diseño pueden contener otros paneles de diseño.  Experimente con colocar un control <xref:System.Windows.Forms.TableLayoutPanel> en el control existente.  
  
-   Acople el control <xref:System.Windows.Forms.TableLayoutPanel> al formulario principal.  Cambie el tamaño del formulario y observe el efecto en el diseño.  
  
## Vea también  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. \(USBN: 0\-7356\-0566\-1\)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)   
 [Walkthrough: Creating a Resizable Windows Form for Data Entry](http://msdn.microsoft.com/es-es/e193b4fc-912a-4917-b036-b76c7a6f58ab)   
 [Walkthrough: Creating a Localizable Windows Form](http://msdn.microsoft.com/es-es/c5240b6e-aaca-4286-9bae-778a416edb9c)   
 [Procedimientos recomendados para el control TableLayoutPanel](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)   
 [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [Cómo: Acoplar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)   
 [Cómo: Delimitar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)   
 [Tutorial: Diseñar controles de formularios Windows Forms con relleno, márgenes y la propiedad AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)