---
title: "Tutorial: Crear un botón mediante el uso de XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c5efa9f8787e65d59e1b544632e806bf3fbbc81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Tutorial: Crear un botón mediante el uso de XAML
El objetivo de este tutorial es aprender a crear un botón animado para su uso en un [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] aplicación. En este tutorial usa estilos y una plantilla para crear un recurso de botón personalizado que permite la reutilización del código y la separación de la lógica de botón de la declaración del botón. En este tutorial se escribe completamente en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
> [!IMPORTANT]
>  Este tutorial le guía a través de los pasos para crear la aplicación escribiendo o copiando y pegando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Si prefiere obtener información sobre cómo usar una herramienta de diseño (Microsoft Expression Blend) para crear la misma aplicación, consulte [crear un botón mediante Microsoft Expression Blend utilizando](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).  
  
 La siguiente ilustración muestra los botones acabados.  
  
 ![Botones personalizados creados mediante XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-basic-buttons"></a>Crear botones básicos  
 Empecemos por crear un nuevo proyecto y agregar unos botones a la ventana.  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>Para crear un nuevo proyecto WPF y agregar botones a la ventana  
  
1.  Iniciar[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  
  
2.  **Cree un nuevo proyecto WPF:** en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**. Buscar el **aplicación de Windows (WPF)** plantilla y el nombre del proyecto "AnimatedButton". Esto creará el esqueleto de la aplicación.  
  
3.  **Agregar botones predeterminados básicos:** todos los archivos que necesita para este tutorial se proporcionan con la plantilla. Abra el archivo Window1.xaml haciendo doble clic en él desde el Explorador de soluciones. De forma predeterminada, hay un <xref:System.Windows.Controls.Grid> elemento en Window1.xaml. Quitar el <xref:System.Windows.Controls.Grid> elemento y agregue algunos botones a la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] página escribiendo o copiar y pegar el código que aparece resaltado a Window1.xaml:  
  
    ```xaml  
    <Window x:Class="AnimatedButton.Window1"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      Title="AnimatedButton" Height="300" Width="300"   
      Background="Black">   <!-- Buttons arranged vertically inside a StackPanel. -->   <StackPanel HorizontalAlignment="Left">     <Button>Button 1</Button>     <Button>Button 2</Button>     <Button>Button 3</Button>   </StackPanel>  
  
    </Window>  
    ```  
  
     Presione F5 para ejecutar la aplicación; debería ver un conjunto de botones que es similar a la siguiente ilustración.  
  
     ![Tres botones básicos](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")  
  
     Ahora que ha creado los botones básicos, haya terminado de trabajar en el archivo Window1.xaml. El resto del tutorial se centra en el archivo app.xaml, definiendo estilos y una plantilla para los botones.  
  
## <a name="set-basic-properties"></a>Establecer las propiedades básicas  
 A continuación, vamos a establecer algunas propiedades en estos botones para controlar la apariencia del botón y el diseño. En lugar de establecer individualmente las propiedades en los botones, utilizará recursos para definir las propiedades de botón de toda la aplicación. Recursos de la aplicación son similares conceptualmente externos [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] para páginas Web; sin embargo, los recursos son mucho más eficaces que [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], tal y como se verá al final de este tutorial. Para más información acerca de los recursos, consulte [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>Utilizar estilos para establecer las propiedades básicas de los botones  
  
1.  **Defina un bloque Application.Resources:** abra app.xaml y agregue el siguiente marcado resaltado si aún no está:  
  
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
  
     Determina el ámbito de recursos donde definir el recurso. Definir recursos de `Application.Resources` en el app.xaml archivo permite el recurso que se va a utilizarse desde cualquier lugar en la aplicación. Para más información acerca de cómo definir el ámbito de los recursos, consulte [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
2.  **Cree un estilo y definir valores de propiedad básicas con él:** agregue el siguiente marcado para la `Application.Resources` bloque. Este marcado crea un <xref:System.Windows.Style> que se aplica a todos los botones en la configuración de la aplicación, el <xref:System.Windows.FrameworkElement.Width%2A> de los botones en 90 y <xref:System.Windows.FrameworkElement.Margin%2A> a 10:  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     El <xref:System.Windows.Style.TargetType%2A> propiedad especifica que el estilo se aplica a todos los objetos de tipo <xref:System.Windows.Controls.Button>. Cada <xref:System.Windows.Setter> establece un valor de propiedad distinto para el <xref:System.Windows.Style>. Por lo tanto, en este momento cada botón de la aplicación tiene un ancho de 90 y un margen de 10.  Si presiona F5 para ejecutar la aplicación, verá la siguiente ventana.  
  
     ![Botones con un ancho de 90 y un margen de 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")  
  
     Hay mucho más que puede hacer con estilos, incluidas diversas maneras de ajustar qué objetos se destinan, especificar valores de propiedad compleja e incluso con estilos como entrada para otros estilos. Para obtener más información, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
3.  **Establecer un valor de propiedad de estilo a un recurso:** recursos permiten reutilizar objetos normalmente definidos y valores de una manera sencilla. Es especialmente útil definir valores complejos utilizando recursos que el código más modular. Agregue el siguiente marcado resaltado en app.xaml.  
  
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
  
     Directamente en el `Application.Resources` bloque, se crea un recurso denominado "GrayBlueGradientBrush". Este recurso define un degradado horizontal. Este recurso se puede utilizar como un valor de propiedad desde cualquier lugar en la aplicación, incluido en el establecedor de estilo de botón de la <xref:System.Windows.Controls.Control.Background%2A> propiedad. Ahora, todos los botones tienen un <xref:System.Windows.Controls.Control.Background%2A> valor de propiedad de este degradado.  
  
     Presione F5 para ejecutar la aplicación. Debe ser similar al siguiente.  
  
     ![Botones con un fondo degradado](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Crear una plantilla que define la apariencia del botón  
 En esta sección, creará una plantilla que se personaliza la apariencia (presentación) del botón. La presentación del botón se compone de varios objetos, incluidos rectángulos y otros componentes para dar el botón una apariencia única.  
  
 Hasta ahora, el control del aspecto de los botones de la aplicación se ha confinado a cambiar las propiedades del botón. ¿Qué ocurre si desea realizar cambios más radicales en la apariencia del botón? Las plantillas permiten un mayor control sobre la presentación de un objeto. Dado que las plantillas pueden utilizarse dentro de estilos, puede aplicar una plantilla a todos los objetos que se aplica el estilo (en este tutorial, el botón).  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>Usar la plantilla para definir la apariencia del botón  
  
1.  **Configurar la plantilla:** porque, como controles <xref:System.Windows.Controls.Button> tiene un <xref:System.Windows.Controls.Control.Template%2A> propiedad, puede definir el valor de propiedad de plantilla al igual que los demás valores de propiedad que hemos configurado en un <xref:System.Windows.Style> mediante un <xref:System.Windows.Setter>. Agregue el siguiente marcado resaltado al estilo de botón.  
  
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
  
2.  **Modificar la presentación del botón:** en este punto, debe definir la plantilla. Agregue el siguiente marcado resaltado. Este marcado especifica dos <xref:System.Windows.Shapes.Rectangle> elementos con las esquinas redondeadas, seguido por un <xref:System.Windows.Controls.DockPanel>. El <xref:System.Windows.Controls.DockPanel> se utiliza al host la <xref:System.Windows.Controls.ContentPresenter> del botón. Un <xref:System.Windows.Controls.ContentPresenter> muestra el contenido del botón. En este tutorial, el contenido es texto ("Button 1", "Button 2", "Button 3"). Todos los componentes de plantilla (los rectángulos y <xref:System.Windows.Controls.DockPanel>) se distribuyen dentro de un <xref:System.Windows.Controls.Grid>.  
  
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
  
     Presione F5 para ejecutar la aplicación. Debe ser similar al siguiente.  
  
     ![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")  
  
3.  **Agregar un vidrio a la plantilla:** a continuación agregará la luna. Primero cree algunos recursos que creen un efecto de degradado de cristal. Agregue estos recursos de degradado en cualquier lugar dentro de la `Application.Resources` bloque:  
  
    ```xaml  
    <Application.Resources>  
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">     <GradientStop Color="WhiteSmoke" Offset="0.2" />     <GradientStop Color="Transparent" Offset="0.4" />     <GradientStop Color="WhiteSmoke" Offset="0.5" />     <GradientStop Color="Transparent" Offset="0.75" />     <GradientStop Color="WhiteSmoke" Offset="0.9" />     <GradientStop Color="Transparent" Offset="1" />   </GradientStopCollection>   <LinearGradientBrush x:Key="MyGlassBrushResource"     StartPoint="0,0" EndPoint="1,1" Opacity="0.75"     GradientStops="{StaticResource MyGlassGradientStopsResource}" />  
    <!-- Styles and other resources below here. -->  
    ```  
  
     Estos recursos se utilizan como el <xref:System.Windows.Shapes.Shape.Fill%2A> para un rectángulo que se pueden insertar en el <xref:System.Windows.Controls.Grid> de la plantilla de botón. Agregue el siguiente marcado resaltado a la plantilla.  
  
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
  
        <!-- Glass Rectangle -->     <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"       VerticalAlignment="Stretch"       StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"       Fill="{StaticResource MyGlassBrushResource}"       RenderTransformOrigin="0.5,0.5">       <Rectangle.Stroke>         <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">           <LinearGradientBrush.GradientStops>             <GradientStop Offset="0.0" Color="LightBlue" />             <GradientStop Offset="1.0" Color="Gray" />           </LinearGradientBrush.GradientStops>         </LinearGradientBrush>       </Rectangle.Stroke>       <!-- These transforms have no effect as they are declared here.             The reason the transforms are included is to be targets             for animation (see later). -->       <Rectangle.RenderTransform>         <TransformGroup>           <ScaleTransform />           <RotateTransform />         </TransformGroup>       </Rectangle.RenderTransform>       <!-- A BevelBitmapEffect is applied to give the button a             "Beveled" look. -->       <Rectangle.BitmapEffect>         <BevelBitmapEffect />       </Rectangle.BitmapEffect>     </Rectangle>  
  
        <!-- Present Text of the button. -->  
        <DockPanel Name="myContentPresenterDockPanel">  
          <ContentPresenter x:Name="myContentPresenter" Margin="20"   
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
        </DockPanel>  
      </Grid>  
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     Tenga en cuenta que la <xref:System.Windows.UIElement.Opacity%2A> del rectángulo con el `x:Name` la propiedad de "glassCube" es 0, por lo que al ejecutar el ejemplo, no verá el rectángulo de cristal situado en la parte superior. Esto es porque más adelante agregaremos desencadenadores a la plantilla para cuando el usuario interactúa con el botón. Sin embargo, puede ver el botón aspecto ahora cambiando el <xref:System.Windows.UIElement.Opacity%2A> valor a 1 y ejecutar la aplicación. Vea la ilustración siguiente. Antes de continuar con el paso siguiente, cambie la <xref:System.Windows.UIElement.Opacity%2A> en 0.  
  
     ![Botones personalizados creados mediante XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-button-interactivity"></a>Crear la interactividad del botón  
 En esta sección, creará desencadenadores de propiedad y desencadenadores de eventos para cambiar los valores de propiedad y ejecutar animaciones en respuesta a las acciones del usuario, como mover el puntero del mouse sobre el botón y haga clic en.  
  
 Una manera fácil de agregar interactividad (pasar el mouse, deje de mouse (ratón), haga clic en y así sucesivamente) es definir los desencadenadores dentro de la plantilla o el estilo. Para crear un <xref:System.Windows.Trigger>, se define una propiedad "condición" como: el botón <xref:System.Windows.UIElement.IsMouseOver%2A> es igual al valor de la propiedad `true`. A continuación, defina establecedores (acciones) que tienen lugar cuando se cumple la condición desencadenadora.  
  
#### <a name="to-create-button-interactivity"></a>Para crear la interactividad del botón  
  
1.  **Agregar desencadenadores de la plantilla:** agregue el marcado resaltado a la plantilla.  
  
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
  
        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
2.  **Agregar desencadenadores de propiedad:** agregue el marcado resaltado a la `ControlTemplate.Triggers` bloque:  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     Presione F5 para ejecutar la aplicación y ver el efecto que se ejecute el puntero del mouse sobre los botones.  
  
3.  **Agregar un desencadenador de foco:** a continuación, vamos a agregar algunos establecedores similares para controlar el caso cuando el botón tiene el foco (por ejemplo, después de que el usuario hace clic en él).  
  
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
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>  
  
    </ControlTemplate.Triggers>  
    ```  
  
     Presione F5 para ejecutar la aplicación y haga clic en uno de los botones. Tenga en cuenta que el botón permanece resaltado después de hacer clic en él porque aún tiene el foco. Si hace clic en otro botón, el nuevo botón recibe el foco mientras el último lo pierde.  
  
4.  **Agregar animaciones para** <xref:System.Windows.UIElement.MouseEnter> **y** <xref:System.Windows.UIElement.MouseLeave> **:** a continuación, agregamos algunas animaciones a los desencadenadores. Agregue el siguiente marcado en cualquier lugar dentro de la `ControlTemplate.Triggers` bloque.  
  
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
  
     El rectángulo de cristal se reduce cuando el puntero del mouse se mueve sobre el botón y se devuelve al tamaño normal cuando el puntero sale.  
  
     Hay dos animaciones que se desencadenan cuando pasa el puntero sobre el botón (<xref:System.Windows.UIElement.MouseEnter> evento se desencadena). Estas animaciones reducen el rectángulo de cristal a lo largo de los ejes X e Y. Observe que las propiedades en el <xref:System.Windows.Media.Animation.DoubleAnimation> elementos: <xref:System.Windows.Media.Animation.Timeline.Duration%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>. El <xref:System.Windows.Media.Animation.Timeline.Duration%2A> especifica que la animación se produce durante medio segundo, y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> especifica que el vidrio se reduce en un 10%.  
  
     El segundo desencadenador de eventos (<xref:System.Windows.UIElement.MouseLeave>) simplemente se detiene la primera de ellas. Cuando detenga un <xref:System.Windows.Media.Animation.Storyboard>, todas las propiedades animadas volver a sus valores predeterminados. Por lo tanto, cuando el usuario mueve el puntero fuera del botón, el botón vuelve a la manera en que estaba antes de que el puntero del mouse se mueve sobre el botón. Para obtener más información acerca de las animaciones, consulte [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
5.  **Agregar una animación para cuando se hace clic en el botón:** el último paso es agregar un desencadenador para cuando el usuario hace clic en el botón. Agregue el siguiente marcado en cualquier lugar dentro de la `ControlTemplate.Triggers` bloque:  
  
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
  
     Presione F5 para ejecutar la aplicación y haga clic en uno de los botones. Al hacer clic en un botón, el rectángulo de cristal gira sobre sí mismo.  
  
## <a name="summary"></a>Resumen  
 En este tutorial, se realizan los ejercicios siguientes:  
  
-   Como destino un <xref:System.Windows.Style> a un tipo de objeto (<xref:System.Windows.Controls.Button>).  
  
-   Controla las propiedades básicas de los botones de la aplicación completa utilizando la <xref:System.Windows.Style>.  
  
-   Crea recursos tales como degradados para utilizarlos para valores de propiedad de la <xref:System.Windows.Style> establecedores.  
  
-   Personalizar la apariencia de los botones en toda la aplicación aplicando una plantilla a los botones.  
  
-   Personalizar el comportamiento de los botones en respuesta a las acciones del usuario (como <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, y <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) que incluyen efectos de animación.  
  
## <a name="see-also"></a>Vea también  
 [Crear un botón mediante Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Información general sobre efectos de imagen](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)
