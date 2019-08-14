---
title: 'Tutorial: Aplicar estilos a contenido de WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: 32ca9658ddf4ab6e8690f29797b7ac7b09df2ca7
ms.sourcegitcommit: d98fdb087d9c8aba7d2cb93fe4b4ee35a2308cee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2019
ms.locfileid: "69012959"
---
# <a name="walkthrough-style-wpf-content"></a>Tutorial: Contenido de estilo WPF

En este tutorial se muestra cómo aplicar un estilo a un control de Windows Presentation Foundation (WPF) hospedado en un Windows Form.

 En este tutorial, realizará las tareas siguientes:

- Crear el proyecto.

- Crear el tipo de control WPF.

- Aplicar un estilo al control WPF.

## <a name="prerequisites"></a>Requisitos previos

Necesita Visual Studio para completar este tutorial.

## <a name="create-the-project"></a>Crear el proyecto

Abra Visual Studio y cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic C# o `StylingWpfContent`en Visual denominado.

> [!NOTE]
> Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.

## <a name="create-the-wpf-control-types"></a>Crear los tipos de control WPF

Después de agregar un tipo de control WPF al proyecto, puede hospedarlo en un control <xref:System.Windows.Forms.Integration.ElementHost>.

1. Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, vea [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)de diseño.

2. En la vista Diseño, asegúrese de que `UserControl1` está seleccionado. Para obtener más información, vea [Cómo: Seleccione y mueva los elementos en el](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))superficie de diseño.

3. En la ventana **propiedades** , establezca el valor de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y en `200`.

4. Agregue un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> <xref:System.Windows.Controls.UserControl> control a y establezca el valor de la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad en **Cancelar**.

5. Agregue un segundo <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control <xref:System.Windows.Controls.UserControl> a y establezca el valor de la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad en **OK**.

6. Compile el proyecto.

## <a name="apply-a-style-to-a-wpf-control"></a>Aplicar un estilo a un control WPF

Puede aplicar diferentes estilos a un control WPF para cambiar su apariencia y comportamiento.

1. Abra `Form1` en el Diseñador de Windows Forms.

1. En el **cuadro de herramientas**, haga `UserControl1` doble clic en para crear `UserControl1` una instancia de en el formulario.

     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.

1. En el panel de etiquetas inteligentes `elementHost1`de, haga clic en **editar contenido hospedado** en la lista desplegable.

     `UserControl1` se abre en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

1. En la vista XAML, inserte el código XAML siguiente después de la etiqueta de apertura `<UserControl>`.

     Este código XAML crea un degradado con un borde de degradado en contraste. Al hacer clic en el control, los degradados cambian para generar el aspecto de un botón presionado. Para obtener más información, consulte [Aplicar estilos y plantillas](../../wpf/controls/styling-and-templating.md).

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

1. Aplique el estilo `SimpleButton` definido en el paso anterior al botón Cancelar insertando el código XAML siguiente en la etiqueta `<Button>` del botón Cancelar.

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   La declaración del botón será similar al código XAML siguiente:

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. Compile el proyecto.

1. Abra `Form1` en el Diseñador de Windows Forms.

1. El nuevo estilo se aplica al control de botón.

1. En el menú Depurar, seleccione **iniciar** depuración para ejecutar la aplicación.

1. Haga clic en los botones Aceptar y Cancelar y vea las diferencias.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Información general sobre XAML (WPF)](../../wpf/advanced/xaml-overview-wpf.md)
- [Aplicar estilos y plantillas](../../wpf/controls/styling-and-templating.md)
