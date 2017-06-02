---
title: "Tutorial: Dise&#241;ar controles de formularios Windows Forms con relleno, m&#225;rgenes y la propiedad AutoSize | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Margin.Bottom"
  - "Margin.Left"
  - "Margin.Top"
  - "Margin.All"
  - "Margin.Right"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "AutoSize (propiedad), tutoriales"
  - "diseño [Windows Forms], márgenes y relleno"
  - "Margin (propiedad) [Windows Forms], tutoriales"
  - "Padding (propiedad) [Windows Forms], tutoriales"
  - "tutoriales [Windows Forms], diseño"
  - "Windows Forms, diseño"
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# Tutorial: Dise&#241;ar controles de formularios Windows Forms con relleno, m&#225;rgenes y la propiedad AutoSize
La posición precisa de los controles en el formulario es de alta prioridad para muchas aplicaciones.  El **Diseñador de Windows Forms** ofrece muchas herramientas de diseño para llevarlo a cabo.  Tres de las herramientas más importante son las propiedades <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A> y <xref:System.Windows.Forms.Control.AutoSize%2A>, presentes en todos los controles de formularios Windows Forms.  
  
 La propiedad <xref:System.Windows.Forms.Control.Margin%2A> define el espacio alrededor del control que mantiene a los demás controles a una distancia especificada de los bordes de control.  
  
 La propiedad <xref:System.Windows.Forms.Control.Padding%2A> define el espacio en el interior de un control que mantiene el contenido del control \(por ejemplo, el valor de su propiedad <xref:System.Windows.Forms.Control.Text%2A>\) a una distancia especificada de los bordes del control.  
  
 En la ilustración siguiente se muestran las propiedades <xref:System.Windows.Forms.Control.Padding%2A> y <xref:System.Windows.Forms.Control.Margin%2A> en un control.  
  
 ![Relleno y margen de controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS\_WinFormPadMargin")  
  
 La propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> indica a un control que ajuste automáticamente su tamaño al contenido.  No cambia su tamaño a uno menor que el valor de la propiedad <xref:System.Windows.Forms.Control.Size%2A> original, y tendrá en cuenta el valor de su propiedad <xref:System.Windows.Forms.Control.Padding%2A>.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de formularios Windows Forms  
  
-   Establecer los márgenes para los controles  
  
-   Establecer el relleno de los controles  
  
-   Ajustar automáticamente el tamaño de los controles  
  
 Al finalizar, podrá entender el rol que desempeñan estas importantes características de diseño.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde esté instalado Visual Studio.  
  
## Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### Para crear el proyecto  
  
1.  Cree un proyecto **Aplicación para Windows** llamado `LayoutExample`.  Para obtener más información, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Seleccione el formulario en el **Diseñador de Windows Forms**.  
  
## Establecer los márgenes para los controles  
 Puede establecer la distancia predeterminada entre los controles mediante la propiedad <xref:System.Windows.Forms.Control.Margin%2A>.  Cuando acerca bastante un control a otro, verá una línea de ajuste que muestra los márgenes de los dos controles.  El control que está moviendo también se ajusta a la distancia definida por los márgenes.  
  
#### Para organizar los controles en el formulario mediante la propiedad Margin  
  
1.  Arrastre dos controles <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al formulario.  
  
2.  Seleccione uno de los controles <xref:System.Windows.Forms.Button> y muévalo cerca del otro, hasta que casi se toquen.  
  
     Observe la línea de ajuste que aparece entre ellos.  Esta distancia es la suma de los valores de la propiedad <xref:System.Windows.Forms.Control.Margin%2A> de los dos controles.  El control que está moviendo se ajusta a esta distancia.  Para obtener información detallada, vea [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
3.  Cambie la propiedad <xref:System.Windows.Forms.Control.Margin%2A> de uno de los controles expandiendo la entrada <xref:System.Windows.Forms.Control.Margin%2A> de la ventana **Propiedades** y estableciendo la propiedad <xref:System.Windows.Forms.Padding.All%2A> en 20.  
  
4.  Seleccione uno de los controles <xref:System.Windows.Forms.Button> y acérquelo al otro.  
  
     La línea de ajuste que define la suma de los valores de margen es más larga y el control se ajusta a una distancia mayor del otro control.  
  
5.  Cambie la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control seleccionado expandiendo la entrada <xref:System.Windows.Forms.Control.Margin%2A> de la ventana **Propiedades** y estableciendo la propiedad <xref:System.Windows.Forms.Padding.Top%2A> en 5.  
  
6.  Mueva el control seleccionado debajo del otro control y observe que la línea de ajuste es más corta.  Mueva el control seleccionado a la izquierda del otro control y observe que la línea de ajuste conserva el valor definido en el paso 4.  
  
7.  Puede establecer cada uno de los aspectos de las propiedades <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A> en distintos valores, o puede establecer todos al mismo valor con la propiedad <xref:System.Windows.Forms.Padding.All%2A>.  
  
## Establecer el relleno de los controles  
 Para conseguir el diseño preciso para su aplicación, los controles suelen contener controles secundarios.  Cuando desea especificar la proximidad del borde del control secundario, utilice la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control principal junto con la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control secundario.  La propiedad <xref:System.Windows.Forms.Control.Padding%2A> también se utiliza para controlar la proximidad de un contenido de control \(por ejemplo, una propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button>\) a los bordes.  
  
#### Para organizar los controles en su formulario utilizando el relleno  
  
1.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al formulario.  
  
2.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Button> a `true`.  
  
3.  Cambie la propiedad <xref:System.Windows.Forms.Control.Padding%2A> expandiendo la entrada <xref:System.Windows.Forms.Control.Padding%2A> en la ventana **Propiedades** y estableciendo la propiedad <xref:System.Windows.Forms.Padding.All%2A> en 5.  
  
     El control se amplía para dejar espacio al nuevo relleno.  
  
4.  Arrastre un control <xref:System.Windows.Forms.GroupBox> desde el **Cuadro de herramientas** al formulario.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al control <xref:System.Windows.Forms.GroupBox>.  Coloque el control <xref:System.Windows.Forms.Button> para alinearlo con la esquina inferior derecha del control <xref:System.Windows.Forms.GroupBox>.  
  
     Observe las líneas de ajuste que aparecen cuando el control <xref:System.Windows.Forms.Button> se acerca los bordes inferior y derecho del control <xref:System.Windows.Forms.GroupBox>.  Estas líneas de ajuste corresponden a la propiedad <xref:System.Windows.Forms.Control.Margin%2A> de <xref:System.Windows.Forms.Button>.  
  
5.  Cambie la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control <xref:System.Windows.Forms.GroupBox> expandiendo la entrada <xref:System.Windows.Forms.Control.Padding%2A> en la ventana **Propiedades** y estableciendo la propiedad <xref:System.Windows.Forms.Padding.All%2A> en 20.  
  
6.  Seleccione el control <xref:System.Windows.Forms.Button> dentro del control <xref:System.Windows.Forms.GroupBox> y acérquelo al centro de <xref:System.Windows.Forms.GroupBox>.  
  
     Las líneas de ajuste se muestran a una distancia mayor de los bordes del control <xref:System.Windows.Forms.GroupBox>.  Esta distancia es la suma de la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control <xref:System.Windows.Forms.Button> y la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control <xref:System.Windows.Forms.GroupBox>.  
  
## Ajustar automáticamente el tamaño de los controles  
 En algunas aplicaciones, el tamaño de un control no será el mismo en tiempo de ejecución que en tiempo de diseño.  El texto de un control <xref:System.Windows.Forms.Button>, por ejemplo, se puede tomar desde una base de datos, por lo que no se conoce de antemano su extensión.  
  
 Cuando la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> se establece en `true`, el control ajusta el tamaño al contenido.  Para obtener más información, consulte [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
#### Para organizar los controles en el formulario mediante la propiedad AutoSize  
  
1.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al formulario.  
  
2.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Button> a `true`.  
  
3.  Cambie la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button> a "Este botón tiene una cadena larga para su propiedad Text".  
  
     Cuando confirma el cambio, el control <xref:System.Windows.Forms.Button> cambia su tamaño para ajustar el nuevo texto.  
  
4.  Arrastre otro control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al formulario.  
  
5.  Cambie la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button> a "Este botón tiene una cadena larga para su propiedad Text".  
  
     Cuando confirma el cambio, el control <xref:System.Windows.Forms.Button> no cambia su tamaño y el borde derecho del control recorta el texto.  
  
6.  Cambie la propiedad <xref:System.Windows.Forms.Control.Padding%2A> expandiendo la entrada <xref:System.Windows.Forms.Control.Padding%2A> en la ventana **Propiedades** y estableciendo la propiedad <xref:System.Windows.Forms.Padding.All%2A> en 5.  
  
     El texto del interior del control se recorta en los cuatro lados.  
  
7.  Establezca la propiedad <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.AutoSize%2A> en `true`.  
  
     El control <xref:System.Windows.Forms.Button> cambia su tamaño para ajustar toda la cadena.  Además, se ha agregado relleno alrededor del texto, por lo que el control <xref:System.Windows.Forms.Button> se ha expandido en las cuatro direcciones.  
  
8.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al formulario.  Colóquelo cerca de la esquina inferior derecha del formulario.  
  
9. Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Button> a `true`.  
  
10. Establezca la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> en <xref:System.Windows.Forms.AnchorStyles>, <xref:System.Windows.Forms.AnchorStyles>.  
  
11. Cambie la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button> a "Este botón tiene una cadena larga para su propiedad Text".  
  
     Cuando confirme el cambio, el control <xref:System.Windows.Forms.Button> cambia su tamaño hacia la izquierda.  En general, el ajuste automático de tamaño aumentará el tamaño de un control en la dirección opuesta a la configuración de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.  
  
## Propiedades AutoSice y AutoSizeMode  
 Algunos controles admiten la propiedad `AutoSizeMode`, que permite un mayor control sobre el comportamiento del ajuste automático del tamaño de un control.  
  
#### Para utilizar la propiedad AutoSizeMode  
  
1.  Arrastre un control <xref:System.Windows.Forms.Panel> desde el **Cuadro de herramientas** al formulario.  
  
2.  Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Panel> en `true`.  
  
3.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** al control <xref:System.Windows.Forms.Panel>.  
  
4.  Coloque el control <xref:System.Windows.Forms.Button> cerca de la esquina inferior derecha del control <xref:System.Windows.Forms.Panel>.  
  
5.  Seleccione el control <xref:System.Windows.Forms.Panel> y mantenga sujeto el cuadro de tamaño inferior derecho.  Cambie el tamaño del control <xref:System.Windows.Forms.Panel> para que sea más largo y más pequeño.  
  
    > [!NOTE]
    >  Puede cambiar libremente el tamaño del control <xref:System.Windows.Forms.Panel>, pero no puede hacerlo más pequeño que la posición de la esquina inferior derecha del control <xref:System.Windows.Forms.Button>.  El valor predeterminado de la propiedad `AutoSizeMode`, que es <xref:System.Windows.Forms.AutoSizeMode>, especifica este comportamiento.  
  
6.  Establezca el valor de la propiedad `AutoSizeMode` del control <xref:System.Windows.Forms.Panel> en <xref:System.Windows.Forms.AutoSizeMode>.  
  
     El control <xref:System.Windows.Forms.Panel> ajusta su tamaño para rodear el control <xref:System.Windows.Forms.Button>.  No puede cambiar el tamaño del control <xref:System.Windows.Forms.Panel>.  
  
7.  Arrastre el control <xref:System.Windows.Forms.Button> hacia la esquina superior izquierda del control <xref:System.Windows.Forms.Panel>.  
  
     El control <xref:System.Windows.Forms.Panel> cambia su tamaño a la nueva posición del control <xref:System.Windows.Forms.Button>.  
  
## Pasos siguientes  
 Los formularios Windows Forms disponen de muchas otras características de diseño para organizar los controles.  Éstas algunas combinaciones que podría probar:  
  
-   Compile un formulario mediante un control <xref:System.Windows.Forms.TableLayoutPanel>.  Para obtener información detallada, vea [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  Pruebe a cambiar los valores de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control <xref:System.Windows.Forms.TableLayoutPanel>, así como la propiedad <xref:System.Windows.Forms.Control.Margin%2A> en sus controles secundarios.  
  
-   Intente lo mismo mediante un control <xref:System.Windows.Forms.FlowLayoutPanel>.  Para obtener información detallada, vea [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
-   Experimente con el acoplamiento de los controles secundarios en un control <xref:System.Windows.Forms.Panel>.  La propiedad <xref:System.Windows.Forms.Control.Padding%2A> es una realización más general de la propiedad <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>, y puede comprobarlo colocando un control secundario en un control <xref:System.Windows.Forms.Panel> y estableciendo la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control secundario en <xref:System.Windows.Forms.DockStyle>.  Establezca la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control <xref:System.Windows.Forms.Panel> en distintos valores y observe el efecto.  
  
## Vea también  
 <xref:System.Windows.Forms.Control.AutoSize%2A>   
 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>   
 <xref:System.Windows.Forms.Control.Margin%2A>   
 <xref:System.Windows.Forms.Control.Padding%2A>   
 [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)