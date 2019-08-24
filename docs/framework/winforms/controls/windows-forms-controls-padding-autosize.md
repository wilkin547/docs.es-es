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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: daf0c6495b89033e75c27a1ff0cbceaff9d85f34
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987160"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a>Tutorial: Diseñar controles con relleno, márgenes y la propiedad AutoSize

La posición precisa de los controles del formulario es de alta prioridad para muchas aplicaciones. El **Diseñador de Windows Forms** en Visual Studio proporciona muchas herramientas de diseño para lograr esto. Tres de las más importantes son las <xref:System.Windows.Forms.Control.Margin%2A>propiedades <xref:System.Windows.Forms.Control.Padding%2A>, y <xref:System.Windows.Forms.Control.AutoSize%2A> , que están presentes en todos los controles Windows Forms.

La propiedad <xref:System.Windows.Forms.Control.Margin%2A> define el espacio alrededor del control que mantiene a los demás controles a una distancia especificada de los bordes del control.

La propiedad <xref:System.Windows.Forms.Control.Padding%2A> define el espacio en el interior de un control que mantiene el contenido del control (por ejemplo, el valor de su propiedad <xref:System.Windows.Forms.Control.Text%2A>) a una distancia especificada de los bordes del control.

La siguiente ilustración muestra las propiedades <xref:System.Windows.Forms.Control.Padding%2A> y <xref:System.Windows.Forms.Control.Margin%2A> de un control.

![Relleno y margen de controles de formularios Windows Forms](./media/vs-winformpadmargin.gif)

La <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad indica a un control que se ajuste automáticamente a su contenido. No cambiará de tamaño para que sea menor que el valor de su propiedad <xref:System.Windows.Forms.Control.Size%2A> original y tendrá en cuenta el valor de su <xref:System.Windows.Forms.Control.Padding%2A> propiedad.

## <a name="prerequisites"></a>Requisitos previos

Necesitará Visual Studio para completar este tutorial.

## <a name="create-the-project"></a>Crear el proyecto

1. En Visual Studio, cree un proyecto de **aplicación** para `LayoutExample`Windows denominado.

2. Seleccione el formulario en el **Diseñador de Windows Forms**.

## <a name="set-margins-for-controls"></a>Establecer márgenes para controles

Puede establecer la distancia predeterminada entre los controles mediante la <xref:System.Windows.Forms.Control.Margin%2A> propiedad. Si mueve un control lo suficientemente cerca de otro control, verá una guía de alineación que muestra los márgenes de los dos controles. El control que está moviendo también se ajustará a la distancia definida por los márgenes.

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a>Organizar controles en el formulario mediante la propiedad margin

1. Arrastre dos <xref:System.Windows.Forms.Button> controles desde el **cuadro de herramientas** hasta el formulario.

2. Seleccione uno de los <xref:System.Windows.Forms.Button> controles y muévalo cerca del otro, hasta que estén casi tocando.

   Observe la línea de ajuste que aparece entre ellas. Esta distancia es la suma de los <xref:System.Windows.Forms.Control.Margin%2A> valores de los dos controles. El control que está moviendo se ajusta a esta distancia. Para obtener más información [, consulte Tutorial: Organizar controles en Windows Forms mediante las líneas](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)de ajuste.

3. <xref:System.Windows.Forms.Padding.All%2A> <xref:System.Windows.Forms.Control.Margin%2A>Cambie la propiedaddeunodeloscontrolesexpandiendolaentradaenlaventanaPropiedadesyestableciendolapropiedaden20.<xref:System.Windows.Forms.Control.Margin%2A>

4. Seleccione uno de los <xref:System.Windows.Forms.Button> controles y muévalo cerca del otro.

   La línea de ajuste que define la suma de los valores de margen es mayor y que el control se ajusta a una distancia mayor desde el otro control.

5. Para cambiar <xref:System.Windows.Forms.Control.Margin%2A> la propiedad del control seleccionado, expanda <xref:System.Windows.Forms.Control.Margin%2A> la entrada en la ventana **propiedades** y establezca <xref:System.Windows.Forms.Padding.Top%2A> la propiedad en **5**.

6. Mueva el control seleccionado debajo del otro control y observe que la línea de ajuste es más corta. Mueva el control seleccionado a la izquierda del otro control y observe que la línea de ajuste conserva el valor observado en el paso 4.

7. Puede establecer cada uno de los aspectos de la <xref:System.Windows.Forms.Control.Margin%2A> propiedad <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Left%2A>,, <xref:System.Windows.Forms.Padding.Right%2A> <xref:System.Windows.Forms.Padding.Bottom%2A>,, en valores diferentes o puede establecerlos todos en el mismo valor con la <xref:System.Windows.Forms.Padding.All%2A> propiedad.

## <a name="set-padding-for-controls"></a>Establecer el relleno de los controles

Para lograr el diseño preciso necesario para la aplicación, los controles suelen contener controles secundarios. Si desea especificar la proximidad del borde del control secundario al borde del control principal, use la propiedad del <xref:System.Windows.Forms.Control.Padding%2A> control primario junto con la propiedad del <xref:System.Windows.Forms.Control.Margin%2A> control secundario. La <xref:System.Windows.Forms.Control.Padding%2A> propiedad también se usa para controlar la proximidad del contenido de un control (por ejemplo, la <xref:System.Windows.Forms.Button> propiedad de <xref:System.Windows.Forms.Control.Text%2A> un control) a sus bordes.

### <a name="arrange-controls-on-your-form-using-padding"></a>Organizar controles en el formulario mediante relleno

1. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.

2. Cambie el valor de la <xref:System.Windows.Forms.Button> propiedad del <xref:System.Windows.Forms.Control.AutoSize%2A> control a **true**.

3. <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Padding.All%2A>Cambie la propiedadexpandiendolaentradaenlaventanaPropiedadesyestableciendolapropiedaden5.<xref:System.Windows.Forms.Control.Padding%2A>

   El control se expande para proporcionar espacio para el nuevo relleno.

4. Arrastre un control <xref:System.Windows.Forms.GroupBox> del **cuadro de herramientas** al formulario. Arrastre un <xref:System.Windows.Forms.Button> control del <xref:System.Windows.Forms.GroupBox> **cuadro de herramientas** al control. Coloque el <xref:System.Windows.Forms.Button> control para que se vacíe con la esquina inferior derecha <xref:System.Windows.Forms.GroupBox> del control.

   Observe las líneas de ajuste que aparecen <xref:System.Windows.Forms.Button> cuando el control se aproxima a los bordes inferior <xref:System.Windows.Forms.GroupBox> y derecho del control. Estas guías <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Button>de alineación corresponden a la propiedad de.

5. Para cambiar <xref:System.Windows.Forms.GroupBox> la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control, expanda la <xref:System.Windows.Forms.Control.Padding%2A> entrada en la ventana **propiedades** y <xref:System.Windows.Forms.Padding.All%2A> establezca la propiedad en **20**.

6. Seleccione el <xref:System.Windows.Forms.Button> control dentro del <xref:System.Windows.Forms.GroupBox> control y muévalo <xref:System.Windows.Forms.GroupBox>hacia el centro del.

   Las guías de alineación aparecen a una distancia mayor desde los bordes <xref:System.Windows.Forms.GroupBox> del control. Esta distancia es la suma de la <xref:System.Windows.Forms.Button> propiedad del <xref:System.Windows.Forms.Control.Margin%2A> control y la <xref:System.Windows.Forms.GroupBox> propiedad del <xref:System.Windows.Forms.Control.Padding%2A> control.

## <a name="size-controls-automatically"></a>Cambiar el tamaño de los controles automáticamente

En algunas aplicaciones, el tamaño de un control no será el mismo en tiempo de ejecución que en tiempo de diseño. El texto de un <xref:System.Windows.Forms.Button> control, por ejemplo, puede tomarse de una base de datos y su longitud no se conoce de antemano.

Cuando la <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad está establecida en `true`, el control cambiará de tamaño a su contenido. Para obtener más información, vea [información general sobre la propiedad AutoSize](autosize-property-overview.md).

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a>Organizar controles en el formulario mediante la propiedad AutoSize

1. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.

2. Cambie el valor de la <xref:System.Windows.Forms.Button> propiedad del <xref:System.Windows.Forms.Control.AutoSize%2A> control a **true**.

3. Cambie la <xref:System.Windows.Forms.Button> propiedad del <xref:System.Windows.Forms.Control.Text%2A> control a **este botón con una cadena larga para su propiedad Text**.

   Al confirmar el cambio, el <xref:System.Windows.Forms.Button> control cambia de tamaño para ajustarse al nuevo texto.

4. Arrastre otro <xref:System.Windows.Forms.Button> control desde el **cuadro de herramientas** hasta el formulario.

5. Cambie la <xref:System.Windows.Forms.Button> propiedad del <xref:System.Windows.Forms.Control.Text%2A> control a "**este botón tiene una cadena larga para su propiedad Text".**

   Cuando se confirma el cambio, el <xref:System.Windows.Forms.Button> control no cambia de tamaño y el texto se recorta por el borde derecho del control.

6. <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Padding.All%2A>Cambie la propiedadexpandiendolaentradaenlaventanaPropiedadesyestableciendolapropiedaden5.<xref:System.Windows.Forms.Control.Padding%2A>

   El texto del interior del control se recorta en los cuatro lados.

7. Cambie la <xref:System.Windows.Forms.Button> propiedad del <xref:System.Windows.Forms.Control.AutoSize%2A> control a **true**.

   El <xref:System.Windows.Forms.Button> control cambia de tamaño para incluir toda la cadena. Además, el relleno se ha agregado alrededor del texto, lo <xref:System.Windows.Forms.Button> que hace que el control se expanda en las cuatro direcciones.

8. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario. Colóquelo cerca de la esquina inferior derecha del formulario.

9. Cambie el valor de la <xref:System.Windows.Forms.Button> propiedad del <xref:System.Windows.Forms.Control.AutoSize%2A> control a **true**.

10. Establezca la <xref:System.Windows.Forms.Button> propiedad del <xref:System.Windows.Forms.Control.Anchor%2A> control en <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.

11. Cambie la <xref:System.Windows.Forms.Button> propiedad del <xref:System.Windows.Forms.Control.Text%2A> control a "**este botón tiene una cadena larga para su propiedad Text".**

   Al confirmar el cambio, el <xref:System.Windows.Forms.Button> control cambia de tamaño hacia la izquierda. En general, el ajuste de tamaño automático aumentará el tamaño de un control en la <xref:System.Windows.Forms.Control.Anchor%2A> dirección opuesta a la del valor de la propiedad.

## <a name="autosize-and-autosizemode-properties"></a>Propiedades AutoSize y AutoSizeMode

 Algunos controles admiten `AutoSizeMode` la propiedad, que proporciona un control más preciso sobre el comportamiento de ajuste automático de tamaño de un control.

### <a name="use-the-autosizemode-property"></a>Usar la propiedad AutoSizeMode

1. Arrastre un control <xref:System.Windows.Forms.Panel> del **cuadro de herramientas** al formulario.

2. Establezca el valor de la <xref:System.Windows.Forms.Panel> propiedad del <xref:System.Windows.Forms.Control.AutoSize%2A> control en **true**.

3. Arrastre un <xref:System.Windows.Forms.Button> control del <xref:System.Windows.Forms.Panel> **cuadro de herramientas** al control.

4. Coloque el <xref:System.Windows.Forms.Button> control cerca de la esquina inferior derecha <xref:System.Windows.Forms.Panel> del control.

5. Seleccione el <xref:System.Windows.Forms.Panel> control y arrastre el controlador de tamaño inferior derecho. Cambie el tamaño <xref:System.Windows.Forms.Panel> del control para que sea mayor y menor.

   > [!NOTE]
   > Puede cambiar libremente el tamaño del <xref:System.Windows.Forms.Panel> control, pero no puede cambiar su tamaño más pequeño que la posición <xref:System.Windows.Forms.Button> de la esquina inferior derecha del control. Este comportamiento se especifica mediante el valor predeterminado de la `AutoSizeMode` propiedad, que es <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.

6. Establezca el valor de la <xref:System.Windows.Forms.Panel> propiedad del `AutoSizeMode` control en <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.

   Tamaño <xref:System.Windows.Forms.Panel> del control para rodear el <xref:System.Windows.Forms.Button> control. No se puede cambiar el <xref:System.Windows.Forms.Panel> tamaño del control.

7. Arrastre el <xref:System.Windows.Forms.Button> control hacia la esquina superior izquierda <xref:System.Windows.Forms.Panel> del control.

   El <xref:System.Windows.Forms.Panel> control cambia de tamaño a la <xref:System.Windows.Forms.Button> nueva posición del control.

## <a name="next-steps"></a>Pasos siguientes

Hay muchas otras características de diseño para organizar los controles en las aplicaciones Windows Forms. Estas son algunas de las combinaciones que podría intentar:

- Cree un formulario con un <xref:System.Windows.Forms.TableLayoutPanel> control. Para obtener más información [, consulte Tutorial: Organizar controles en Windows Forms mediante un control TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md). Pruebe a cambiar los valores de <xref:System.Windows.Forms.TableLayoutPanel> la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control, así como la <xref:System.Windows.Forms.Control.Margin%2A> propiedad en sus controles secundarios.

- Pruebe el mismo experimento con un <xref:System.Windows.Forms.FlowLayoutPanel> control. Para obtener más información [, consulte Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

- Experimente con el acoplamiento de controles secundarios <xref:System.Windows.Forms.Panel> en un control. La <xref:System.Windows.Forms.Control.Padding%2A> propiedad es una realización más general de la <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> propiedad, y se puede lograr que esto sea así al colocar un control secundario en un <xref:System.Windows.Forms.Panel> control y establecer la propiedad del <xref:System.Windows.Forms.Control.Dock%2A> control secundario en. <xref:System.Windows.Forms.DockStyle.Fill>. Establezca la <xref:System.Windows.Forms.Panel> propiedad del <xref:System.Windows.Forms.Control.Padding%2A> control en varios valores y observe el efecto.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [Información general sobre la propiedad AutoSize](autosize-property-overview.md)
- [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Tutorial: Organizar controles en Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
