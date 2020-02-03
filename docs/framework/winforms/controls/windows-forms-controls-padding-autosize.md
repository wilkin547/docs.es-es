---
title: Diseñar controles con relleno, márgenes y la propiedad AutoSize
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: ca7942c04434592f2541252c47ac3dd17e03dbac
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742368"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a>Tutorial: diseñar controles con relleno, márgenes y la propiedad AutoSize

La posición precisa de los controles del formulario es de alta prioridad para muchas aplicaciones. El **Diseñador de Windows Forms** en Visual Studio proporciona muchas herramientas de diseño para lograr esto. Tres de las más importantes son las propiedades <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>y <xref:System.Windows.Forms.Control.AutoSize%2A>, que están presentes en todos los controles de Windows Forms.

La propiedad <xref:System.Windows.Forms.Control.Margin%2A> define el espacio alrededor del control que mantiene a los demás controles a una distancia especificada de los bordes del control.

La propiedad <xref:System.Windows.Forms.Control.Padding%2A> define el espacio en el interior de un control que mantiene el contenido del control (por ejemplo, el valor de su propiedad <xref:System.Windows.Forms.Control.Text%2A>) a una distancia especificada de los bordes del control.

La siguiente ilustración muestra las propiedades <xref:System.Windows.Forms.Control.Padding%2A> y <xref:System.Windows.Forms.Control.Margin%2A> de un control.

![Relleno y margen de controles de formularios Windows Forms](./media/vs-winformpadmargin.gif)

La propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> indica a un control que se ajuste automáticamente a su contenido. No cambiará de tamaño para que sea menor que el valor de su propiedad <xref:System.Windows.Forms.Control.Size%2A> original, y tendrá en cuenta el valor de su propiedad <xref:System.Windows.Forms.Control.Padding%2A>.

## <a name="prerequisites"></a>Prerequisites

Necesitará Visual Studio para completar este tutorial.

## <a name="create-the-project"></a>Creación del proyecto

1. En Visual Studio, cree un proyecto de **aplicación para Windows** denominado `LayoutExample`.

2. Seleccione el formulario en el **Diseñador de Windows Forms**.

## <a name="set-margins-for-controls"></a>Establecer márgenes para controles

Puede establecer la distancia predeterminada entre los controles mediante el <xref:System.Windows.Forms.Control.Margin%2A> propiedad. Si mueve un control lo suficientemente cerca de otro control, verá una guía de alineación que muestra los márgenes de los dos controles. El control que está moviendo también se ajustará a la distancia definida por los márgenes.

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a>Organizar controles en el formulario mediante la propiedad margin

1. Arrastre dos controles <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** hasta el formulario.

2. Seleccione uno de los controles de <xref:System.Windows.Forms.Button> y muévalo cerca del otro, hasta que estén casi tocando.

   Observe la línea de ajuste que aparece entre ellas. Esta distancia es la suma de los valores de <xref:System.Windows.Forms.Control.Margin%2A> de los dos controles. El control que está moviendo se ajusta a esta distancia. Para obtener más información, vea [Tutorial: organizar controles en Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

3. Cambie la propiedad <xref:System.Windows.Forms.Control.Margin%2A> de uno de los controles expandiendo la entrada <xref:System.Windows.Forms.Control.Margin%2A> en la ventana **propiedades** y estableciendo la propiedad <xref:System.Windows.Forms.Padding.All%2A> en **20**.

4. Seleccione uno de los controles de <xref:System.Windows.Forms.Button> y muévalo cerca del otro.

   La línea de ajuste que define la suma de los valores de margen es mayor y que el control se ajusta a una distancia mayor desde el otro control.

5. Para cambiar la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control seleccionado, expanda la entrada <xref:System.Windows.Forms.Control.Margin%2A> en la ventana **propiedades** y establezca la propiedad <xref:System.Windows.Forms.Padding.Top%2A> en **5**.

6. Mueva el control seleccionado debajo del otro control y observe que la línea de ajuste es más corta. Mueva el control seleccionado a la izquierda del otro control y observe que la línea de ajuste conserva el valor observado en el paso 4.

7. Puede establecer cada uno de los aspectos de la propiedad <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, en valores diferentes o puede establecerlos todos en el mismo valor con la propiedad <xref:System.Windows.Forms.Padding.All%2A>.

## <a name="set-padding-for-controls"></a>Establecer el relleno de los controles

Para lograr el diseño preciso necesario para la aplicación, los controles suelen contener controles secundarios. Si desea especificar la proximidad del borde del control secundario al borde del control principal, use la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control primario junto con la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control secundario. La propiedad <xref:System.Windows.Forms.Control.Padding%2A> también se usa para controlar la proximidad del contenido de un control (por ejemplo, la propiedad <xref:System.Windows.Forms.Control.Text%2A> de un control <xref:System.Windows.Forms.Button>) a sus bordes.

### <a name="arrange-controls-on-your-form-using-padding"></a>Organizar controles en el formulario mediante relleno

1. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.

2. Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Button> a **true**.

3. Cambie la propiedad <xref:System.Windows.Forms.Control.Padding%2A> expandiendo la <xref:System.Windows.Forms.Control.Padding%2A> entrada en la ventana **propiedades** y establezca la propiedad <xref:System.Windows.Forms.Padding.All%2A> en **5**.

   El control se expande para proporcionar espacio para el nuevo relleno.

4. Arrastre un control <xref:System.Windows.Forms.GroupBox> del **cuadro de herramientas** al formulario. Arrastre un control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** al control <xref:System.Windows.Forms.GroupBox>. Coloque el control <xref:System.Windows.Forms.Button> de modo que se vacíe con la esquina inferior derecha del control <xref:System.Windows.Forms.GroupBox>.

   Observe las líneas de ajuste que aparecen cuando el control <xref:System.Windows.Forms.Button> se aproxima a los bordes inferior y derecho del control <xref:System.Windows.Forms.GroupBox>. Estas guías de alineación corresponden a la propiedad <xref:System.Windows.Forms.Control.Margin%2A> de la <xref:System.Windows.Forms.Button>.

5. Cambie la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control <xref:System.Windows.Forms.GroupBox> expandiendo la entrada <xref:System.Windows.Forms.Control.Padding%2A> en la ventana **propiedades** y establezca la propiedad <xref:System.Windows.Forms.Padding.All%2A> en **20**.

6. Seleccione el control <xref:System.Windows.Forms.Button> dentro del control <xref:System.Windows.Forms.GroupBox> y muévalo hacia el centro de la <xref:System.Windows.Forms.GroupBox>.

   Las guías de alineación aparecen a una distancia mayor desde los bordes del control <xref:System.Windows.Forms.GroupBox>. Esta distancia es la suma de la propiedad <xref:System.Windows.Forms.Control.Margin%2A> del control <xref:System.Windows.Forms.Button> y la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control <xref:System.Windows.Forms.GroupBox>.

## <a name="size-controls-automatically"></a>Cambiar el tamaño de los controles automáticamente

En algunas aplicaciones, el tamaño de un control no será el mismo en tiempo de ejecución que en tiempo de diseño. El texto de un control de <xref:System.Windows.Forms.Button>, por ejemplo, puede tomarse de una base de datos y su longitud no se conoce de antemano.

Cuando la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> está establecida en `true`, el control cambiará de tamaño a su contenido. Para obtener más información, vea [información general sobre la propiedad AutoSize](autosize-property-overview.md).

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a>Organizar controles en el formulario mediante la propiedad AutoSize

1. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.

2. Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Button> a **true**.

3. Cambie la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button> a **este botón tiene una cadena larga para su propiedad Text**.

   Al confirmar el cambio, el control <xref:System.Windows.Forms.Button> cambia de tamaño para ajustarse al nuevo texto.

4. Arrastre otro control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** hasta el formulario.

5. Cambie la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button> a "**este botón tiene una cadena larga para su propiedad Text".**

   Al confirmar el cambio, el control <xref:System.Windows.Forms.Button> no cambia de tamaño y el texto se recorta por el borde derecho del control.

6. Cambie la propiedad <xref:System.Windows.Forms.Control.Padding%2A> expandiendo la <xref:System.Windows.Forms.Control.Padding%2A> entrada en la ventana **propiedades** y establezca la propiedad <xref:System.Windows.Forms.Padding.All%2A> en **5**.

   El texto del interior del control se recorta en los cuatro lados.

7. Cambie la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Button> a **true**.

   El control <xref:System.Windows.Forms.Button> cambia de tamaño para incluir toda la cadena. Además, el relleno se ha agregado alrededor del texto, lo que hace que el control de <xref:System.Windows.Forms.Button> se expanda en las cuatro direcciones.

8. Arrastre un control <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario. Colóquelo cerca de la esquina inferior derecha del formulario.

9. Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Button> a **true**.

10. Establezca la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> en <xref:System.Windows.Forms.AnchorStyles.Right><xref:System.Windows.Forms.AnchorStyles.Bottom>.

11. Cambie la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button> a "**este botón tiene una cadena larga para su propiedad Text".**

   Al confirmar el cambio, el control <xref:System.Windows.Forms.Button> cambia de tamaño hacia la izquierda. En general, el ajuste de tamaño automático aumentará el tamaño de un control en la dirección opuesta a la configuración de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.

## <a name="autosize-and-autosizemode-properties"></a>Propiedades AutoSize y AutoSizeMode

 Algunos controles admiten la propiedad `AutoSizeMode`, que proporciona un control más preciso sobre el comportamiento de ajuste automático de tamaño de un control.

### <a name="use-the-autosizemode-property"></a>Usar la propiedad AutoSizeMode

1. Arrastre un control <xref:System.Windows.Forms.Panel> del **cuadro de herramientas** al formulario.

2. Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> del control <xref:System.Windows.Forms.Panel> en **true**.

3. Arrastre un control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** al control <xref:System.Windows.Forms.Panel>.

4. Coloque el control <xref:System.Windows.Forms.Button> cerca de la esquina inferior derecha del control <xref:System.Windows.Forms.Panel>.

5. Seleccione el control de <xref:System.Windows.Forms.Panel> y arrastre el controlador de tamaño inferior derecho. Cambie el tamaño del control <xref:System.Windows.Forms.Panel> para que sea mayor y menor.

   > [!NOTE]
   > Puede cambiar el tamaño del control de <xref:System.Windows.Forms.Panel> libremente, pero no puede cambiar su tamaño más pequeño que la posición de la esquina inferior derecha del control <xref:System.Windows.Forms.Button>. Este comportamiento se especifica mediante el valor predeterminado de la propiedad `AutoSizeMode`, que es <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.

6. Establezca el valor de la propiedad `AutoSizeMode` del control <xref:System.Windows.Forms.Panel> en <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.

   Los tamaños de control <xref:System.Windows.Forms.Panel> para rodear el control <xref:System.Windows.Forms.Button>. No se puede cambiar el tamaño del control de <xref:System.Windows.Forms.Panel>.

7. Arrastre el control <xref:System.Windows.Forms.Button> hacia la esquina superior izquierda del control <xref:System.Windows.Forms.Panel>.

   El control <xref:System.Windows.Forms.Panel> cambia de tamaño a la nueva posición del control <xref:System.Windows.Forms.Button>.

## <a name="next-steps"></a>Pasos siguientes

Hay muchas otras características de diseño para organizar los controles en las aplicaciones Windows Forms. Estas son algunas de las combinaciones que podría intentar:

- Cree un formulario con un control de <xref:System.Windows.Forms.TableLayoutPanel>. Para obtener más información, vea [Tutorial: organizar controles en Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md). Pruebe a cambiar los valores de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control <xref:System.Windows.Forms.TableLayoutPanel>, así como la propiedad <xref:System.Windows.Forms.Control.Margin%2A> en sus controles secundarios.

- Pruebe el mismo experimento con un control de <xref:System.Windows.Forms.FlowLayoutPanel>. Para obtener más información, vea [Tutorial: organizar controles en Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

- Experimente con el acoplamiento de controles secundarios en un control de <xref:System.Windows.Forms.Panel>. La propiedad <xref:System.Windows.Forms.Control.Padding%2A> es una realización más general de la propiedad <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>, y se puede solucionar por sí mismo que este es el caso colocando un control secundario en un control <xref:System.Windows.Forms.Panel> y estableciendo la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control secundario en <xref:System.Windows.Forms.DockStyle.Fill>. Establezca la propiedad <xref:System.Windows.Forms.Control.Padding%2A> del control <xref:System.Windows.Forms.Panel> en varios valores y observe el efecto.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [Información general sobre la propiedad AutoSize](autosize-property-overview.md)
- [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
