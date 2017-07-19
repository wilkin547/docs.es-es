---
title: "Tutorial: Aplicar estilos al contenido de WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "interoperabilidad [WDF]"
  - "estilos, contenido WPF"
  - "WPF Designer, aplicar estilos a contenido de WPF"
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Tutorial: Aplicar estilos al contenido de WPF
En este tutorial se muestra cómo aplicar un estilo a un control de Windows Presentation Foundation \(WPF\) hospedado en un Windows Form.  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Crear el proyecto.  
  
-   Crear el tipo de control WPF.  
  
-   Aplicar un estilo al control WPF.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas**.  Para obtener más información, consulte [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## Crear el proyecto  
 El primer paso es crear el proyecto de Windows Forms.  
  
> [!NOTE]
>  Al hospedar contenido de WPF, solo se admiten proyectos de C\# y Visual Basic.  
  
#### Para crear el proyecto  
  
-   Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C\# llamado `SelectingWpfContent`.  
  
## Crear los tipos de control WPF  
 Después de agregar un tipo de control WPF al proyecto, puede hospedarlo en un control <xref:System.Windows.Forms.Integration.ElementHost>.  
  
#### Para crear tipos de control WPF  
  
1.  Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución.  Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.  Para obtener más información, consulte [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.  Para obtener más información, consulte [Cómo: Seleccionar y mover elementos en la superficie de diseño](http://msdn.microsoft.com/es-es/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  En la ventana **Propiedades**, establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> en `200`.  
  
4.  Agregue un control <xref:System.Windows.Controls.Button?displayProperty=fullName> al <xref:System.Windows.Controls.UserControl> y establezca el valor de la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> en Cancel.  
  
5.  Agregue un segundo control <xref:System.Windows.Controls.Button?displayProperty=fullName> al <xref:System.Windows.Controls.UserControl> y establezca el valor de la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> en Aceptar.  
  
6.  Compile el proyecto.  
  
## Aplicar un estilo a un control WPF  
 Puede aplicar diferentes estilos a un control WPF para cambiar su apariencia y comportamiento.  
  
#### Para aplicar un estilo a un control WPF  
  
1.  Abra `Form1` en el Diseñador de Windows Forms.  
  
2.  En el **Cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en el formulario.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.  
  
3.  En el panel de etiquetas inteligentes de `elementHost1`, haga clic en **Editar contenido hospedado** en la lista desplegable.  
  
     `UserControl1` se abre en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  En la vista XAML, inserte el código XAML siguiente después de la etiqueta de apertura `<UserControl>`.  
  
     Este código XAML crea un degradado con un borde de degradado en contraste.  Al hacer clic en el control, los degradados cambian para generar el aspecto de un botón presionado.  Para obtener más información, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
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
  
1.  Aplique el estilo `SimpleButton` definido en el paso anterior al botón Cancelar insertando el código XAML siguiente en la etiqueta `<Button>` del botón Cancelar.  
  
    ```  
    Style="{StaticResource SimpleButton}  
    ```  
  
     La declaración del botón será similar al código XAML siguiente.  
  
```xaml  
<Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"  
                Style="{StaticResource SimpleButton}">Cancel</Button>  
```  
  
1.  Compile el proyecto.  
  
2.  Abra `Form1` en el Diseñador de Windows Forms.  
  
3.  El nuevo estilo se aplica al control de botón.  
  
4.  En el menú **Depurar**, seleccione **Iniciar depuración** para ejecutar la aplicación.  
  
5.  Haga clic en los botones Aceptar y Cancelar y vea las diferencias.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)