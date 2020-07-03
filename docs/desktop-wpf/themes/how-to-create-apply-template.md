---
title: 'Creación de una plantilla en WPF: Escritorio de .NET'
description: Obtenga información sobre cómo crear una plantilla de control y hacer referencia a esta en Windows Presentation Foundation y .NET Core.
author: adegeo
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
ms.openlocfilehash: c372659676b450cde789c96e45c7ec5de2aea194
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325728"
---
# <a name="create-a-template-for-a-control"></a>Creación de una plantilla de un control

Con Windows Presentation Foundation (WPF), puede usar su propia plantilla reutilizable para personalizar la estructura visual y el comportamiento de un control existente. Las plantillas se pueden aplicar de forma global a la aplicación, las ventanas y las páginas, o bien directamente a los controles. La mayoría de los escenarios en los que es necesario crear un control se pueden solventar creando en su lugar una plantilla para un control existente.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

En este artículo, veremos cómo crear un objeto <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Button>.

## <a name="when-to-create-a-controltemplate"></a>Cuándo crear un objeto ControlTemplate

Los controles tienen muchas propiedades, como <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> y <xref:System.Windows.Controls.Control.FontFamily%2A>. Estas propiedades se encargan de distintos aspectos relacionados con la apariencia del control, pero los cambios que se pueden realizar configurando estas propiedades son limitados. Por ejemplo, la propiedad <xref:System.Windows.Controls.Control.Foreground%2A> se puede establecer en azul y <xref:System.Windows.Controls.Control.FontStyle%2A> en cursiva en un objeto <xref:System.Windows.Controls.CheckBox>. Si queremos personalizar la apariencia del control de forma diferente a como lo hace la configuración de las demás propiedades del control, hay que crear un objeto <xref:System.Windows.Controls.ControlTemplate>.

En la mayoría de las interfaces de usuario, los botones tienen la misma apariencia en general: un rectángulo con texto. Si quisiéramos crear un botón redondeado, podríamos crear un control que herede del botón o que vuelva a crear la funcionalidad del botón y que, además, aporte el elemento visual circular.

Para no tener que crear más controles, se puede personalizar el diseño visual de un control existente. En el caso del botón redondeado, hay que crear un objeto <xref:System.Windows.Controls.ControlTemplate> con el diseño visual que buscamos.

Por otra parte, si necesitamos un control con nueva funcionalidad, con propiedades diferentes y con nuevas configuraciones, crearíamos un objeto <xref:System.Windows.Controls.UserControl>.

## <a name="prerequisites"></a>Requisitos previos

Cree una aplicación de WPF y, en *MainWindow.xaml* (o en otra ventana de su elección), configure las siguientes propiedades en el elemento **\<Window>** :

|     |     |
| --- | --- |
| **Title**         | `Template Intro Sample` |
| **SizeToContent** | `WidthAndHeight` |
| **MinWidth**      | `250` |

Configure el contenido del elemento **\<Window>** en el siguiente código XAML:

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Al final del proceso, el archivo *MainWindow.xaml* debe tener un aspecto similar al siguiente:

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

Si la aplicación se ejecuta, tendrá el siguiente aspecto:

![Ventana de WPF con dos botones sin estilo](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a>Creación de una clase ControlTemplate

La forma más común de declarar un objeto <xref:System.Windows.Controls.ControlTemplate> es como un recurso en la sección `Resources` de un archivo XAML. Dado que las plantillas son recursos, siguen las mismas reglas de ámbito que se aplican a todos los recursos. Simplemente, la ubicación de la declaración de una plantilla afecta a dónde se puede aplicar la plantilla. Por ejemplo, si declara una plantilla en el elemento raíz del archivo XAML de definición de la aplicación, puede usar en cualquier parte de esta. Si la plantilla se define en una ventana, solo los controles de esa ventana podrán usarla.

Para empezar, agregue un elemento `Window.Resources` al archivo *MainWindow.xaml*:

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

Cree un valor **\<ControlTemplate>** nuevo con las propiedades siguientes:

|     |     |
| --- | --- |
| **x:Key**         | `roundbutton` |
| **TargetType**    | `Button` |

Esta plantilla de control será sencilla:

- Un elemento raíz del control, un elemento <xref:System.Windows.Controls.Grid>
- Un elemento <xref:System.Windows.Shapes.Ellipse> para trazar el aspecto redondeado del botón
- Un elemento <xref:System.Windows.Controls.ContentPresenter> para mostrar el contenido del botón especificado por el usuario

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a>TemplateBinding

Al crear un elemento <xref:System.Windows.Controls.ControlTemplate>, puede que quiera seguir usando las propiedades públicas para cambiar la apariencia del control. La extensión de marcado [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) enlaza una propiedad de un elemento que está en el elemento <xref:System.Windows.Controls.ControlTemplate> a una propiedad pública que está definida por el control. Cuando se usa [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), se habilitan propiedades en el control que actúan como parámetros de la plantilla. Es decir, cuando se establece una propiedad de un control, ese valor se pasa al elemento que tiene la extensión [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).

### <a name="ellipse"></a>Ellipse

Cabe decir que las propiedades **:::no-loc text="Fill":::** y **:::no-loc text="Stroke":::** del elemento **\<Ellipse>** están enlazadas a las propiedades <xref:System.Windows.Controls.Control.Foreground> y <xref:System.Windows.Controls.Control.Background> del control.

### <a name="contentpresenter"></a>ContentPresenter

También se agrega a la plantilla un elemento [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter). Dado que esta plantilla está diseñada para un botón, tenga en cuenta que el botón hereda de <xref:System.Windows.Controls.ContentControl>. El botón presenta el contenido del elemento. Se puede establecer cualquier elemento dentro del botón, como texto sin formato o incluso otro control. Los dos botones siguientes son válidos:

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

En estos dos ejemplos, el texto y la casilla se configuran como la propiedad [Button.Content](xref:System.Windows.Controls.ContentControl.Content). Lo que se establezca como contenido se puede mostrar a través de un elemento **\<ContentPresenter>** , que es lo que la plantilla hace.

Si el elemento <xref:System.Windows.Controls.ControlTemplate> se aplica a un tipo <xref:System.Windows.Controls.ContentControl>, como un elemento `Button`, se busca un elemento <xref:System.Windows.Controls.ContentPresenter> en el árbol de elementos. Si se halla el elemento `ContentPresenter`, la plantilla enlaza automáticamente la propiedad <xref:System.Windows.Controls.ContentControl.Content> del control a `ContentPresenter`.

## <a name="use-the-template"></a>Uso de la plantilla

Busque los botones que se declararon al principio de este artículo.

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Establezca la propiedad <xref:System.Windows.Controls.Control.Template> del segundo botón en el recurso `roundbutton`:

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

Si ejecuta el proyecto y observa el resultado, verá que el botón tiene un fondo redondeado.

![Ventana de WPF con un botón ovalado de plantilla](media/create-apply-template/styled-button.png)

Posiblemente se haya dado cuenta de que el botón no es un círculo perfecto, sino que está distorsionado. El elemento **\<Ellipse>** funciona de forma que se expande para rellenar el espacio disponible. Para que el círculo sea uniforme, cambie las propiedades **:::no-loc text="width":::** y **:::no-loc text="height":::** del botón al mismo valor:

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Ventana de WPF con un botón circular de plantilla](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a>Incorporación de un desencadenador

Aunque un botón que tiene una plantilla aplicada tiene un aspecto diferente, se comporta igual que cualquier otro botón. Si se presiona, se activa el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. Pese a ello, posiblemente se haya dado cuenta de que, al mover el ratón por el botón, sus elementos visuales no cambian. Todas estas interacciones visuales están definidas por la plantilla.

Gracias a los sistemas de propiedades y eventos dinámicos que WPF proporciona, se puede ver una propiedad específica de un valor y, después, volver a aplicar el estilo de la plantilla cuando sea necesario. En este ejemplo, veremos la propiedad <xref:System.Windows.UIElement.IsMouseOver> del botón. Cuando el mouse esté sobre el control, aplique el estilo **\<Ellipse>** con un nuevo color. Este tipo de desencadenador se conoce como *PropertyTrigger*.

Para que funcione, hay que agregar un nombre al elemento **\<Ellipse>** al que poder hacer referencia. Asígnele el nombre **backgroundElement**.

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

Después, agregue un nuevo elemento <xref:System.Windows.Trigger> a la colección [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers). El desencadenador inspeccionará el evento `IsMouseOver` en busca del valor `true`.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

Después, agregue un elemento **\<Setter>** al elemento **\<Trigger>** , que cambia la propiedad **Fill** de **\<Ellipse>** a un nuevo color.

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

Ejecute el proyecto. Fíjese en que, al mover el mouse por el botón, el color de **\<Ellipse>** cambia.

![El ratón se mueve por el botón de WPF para cambiar el color de relleno](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a>Uso de un elemento VisualState

Los estados visuales se definen y desencadenan a través de un control. Por ejemplo, cuando el ratón se mueve por el control, se desencadena el estado `CommonStates.MouseOver`. Los cambios de propiedad se pueden animar en función del estado actual del control. En la sección anterior, usamos un elemento **\<PropertyTrigger>** para cambiar el primer plano del botón a `AliceBlue` cuando la propiedad `IsMouseOver` era `true`. Esta vez, cree un estado visual que anime el cambio de este color a través de una transición suave. Para más información sobre los elementos *VisualState*, vea [Estilos y plantillas en WPF](../fundamentals/styles-templates-overview.md#visual-states).

Para convertir **\<PropertyTrigger>** a un estado visual animado, quite en primer lugar el elemento **\<ControlTemplate.Triggers>** de la plantilla.

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

A continuación, en la raíz **\<Grid>** de la plantilla de control, agregue el elemento **\<VisualStateManager.VisualStateGroups>** con un **\<VisualStateGroup>** para `CommonStates`. Defina dos estados, `Normal` y `MouseOver`.

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

Cuando ese estado se desencadene, se aplicarán las animaciones definidas en el elemento **\<VisualState>** . Cree animaciones para cada estado. Las animaciones se colocan en un elemento **\<Storyboard>** . Para obtener más información sobre los guiones gráficos, vea [Información general sobre guiones gráficos](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

- Normal

  Este estado anima el relleno de la elipse y lo restaura al color `Background` del control.

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- MouseOver

  Este estado anima el color `Background` de la elipse hacia un nuevo color: `Yellow`.

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

**\<ControlTemplate>** debería tener ahora un aspecto similar al siguiente.

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

Ejecute el proyecto. Fíjese en que, al mover el mouse por el botón, el color de **\<Ellipse>** se cobra movimiento.

![El ratón se mueve por el botón de WPF para cambiar el color de relleno](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a>Pasos siguientes

- [Creación de un estilo de un control en WPF](../fundamentals/styles-templates-create-apply-style.md)
- [Estilos y plantillas en WPF](../fundamentals/styles-templates-overview.md)
- [Información general de los recursos XAML](../fundamentals/xaml-resources-define.md)
