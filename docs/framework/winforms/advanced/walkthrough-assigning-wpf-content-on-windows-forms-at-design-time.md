---
title: Seleccionar controles WPF para Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 19f1dfec282b025f5a1fa367ec5fa9a52472c691
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746803"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a>Tutorial: asignar contenido de WPF en Windows Forms en tiempo de diseño

En este artículo se muestra cómo seleccionar los tipos de control de Windows Presentation Foundation (WPF) que desea mostrar en el formulario. Puede seleccionar los tipos de control de WPF que se incluyen en el proyecto.

## <a name="prerequisites"></a>Requisitos previos

Necesita Visual Studio para completar este tutorial.

## <a name="create-the-project"></a>Crear el proyecto

Abra Visual Studio y cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic C# o visual denominado `SelectingWpfContent`.

> [!NOTE]
> Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.

## <a name="create-the-wpf-control-types"></a>Crear los tipos de control WPF

Después de agregar los tipos de control WPF al proyecto, puede hospedarlos en diferentes controles <xref:System.Windows.Forms.Integration.ElementHost>.

1. Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, vea [Tutorial: crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.

3. En la ventana **propiedades** , establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> en **200**.

4. Agregue un control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> al <xref:System.Windows.Controls.UserControl> y establezca el valor de la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> en **contenido hospedado**.

5. Agregue un segundo <xref:System.Windows.Controls.UserControl> de WPF al proyecto. Use el nombre predeterminado del tipo de control, `UserControl2.xaml`.

6. En la ventana **propiedades** , establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> en **200**.

7. Agregue un control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> al <xref:System.Windows.Controls.UserControl> y establezca el valor de la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> en **contenido hospedado 2**.

   > [!NOTE]
   > Por lo general, debería hospedar contenido WPF más sofisticado. El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.

8. Generar el proyecto.

## <a name="select-wpf-controls"></a>Seleccionar controles WPF

Puede asignar contenido de WPF diferente a un control <xref:System.Windows.Forms.Integration.ElementHost>, que ya hospeda contenido.

1. Abra `Form1` en el Diseñador de Windows Forms.

2. En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en el formulario.

   La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.

3. En el panel de etiquetas inteligentes de `elementHost1`, abra la lista desplegable **seleccionar contenido hospedado** .

4. Seleccione **UserControl2** en el cuadro de lista desplegable.

   El control `elementHost1` ahora hospeda una instancia del tipo `UserControl2`.

5. En la ventana **propiedades** , confirme que la propiedad <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> está establecida en **UserControl2**.

6. En el **cuadro de herramientas**, en el grupo **interoperabilidad de WPF** , arrastre un control <xref:System.Windows.Forms.Integration.ElementHost> al formulario.

   El nombre predeterminado del nuevo control es `elementHost2`.

7. En el panel de etiquetas inteligentes de `elementHost2`, abra la lista desplegable **seleccionar contenido hospedado** .

8. Seleccione **UserControl1** en la lista desplegable.

9. El control `elementHost2` ahora hospeda una instancia del tipo `UserControl1`.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
