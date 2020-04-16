---
title: Crear un estilo para un control
description: Aprenda a crear y hacer referencia a un estilo de control en Windows Presentation Foundation y .NET Core.
author: thraka
ms.author: adegeo
ms.date: 09/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: 2956dbf93a1d34feca31d3ab10536f5089010189
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "81432561"
---
# <a name="create-a-style-for-a-control-in-wpf"></a>Crear un estilo para un control en WPFWPF

Con Windows Presentation Foundation (WPF), puede personalizar la apariencia de un control existente con su propio estilo reutilizable. Los estilos se pueden aplicar globalmente a la aplicación, las ventanas y las páginas, o directamente a los controles.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="create-a-style"></a>Crear un estilo

Puede pensar en <xref:System.Windows.Style> una forma cómoda de aplicar un conjunto de valores de propiedad a uno o varios elementos. Puede utilizar un estilo en cualquier <xref:System.Windows.FrameworkElement> elemento <xref:System.Windows.FrameworkContentElement> que <xref:System.Windows.Window> derive <xref:System.Windows.Controls.Button>de o como un archivo o un archivo .

La forma más común de declarar un `Resources` estilo es como un recurso en la sección de un archivo XAML. Dado que los estilos son recursos, obedecen las mismas reglas de ámbito que se aplican a todos los recursos. En pocas palabras, donde se declara un estilo afecta a donde se puede aplicar el estilo. Por ejemplo, si declara el estilo en el elemento raíz del archivo XAML de definición de aplicación, el estilo se puede usar en cualquier lugar de la aplicación.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/App.xaml#AppResources)]

Si declaras el estilo en uno de los archivos XAML de la aplicación, el estilo solo se puede usar en ese archivo XAML. Para más información acerca de las reglas de ámbito de los recursos, consulte [Recursos XAML](xaml-resources-define.md).

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowSingleResource.xaml#WindowResources)]

Un estilo se `<Setter>` compone de elementos secundarios que establecen propiedades en los elementos a los que se aplica el estilo. En el ejemplo anterior, observe que el `TextBlock` estilo `TargetType` se establece para aplicarse a los tipos a través del atributo. El estilo establecerá <xref:System.Windows.Controls.Control.FontSize%2A> `15` el <xref:System.Windows.Controls.Control.FontWeight%2A> to `ExtraBold`y el to . Agregue `<Setter>` un para cada propiedad que cambie el estilo.

## <a name="apply-a-style-implicitly"></a>Aplicar un estilo implícitamente

A <xref:System.Windows.Style> es una manera conveniente de aplicar un conjunto de valores de propiedad a más de un elemento. Por ejemplo, considere <xref:System.Windows.Controls.TextBlock> los siguientes elementos y su apariencia predeterminada en una ventana.

[!code-xaml[TextBlocks](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetTextBlocks)]

![Captura de pantalla de ejemplo de estilo](./media/styles-and-templates-overview/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")

Puede cambiar la apariencia predeterminada estableciendo <xref:System.Windows.Controls.Control.FontSize%2A> <xref:System.Windows.Controls.Control.FontFamily%2A>propiedades, <xref:System.Windows.Controls.TextBlock> como y , en cada elemento directamente. Sin embargo, <xref:System.Windows.Controls.TextBlock> si desea que los elementos <xref:System.Windows.Style> compartan algunas propiedades, puede crear una en la `Resources` sección del archivo XAML, como se muestra aquí.

[!code-xaml[DefaultTextBlockStyle](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetDefaultTextBlockStyle)]

Cuando se <xref:System.Windows.Style.TargetType%2A> establece el estilo <xref:System.Windows.Controls.TextBlock> en el `x:Key` tipo y se omite <xref:System.Windows.Controls.TextBlock> el atributo, el estilo se aplica a todos los elementos con ámbito al estilo, que suele ser el propio archivo XAML.

Ahora <xref:System.Windows.Controls.TextBlock> los elementos aparecen de la siguiente manera.

![Captura de pantalla de ejemplo de estilo](./media/styles-and-templates-overview/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")

## <a name="apply-a-style-explicitly"></a>Aplicar un estilo explícitamente

Si agrega `x:Key` un atributo con valor al estilo, el estilo ya <xref:System.Windows.Style.TargetType%2A>no se aplica implícitamente a todos los elementos de . Solo los elementos que hacen referencia explícitamente al estilo tendrán el estilo aplicado a ellos.

Aquí está el estilo de la sección `x:Key` anterior, pero declarado con el atributo.

[!code-xaml[ExplicitStyleDeclare](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleDeclare)]

Para aplicar el estilo, establezca la <xref:System.Windows.FrameworkElement.Style%2A> `x:Key` propiedad del elemento en el valor, mediante una extensión de [marcado StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md), como se muestra aquí.

[!code-xaml[ExplicitStyleReference](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleReference)]

Observe que <xref:System.Windows.Controls.TextBlock> el primer elemento tiene el estilo aplicado mientras el segundo elemento TextBlock permanece sin cambios. El estilo implícito de la sección anterior se `x:Key` cambió a un estilo que declaró el atributo, es decir, el único elemento afectado por el estilo es el que hace referencia al estilo directamente.

![Captura de pantalla de ejemplo de estilo](./media/styles-and-templates-overview/create-a-style-explicit-textblock.png "create-a-style-explicit-textblock")

Una vez que se aplica un estilo, explícita o implícitamente, se sella y no se puede cambiar. Si desea cambiar un estilo que se ha aplicado, cree un nuevo estilo para reemplazar el existente. Para obtener más información, vea la propiedad <xref:System.Windows.Style.IsSealed%2A>.

Puede crear un objeto que elija un estilo que se aplique según una lógica personalizada. Para obtener un ejemplo, vea <xref:System.Windows.Controls.StyleSelector> el ejemplo proporcionado para la clase.

## <a name="apply-a-style-programmatically"></a>Aplicar un estilo mediante programación

Para asignar un estilo con nombre a un elemento mediante programación, obtenga <xref:System.Windows.FrameworkElement.Style%2A> el estilo de la colección de recursos y asígnelo a la propiedad del elemento. Los elementos de una <xref:System.Object>colección de recursos son de tipo . Por lo tanto, debe convertir <xref:System.Windows.Style?displayProperty=fullName> el estilo recuperado `Style` en un antes de asignarlo a la propiedad. Por ejemplo, el código siguiente `TextBlock` establece `textblock1` el estilo `TitleText`de un nombre en el estilo definido.

[!code-csharp[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml.cs#SnippetSetStyleCode)]
[!code-vb[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/MainWindow.xaml.vb#SnippetSetStyleCode)]

## <a name="extend-a-style"></a>Extender un estilo

Tal vez desee que los dos <xref:System.Windows.Controls.TextBlock> elementos <xref:System.Windows.Controls.Control.FontFamily%2A> compartan <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>algunos valores de propiedad, como el . y el centrado. Pero también desea que el texto **Mis imágenes** tenga algunas propiedades adicionales. Puede hacerlo creando un nuevo estilo basado en el primer estilo, como se muestra aquí.

[!code-xaml[DefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

[!code-xaml[TextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

Este `TextBlock` estilo ahora está centrado, utiliza `Comic Sans MS` una `26`fuente con un tamaño <xref:System.Windows.Media.LinearGradientBrush> de , y el color de primer plano establecido en el ejemplo. Observe que reemplaza <xref:System.Windows.Controls.Control.FontSize%2A> el valor del estilo base. Si hay más de <xref:System.Windows.Setter> uno apuntando a <xref:System.Windows.Style>la `Setter` misma propiedad en un , el que se declara último tiene prioridad.

A continuación se <xref:System.Windows.Controls.TextBlock> muestra el aspecto de los elementos:

![TextBlocks con estilo](./media/styles-and-templates-overview/stylingintro-textblocks.png "StylingIntro_TextBlocks")

Este `TitleText` estilo amplía el estilo que <xref:System.Windows.Controls.TextBlock> se ha `BasedOn="{StaticResource {x:Type TextBlock}}"`creado para el tipo, al que se hace referencia con . También puede extender un estilo `x:Key` que `x:Key` tiene un mediante el uso del estilo. Por ejemplo, si hubiera `Header1` un estilo con nombre y desea `BasedOn="{StaticResource Header1}"`ampliar ese estilo, usaría .

## <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Relación de la propiedad TargetType y el atributo x:Key

Como se ha <xref:System.Windows.Style.TargetType%2A> mostrado `TextBlock` anteriormente, establecer `x:Key` la propiedad en sin asignar el estilo un hace que el estilo se aplique a todos los <xref:System.Windows.Controls.TextBlock> elementos. En este caso, `x:Key` se establece implícitamente en `{x:Type TextBlock}`. Esto significa que si establece `x:Key` explícitamente el `{x:Type TextBlock}`valor <xref:System.Windows.Style> en algo distinto `TextBlock` de , el no se aplica a todos los elementos automáticamente. En su lugar, debe aplicar `x:Key` el estilo `TextBlock` (mediante el valor) a los elementos explícitamente. Si el estilo está en la sección resources `TargetType` y no establece la propiedad `x:Key` en el estilo, debe establecer el atributo.

Además de proporcionar un `x:Key`valor `TargetType` predeterminado para el , la propiedad especifica el tipo al que se aplican las propiedades del establecedor. Si no especifica un `TargetType`, debe calificar las <xref:System.Windows.Setter> propiedades de los objetos `Property="ClassName.Property"`con un nombre de clase mediante la sintaxis . Por ejemplo, en `Property="FontSize"`lugar de <xref:System.Windows.Setter.Property%2A> `"TextBlock.FontSize"` establecer `"Control.FontSize"`, debe establecer en o .

Tenga en cuenta también que muchos WPFWPF controles constan de una combinación de otros WPFWPF controles. Si crea un estilo aplicable a todos los controles de un tipo, podría obtener resultados inesperados. Por ejemplo, si crea un <xref:System.Windows.Controls.TextBlock> estilo que <xref:System.Windows.Window>tiene como destino `TextBlock` el tipo en un `TextBlock` , el estilo se aplica <xref:System.Windows.Controls.ListBox>a todos los controles de la ventana, incluso si forma parte de otro control, como un archivo .

## <a name="see-also"></a>Consulte también

<!-- - [Create a style for a control](styles-templates-create-apply-template.md) -->
- [Descripción general de los recursos XAML](xaml-resources-define.md)
- [Información general de XAML (WPF & .NET Core)](xaml.md)
