---
title: 'Tutorial: Crear un botón mediante el uso de XAML'
description: Use este tutorial para aprender a crear un botón animado para usarlo en una aplicación Windows Presentation Foundation mediante XAML.
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 136d1ad5d6fefd70f0d977e5287ae75f06c52d36
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164849"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Tutorial: Crear un botón mediante el uso de XAML

El objetivo de este tutorial es aprender a crear un botón animado para usarlo en una aplicación Windows Presentation Foundation (WPF). En este tutorial se usan estilos y una plantilla para crear un recurso de botón personalizado que permite la reutilización del código y la separación de la lógica del botón desde la declaración del botón. Este tutorial se ha escrito en su totalidad en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .

> [!IMPORTANT]
> Este tutorial le guía a través de los pasos necesarios para crear la aplicación escribiendo o copiando y pegando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en Visual Studio. Si prefiere obtener información sobre cómo usar un diseñador para crear la misma aplicación, vea [crear un botón mediante Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).

En la ilustración siguiente se muestran los botones terminados.

![Botones personalizados creados mediante XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-basic-buttons"></a>Crear botones básicos

Comencemos por crear un nuevo proyecto y agregando algunos botones a la ventana.

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>Para crear un nuevo proyecto de WPF y agregar botones a la ventana

1. Inicie Visual Studio.

2. **Cree un nuevo proyecto de WPF:** En el menú **archivo** , seleccione **nuevo**y, a continuación, haga clic en **proyecto**. Busque la plantilla **aplicación para Windows (WPF)** y asigne al proyecto el nombre "AnimatedButton". Esto creará el esqueleto de la aplicación.

3. **Agregar botones predeterminados básicos:** Todos los archivos que necesita para este tutorial se proporcionan en la plantilla. Haga doble clic en el archivo Window1. XAML para abrirlo en Explorador de soluciones. De forma predeterminada, hay un <xref:System.Windows.Controls.Grid> elemento en Window1. Xaml. Quite el <xref:System.Windows.Controls.Grid> elemento y agregue algunos botones a la página; para [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ello, escriba o copie y pegue el siguiente código resaltado en Window1. XAML:

    ```xaml
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

     Presione F5 para ejecutar la aplicación; debería ver un conjunto de botones que se parece a la siguiente ilustración.

     ![Tres botones básicos](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")

     Ahora que ha creado los botones básicos, ha terminado de trabajar en el archivo Window1. Xaml. El resto del tutorial se centra en el archivo app. XAML, lo que define los estilos y una plantilla para los botones.

## <a name="set-basic-properties"></a>Establecer propiedades básicas

A continuación, vamos a establecer algunas propiedades en estos botones para controlar la apariencia y el diseño del botón. En lugar de establecer las propiedades de los botones individualmente, usará los recursos para definir las propiedades del botón para toda la aplicación. Los recursos de la aplicación son conceptualmente similares a los Hojas de estilo CSS externos (CSS) para las páginas Web. sin embargo, los recursos son mucho más eficaces que Hojas de estilo CSS (CSS), como verá al final de este tutorial. Para obtener más información sobre los recursos, vea [recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>Para usar estilos para establecer las propiedades básicas de los botones

1. **Defina un bloque Application. Resources:** Abra app. XAML y agregue el siguiente marcado resaltado si aún no está ahí:

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     El ámbito del recurso está determinado por la ubicación en la que se define el recurso. La definición de recursos en `Application.Resources` en el archivo app. Xaml permite que el recurso se use desde cualquier parte de la aplicación. Para obtener más información sobre cómo definir el ámbito de los recursos, vea [recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

2. **Cree un estilo y defina los valores de propiedad básicos con él:** Agregue el marcado siguiente al `Application.Resources` bloque. Este marcado crea un <xref:System.Windows.Style> que se aplica a todos los botones de la aplicación, estableciendo el <xref:System.Windows.FrameworkElement.Width%2A> de los botones en 90 y <xref:System.Windows.FrameworkElement.Margin%2A> en 10:

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     La <xref:System.Windows.Style.TargetType%2A> propiedad especifica que el estilo se aplica a todos los objetos de tipo <xref:System.Windows.Controls.Button> . Cada <xref:System.Windows.Setter> establece un valor de propiedad diferente para <xref:System.Windows.Style> . Por lo tanto, en este punto, cada botón de la aplicación tiene un ancho de 90 y un margen de 10.  Si presiona F5 para ejecutar la aplicación, verá la siguiente ventana.

     ![Botones con un ancho de 90 y un margen de 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")

     Hay mucho más que puede hacer con los estilos, como una variedad de formas de ajustar los objetos de destino, especificar valores de propiedad complejos e incluso usar estilos como entrada para otros estilos. Para obtener más información, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

3. **Establezca un valor de propiedad de estilo en un recurso:** Los recursos permiten una forma sencilla de reutilizar objetos y valores definidos comúnmente. Es especialmente útil definir valores complejos mediante recursos para que el código sea más modular. Agregue el siguiente marcado resaltado a app. Xaml.

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     Directamente en el `Application.Resources` bloque, ha creado un recurso denominado "GrayBlueGradientBrush". Este recurso define un degradado horizontal. Este recurso se puede usar como un valor de propiedad desde cualquier parte de la aplicación, incluso dentro del establecedor de estilo de botón para la <xref:System.Windows.Controls.Control.Background%2A> propiedad. Ahora, todos los botones tienen un <xref:System.Windows.Controls.Control.Background%2A> valor de propiedad de este degradado.

     Presione F5 para ejecutar la aplicación. Debería tener un aspecto similar al siguiente.

     ![Botones con un fondo degradado](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")

## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Crear una plantilla que defina el aspecto del botón

En esta sección, creará una plantilla que personaliza la apariencia (presentación) del botón. La presentación del botón se compone de varios objetos, incluidos los rectángulos y otros componentes, para dar al botón una apariencia única.

Hasta ahora, el control de cómo se muestran los botones en la aplicación se ha limitado a cambiar las propiedades del botón. ¿Qué ocurre si desea realizar cambios más radicales en la apariencia del botón? Las plantillas permiten un control eficaz sobre la presentación de un objeto. Dado que las plantillas se pueden usar dentro de los estilos, puede aplicar una plantilla a todos los objetos a los que se aplica el estilo (en este tutorial, el botón).

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>Para usar la plantilla para definir el aspecto del botón

1. **Configure la plantilla:** Dado que los controles como <xref:System.Windows.Controls.Button> tienen una <xref:System.Windows.Controls.Control.Template%2A> propiedad, puede definir el valor de la propiedad de plantilla de la misma manera que los demás valores de propiedad que hemos establecido en un <xref:System.Windows.Style> mediante <xref:System.Windows.Setter> . Agregue el siguiente marcado resaltado al estilo de botón.

    ```xaml
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

2. **Presentación del botón modificar:** En este punto, debe definir la plantilla. Agregue el siguiente marcado resaltado. Este marcado especifica dos <xref:System.Windows.Shapes.Rectangle> elementos con bordes redondeados, seguidos de un <xref:System.Windows.Controls.DockPanel> . <xref:System.Windows.Controls.DockPanel>Se utiliza para hospedar el <xref:System.Windows.Controls.ContentPresenter> del botón. <xref:System.Windows.Controls.ContentPresenter>Muestra el contenido del botón. En este tutorial, el contenido es texto ("botón 1", "botón 2", "botón 3"). Todos los componentes de plantilla (los rectángulos y <xref:System.Windows.Controls.DockPanel> ) se colocan dentro de un <xref:System.Windows.Controls.Grid> .

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     Presione F5 para ejecutar la aplicación. Debería tener un aspecto similar al siguiente.

     ![Ventana con 3 botones](./media/custom-button-animatedbutton-4.gif)

3. **Agregue un glasseffect a la plantilla:** A continuación, agregará el cristal. En primer lugar, cree algunos recursos que creen un efecto de degradado de cristal. Agregue estos recursos de degradado en cualquier parte del `Application.Resources` bloque:

    ```xaml
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

     Estos recursos se utilizan como <xref:System.Windows.Shapes.Shape.Fill%2A> para un rectángulo que se inserta en <xref:System.Windows.Controls.Grid> de la plantilla de botón. Agregue el siguiente marcado resaltado a la plantilla.

    ```xaml
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
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
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

     Observe que el <xref:System.Windows.UIElement.Opacity%2A> del rectángulo con la `x:Name` propiedad de "glassCube" es 0, por lo que, al ejecutar el ejemplo, no verá el rectángulo de cristal superpuesto en la parte superior. Esto se debe a que más adelante se agregarán desencadenadores a la plantilla para cuando el usuario interactúe con el botón. Sin embargo, puede ver el aspecto del botón ahora cambiando el <xref:System.Windows.UIElement.Opacity%2A> valor a 1 y ejecutando la aplicación. Consulte la siguiente figura. Antes de continuar con el paso siguiente, cambie el <xref:System.Windows.UIElement.Opacity%2A> valor de nuevo a 0.

     ![Botones personalizados creados mediante XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-button-interactivity"></a>Crear interactividad del botón

En esta sección, creará desencadenadores de propiedades y desencadenadores de eventos para cambiar los valores de propiedad y ejecutar animaciones en respuesta a las acciones del usuario, como mover el puntero del mouse sobre el botón y hacer clic en.

Una manera fácil de agregar interactividad (pasar el mouse sobre, salir del mouse, hacer clic, etc.) es definir desencadenadores dentro de la plantilla o el estilo. Para crear una <xref:System.Windows.Trigger> , defina una "condición" de propiedad como: el valor de la <xref:System.Windows.UIElement.IsMouseOver%2A> propiedad Button es igual a `true` . A continuación, defina los establecedores (acciones) que tienen lugar cuando se cumple la condición del desencadenador.

### <a name="to-create-button-interactivity"></a>Para crear interactividad del botón

1. **Agregar desencadenadores de plantilla:** Agregue el marcado resaltado a la plantilla.

    ```xaml
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

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. **Agregar desencadenadores de propiedad:** Agregue el marcado resaltado al `ControlTemplate.Triggers` bloque:

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     Presione F5 para ejecutar la aplicación y ver el efecto al ejecutar el puntero del mouse sobre los botones.

3. **Agregar un desencadenador de foco:** A continuación, agregaremos algunos establecedores similares para controlar el caso cuando el botón tenga el foco (por ejemplo, después de que el usuario haga clic en él).

    ```xaml
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
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     Presione F5 para ejecutar la aplicación y haga clic en uno de los botones. Tenga en cuenta que el botón permanece resaltado después de hacer clic en él porque todavía tiene el foco. Si hace clic en otro botón, el nuevo botón gana el foco mientras el último lo pierde.

4. **Agregar animaciones para** <xref:System.Windows.UIElement.MouseEnter> **y** <xref:System.Windows.UIElement.MouseLeave> **:** A continuación, se agregan algunas animaciones a los desencadenadores.   Agregue el siguiente marcado en cualquier parte dentro del `ControlTemplate.Triggers` bloque.

    ```xaml
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

     El rectángulo Glass se reduce cuando el puntero del mouse se mueve sobre el botón y vuelve al tamaño normal cuando el puntero sale.

     Hay dos animaciones que se desencadenan cuando el puntero pasa por encima del botón ( <xref:System.Windows.UIElement.MouseEnter> se genera el evento). Estas animaciones reducen el rectángulo de cristal a lo largo del eje X e y. Observe las propiedades de los <xref:System.Windows.Media.Animation.DoubleAnimation> elementos, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> . <xref:System.Windows.Media.Animation.Timeline.Duration%2A>Especifica que la animación se produce más de medio segundo y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> especifica que el cristal se reduce en un 10%.

     El segundo desencadenador de eventos ( <xref:System.Windows.UIElement.MouseLeave> ) simplemente detiene el primero. Al detener <xref:System.Windows.Media.Animation.Storyboard> , todas las propiedades animadas vuelven a sus valores predeterminados. Por lo tanto, cuando el usuario mueve el puntero sobre el botón, el botón vuelve a la manera en que estaba antes de que se moviera el puntero del mouse sobre el botón. Para obtener más información sobre las animaciones, vea [información general sobre animaciones](../graphics-multimedia/animation-overview.md).

5. **Agregue una animación para cuando se haga clic en el botón:** El paso final consiste en agregar un desencadenador para cuando el usuario haga clic en el botón. Agregue el siguiente marcado en cualquier parte dentro del `ControlTemplate.Triggers` bloque:

    ```xaml
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

     Presione F5 para ejecutar la aplicación y haga clic en uno de los botones. Al hacer clic en un botón, el rectángulo de cristal gira alrededor.

## <a name="summary"></a>Resumen
 En este tutorial, ha realizado los ejercicios siguientes:

- Se destina <xref:System.Windows.Style> a un tipo de objeto ( <xref:System.Windows.Controls.Button> ).

- Propiedades básicas controladas de los botones de toda la aplicación mediante <xref:System.Windows.Style> .

- Se crearon recursos como degradados que se van a usar para los valores de propiedad de los <xref:System.Windows.Style> establecedores.

- Personalizar el aspecto de los botones de toda la aplicación aplicando una plantilla a los botones.

- Comportamiento personalizado de los botones en respuesta a las acciones del usuario (como <xref:System.Windows.UIElement.MouseEnter> , <xref:System.Windows.UIElement.MouseLeave> y <xref:System.Windows.Controls.Primitives.ButtonBase.Click> ) que incluyen efectos de animación.

## <a name="see-also"></a>Consulte también

- [Crear un botón mediante Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Información general sobre animaciones](../graphics-multimedia/animation-overview.md)
- [Información general sobre el dibujo con colores sólidos y degradados](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Información general sobre efectos de imagen](../graphics-multimedia/bitmap-effects-overview.md)
