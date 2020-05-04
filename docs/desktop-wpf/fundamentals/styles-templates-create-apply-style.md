---
title: Creación de un estilo de control
description: Obtenga información sobre cómo crear un estilo de control y hacer referencia a este en Windows Presentation Foundation y .NET Core.
author: thraka
ms.author: adegeo
ms.date: 09/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: 2956dbf93a1d34feca31d3ab10536f5089010189
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "81432561"
---
# <a name="create-a-style-for-a-control-in-wpf"></a>Creación de un estilo de control en WPF

Con Windows Presentation Foundation (WPF), puede usar su propia plantilla reutilizable para personalizar la apariencia de un control existente. Los estilos se pueden aplicar de forma global a la aplicación, las ventanas y las páginas, o bien directamente a los controles.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="create-a-style"></a>Crear un estilo

Puede considerar <xref:System.Windows.Style> como una forma cómoda de aplicar un conjunto de valores de propiedad a uno o varios elementos. Puede usar un estilo en cualquier elemento que se derive de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, como <xref:System.Windows.Window> o <xref:System.Windows.Controls.Button>.

La manera más común de declarar un estilo es como un recurso en la sección `Resources` de un archivo XAML. Dado que los estilos son recursos, siguen las mismas reglas de ámbito que se aplican a todos los recursos. Dicho de una manera simple, la ubicación de la declaración de un estilo afecta a dónde se puede aplicar el estilo. Por ejemplo, si declara el estilo en el elemento raíz del archivo XAML de definición de la aplicación, el estilo se puede usar en cualquier parte de la aplicación.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/App.xaml#AppResources)]

Si lo declara en uno de los archivos XAML de la aplicación, solo se podrá usar en ese archivo XAML. Para más información acerca de las reglas de ámbito de los recursos, consulte [Recursos XAML](xaml-resources-define.md).

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowSingleResource.xaml#WindowResources)]

Un estilo se compone de elementos secundarios `<Setter>` que establecen propiedades en los elementos a los que el estilo en cuestión se aplica. En el ejemplo anterior, observe que el estilo está configurado para aplicarse a tipos `TextBlock` a través del atributo `TargetType`. El estilo establecerá <xref:System.Windows.Controls.Control.FontSize%2A> en `15` y <xref:System.Windows.Controls.Control.FontWeight%2A> en `ExtraBold`. Agregue un elemento `<Setter>` por cada propiedad que el estilo cambie.

## <a name="apply-a-style-implicitly"></a>Aplicación implícita de un estilo

<xref:System.Windows.Style> es una forma cómoda de aplicar un conjunto de valores de propiedad a más de un elemento. Por ejemplo, fíjese en los siguientes elementos <xref:System.Windows.Controls.TextBlock> y en su apariencia predeterminada en una ventana.

[!code-xaml[TextBlocks](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetTextBlocks)]

![Captura de pantalla de ejemplo de aplicación de un estilo](./media/styles-and-templates-overview/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")

Para cambiar la apariencia predeterminada, puede establecer propiedades como, por ejemplo, <xref:System.Windows.Controls.Control.FontSize%2A> y <xref:System.Windows.Controls.Control.FontFamily%2A> en cada elemento <xref:System.Windows.Controls.TextBlock> directamente. Si, en cambio, quiere que los elementos <xref:System.Windows.Controls.TextBlock> compartan algunas propiedades, puede crear un elemento <xref:System.Windows.Style> en la sección `Resources` del archivo XAML, como se muestra aquí.

[!code-xaml[DefaultTextBlockStyle](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetDefaultTextBlockStyle)]

Al establecer el elemento <xref:System.Windows.Style.TargetType%2A> del estilo en el tipo <xref:System.Windows.Controls.TextBlock> y omitir el atributo `x:Key`, el estilo se aplica a todos los elementos <xref:System.Windows.Controls.TextBlock> cuyo ámbito sea ese estilo, que suele ser el propio archivo XAML.

Ahora los elementos <xref:System.Windows.Controls.TextBlock> aparecen del modo siguiente.

![Captura de pantalla de ejemplo de aplicación de un estilo](./media/styles-and-templates-overview/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")

## <a name="apply-a-style-explicitly"></a>Aplicación explícita de un estilo

Si agrega al estilo un atributo `x:Key` con valor, dicho estilo ya no se aplicará implícitamente a todos los elementos <xref:System.Windows.Style.TargetType%2A>, sino únicamente a los elementos que hagan referencia explícitamente al estilo.

Este es el estilo de la sección anterior, pero declarado con el atributo `x:Key`.

[!code-xaml[ExplicitStyleDeclare](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleDeclare)]

Para aplicar el estilo, establezca la propiedad <xref:System.Windows.FrameworkElement.Style%2A> del elemento en el valor `x:Key`, usando para ello una [extensión de marcado StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md), como se muestra aquí.

[!code-xaml[ExplicitStyleReference](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleReference)]

Fíjese en que el primer elemento <xref:System.Windows.Controls.TextBlock> tiene el estilo aplicado, mientras que el segundo elemento TextBlock permanece inalterado. El estilo implícito de la sección anterior cambió a un estilo que declaró el atributo `x:Key`, lo que significa que el único elemento afectado por el estilo es el que hacía referencia al estilo directamente.

![Captura de pantalla de ejemplo de aplicación de un estilo](./media/styles-and-templates-overview/create-a-style-explicit-textblock.png "create-a-style-explicit-textblock")

Una vez aplicado un estilo, sea implícita o explícitamente, se bloquea y no se puede cambiar. Si desea cambiar un estilo que ya se ha aplicado, cree otro estilo para reemplazar al ya existente. Para obtener más información, vea la propiedad <xref:System.Windows.Style.IsSealed%2A>.

Puede crear un objeto que elija un estilo que se aplique según una lógica personalizada. Puede ver el ejemplo relativo al código de la clase <xref:System.Windows.Controls.StyleSelector>.

## <a name="apply-a-style-programmatically"></a>Aplicación de un estilo mediante programación

Para asignar un estilo con nombre a un elemento mediante programación, obtenga el estilo de la colección de recursos y asígnelo a la propiedad <xref:System.Windows.FrameworkElement.Style%2A> del elemento. Los elementos de una colección de recursos son de tipo <xref:System.Object>, de modo que hay que convertir el estilo recuperado en un estilo <xref:System.Windows.Style?displayProperty=fullName> para poder asignarlo a la propiedad `Style`. Por ejemplo, el siguiente código establece el estilo de un elemento `TextBlock` denominado `textblock1` en el estilo definido `TitleText`.

[!code-csharp[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml.cs#SnippetSetStyleCode)]
[!code-vb[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/MainWindow.xaml.vb#SnippetSetStyleCode)]

## <a name="extend-a-style"></a>Ampliación de un estilo

Puede que queramos que los dos elementos <xref:System.Windows.Controls.TextBlock> compartan algunos valores de propiedad, como <xref:System.Windows.Controls.Control.FontFamily%2A> y una alineación <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> centrada. Pero quizá también aplicar algunas propiedades más al texto **My Pictures**. Esto se puede realizar creando un estilo basado en el primero, como se muestra aquí.

[!code-xaml[DefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

[!code-xaml[TextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

Ahora, este estilo `TextBlock` está centrado y usa una fuente `Comic Sans MS` con un tamaño de `26` y el color de primer plano establecido en <xref:System.Windows.Media.LinearGradientBrush>, como se muestra en el ejemplo. Fíjese en que el valor de <xref:System.Windows.Controls.Control.FontSize%2A> del estilo base se ha reemplazado. Si hay más de un elemento <xref:System.Windows.Setter> que apunta a la misma propiedad en <xref:System.Windows.Style>, el elemento `Setter` que se haya declarado más recientemente será el que tenga prioridad.

Aquí se muestra el aspecto de los elementos <xref:System.Windows.Controls.TextBlock> ahora:

![Bloques de texto con estilo](./media/styles-and-templates-overview/stylingintro-textblocks.png "StylingIntro_TextBlocks")

Este estilo de `TitleText` amplía el estilo que se ha creado para el tipo <xref:System.Windows.Controls.TextBlock>, al que se hace referencia con `BasedOn="{StaticResource {x:Type TextBlock}}"`. También se puede ampliar un estilo que tiene un elemento `x:Key` usando el elemento `x:Key` del estilo en cuestión. Por ejemplo, si hay un estilo denominado `Header1` y queremos ampliarlo, usaríamos `BasedOn="{StaticResource Header1}"`.

## <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Relación entre la propiedad TargetType y el atributo x:Key

Como hemos visto antes, si la propiedad <xref:System.Windows.Style.TargetType%2A> se establece en `TextBlock` sin asignar un elemento `x:Key` al estilo, esto hace que el estilo se aplique a todos los elementos <xref:System.Windows.Controls.TextBlock>. En este caso, `x:Key` se establece implícitamente en `{x:Type TextBlock}`. Esto significa que si el valor de `x:Key` se establece explícitamente en algo distinto de `{x:Type TextBlock}`, <xref:System.Windows.Style> no se aplicará automáticamente a todos los elementos `TextBlock`. En su lugar, deberá aplicar el estilo (usando el valor de `x:Key`) a los elementos `TextBlock` explícitamente. Si el estilo está en la sección de recursos y no se establece la propiedad `TargetType` en el estilo, deberá establecer el atributo `x:Key`.

Además de proporcionar un valor predeterminado para `x:Key`, la propiedad `TargetType` especifica el tipo al que se aplican las propiedades del establecedor. Si no especifica un elemento `TargetType`, deberá calificar las propiedades de los objetos <xref:System.Windows.Setter> con un nombre de clase usando la sintaxis `Property="ClassName.Property"`. Por ejemplo, en lugar de establecer `Property="FontSize"`, deberá establecer <xref:System.Windows.Setter.Property%2A> en `"TextBlock.FontSize"` o en `"Control.FontSize"`.

Tenga en cuenta también que muchos controles de WPF son una combinación de otros controles de WPF. Si crea un estilo aplicable a todos los controles de un tipo, podría obtener resultados inesperados. Por ejemplo, si crea un estilo que tiene como destino el tipo <xref:System.Windows.Controls.TextBlock> en un elemento <xref:System.Windows.Window>, el estilo se aplicará a todos los controles `TextBlock` de la ventana, aun cuando `TextBlock` forme parte de otro control, como <xref:System.Windows.Controls.ListBox>.

## <a name="see-also"></a>Vea también

<!-- - [Create a style for a control](styles-templates-create-apply-template.md) -->
- [Información general de los recursos XAML](xaml-resources-define.md)
- [Información general sobre XAML (WPF y .NET Core)](xaml.md)
