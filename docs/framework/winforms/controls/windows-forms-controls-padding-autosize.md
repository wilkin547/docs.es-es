---
title: 'Tutorial: Diseñar controles de formularios Windows Forms con relleno, márgenes y la propiedad AutoSize'
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
ms.openlocfilehash: 52bc75135e4f8cf5b9c1888b2ad9f5e278c1d6e2
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271291"
---
# <a name="walkthrough-laying-out-windows-forms-controls-with-padding-margins-and-the-autosize-property"></a>Tutorial: Diseñar controles de formularios Windows Forms con relleno, márgenes y la propiedad AutoSize
La posición precisa de los controles del formulario es de alta prioridad para muchas aplicaciones. El **Diseñador de Windows Forms** le ofrece muchas herramientas de diseño para realizar esta acción. Tres de las más importantes son la <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, y <xref:System.Windows.Forms.Control.AutoSize%2A> propiedades, que están presentes en todos los controles de Windows Forms.  
  
 La propiedad <xref:System.Windows.Forms.Control.Margin%2A> define el espacio alrededor del control que mantiene a los demás controles a una distancia especificada de los bordes del control.  
  
 La propiedad <xref:System.Windows.Forms.Control.Padding%2A> define el espacio en el interior de un control que mantiene el contenido del control (por ejemplo, el valor de su propiedad <xref:System.Windows.Forms.Control.Text%2A>) a una distancia especificada de los bordes del control.  
  
 La siguiente ilustración muestra las propiedades <xref:System.Windows.Forms.Control.Padding%2A> y <xref:System.Windows.Forms.Control.Margin%2A> de un control.  
  
 ![Relleno y margen de Windows Forms controles](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")  
  
 El <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad indica a un control de tamaño automáticamente a su contenido. No cambiará de tamaño para que sea menor que el valor de su original <xref:System.Windows.Forms.Control.Size%2A> se tendrá en cuenta para el valor de propiedad y su <xref:System.Windows.Forms.Control.Padding%2A> propiedad.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de Windows Forms  
  
-   Establecer los márgenes para los controles  
  
-   Establecer el relleno de los controles  
  
-   Ajustar automáticamente el tamaño de los controles  
  
 Cuando termine, comprenderá el rol de estas importantes características de diseño.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde está instalado Visual Studio.  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
1.  Crear un **aplicación Windows** proyecto denominado `LayoutExample`. Para obtener más información, consulte [Cómo: crear un proyecto de aplicación Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) .  
  
2.  Seleccione el formulario en el **Diseñador de Windows Forms**.  
  
## <a name="setting-margins-for-your-controls"></a>Establecer los márgenes para los controles  
 Puede establecer la distancia predeterminada entre los controles mediante el <xref:System.Windows.Forms.Control.Margin%2A> propiedad. Cuando se mueve un control quede suficientemente a otro control, verá una línea de ajuste que se muestra los márgenes de los dos controles. El control que está moviendo también se ajusta a la distancia definida por los márgenes.  
  
#### <a name="to-arrange-controls-on-your-form-using-the-margin-property"></a>Para organizar los controles en el formulario mediante la propiedad Margin  
  
1.  Arrastre dos <xref:System.Windows.Forms.Button> controla desde el **cuadro de herramientas** hasta su formulario.  
  
2.  Seleccione uno de los <xref:System.Windows.Forms.Button> controla y muévalo cerca del otro, hasta que casi se toquen.  
  
     Observe la línea de ajuste que aparece entre ellos. La distancia es la suma de los dos controles <xref:System.Windows.Forms.Control.Margin%2A> valores. El control que está moviendo se ajusta a esta distancia. Para obtener más información, consulte [Tutorial: organizar controles en Windows Forms utilizando las guías de alineación](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
3.  Cambiar el <xref:System.Windows.Forms.Control.Margin%2A> propiedad de uno de los controles expandiendo el <xref:System.Windows.Forms.Control.Margin%2A> entrada en el **propiedades** ventana y la configuración de la <xref:System.Windows.Forms.Padding.All%2A> propiedad a 20.  
  
4.  Seleccione uno de los <xref:System.Windows.Forms.Button> controla y muévalo cerca del otro.  
  
     La Guía de alineación definir la suma de los valores de margen es más larga y que el control se ajusta a una distancia mayor del otro control.  
  
5.  Cambiar el <xref:System.Windows.Forms.Control.Margin%2A> propiedad del control seleccionado expandiendo el <xref:System.Windows.Forms.Control.Margin%2A> entrada en el **propiedades** ventana y la configuración de la <xref:System.Windows.Forms.Padding.Top%2A> en 5.  
  
6.  Mover el control seleccionado debajo del otro control y observe que la Guía de alineación es más corta. Mover el control seleccionado a la izquierda del control otro y observe que la línea de ajuste conserva el valor observado en el paso 4.  
  
7.  Puede establecer cada uno de los aspectos de la <xref:System.Windows.Forms.Control.Margin%2A> propiedad <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, valores diferentes, o bien puede establecerlas todo en el mismo valor con el <xref:System.Windows.Forms.Padding.All%2A> propiedad.  
  
## <a name="setting-padding-for-your-controls"></a>Establecer el relleno de los controles  
 Para lograr el diseño preciso para su aplicación, los controles suelen contener controles secundarios. Cuando desea especificar la proximidad del borde del control secundario para el borde del control primario, utilice el control primario <xref:System.Windows.Forms.Control.Padding%2A> propiedad junto con el control secundario <xref:System.Windows.Forms.Control.Margin%2A> propiedad. El <xref:System.Windows.Forms.Control.Padding%2A> propiedad también se usa para controlar la proximidad del contenido de un control (por ejemplo, un <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Text%2A> propiedad) para sus bordes.  
  
#### <a name="to-arrange-controls-on-your-form-using-padding"></a>Para organizar los controles del formulario mediante el relleno  
  
1.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** hasta su formulario.  
  
2.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Button> a `true`.  
  
3.  Cambiar el <xref:System.Windows.Forms.Control.Padding%2A> propiedad expandiendo el <xref:System.Windows.Forms.Control.Padding%2A> entrada en el **propiedades** ventana y la configuración de la <xref:System.Windows.Forms.Padding.All%2A> en 5.  
  
     El control se expande para proporcionar espacio para el relleno nuevo.  
  
4.  Arrastre un <xref:System.Windows.Forms.GroupBox> controlar desde la **cuadro de herramientas** hasta su formulario. Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en el <xref:System.Windows.Forms.GroupBox> control. Posición del <xref:System.Windows.Forms.Button> controlar para alinearlo con la esquina inferior derecha de la <xref:System.Windows.Forms.GroupBox> control.  
  
     Observe las líneas de ajuste que aparecen como el <xref:System.Windows.Forms.Button> control acerca de los bordes inferior y derecho de la <xref:System.Windows.Forms.GroupBox> control. Estas líneas de ajuste se corresponden con los <xref:System.Windows.Forms.Control.Margin%2A> propiedad de la <xref:System.Windows.Forms.Button>.  
  
5.  Cambiar el <xref:System.Windows.Forms.GroupBox> del control <xref:System.Windows.Forms.Control.Padding%2A> propiedad expandiendo el <xref:System.Windows.Forms.Control.Padding%2A> entrada en el **propiedades** ventana y la configuración de la <xref:System.Windows.Forms.Padding.All%2A> propiedad a 20.  
  
6.  Seleccione el <xref:System.Windows.Forms.Button> control dentro de la <xref:System.Windows.Forms.GroupBox> controlar y muévalo hacia el centro de la <xref:System.Windows.Forms.GroupBox>.  
  
     Las guías de alineación aparecen a una distancia mayor de los bordes de la <xref:System.Windows.Forms.GroupBox> control. La distancia es la suma de los <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Margin%2A> propiedad y el <xref:System.Windows.Forms.GroupBox> del control <xref:System.Windows.Forms.Control.Padding%2A> propiedad.  
  
## <a name="automatically-sizing-your-controls"></a>Ajustar automáticamente el tamaño de los controles  
 En algunas aplicaciones, el tamaño de un control no será la misma en tiempo de ejecución tal como estaba en tiempo de diseño. El texto de un <xref:System.Windows.Forms.Button> , por ejemplo, podría asumir el control de una base de datos y su longitud no se conocerá con antelación.  
  
 Cuando el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad está establecida en `true`, el control debe cambiar de tamaño a su contenido. Para obtener más información, consulte [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
#### <a name="to-arrange-controls-on-your-form-using-the-autosize-property"></a>Para organizar los controles en el formulario mediante la propiedad AutoSize  
  
1.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** hasta su formulario.  
  
2.  Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Button> a `true`.  
  
3.  Cambiar el <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Text%2A> propiedad en "**este botón tiene una cadena larga de su propiedad Text**."  
  
     Cuando se confirma el cambio, el <xref:System.Windows.Forms.Button> control cambia de tamaño para ajustarse al nuevo texto.  
  
4.  Arrastre otro <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** hasta su formulario.  
  
5.  Cambiar el <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Text%2A> propiedad en "**este botón tiene una cadena larga de su propiedad Text.**"  
  
     Cuando se confirma el cambio, el <xref:System.Windows.Forms.Button> control no se ajusta y el texto se recorta por el borde derecho del control.  
  
6.  Cambiar el <xref:System.Windows.Forms.Control.Padding%2A> propiedad expandiendo el <xref:System.Windows.Forms.Control.Padding%2A> entrada en el **propiedades** ventana y la configuración de la <xref:System.Windows.Forms.Padding.All%2A> en 5.  
  
     El texto en el interior del control se recorta en los cuatro lados.  
  
7.  Cambiar el <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad `true`.  
  
     El <xref:System.Windows.Forms.Button> control cambia de tamaño para abarcar toda la cadena. Además, se ha agregado el relleno alrededor del texto, provocando la <xref:System.Windows.Forms.Button> control para expandir en las cuatro direcciones.  
  
8.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** hasta su formulario. Colóquelo cerca de la esquina inferior derecha del formulario.  
  
9. Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Button> a `true`.  
  
10. Establecer el <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> propiedad <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.  
  
11. Cambiar el <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Text%2A> propiedad en "**este botón tiene una cadena larga de su propiedad Text.**"  
  
     Cuando se confirma el cambio, el <xref:System.Windows.Forms.Button> control cambia de tamaño hacia la izquierda. En general, ajuste de tamaño automático, aumentará el tamaño de un control en la dirección opuesta su <xref:System.Windows.Forms.Control.Anchor%2A> configuración de la propiedad.  
  
## <a name="autosize-and-autosizemode-properties"></a>AutoSize y AutoSizeMode propiedades  
 Algunos controles admiten la `AutoSizeMode` propiedad, que le ofrece un mayor control sobre el comportamiento de ajuste automático de tamaño de un control.  
  
#### <a name="to-use-the-autosizemode-property"></a>Para usar la propiedad AutoSizeMode  
  
1.  Arrastre un <xref:System.Windows.Forms.Panel> controlar desde la **cuadro de herramientas** hasta su formulario.  
  
2.  Establezca el valor de la <xref:System.Windows.Forms.Panel> del control <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad `true`.  
  
3.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en el <xref:System.Windows.Forms.Panel> control.  
  
4.  Colocar el <xref:System.Windows.Forms.Button> control cerca de la esquina inferior derecha de la <xref:System.Windows.Forms.Panel> control.  
  
5.  Seleccione el <xref:System.Windows.Forms.Panel> controlar y tomo el controlador de tamaño inferior derecha. Cambiar el tamaño de la <xref:System.Windows.Forms.Panel> que sea superior e inferior del control.  
  
    > [!NOTE]
    >  Se puede cambiar libremente el <xref:System.Windows.Forms.Panel> control, pero no se puede cambiar su tamaño más pequeño que la posición de la <xref:System.Windows.Forms.Button> esquina inferior derecha del control. Este comportamiento se especifica mediante el valor predeterminado de la `AutoSizeMode` propiedad, que es <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.  
  
6.  Establezca el valor de la <xref:System.Windows.Forms.Panel> del control `AutoSizeMode` propiedad <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.  
  
     El <xref:System.Windows.Forms.Panel> control se ajusta para rodear el <xref:System.Windows.Forms.Button> control. No se puede cambiar el tamaño de la <xref:System.Windows.Forms.Panel> control.  
  
7.  Arrastre el <xref:System.Windows.Forms.Button> control hacia la esquina superior izquierda de la <xref:System.Windows.Forms.Panel> control.  
  
     El <xref:System.Windows.Forms.Panel> control cambia de tamaño para el <xref:System.Windows.Forms.Button> nueva posición del control.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Hay muchas otras características de diseño para organizar controles en las aplicaciones de Windows Forms. Estas son algunas combinaciones que podría probar:  
  
-   Crear un formulario mediante un <xref:System.Windows.Forms.TableLayoutPanel> control. Para obtener más información, consulte [Tutorial: organizar controles en Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md). Intente cambiar los valores de la <xref:System.Windows.Forms.TableLayoutPanel> del control <xref:System.Windows.Forms.Control.Padding%2A> propiedad, así como el <xref:System.Windows.Forms.Control.Margin%2A> propiedad en sus controles secundarios.  
  
-   Pruebe el mismo experimento con un <xref:System.Windows.Forms.FlowLayoutPanel> control. Para obtener más información, consulte [Tutorial: organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
-   Experimento con el acoplamiento de controles secundarios en un <xref:System.Windows.Forms.Panel> control. El <xref:System.Windows.Forms.Control.Padding%2A> propiedad es una realización más general de la <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> propiedad y se puede satisfacer por sí mismo que este es el caso al colocar un control secundario en un <xref:System.Windows.Forms.Panel> control y establecer el control secundario <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>. Establecer el <xref:System.Windows.Forms.Panel> del control <xref:System.Windows.Forms.Control.Padding%2A> propiedad para distintos valores y tenga en cuenta el efecto.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>  
 <xref:System.Windows.Forms.Control.Margin%2A>  
 <xref:System.Windows.Forms.Control.Padding%2A>  
 [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
