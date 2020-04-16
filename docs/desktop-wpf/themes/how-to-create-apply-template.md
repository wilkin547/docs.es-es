---
title: Crear una plantilla en WPF - .NET Desktop
description: Aprenda a crear y hacer referencia a una plantilla de control en Windows Presentation Foundation y .NET Core.
author: thraka
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432543"
---
# <a name="create-a-template-for-a-control"></a>Crear una plantilla para un control

Con Windows Presentation Foundation (WPF), puede personalizar la estructura visual y el comportamiento de un control existente con su propia plantilla reutilizable. Las plantillas se pueden aplicar globalmente a la aplicación, ventanas y páginas, o directamente a los controles. La mayoría de los escenarios que requieren que cree un nuevo control se pueden cubrir creando en su lugar una nueva plantilla para un control existente.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

En este artículo, explorará la <xref:System.Windows.Controls.ControlTemplate> creación <xref:System.Windows.Controls.Button> de un nuevo para el control.

## <a name="when-to-create-a-controltemplate"></a>Cuándo crear un ControlTemplate

Los controles tienen muchas <xref:System.Windows.Controls.Border.Background%2A> <xref:System.Windows.Controls.Control.Foreground%2A>propiedades, <xref:System.Windows.Controls.Control.FontFamily%2A>como , , y . Estas propiedades controlan diferentes aspectos de la apariencia del control, pero los cambios que puede realizar estableciendo estas propiedades son limitados. Por ejemplo, puede <xref:System.Windows.Controls.Control.Foreground%2A> establecer la <xref:System.Windows.Controls.Control.FontStyle%2A> propiedad en <xref:System.Windows.Controls.CheckBox>azul y en cursiva en un archivo . Si desea personalizar la apariencia del control más allá de lo que puede <xref:System.Windows.Controls.ControlTemplate>hacer la configuración de las otras propiedades del control, cree un archivo .

En la mayoría de las interfaces de usuario, un botón tiene la misma apariencia general: un rectángulo con algún texto. Si desea crear un botón redondeado, puede crear un nuevo control que herede del botón o volver a crear la funcionalidad del botón. Además, el nuevo control de usuario proporcionaría el objeto visual circular.

Puede evitar la creación de nuevos controles personalizando el diseño visual de un control existente. Con un botón redondeado, se crea un <xref:System.Windows.Controls.ControlTemplate> diseño visual con el diseño visual deseado.

Por otro lado, si necesita un control con nueva funcionalidad, propiedades diferentes y <xref:System.Windows.Controls.UserControl>nueva configuración, crearía un nuevo archivo .

## <a name="prerequisites"></a>Prerrequisitos

Cree una nueva aplicación WPF y en *MainWindow.xaml* (u otra ventana ** \<** de su elección) establezca las siguientes propiedades en el elemento>Window:

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

Establezca el contenido del elemento ** \<Window>** en el siguiente XAML:

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Al final, el archivo *MainWindow.xaml* debe ser similar al siguiente:

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

Si ejecuta la aplicación, tiene el siguiente aspecto:

![Ventana WPF con dos botones sin estilo](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a>Creación de una clase ControlTemplate

La forma más común <xref:System.Windows.Controls.ControlTemplate> de declarar a `Resources` es como un recurso en la sección de un archivo XAML. Dado que las plantillas son recursos, obedecen las mismas reglas de ámbito que se aplican a todos los recursos. En pocas palabras, donde se declara una plantilla afecta a dónde se puede aplicar la plantilla. Por ejemplo, si declara la plantilla en el elemento raíz del archivo XAML de definición de aplicación, la plantilla se puede usar en cualquier lugar de la aplicación. Si define la plantilla en una ventana, solo los controles de esa ventana pueden usar la plantilla.

Para empezar, agregue `Window.Resources` un elemento al archivo *MainWindow.xaml:*

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

Cree un nuevo ** \<>ControlTemplate** con las siguientes propiedades establecidas:

|     |     |
| --- | --- |
| **x:Key**         | `roundbutton` |
| **TargetType**    | `Button` |

Esta plantilla de control será simple:

- un elemento raíz para el control, un<xref:System.Windows.Controls.Grid>
- y <xref:System.Windows.Shapes.Ellipse> dibujar la apariencia redondeada del botón
- <xref:System.Windows.Controls.ContentPresenter> a para mostrar el contenido del botón especificado por el usuario

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a>TemplateBinding

Al crear un <xref:System.Windows.Controls.ControlTemplate>nuevo , es posible que desee usar las propiedades públicas para cambiar la apariencia del control. El [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) extensión de marcado enlaza una propiedad <xref:System.Windows.Controls.ControlTemplate> de un elemento que se encuentra en el a una propiedad pública definida por el control. Cuando se usa [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), se habilitan las propiedades del control para que actúen como parámetros de la plantilla. Es decir, cuando se establece una propiedad de un control, ese valor se pasa al elemento que tiene la extensión [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).

### <a name="ellipse"></a>Elipse

Observe que **:::no-loc text="Fill":::** **:::no-loc text="Stroke":::** las propiedades y del ** \<elemento de>** <xref:System.Windows.Controls.Control.Background> Ellipse están enlazadas a las propiedades y propiedades del <xref:System.Windows.Controls.Control.Foreground> control.

### <a name="contentpresenter"></a>ContentPresenter

Un [ \<Elemento de>ContentPresenter](xref:System.Windows.Controls.ContentPresenter) también se agrega a la plantilla. Dado que esta plantilla está diseñada para un botón, tenga en cuenta que el botón hereda de <xref:System.Windows.Controls.ContentControl>. El botón presenta el contenido del elemento. Puede establecer cualquier cosa dentro del botón, como texto sin formato o incluso otro control. Ambos de los siguientes son botones válidos:

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

En los dos ejemplos anteriores, el texto y la casilla de verificación se establecen como la propiedad [Button.Content.](xref:System.Windows.Controls.ContentControl.Content) Lo que se establece como el contenido se puede presentar a través de un ** \<ContentPresenter>**, que es lo que hace la plantilla.

Si <xref:System.Windows.Controls.ControlTemplate> se aplica <xref:System.Windows.Controls.ContentControl> a un tipo, como un `Button`, <xref:System.Windows.Controls.ContentPresenter> se busca en el árbol de elementos. Si `ContentPresenter` se encuentra, la plantilla enlaza automáticamente <xref:System.Windows.Controls.ContentControl.Content> la `ContentPresenter`propiedad del control a la .

## <a name="use-the-template"></a>Uso de la plantilla

Busque los botones que se declararon al principio de este artículo.

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Establezca la propiedad <xref:System.Windows.Controls.Control.Template> del segundo `roundbutton` botón en el recurso:

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

Si ejecuta el proyecto y observa el resultado, verá que el botón tiene un fondo redondeado.

![Ventana WPF con un botón ovalado de plantilla](media/create-apply-template/styled-button.png)

Es posible que haya notado que el botón no es un círculo, pero está sesgado. Debido a la forma en que funciona el ** \<elemento elipse>,** siempre se expande para rellenar el espacio disponible. Haga que el círculo sea **:::no-loc text="width":::** uniforme **:::no-loc text="height":::** cambiando las propiedades y el botón al mismo valor:

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Ventana WPF con un botón circular de plantilla](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a>Añadir un disparador

Aunque un botón con una plantilla aplicada tiene un aspecto diferente, se comporta igual que cualquier otro botón. Si pulsa el botón, el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento se activa. Sin embargo, es posible que haya notado que cuando mueve el ratón sobre el botón, los objetos visuales del botón no cambian. Todas estas interacciones visuales se definen mediante la plantilla.

Con los sistemas de propiedades y eventos dinámicos que WPFWPF proporciona, puede ver una propiedad específica para un valor y, a continuación, cambiar el estilo de la plantilla cuando corresponda. En este ejemplo, verá la propiedad <xref:System.Windows.UIElement.IsMouseOver> del botón. Cuando el ratón está sobre el control, el estilo de la ** \<Elipse>** con un nuevo color. Este tipo de desencadenador se conoce como *PropertyTrigger*.

Para que esto funcione, deberá agregar un ** \<** nombre a la>Ellipse a la que puede hacer referencia. Asír como el nombre **backgroundElement**.

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

A continuación, <xref:System.Windows.Trigger> agregue un nuevo a la [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) colección. El desencadenador observará el `IsMouseOver` `true`evento para el valor .

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

A continuación, agregue un ** \<>Setter** al ** \<desencadenador>** que cambia el **Fill** propiedad de la ** \<Ellipse>** a un nuevo color.

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

Ejecute el proyecto. Tenga en cuenta que al mover el ratón sobre el botón, el color de la ** \<Elipse>** cambia.

![ratón se mueve sobre el botón WPF para cambiar el color de relleno](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a>Usar un VisualState

Los estados visuales se definen y desencadenan mediante un control. Por ejemplo, cuando el mouse se mueve `CommonStates.MouseOver` en la parte superior del control, se desencadena el estado. Puede animar los cambios de propiedad en función del estado actual del control. En la sección anterior, se usaba un `AliceBlue` `IsMouseOver` `true` ** \<>PropertyTrigger** para cambiar el primer plano del botón a cuando la propiedad era . En su lugar, cree un estado visual que anime el cambio de este color, proporcionando una transición suave. Para obtener más información acerca de *VisualStates*, vea [Estilos y plantillas en WPF](../fundamentals/styles-templates-overview.md#visual-states).

Para convertir el ** \<PropertyTrigger>** en un estado visual animado, En primer lugar, quite el ** \<ControlTemplate.Triggers>** elemento de la plantilla.

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

A continuación, ** \<** en la cuadrícula>raíz de la plantilla de control, agregue el `CommonStates` ** \<VisualStateManager.VisualStateGroups>** elemento con un ** \<VisualStateGroup>** para . Defina dos `Normal` estados `MouseOver`y .

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

Las animaciones definidas en un ** \<>VisualState** se aplican cuando se desencadena ese estado. Cree animaciones para cada estado. Las animaciones se colocan dentro de un ** \<elemento de>Storyboard.** Para obtener más información acerca de los guiones gráficos, vea Información general sobre [guiones gráficos](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

- Normal

  Este estado anima el relleno de elipse, `Background` restableciéndolo al color del control.

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- MouseOver

  Este estado anima `Background` el color de `Yellow`elipse a un nuevo color: .

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

El ** \<>ControlTemplate** ahora debería tener el siguiente aspecto.

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

Ejecute el proyecto. Tenga en cuenta que al mover el ratón sobre el botón, el color de la ** \<Elipse>** se anima.

![ratón se mueve sobre el botón WPF para cambiar el color de relleno](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a>Pasos siguientes

- [Crear un estilo para un control en WPFWPF](../fundamentals/styles-templates-create-apply-style.md)
- [Estilos y plantillas en WPF](../fundamentals/styles-templates-overview.md)
- [Descripción general de los recursos XAML](../fundamentals/xaml-resources-define.md)
