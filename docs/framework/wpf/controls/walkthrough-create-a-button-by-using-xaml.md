---
title: 'Tutorial: Crear un botón mediante el uso de XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a8cc227703e81e5de9dea7e44e10dfecca2cd05c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646476"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Tutorial: Crear un botón mediante el uso de XAML

El objetivo de este tutorial es aprender a crear un botón animado para su uso en una aplicación de Windows Presentation Foundation (WPF). Este tutorial usa estilos y una plantilla para crear un recurso de botón personalizado que permite la reutilización del código y la separación de la lógica de botón de la declaración de botón. Este tutorial está escrito [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]completamente en .

> [!IMPORTANT]
> Este tutorial le guía a través de los pasos [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para crear la aplicación escribiendo o copiando y pegando en Visual Studio. Si prefiere aprender a usar un diseñador para crear la misma aplicación, consulte [Crear un botón mediante Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).

La figura siguiente muestra los botones terminados.

![Botones personalizados creados mediante XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-basic-buttons"></a>Crear botones básicos

Comencemos creando un nuevo proyecto y agregando algunos botones a la ventana.

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>Para crear un nuevo proyecto WPF y agregar botones a la ventana

1. Inicie Visual Studio.

2. **Cree un nuevo proyecto WPF:** En el menú **Archivo,** seleccione **Nuevo**y, a continuación, haga clic en **Proyecto**. Busque la plantilla **Aplicación de Windows (WPF)** y asigne al proyecto el nombre "AnimatedButton". Esto creará el esqueleto de la aplicación.

3. **Añadir botones predeterminados básicos:** La plantilla proporciona todos los archivos que necesita para este tutorial. Abra el archivo Window1.xaml haciendo doble clic en él en el Explorador de soluciones. De forma predeterminada, <xref:System.Windows.Controls.Grid> hay un elemento en Window1.xaml. Quite <xref:System.Windows.Controls.Grid> el elemento y agregue [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] algunos botones a la página escribiendo o copiando y pegando el siguiente código resaltado en Window1.xaml:

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

     Presione F5 para ejecutar la aplicación; debería ver un conjunto de botones que se parece a la siguiente figura.

     ![Tres botones básicos](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")

     Ahora que ha creado los botones básicos, ha terminado de trabajar en el archivo Window1.xaml. El resto del tutorial se centra en el archivo app.xaml, definiendo estilos y una plantilla para los botones.

## <a name="set-basic-properties"></a>Establecer propiedades básicas

A continuación, vamos a establecer algunas propiedades en estos botones para controlar la apariencia y el diseño del botón. En lugar de establecer propiedades en los botones individualmente, usará recursos para definir propiedades de botón para toda la aplicación. Los recursos de aplicación son conceptualmente similares a las hojas de estilos en cascada (CSS) externas para páginas Web; sin embargo, los recursos son mucho más eficaces que las hojas de estilos en cascada (CSS), como verá al final de este tutorial. Para obtener más información sobre los recursos, vea [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>Usar estilos para establecer propiedades básicas en los botones

1. **Defina un bloque Application.Resources:** Abra app.xaml y agregue el siguiente marcado resaltado si aún no está allí:

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

     El ámbito de recursos viene determinado por el lugar donde se define el recurso. La definición `Application.Resources` de recursos en el archivo app.xaml permite usar el recurso desde cualquier lugar de la aplicación. Para obtener más información sobre cómo definir el ámbito de los recursos, vea [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

2. **Cree un estilo y defina valores de propiedad básicos con él:** Agregue el siguiente `Application.Resources` marcado al bloque. Este marcado <xref:System.Windows.Style> crea un que se aplica a <xref:System.Windows.FrameworkElement.Width%2A> todos los botones <xref:System.Windows.FrameworkElement.Margin%2A> de la aplicación, estableciendo los botones en 90 y 10:

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     La <xref:System.Windows.Style.TargetType%2A> propiedad especifica que el estilo se <xref:System.Windows.Controls.Button>aplica a todos los objetos de tipo . Cada <xref:System.Windows.Setter> uno establece un <xref:System.Windows.Style>valor de propiedad diferente para el archivo . Por lo tanto, en este punto cada botón de la aplicación tiene un ancho de 90 y un margen de 10.  Si presiona F5 para ejecutar la aplicación, verá la siguiente ventana.

     ![Botones con un ancho de 90 y un margen de 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")

     Hay mucho más que puede hacer con los estilos, incluida una variedad de formas de ajustar los objetos de destino, especificar valores de propiedad complejos e incluso usar estilos como entrada para otros estilos. Para obtener más información, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

3. Establezca un valor de propiedad de estilo en **un recurso:** Los recursos permiten una forma sencilla de reutilizar los objetos y valores definidos con frecuencia. Es especialmente útil definir valores complejos mediante recursos para que el código sea más modular. Agregue el siguiente marcado resaltado a app.xaml.

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

     Directamente `Application.Resources` debajo del bloque, ha creado un recurso denominado "GrayBlueGradientBrush". Este recurso define un degradado horizontal. Este recurso se puede usar como un valor de propiedad desde cualquier <xref:System.Windows.Controls.Control.Background%2A> lugar de la aplicación, incluido dentro del establecedor de estilo de botón para la propiedad. Ahora, todos los <xref:System.Windows.Controls.Control.Background%2A> botones tienen un valor de propiedad de este degradado.

     Presione F5 para ejecutar la aplicación. Debería parecerse a lo siguiente.

     ![Botones con un fondo degradado](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")

## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Crear una plantilla que defina el aspecto del botón

En esta sección, creará una plantilla que personalice la apariencia (presentación) del botón. La presentación del botón se compone de varios objetos, incluidos rectángulos y otros componentes para dar al botón un aspecto único.

Hasta ahora, el control de cómo se ven los botones en la aplicación se ha limitado a cambiar las propiedades del botón. ¿Qué pasa si quieres hacer cambios más radicales en la apariencia del botón? Las plantillas permiten un control eficaz sobre la presentación de un objeto. Dado que las plantillas se pueden usar dentro de estilos, puede aplicar una plantilla a todos los objetos a los que se aplica el estilo (en este tutorial, el botón).

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>Utilizar la plantilla para definir el aspecto del botón

1. **Configure la plantilla:** Dado que <xref:System.Windows.Controls.Button> los <xref:System.Windows.Controls.Control.Template%2A> controles como tienen una propiedad, puede definir el valor <xref:System.Windows.Style> de <xref:System.Windows.Setter>propiedad de plantilla al igual que los otros valores de propiedad que hemos establecido en un using a . Agregue el siguiente marcado resaltado al estilo de botón.

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

2. **Modificar la presentación del botón:** En este punto, debe definir la plantilla. Agregue el siguiente marcado resaltado. Este marcado especifica <xref:System.Windows.Shapes.Rectangle> dos elementos con <xref:System.Windows.Controls.DockPanel>bordes redondeados, seguidos de un archivo . Se <xref:System.Windows.Controls.DockPanel> utiliza para <xref:System.Windows.Controls.ContentPresenter> alojar el botón. A <xref:System.Windows.Controls.ContentPresenter> muestra el contenido del botón. En este tutorial, el contenido es texto ("Botón 1", "Botón 2", "Botón 3"). Todos los componentes de la <xref:System.Windows.Controls.DockPanel>plantilla (los rectángulos <xref:System.Windows.Controls.Grid>y el ) se colocan dentro de un archivo .

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

     Presione F5 para ejecutar la aplicación. Debería parecerse a lo siguiente.

     ![Ventana con 3 botones](./media/custom-button-animatedbutton-4.gif)

3. **Agregue un efecto de vidrio a la plantilla:** A continuación, añadirá el vidrio. En primer lugar, cree algunos recursos que creen un efecto de degradado de vidrio. Agregue estos recursos de `Application.Resources` degradado en cualquier lugar dentro del bloque:

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

     Estos recursos se <xref:System.Windows.Shapes.Shape.Fill%2A> utilizan como para un <xref:System.Windows.Controls.Grid> rectángulo que insertamos en la plantilla de botón. Agregue el siguiente marcado resaltado a la plantilla.

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

     Observe que <xref:System.Windows.UIElement.Opacity%2A> el rectángulo `x:Name` del rectángulo con la propiedad de "glassCube" es 0, por lo que al ejecutar la muestra, no verá el rectángulo de vidrio superpuesto en la parte superior. Esto se debe a que más adelante agregaremos desencadenadores a la plantilla para cuando el usuario interactúe con el botón. Sin embargo, puede ver cómo se <xref:System.Windows.UIElement.Opacity%2A> ve el botón ahora cambiando el valor a 1 y ejecutando la aplicación. Consulte la siguiente figura. Antes de continuar con el <xref:System.Windows.UIElement.Opacity%2A> paso siguiente, cambie la parte posterior a 0.

     ![Botones personalizados creados mediante XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-button-interactivity"></a>Crear interactividad de botones

En esta sección, creará desencadenadores de propiedades y desencadenadores de eventos para cambiar los valores de propiedad y ejecutar animaciones en respuesta a acciones del usuario, como mover el puntero del mouse sobre el botón y hacer clic.

Una manera fácil de agregar interactividad (ratón sobre, mouse-leave, clic, etc.) es definir desencadenadores dentro de su plantilla o estilo. Para crear <xref:System.Windows.Trigger>un , se define una propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> "condición" `true`como: El valor de la propiedad button es igual a . A continuación, defina los establecedores (acciones) que tienen lugar cuando la condición de desencadenador es true.

### <a name="to-create-button-interactivity"></a>Para crear interactividad de botones

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

2. **Agregar desencadenadores** de propiedad: Agregue el marcado resaltado `ControlTemplate.Triggers` al bloque:

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     Presione F5 para ejecutar la aplicación y ver el efecto al ejecutar el puntero del ratón sobre los botones.

3. **Agregue un desencadenador** de foco: A continuación, agregaremos algunos establecedores similares para controlar el caso cuando el botón tenga el foco (por ejemplo, después de que el usuario haga clic en él).

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

     Presione F5 para ejecutar la aplicación y haga clic en uno de los botones. Tenga en cuenta que el botón permanece resaltado después de hacer clic en él porque todavía tiene el foco. Si hace clic en otro botón, el nuevo botón gana el foco mientras que el último lo pierde.

4. **Añadir animaciones para** <xref:System.Windows.UIElement.MouseEnter> **y** <xref:System.Windows.UIElement.MouseLeave> **:** A continuación, añadimos algunas animaciones a los desencadenadores.   Agregue el siguiente marcado `ControlTemplate.Triggers` en cualquier lugar dentro del bloque.

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

     El rectángulo de vidrio se reduce cuando el puntero del mouse se mueve sobre el botón y vuelve al tamaño normal cuando el puntero sale.

     Hay dos animaciones que se desencadenan cuando<xref:System.Windows.UIElement.MouseEnter> el puntero pasa por encima del botón (se genera el evento). Estas animaciones reducen el rectángulo de cristal a lo largo del eje X e Y. Observe las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation> de <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>los elementos y . Especifica <xref:System.Windows.Media.Animation.Timeline.Duration%2A> que la animación se produce <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> durante medio segundo y especifica que el vidrio se reduce en un 10%.

     El segundo desencadenador<xref:System.Windows.UIElement.MouseLeave>de evento ( ) simplemente detiene el primero. Cuando se <xref:System.Windows.Media.Animation.Storyboard>detiene un , todas las propiedades animadas vuelven a sus valores predeterminados. Por lo tanto, cuando el usuario mueve el puntero fuera del botón, el botón vuelve a la forma en que estaba antes de que el puntero del mouse se moviera sobre el botón. Para obtener más información acerca de las animaciones, vea [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).

5. **Agregue una animación para cuando se haga clic en el botón:** El último paso es agregar un desencadenador para cuando el usuario hace clic en el botón. Agregue el siguiente marcado `ControlTemplate.Triggers` en cualquier lugar dentro del bloque:

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

     Presione F5 para ejecutar la aplicación y haga clic en uno de los botones. Al hacer clic en un botón, el rectángulo de vidrio gira alrededor.

## <a name="summary"></a>Resumen
 En este tutorial, ha realizado los siguientes ejercicios:

- Dirigido <xref:System.Windows.Style> a un tipo<xref:System.Windows.Controls.Button>de objeto ( ).

- Propiedades básicas controladas de los botones de toda la aplicación mediante el <xref:System.Windows.Style>archivo .

- Se han creado recursos como degradados <xref:System.Windows.Style> que se usan para los valores de propiedad de los establecedores.

- Se ha personalizado el aspecto de los botones de toda la aplicación aplicando una plantilla a los botones.

- Comportamiento personalizado de los botones en <xref:System.Windows.UIElement.MouseEnter>respuesta <xref:System.Windows.UIElement.MouseLeave>a <xref:System.Windows.Controls.Primitives.ButtonBase.Click>las acciones del usuario (como , , y ) que incluían efectos de animación.

## <a name="see-also"></a>Consulte también

- [Crear un botón mediante Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Información general sobre animaciones](../graphics-multimedia/animation-overview.md)
- [Información general sobre el dibujo con colores sólidos y degradados](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Información general sobre efectos de imagen](../graphics-multimedia/bitmap-effects-overview.md)
