---
title: 'Tutorial: Estilo WPF contenido'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 07241d41e3fbf270a76bd241765bfa369ee265d5
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646329"
---
# <a name="walkthrough-style-wpf-content"></a>Tutorial: Estilo WPF contenido

En este artículo se muestra cómo aplicar estilos a un control de Windows Presentation Foundation (WPF) hospedado en un formulario Windows Forms.

## <a name="prerequisites"></a>Prerrequisitos

Necesita Visual Studio para completar este tutorial.

## <a name="create-the-project"></a>Creación del proyecto

Abra Visual Studio y cree un nuevo proyecto de aplicación `StylingWpfContent`de formularios Windows Forms en Visual Basic o Visual C. denominado .

> [!NOTE]
> Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.

## <a name="create-the-wpf-control-types"></a>Crear los tipos de control WPFWPF

Después de agregar un tipo de control WPF al proyecto, puede hospedarlo en un control <xref:System.Windows.Forms.Integration.ElementHost>.

1. Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, vea [Tutorial: crear nuevo contenido de WPF en formularios Windows Forms en tiempo](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)de diseño .

2. En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.

3. En la ventana **Propiedades,** establezca <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> el valor de las propiedades y en **200**.

4. Agregue <xref:System.Windows.Controls.Button?displayProperty=nameWithType> un control <xref:System.Windows.Controls.UserControl> al valor y <xref:System.Windows.Controls.ContentControl.Content%2A> establezca el valor de la propiedad en **Cancelar**.

5. Agregue un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> segundo <xref:System.Windows.Controls.UserControl> control al valor <xref:System.Windows.Controls.ContentControl.Content%2A> y establezca el valor de la propiedad en **OK**.

6. Compile el proyecto.

## <a name="apply-a-style-to-a-wpf-control"></a>Aplicar un style a un control WPFWPF

Puede aplicar diferentes estilos a un control WPF para cambiar su apariencia y comportamiento.

1. Abra `Form1` en el Diseñador de Windows Forms.

1. En el **cuadro**de `UserControl1` herramientas , `UserControl1` haga doble clic para crear una instancia del formulario.

   La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.

1. En el panel `elementHost1`de etiquetas inteligentes para , haga clic en **Editar contenido hospedado** en la lista desplegable.

   `UserControl1`Se abre en el Diseñador wpfWPF.

1. En la vista XAML, inserte el código XAML siguiente después de la etiqueta de apertura `<UserControl>`. Este código XAML crea un degradado con un borde de degradado en contraste. Al hacer clic en el control, los degradados cambian para generar el aspecto de un botón presionado. Para obtener más información, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. Aplique `SimpleButton` el estilo definido en el paso anterior al botón `<Button>` Cancelar insertando el siguiente XAML en la etiqueta del botón **Cancelar.**

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   La declaración de botón será similar al siguiente XAML:

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. Compile el proyecto.

1. Abra `Form1` en el Diseñador de Windows Forms.

1. El nuevo estilo se aplica al control de botón.

1. En el menú **Depurar,** seleccione **Iniciar depuración** para ejecutar la aplicación.

1. Haga clic en los botones **Aceptar** y **Cancelar** y vea las diferencias.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
