---
title: "Tutorial: Crear un bot&#243;n mediante el uso de XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "botones"
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Tutorial: Crear un bot&#243;n mediante el uso de XAML
El objetivo de este tutorial es aprender a crear un botón animado para usarlo en una aplicación [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  Este tutorial utiliza estilos y una plantilla para crear un recurso de botón personalizado que permite la reutilización de código y la separación de la lógica del botón de la declaración del botón.  Este tutorial está escrito completamente en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
> [!IMPORTANT]
>  Este tutorial sirve como guía en los pasos necesarios para crear la aplicación escribiendo, o copiando y pegando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  Si prefiere aprender a usar una herramienta de diseño \(Microsoft Expression Blend\) para crear la misma aplicación, vea [Crear un botón mediante Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).  
  
 La figura siguiente muestra los botones acabados.  
  
 ![Botones personalizados creados mediante XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.png "custom\_button\_AnimatedButton\_5")  
  
## Crear botones básicos  
 Empecemos por crear un nuevo proyecto y agregar unos botones a la ventana.  
  
#### Para crear un nuevo proyecto de WPF y agregar botones a la ventana  
  
1.  Inicie [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  
  
2.  **Cree un nuevo proyecto de WPF:** En el menú **Archivo**, señale a **Nuevo** y, a continuación, haga clic en **Proyecto**.  Busque la plantilla **Aplicación para Windows \(WPF\)** y asigne al proyecto el nombre "AnimatedButton".  Esto creará el esqueleto para la aplicación.  
  
3.  **Agregue los botones predeterminados básicos:** la plantilla proporciona todos los archivos que necesita para este tutorial.  Abra el archivo Window1.xaml haciendo doble clic en él en el Explorador de soluciones.  De forma predeterminada, hay un elemento <xref:System.Windows.Controls.Grid> en Window1.xaml.  Quite el elemento <xref:System.Windows.Controls.Grid> y agregue unos botones a la página [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] escribiendo o copiando y pegando el siguiente código resaltado en Window1.xaml:  
  
    ```  
    <Window x:Class="AnimatedButton.Window1"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      Title="AnimatedButton" Height="300" Width="300"   
      Background="Black">  
  
      <!-- Buttons arranged vertically inside a StackPanel. -->  
      <StackPanel HorizontalAlignment="Left">  
        <Button>Button 1</Button>  
        <Button>Button 2</Button>  
        <Button>Button 3</Button>  
      </StackPanel>  
  
    </Window>  
    ```  
  
     Presione F5 para ejecutar la aplicación; debería ver un conjunto de botones parecido a la ilustración siguiente.  
  
     ![Tres botones básicos](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.png "custom\_button\_AnimatedButton\_1")  
  
     Ahora que ha creado los botones básicos, ha terminado de trabajar en el archivo Window1.xaml.  El resto del tutorial se centra en el archivo app.xaml, definiendo estilos y una plantilla para los botones.  
  
## Establecer propiedades básicas  
 A continuación, establezcamos algunas propiedades de estos botones para controlar su aspecto y su diseño.  En lugar de establecer individualmente las propiedades de los botones, utilizará recursos para definir las propiedades de botón de toda la aplicación.  Los recursos de aplicación son conceptualmente similares a [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] externas para páginas web; sin embargo, los recursos son mucho más eficaces que [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], como verá al final de este tutorial.  Para obtener más información sobre los recursos, vea [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
#### Para utilizar estilos para establecer propiedades básicas en los botones  
  
1.  **Defina un bloque Application.Resources:** abra app.xaml y agregue el marcado resaltado siguiente si aún no está allí:  
  
    ```  
    <Application x:Class="AnimatedButton.App"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      StartupUri="Window1.xaml"  
      >  
      <Application.Resources>  
  
        <!-- Resources for the entire application can be   
             defined here. -->  
  
      </Application.Resources>  
    </Application>  
    ```  
  
     El ámbito del recurso lo determina dónde se defina el recurso.  Definir recursos en `Application.Resoureses` en el archivo app.xaml permite utilizar el recurso en cualquier parte de la aplicación.  Para obtener más información sobre cómo definir el ámbito de los recursos, vea [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
2.  **Cree un estilo y defina los valores de propiedad básicos con él:** agregue el marcado siguiente al bloque `Application.Resources`.  Este marcado crea un objeto <xref:System.Windows.Style> que se aplica a todos los botones de la aplicación, estableciendo la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de los botones en 90 y <xref:System.Windows.FrameworkElement.Margin%2A> en 10:  
  
    ```  
    <Application.Resources>  
  
      <Style TargetType="Button">  
        <Setter Property="Width" Value="90" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
  
    </Application.Resources>  
    ```  
  
     La propiedad <xref:System.Windows.Style.TargetType%2A> especifica que el estilo se aplica a todos los objetos de tipo <xref:System.Windows.Controls.Button>.  Cada <xref:System.Windows.Setter> establece un valor de propiedad diferente para el objeto <xref:System.Windows.Style>.  Por tanto, en este punto cada botón de la aplicación tiene un ancho de 90 y un margen de 10.  Si presiona F5 para ejecutar la aplicación, verá la siguiente ventana.  
  
     ![Botones con un ancho de 90 y un margen de 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.png "custom\_button\_AnimatedButton\_2")  
  
     Hay mucho más que puede hacer con estilos, incluidas diversas maneras de ajustar con precisión a qué objetos se destinan, especificar valores de propiedad complejos e incluso utilizar estilos como entrada para otros estilos.  Para obtener más información, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
3.  **Establezca un valor de propiedad de estilo en un recurso:** los recursos permiten reutilizar fácilmente objetos y valores que se definen con frecuencia.  Es especialmente útil definir valores complejos utilizando recursos, para hacer el código más modular.  Agregue el marcado resaltado siguiente a app.xaml.  
  
    ```  
    <Application.Resources>  
  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"   
        StartPoint="0,0" EndPoint="1,1">  
        <GradientStop Color="DarkGray" Offset="0" />  
        <GradientStop Color="#CCCCFF" Offset="0.5" />  
        <GradientStop Color="DarkGray" Offset="1" />  
      </LinearGradientBrush>  
  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background"   
          Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
  
    </Application.Resources>  
    ```  
  
     Directamente bajo el bloque `Application.Resources`, creó un recurso llamado "GrayBlueGradientBrush".  Este recurso define un degradado horizontal.  Este recurso se puede utilizar en cualquier parte de la aplicación como un valor de propiedad, incluso dentro del establecedor de estilo del botón para la propiedad <xref:System.Windows.Controls.Control.Background%2A>.  Ahora, todos los botones tienen un valor de propiedad <xref:System.Windows.Controls.Control.Background%2A> de este degradado.  
  
     Presione F5 para ejecutar la aplicación.  Debe tener este aspecto:  
  
     ![Botones con un fondo degradado](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.png "custom\_button\_AnimatedButton\_3")  
  
## Crear una plantilla que define la apariencia del botón  
 En esta sección creará una plantilla que personaliza la apariencia \(presentación\) del botón.  La presentación del botón se compone de varios objetos, que incluyen rectángulos y otros componentes para dar una apariencia única al botón.  
  
 Hasta ahora, el control de la apariencia de los botones de la aplicación se ha confinado a cambiar propiedades del botón.  ¿Qué ocurre si desea realizar cambios más radicales en la apariencia del botón?  Las plantillas permiten un control eficaz sobre la presentación de un objeto.  Dado que las plantillas se pueden utilizar dentro de estilos, puede aplicar una plantilla a todos los objetos a los que se aplica el estilo \(en este tutorial, el botón\).  
  
#### Para utilizar la plantilla para definir la apariencia del botón  
  
1.  **Configure la plantilla:** dado que los controles como <xref:System.Windows.Controls.Button> tienen una propiedad <xref:System.Windows.Controls.Control.Template%2A>, puede definir el valor de la propiedad de la plantilla igual que los demás valores de propiedades que hemos establecido en un objeto <xref:System.Windows.Style>, utilizando un objeto <xref:System.Windows.Setter>.  Agregue el marcado resaltado siguiente al estilo de botón.  
  
    ```  
    <Application.Resources>  
  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"   
        StartPoint="0,0" EndPoint="1,1">  
        <GradientStop Color="DarkGray" Offset="0" />  
        <GradientStop Color="#CCCCFF" Offset="0.5" />  
        <GradientStop Color="DarkGray" Offset="1" />  
      </LinearGradientBrush>  
  
      <Style TargetType="{x:Type Button}">  
      <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
        <Setter Property="Template">  
          <Setter.Value>  
            <!-- The button template is defined here. -->  
          </Setter.Value>  
        </Setter>  
      </Style>  
  
    </Application.Resources>  
    ```  
  
2.  **Modifique la presentación del botón:** en este punto, debe definir la plantilla.  Agregue el siguiente marcado resaltado:  Este marcado especifica dos elementos <xref:System.Windows.Shapes.Rectangle> con bordes redondeados, seguidos por un control <xref:System.Windows.Controls.DockPanel>.  El control <xref:System.Windows.Controls.DockPanel> se utiliza para hospedar el objeto <xref:System.Windows.Controls.ContentPresenter> del botón.  Un objeto <xref:System.Windows.Controls.ContentPresenter> muestra el contenido del botón.  En este tutorial, el contenido es texto \("Button 1", "Button 2", "Button 3"\).  Todos los componentes de la plantilla \(los rectángulos y el control <xref:System.Windows.Controls.DockPanel>\) se disponen dentro de un control <xref:System.Windows.Controls.Grid>.  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="Button">  
        <Grid Width="{TemplateBinding Width}"   
         Height="{TemplateBinding Height}" ClipToBounds="True">  
  
          <!-- Outer Rectangle with rounded corners. -->  
          <Rectangle x:Name="outerRectangle"   
            HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch"   
            Stroke="{TemplateBinding Background}"   
            RadiusX="20" RadiusY="20" StrokeThickness="5"   
            Fill="Transparent" />  
  
          <!-- Inner Rectangle with rounded corners. -->  
          <Rectangle x:Name="innerRectangle"   
            HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch" Stroke="Transparent"   
            StrokeThickness="20"   
            Fill="{TemplateBinding Background}"   
            RadiusX="20" RadiusY="20"   />  
  
          <!-- Present Content (text) of the button. -->  
          <DockPanel Name="myContentPresenterDockPanel">  
            <ContentPresenter x:Name="myContentPresenter" Margin="20"   
              Content="{TemplateBinding  Content}"   
              TextBlock.Foreground="Black" />  
          </DockPanel>  
        </Grid>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     Presione F5 para ejecutar la aplicación.  Debe tener este aspecto:  
  
     ![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom\_button\_AnimatedButton\_4")  
  
3.  **Agregue un efecto de vidrio a la plantilla:** a continuación agregará el vidrio.  Primero cree algunos recursos que creen un efecto de degradado de vidrio.  Agregue estos recursos de degradado en cualquier punto del bloque `Application.Resources`:  
  
    ```  
    <Application.Resources>  
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">  
        <GradientStop Color="WhiteSmoke" Offset="0.2" />  
        <GradientStop Color="Transparent" Offset="0.4" />  
        <GradientStop Color="WhiteSmoke" Offset="0.5" />  
        <GradientStop Color="Transparent" Offset="0.75" />  
        <GradientStop Color="WhiteSmoke" Offset="0.9" />  
        <GradientStop Color="Transparent" Offset="1" />  
      </GradientStopCollection>  
  
      <LinearGradientBrush x:Key="MyGlassBrushResource"   
       StartPoint="0,0" EndPoint="1,1" Opacity="0.75"   
       GradientStops="{StaticResource MyGlassGradientStopsResource}" />  
    <!-- Styles and other resources below here. -->  
    ```  
  
     Estos recursos se utilizan como propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> para un rectángulo que insertamos en el control <xref:System.Windows.Controls.Grid> de la plantilla de botón.  Agregue el siguiente marcado resaltado a la plantilla.  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="{x:Type Button}">  
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"  
    ClipToBounds="True">  
  
        <!-- Outer Rectangle with rounded corners. -->  
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"   
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />  
  
        <!-- Inner Rectangle with rounded corners. -->  
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"   
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />  
  
        <!-- Glass Rectangle -->  
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"  
          VerticalAlignment="Stretch"  
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"  
          Fill="{StaticResource MyGlassBrushResource}"  
          RenderTransformOrigin="0.5,0.5">  
          <Rectangle.Stroke>  
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">  
              <LinearGradientBrush.GradientStops>  
                <GradientStop Offset="0.0" Color="LightBlue" />  
                <GradientStop Offset="1.0" Color="Gray" />  
              </LinearGradientBrush.GradientStops>  
            </LinearGradientBrush>  
          </Rectangle.Stroke>  
  
          <!-- These transforms have no effect as they are declared here.   
               The reason the transforms are included is to be targets   
               for animation (see later). -->  
          <Rectangle.RenderTransform>  
            <TransformGroup>  
              <ScaleTransform />  
              <RotateTransform />  
            </TransformGroup>  
          </Rectangle.RenderTransform>  
  
          <!-- A BevelBitmapEffect is applied to give the button a   
               "Beveled" look. -->  
          <Rectangle.BitmapEffect>  
            <BevelBitmapEffect />  
          </Rectangle.BitmapEffect>  
        </Rectangle>  
  
        <!-- Present Text of the button. -->  
        <DockPanel Name="myContentPresenterDockPanel">  
          <ContentPresenter x:Name="myContentPresenter" Margin="20"   
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
        </DockPanel>  
      </Grid>  
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     Observe que la propiedad <xref:System.Windows.UIElement.Opacity%2A> del rectángulo con la propiedad `x:Name` de "glassCube" es 0, por lo que al ejecutar el ejemplo no verá el rectángulo de vidrio superpuesto.  Esto se debe a que agregaremos después a la plantilla los desencadenadores para cuando el usuario interactúe con el botón.  Sin embargo, puede ver la apariencia que tiene ahora el botón cambiando el valor <xref:System.Windows.UIElement.Opacity%2A> a 1 y ejecutando la aplicación.  Vea la ilustración siguiente.  Antes de continuar con el paso siguiente, vuelva a establecer <xref:System.Windows.UIElement.Opacity%2A> en 0.  
  
     ![Botones personalizados creados mediante XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.png "custom\_button\_AnimatedButton\_5")  
  
## Crear la interactividad del botón  
 En esta sección, creará desencadenadores de propiedad y desencadenadores de evento para cambiar valores de propiedad y ejecutar animaciones en respuesta a acciones del usuario tales como mover el puntero del mouse sobre el botón y hacer clic.  
  
 Una manera fácil de agregar interactividad \(entrada de mouse, salida de mouse, clic, etc.\) es definir los desencadenadores dentro de la plantilla o del estilo.  Para crear un objeto <xref:System.Windows.Trigger>, defina una propiedad "condición" tal como: el valor de propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> del botón es igual a `true`.  A continuación, defina establecedores \(acciones\) que tengan lugar cuando la condición de activación sea verdadera.  
  
#### Para crear la interactividad del botón  
  
1.  **Agregue desencadenadores de plantilla:** agregue el marcado resaltado a la plantilla.  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="{x:Type Button}">  
        <Grid Width="{TemplateBinding Width}"   
          Height="{TemplateBinding Height}" ClipToBounds="True">  
  
          <!-- Outer Rectangle with rounded corners. -->  
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"   
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />  
  
          <!-- Inner Rectangle with rounded corners. -->  
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch" Stroke="Transparent"   
            StrokeThickness="20"   
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"   
          />  
  
          <!-- Glass Rectangle -->  
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"  
            VerticalAlignment="Stretch"  
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"  
            Fill="{StaticResource MyGlassBrushResource}"  
            RenderTransformOrigin="0.5,0.5">  
            <Rectangle.Stroke>  
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">  
                <LinearGradientBrush.GradientStops>  
                  <GradientStop Offset="0.0" Color="LightBlue" />  
                  <GradientStop Offset="1.0" Color="Gray" />  
                </LinearGradientBrush.GradientStops>  
              </LinearGradientBrush>  
            </Rectangle.Stroke>  
  
            <!-- These transforms have no effect as they   
                 are declared here.   
                 The reason the transforms are included is to be targets   
                 for animation (see later). -->  
            <Rectangle.RenderTransform>  
              <TransformGroup>  
                <ScaleTransform />  
                <RotateTransform />  
              </TransformGroup>  
            </Rectangle.RenderTransform>  
  
              <!-- A BevelBitmapEffect is applied to give the button a   
                   "Beveled" look. -->  
            <Rectangle.BitmapEffect>  
              <BevelBitmapEffect />  
            </Rectangle.BitmapEffect>  
          </Rectangle>  
  
          <!-- Present Text of the button. -->  
          <DockPanel Name="myContentPresenterDockPanel">  
            <ContentPresenter x:Name="myContentPresenter" Margin="20"   
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
          </DockPanel>  
        </Grid>  
  
        <ControlTemplate.Triggers>  
          <!-- Set action triggers for the buttons and define  
               what the button does in response to those triggers. -->  
        </ControlTemplate.Triggers>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
2.  **Agregue desencadenadores de propiedad:** agregue el marcado resaltado al bloque `ControlTemplate.Triggers`:  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->  
      <Trigger Property="IsMouseOver" Value="True">  
  
        <!-- Below are three property settings that occur when the   
             condition is met (user mouses over button).  -->  
        <!-- Change the color of the outer rectangle when user   
             mouses over it. -->  
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
  
        <!-- Sets the glass opacity to 1, therefore, the   
             glass "appears" when user mouses over it. -->  
        <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />  
  
        <!-- Makes the text slightly blurry as though you   
             were looking at it through blurry glass. -->  
        <Setter Property="ContentPresenter.BitmapEffect"   
          TargetName="myContentPresenter">  
          <Setter.Value>  
            <BlurBitmapEffect Radius="1" />  
          </Setter.Value>  
        </Setter>  
      </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     Presione F5 para ejecutar la aplicación y ver el efecto al pasar el puntero del mouse sobre los botones.  
  
3.  **Agregue un desencadenador de foco:** a continuación, agregaremos algunos establecedores similares para administrar el caso en el que el botón tenga el foco \(por ejemplo, después de que el usuario haga clic en él\).  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->  
      <Trigger Property="IsMouseOver" Value="True">  
  
        <!-- Below are three property settings that occur when the   
             condition is met (user mouses over button).  -->  
        <!-- Change the color of the outer rectangle when user          mouses over it. -->  
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
  
        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->  
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />  
  
        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->  
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">  
          <Setter.Value>  
            <BlurBitmapEffect Radius="1" />  
          </Setter.Value>  
        </Setter>  
      </Trigger>  
      <!-- Set properties when button has focus. -->  
      <Trigger Property="IsFocused" Value="true">  
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />  
        <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
        <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />  
      </Trigger>  
  
    </ControlTemplate.Triggers>  
    ```  
  
     Presione F5 para ejecutar la aplicación y haga clic en uno de los botones.  Observa que el botón permanece resaltado después de hacer clic en él, porque todavía tiene el foco.  Si hace clic en otro botón, el nuevo botón obtendrá el foco mientras el último lo pierde.  
  
4.  **Agregue animaciones para**  <xref:System.Windows.UIElement.MouseEnter> **y** <xref:System.Windows.UIElement.MouseLeave>**:** a continuación, agregamos algunas animaciones a los desencadenadores.  Agregue el marcado siguiente en cualquier punto del bloque `ControlTemplate.Triggers`.  
  
    ```  
  
                    <!-- Animations that start when mouse enters and leaves button. -->  
    <EventTrigger RoutedEvent="Mouse.MouseEnter">  
      <EventTrigger.Actions>  
        <BeginStoryboard Name="mouseEnterBeginStoryboard">  
          <Storyboard>  
  
          <!-- This animation makes the glass rectangle shrink in the X direction. -->  
            <DoubleAnimation Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"  
              By="-0.1" Duration="0:0:0.5" />  
  
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->  
            <DoubleAnimation  
            Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"   
              By="-0.1" Duration="0:0:0.5" />  
          </Storyboard>  
        </BeginStoryboard>  
      </EventTrigger.Actions>  
    </EventTrigger>  
    <EventTrigger RoutedEvent="Mouse.MouseLeave">  
      <EventTrigger.Actions>  
  
        <!-- Stopping the storyboard sets all animated properties back to default. -->  
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />  
      </EventTrigger.Actions>  
    </EventTrigger>  
    ```  
  
     El rectángulo de vidrio se reduce cuando el puntero del mouse pasa sobre el botón y vuelve al tamaño normal cuando el puntero sale.  
  
     Hay dos animaciones que se desencadenan cuando el puntero pasa sobre el botón \(cuando se provoca el evento <xref:System.Windows.UIElement.MouseEnter>\).  Estas animaciones reducen el rectángulo de vidrio a lo largo de los ejes X e Y.  Observe las propiedades de los elementos <xref:System.Windows.Media.Animation.DoubleAnimation>, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  La propiedad <xref:System.Windows.Media.Animation.Timeline.Duration%2A> especifica que la animación se produce durante medio segundo, y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> especifica que el vidrio se reduce un 10%.  
  
     El segundo desencadenador de eventos \(<xref:System.Windows.UIElement.MouseLeave>\) detiene simplemente el primero.  Al detener un objeto <xref:System.Windows.Media.Animation.Storyboard>, todas las propiedades animadas vuelven a sus valores predeterminados.  Por consiguiente, cuando el usuario saca el puntero del botón, el botón vuelve a ser como era antes de que el puntero del mouse pasara sobre el botón.  Para obtener más información acerca de las animaciones, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
5.  **Agregue una animación para cuando se haga clic en el botón:** el paso final es agregar un desencadenador para cuando el usuario haga clic en el botón.  Agregue el marcado siguiente en cualquier punto del bloque `ControlTemplate.Triggers`.  
  
    ```  
  
                    <!-- Animation fires when button is clicked, causing glass to spin.  -->  
    <EventTrigger RoutedEvent="Button.Click">  
      <EventTrigger.Actions>  
        <BeginStoryboard>  
          <Storyboard>  
            <DoubleAnimation Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"   
              By="360" Duration="0:0:0.5" />  
          </Storyboard>  
        </BeginStoryboard>  
      </EventTrigger.Actions>  
    </EventTrigger>  
    ```  
  
     Presione F5 para ejecutar la aplicación y haga clic en uno de los botones.  Al hacer clic en un botón, el rectángulo de vidrio gira sobre sí mismo.  
  
## Resumen  
 En este tutorial, ha realizado los siguientes ejercicios:  
  
-   Ha destinado un objeto <xref:System.Windows.Style> a un tipo de objeto \(<xref:System.Windows.Controls.Button>\).  
  
-   Ha controlado propiedades básicas de los botones en toda la aplicación utilizando el objeto <xref:System.Windows.Style>.  
  
-   Ha creado recursos tales como degradados para utilizarlos para valores de propiedades de los establecedores de <xref:System.Windows.Style>.  
  
-   Ha personalizado la apariencia de botones de toda la aplicación aplicando una plantilla a los botones.  
  
-   Ha personalizado el comportamiento de los botones en respuesta a acciones del usuario \(tales como <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave> y <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\) incluyendo efectos de animación.  
  
## Vea también  
 [Crear un botón mediante Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Información general sobre efectos de imagen](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)