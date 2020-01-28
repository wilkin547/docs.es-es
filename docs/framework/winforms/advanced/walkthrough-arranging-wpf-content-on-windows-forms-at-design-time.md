---
title: Organizar el contenido de WPF en Windows Forms en tiempo de diseño
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5a6b12def45052e117fb149555946ea42d6cd3c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746821"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a>Tutorial: organizar el contenido de WPF en Windows Forms en tiempo de diseño

En este artículo se muestra cómo usar las características de diseño Windows Forms, como la delimitación y las guías de alineación, para organizar controles de Windows Presentation Foundation (WPF).

## <a name="prerequisites"></a>Requisitos previos

Necesita Visual Studio para completar este tutorial.

## <a name="create-the-project"></a>Crear el proyecto

Abra Visual Studio y cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic C# o visual denominado `ArrangeElementHost`.

> [!NOTE]
> Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.

## <a name="create-the-wpf-control"></a>Crear el control WPF

Después de agregar un control WPF al proyecto, puede organizarlo en el formulario.

1. Agregue un nuevo <xref:System.Windows.Controls.UserControl> WPF al proyecto. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, vea [Tutorial: crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.

3. En la ventana **propiedades** , establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> en **200**.

4. Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en **Blue**.

5. Generar el proyecto.

## <a name="host-wpf-controls-in-a-layout-panel"></a>Hospedar controles WPF en un panel de diseño

Puede usar controles WPF en paneles de diseño de la misma forma que usa otros controles de Windows Forms.

1. Abra `Form1` en el Diseñador de Windows Forms.

2. En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> al formulario.

3. En el panel de etiquetas inteligentes del control de <xref:System.Windows.Forms.TableLayoutPanel>, seleccione **quitar última fila**.

4. Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un ancho y alto mayor.

5. En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en la primera celda del control <xref:System.Windows.Forms.TableLayoutPanel>.

   La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.

6. En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear otra instancia en la segunda celda del control <xref:System.Windows.Forms.TableLayoutPanel>.

7. En la ventana **esquema del documento** , seleccione `tableLayoutPanel1`.

8. En la ventana **propiedades** , establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> en **10, 10, 10, 10**.

   Ambos controles <xref:System.Windows.Forms.Integration.ElementHost> cambian de tamaño para ajustarse al nuevo diseño.

## <a name="use-snaplines-to-align-wpf-controls"></a>Usar líneas de ajuste para alinear controles WPF

Las líneas de ajuste permiten alinear fácilmente los controles en un formulario. Puede usar líneas de ajuste para alinear también controles WPF. Para obtener más información, vea [Tutorial: organizar controles en Windows Forms mediante líneas de ajuste](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

1. En el **cuadro de herramientas**, arrastre una instancia de `UserControl1` al formulario y colóquela en el espacio situado debajo del control <xref:System.Windows.Forms.TableLayoutPanel>.

   La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost3`.

2. Use las líneas de ajuste para alinear el borde izquierdo de `elementHost3` con el borde izquierdo del control <xref:System.Windows.Forms.TableLayoutPanel>.

3. Use las líneas de ajuste para ajustar el tamaño de `elementHost3` al mismo ancho que el control <xref:System.Windows.Forms.TableLayoutPanel>.

4. Mueva `elementHost3` hacia el control <xref:System.Windows.Forms.TableLayoutPanel> hasta que aparezca una línea de ajuste central entre los controles.

5. En la ventana **propiedades** , establezca el valor de la propiedad margin en **20, 20, 20, 20**.

6. Aleje `elementHost3` del control <xref:System.Windows.Forms.TableLayoutPanel> hasta que la línea de ajuste central aparezca de nuevo. Ahora, la línea de ajuste central indica un margen de 20.

7. Mueva `elementHost3` hacia la derecha hasta que su margen izquierdo se alinee con el borde izquierdo de `elementHost1`.

8. Cambie el ancho de `elementHost3` hasta que su borde derecho quede alineado con el borde derecho de `elementHost2`.

## <a name="anchor-and-dock-wpf-controls"></a>Delimitar y acoplar controles WPF

La delimitación y el acoplamiento de un control WPF hospedado en un formulario se comportan igual que los de otros controles de Windows Forms.

1. Seleccione `elementHost1`.

2. En la ventana **propiedades** , establezca la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> en **superior, inferior, izquierda, derecha**.

3. Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un tamaño mayor.

   El control `elementHost1` cambia de tamaño para llenar la celda.

4. Seleccione `elementHost2`.

5. En la ventana **propiedades** , establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.

   El control `elementHost2` cambia de tamaño para llenar la celda.

6. Seleccione el control <xref:System.Windows.Forms.TableLayoutPanel>.

7. Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Top>.

8. Seleccione `elementHost3`.

9. Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.

   El control `elementHost3` cambia de tamaño para llenar el espacio restante en el formulario.

10. Cambie de tamaño el formulario.

    Los tres controles <xref:System.Windows.Forms.Integration.ElementHost> ajustan su tamaño correctamente.

    Para obtener más información, vea [Cómo: delimitar y acoplar controles secundarios en un control TableLayoutPanel](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Delimitar y acoplar controles secundarios en un control TableLayoutPanel](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
