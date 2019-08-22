---
title: 'Tutorial: Asignar contenido de WPF en formularios Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bc5f5e2d8808c0a60df721bf2c0ed76b45ef49a0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666261"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a>Tutorial: Asignar contenido de WPF en Windows Forms en tiempo de diseño

En este artículo se muestra cómo seleccionar los tipos de control de Windows Presentation Foundation (WPF) que desea mostrar en el formulario. Puede seleccionar cualquier tipo de control WPF incluido en su proyecto.

## <a name="prerequisites"></a>Requisitos previos

Necesita Visual Studio para completar este tutorial.

## <a name="create-the-project"></a>Crear el proyecto

Abra Visual Studio y cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic C# o `SelectingWpfContent`en Visual denominado.

> [!NOTE]
> Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.

## <a name="create-the-wpf-control-types"></a>Crear los tipos de control WPF

Después de agregar los tipos de control WPF al proyecto, puede hospedarlos en diferentes controles <xref:System.Windows.Forms.Integration.ElementHost>.

1. Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, vea [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)de diseño.

2. En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.

3. En la ventana **propiedades** , establezca el valor de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y en **200**.

4. Agregue un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> <xref:System.Windows.Controls.UserControl> control a y establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad en **contenido hospedado**.

5. Agregue un segundo <xref:System.Windows.Controls.UserControl> de WPF al proyecto. Use el nombre predeterminado del tipo de control, `UserControl2.xaml`.

6. En la ventana **propiedades** , establezca el valor de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y en **200**.

7. Agregue un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> <xref:System.Windows.Controls.UserControl> control a y establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad en **Hosted Content 2**.

   > [!NOTE]
   > Por lo general, debería hospedar contenido WPF más sofisticado. El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.

8. Compile el proyecto.

## <a name="select-wpf-controls"></a>Seleccionar controles WPF

Puede asignar contenido de WPF diferente a un control <xref:System.Windows.Forms.Integration.ElementHost>, que ya hospeda contenido.

1. Abra `Form1` en el Diseñador de Windows Forms.

2. En el **cuadro de herramientas**, haga `UserControl1` doble clic en para crear `UserControl1` una instancia de en el formulario.

   La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.

3. En el panel de etiquetas inteligentes `elementHost1`de, abra la lista desplegable **seleccionar contenido hospedado** .

4. Seleccione **UserControl2** en el cuadro de lista desplegable.

   El control `elementHost1` ahora hospeda una instancia del tipo `UserControl2`.

5. En la ventana **propiedades** , confirme que la <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> propiedad está establecida en **UserControl2**.

6. En el **cuadro de herramientas**, en el grupo de interoperabilidad <xref:System.Windows.Forms.Integration.ElementHost> de **WPF** , arrastre un control hasta el formulario.

   El nombre predeterminado del nuevo control es `elementHost2`.

7. En el panel de etiquetas inteligentes `elementHost2`de, abra la lista desplegable **seleccionar contenido hospedado** .

8. Seleccione **UserControl1** en la lista desplegable.

9. El control `elementHost2` ahora hospeda una instancia del tipo `UserControl1`.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
