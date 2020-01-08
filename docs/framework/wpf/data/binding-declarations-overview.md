---
title: Información general sobre declaraciones de enlaces
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- markup extensions [WPF]
- data binding [WPF], declarations
- object element syntax [WPF]
- binding data [WPF], declarations
- syntax [WPF], object elements
- binding declarations [WPF]
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
ms.openlocfilehash: 8fea61c463928ee69ef5dd0dfbf107f89c5384ff
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544469"
---
# <a name="binding-declarations-overview"></a>Información general sobre declaraciones de enlaces

En este tema se describen las distintas formas de declarar un enlace.

<a name="Prereq"></a>

## <a name="prerequisites"></a>Requisitos previos

Antes de leer este tema, es importante que esté familiarizado con el concepto y el uso de las extensiones de marcado. Para más información sobre las extensiones de marcado, consulte [Extensiones de marcado y XAML de WPF](../advanced/markup-extensions-and-wpf-xaml.md).

En este tema no se tratan los conceptos de enlace de datos. Para obtener una explicación de los conceptos de enlace de datos, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).

<a name="BindinginXAML"></a>

## <a name="declaring-a-binding-in-xaml"></a>Declarar un enlace en XAML

En esta sección se describe cómo declarar en XAML.

<a name="MarkupExtensionSyntax"></a>

### <a name="markup-extension-usage"></a>Uso de la extensión de marcado

<xref:System.Windows.Data.Binding> es una extensión de marcado. Cuando se utiliza la extensión de enlace para declarar un enlace, la declaración consta de una serie de cláusulas después de la palabra clave `Binding` y separadas por comas (,). Las cláusulas de la declaración de enlace pueden estar en cualquier orden y hay muchas combinaciones posibles. Las cláusulas son *nombres*=pares de *valores* donde *Name* es el nombre de la propiedad <xref:System.Windows.Data.Binding> y *Value* es el valor que se establece para la propiedad.

Al crear cadenas de declaración de enlace en el marcado, se adjuntará a la propiedad de dependencia concreta de un objeto de destino. En el ejemplo siguiente se muestra cómo enlazar la propiedad <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> mediante la extensión de enlace, especificando las propiedades <xref:System.Windows.Data.Binding.Source%2A> y <xref:System.Windows.Data.Binding.Path%2A>.

[!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#L37-L37)]

Puede especificar la mayoría de las propiedades de la clase <xref:System.Windows.Data.Binding> de esta manera. Para obtener más información sobre la extensión de enlace, así como para obtener una lista de las propiedades de <xref:System.Windows.Data.Binding> que no se pueden establecer mediante la extensión de enlace, vea información general sobre la [extensión de marcado de enlace](../advanced/binding-markup-extension.md) .

<a name="ObjectElementSyntax"></a>

### <a name="object-element-syntax"></a>Sintaxis de elemento de objeto

La sintaxis de elemento de objeto es una alternativa a la creación de la declaración de enlace. En la mayoría de los casos, no hay ninguna ventaja particular para usar la extensión de marcado o la sintaxis de elemento de objeto. Sin embargo, en aquellos casos en los que la extensión de marcado no admite el escenario, como cuando el valor de la propiedad es de un tipo que no es una cadena para la que no existe conversión de tipo, debe utilizar la sintaxis de elemento de objeto.

El siguiente es un ejemplo de la sintaxis de elemento de objeto y el uso de la extensión de marcado:

[!code-xaml[BindConversionMarkup#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]

En el ejemplo se enlaza la propiedad <xref:System.Windows.Controls.TextBlock.Foreground%2A> declarando un enlace mediante la sintaxis de la extensión. La declaración de enlace para la propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> usa la sintaxis del elemento de objeto.

Para más información sobre los distintos términos, consulte [Detalles de la sintaxis XAML](../advanced/xaml-syntax-in-detail.md).

<a name="MBandPB"></a>

### <a name="multibinding-and-prioritybinding"></a>MultiBinding y PriorityBinding

<xref:System.Windows.Data.MultiBinding> y <xref:System.Windows.Data.PriorityBinding> no admiten la sintaxis de la extensión XAML. Por lo tanto, debe usar la sintaxis del elemento de objeto si está declarando un <xref:System.Windows.Data.MultiBinding> o un <xref:System.Windows.Data.PriorityBinding> en XAML.

<a name="BindinginCode"></a>

## <a name="creating-a-binding-in-code"></a>Crear un enlace mediante código

Otra manera de especificar un enlace es establecer las propiedades directamente en un <xref:System.Windows.Data.Binding> objeto en el código. En el ejemplo siguiente se muestra cómo crear un objeto <xref:System.Windows.Data.Binding> y especificar las propiedades en el código.  En este ejemplo, `TheConverter` es un objeto que implementa la interfaz <xref:System.Windows.Data.IValueConverter>.

[!code-csharp[BindConversion#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
[!code-vb[BindConversion#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]

Si el objeto que se va a enlazar es un <xref:System.Windows.FrameworkElement> o un <xref:System.Windows.FrameworkContentElement>, puede llamar al método `SetBinding` en el objeto directamente en lugar de utilizar <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>. Para obtener un ejemplo, consulte [Crear un enlace mediante código](how-to-create-a-binding-in-code.md).

<a name="Path_Syntax"></a>

## <a name="binding-path-syntax"></a>Sintaxis de la ruta de enlace

Use la propiedad <xref:System.Windows.Data.Binding.Path%2A> para especificar el valor de origen al que desea enlazar:

- En el caso más simple, el valor de la propiedad <xref:System.Windows.Data.Binding.Path%2A> es el nombre de la propiedad del objeto de origen que se va a usar para el enlace, como `Path=PropertyName`.

- Las subpropiedades de una propiedad se pueden especificar mediante una sintaxis similar C#a la de. Por ejemplo, la cláusula `Path=ShoppingCart.Order` define el enlace a la subpropiedad `Order` del objeto o la propiedad `ShoppingCart`.

- Para enlazar a una propiedad adjunta, coloque paréntesis alrededor de esta propiedad. Por ejemplo, para enlazar a la propiedad adjunta <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, la sintaxis es `Path=(DockPanel.Dock)`.

- Los indizadores de una propiedad pueden especificarse entre corchetes después del nombre de la propiedad donde se aplica el indizador. Por ejemplo, la cláusula `Path=ShoppingCart[0]` establece el enlace al índice que se corresponde a cómo la indización interna de la propiedad administra la cadena literal "0". También se admiten indizadores anidados.

- Los indizadores y las subpropiedades se pueden combinar en una cláusula `Path`; por ejemplo, `Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`.

- Dentro de los indexadores puede tener varios parámetros de indizador separados por comas (,). El tipo de cada parámetro se puede especificar entre paréntesis. Por ejemplo, puede tener `Path="[(sys:Int32)42,(sys:Int32)24]"`, donde `sys` está asignado al espacio de nombres `System`.

- Cuando el origen es una vista de colección, el elemento actual se puede especificar con una barra diagonal (/). Por ejemplo, la cláusula `Path=/` establece el enlace con el elemento actual de la vista. Cuando el origen es una colección, esta sintaxis especifica el elemento actual de la vista de colección predeterminada.

- Los nombres de propiedad y las barras diagonales se pueden combinar para atravesar propiedades que son colecciones. Por ejemplo, `Path=/Offices/ManagerName` especifica el elemento actual de la colección de origen, que contiene una propiedad `Offices` que también es una colección. Su elemento actual es un objeto que contiene una propiedad `ManagerName`.

- Opcionalmente, se puede usar una ruta de acceso de punto (.) para enlazar con el origen actual. Por ejemplo, `Text="{Binding}"` es equivalente a `Text="{Binding Path=.}"`.

### <a name="escaping-mechanism"></a>Mecanismo de escape

- Dentro de los indizadores ([ ]), el carácter de intercalación (^) realiza el escape del carácter siguiente.

- Si establece <xref:System.Windows.Data.Binding.Path%2A> en XAML, también necesitará usar como escape (mediante entidades XML) determinados caracteres que son especiales para la definición del lenguaje XML:

  - Use `&amp;` para realizar el escape del carácter "&".

  - Use `&gt;` para realizar el escape de la etiqueta final ">".

- Además, si describe el enlace completo en un atributo mediante la sintaxis de extensión de marcado, deberá realizar el escape (con la barra diagonal inversa \\) de los caracteres que son especiales para el analizador de extensión de marcado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

  - La barra diagonal inversa (\\) es el mismo carácter de escape.

  - El signo igual (=) separa el nombre de propiedad del valor de propiedad.

  - La coma (,) separa las propiedades.

  - La llave de cierre (}) es el final de una extensión de marcado.

<a name="Default"></a>

## <a name="default-behaviors"></a>Comportamientos predeterminados

El comportamiento predeterminado es el siguiente si no se especifica en la declaración.

- Se crea un convertidor predeterminado que intenta realizar una conversión de tipos entre el valor de origen de enlace y el valor de destino del enlace. Si no se puede realizar una conversión, el convertidor predeterminado devuelve `null`.

- Si no se establece <xref:System.Windows.Data.Binding.ConverterCulture%2A>, el motor de enlace utiliza la propiedad `Language` del objeto de destino de enlace. En XAML, tiene como valor predeterminado "en-US" o hereda el valor de elemento raíz (o cualquier elemento) de la página, si se ha establecido explícitamente.

- Siempre que el enlace ya tenga un contexto de datos (por ejemplo, el contexto de datos heredado procedente de un elemento primario) y con independencia de que el elemento o la colección que se devuelve en ese contexto sea apropiado para el enlace sin necesitar una modificación adicional de la ruta, una declaración de enlace no puede tener ninguna cláusula: `{Binding}` suele ser la manera en que se especifica un enlace para los estilos de datos, donde el enlace se actúa sobre una colección. Para más información, consulte la sección "Utilizar objetos completos como origen de enlace" en [Información general sobre orígenes de enlaces](binding-sources-overview.md).

- La <xref:System.Windows.Data.Binding.Mode%2A> predeterminada varía en función de la propiedad de dependencia que se está enlazando. Siempre puede declarar explícitamente el modo de enlace para asegurarse de que el enlace tiene el comportamiento deseado. En general, las propiedades de control que puede modificar el usuario, como <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> y <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType>, tienen como valor predeterminado enlaces bidireccionales, mientras que la mayoría de las demás propiedades tienen como valor predeterminado enlaces unidireccionales.

- El valor <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> predeterminado varía entre <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> y <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> en función de la propiedad de dependencia enlazada. El valor predeterminado de la mayoría de las propiedades de dependencia es <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, mientras que la propiedad <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> tiene un valor predeterminado de <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.

## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
- [Enlace de datos](../advanced/optimizing-performance-data-binding.md)
- [Sintaxis de PropertyPath de XAML](../advanced/propertypath-xaml-syntax.md)
