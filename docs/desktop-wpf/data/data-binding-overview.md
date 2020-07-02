---
title: Información general sobre el enlace de datos
description: Obtenga información sobre los distintos orígenes de datos que puede agregar al proyecto en Windows Presentation Foundation para .NET Core. Los orígenes de datos se pueden enlazar a elementos XAML para crear aplicaciones dinámicas.
author: adegeo
ms.date: 09/19/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
ms.openlocfilehash: 829c93e97990b87e6e568614236de9708ef080d9
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325754"
---
# <a name="data-binding-overview-in-wpf"></a>Introducción al enlace de datos en WPF

El enlace de datos en Windows Presentation Foundation (WPF) ofrece una manera sencilla y coherente de que las aplicaciones presenten datos e interactúen con ellos. Los elementos se pueden enlazar a datos desde una variedad de orígenes de datos en forma de objetos .NET y XML. Cualquier control <xref:System.Windows.Controls.ContentControl>, como <xref:System.Windows.Controls.Button>, y cualquier control <xref:System.Windows.Controls.ItemsControl>, como <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ListView>, tienen funciones integradas para habilitar el estilo flexible de elementos de datos individuales o colecciones de elementos de datos. Se pueden generar vistas de ordenación, filtrado ya agrupación encima de los datos.

Las funciones de enlace de datos de WPF ofrecen varias ventajas con respecto a los modelos tradicionales. Por ejemplo, un amplio espectro de propiedades admite de forma inherente el enlace de datos, la representación de los datos es flexible y hay una separación bien definida entre la lógica de negocio y la interfaz de usuario.

En este artículo se describen primero los conceptos fundamentales para el enlace de datos de WPF y, después, se explica el uso de la clase <xref:System.Windows.Data.Binding> y otras características del enlace de datos.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-data-binding"></a>¿Qué es el enlace de datos?

El enlace de datos es el proceso que establece una conexión entre la interfaz de usuario de la aplicación y los datos. Si el enlace está configurado correctamente y los datos proporcionan la notificaciones adecuadas, al cambiar los valores de los datos, los elementos enlazados a los mismos reflejarán de manera automática dichos cambios. El enlace de datos también puede implicar la actualización automática de los datos que subyacen a una representación externa de los datos de un elemento, cuando esta representación cambia. Por ejemplo, si el usuario modifica el valor en un elemento `TextBox`, el valor de los datos subyacentes se actualiza automáticamente para reflejar ese cambio.

Un uso típico del enlace de datos es colocar los datos de configuración locales o de servidor en formularios o en otros controles de la interfaz de usuario. En WPF, este concepto se expande para incluir el enlace de un gran número de propiedades a una gran variedad de orígenes de datos. En WPF, las propiedades de dependencia de los elementos se pueden enlazar a objetos .NET (incluidos los objetos ADO.NET u objetos asociados a propiedades web y servicios web) y datos XML.

Para ver un ejemplo de enlace de datos, eche un vistazo a la interfaz de usuario de la aplicación [Data binding demo][data-binding-demo], que muestra la lista de elementos de una subasta.

![Captura de pantalla de ejemplo de enlace de datos](./media/data-binding-overview/demo.png "DataBinding_DataBindingDemo")

La aplicación muestra las características siguientes de enlace de datos:

- El contenido de ListBox está enlazado a una colección de objetos *AuctionItem*. Un objeto *AuctionItem* tiene propiedades como *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures*, etc.

- A los datos (objetos *AuctionItem*) mostrados en `ListBox` se les ha aplicado una plantilla para que la descripción y el precio actual se muestren para cada artículo. La plantilla se crea mediante <xref:System.Windows.DataTemplate>. Además, la apariencia de cada artículo depende del valor de *SpecialFeatures* del elemento *AuctionItem* que se muestra. Si el valor de *SpecialFeatures* de *AuctionItem* es *Color*, el artículo tiene un borde azul. Si el valor es *Highlight*, el artículo tiene un borde naranja y una estrella. En la sección [Plantillas de datos](#data-templating) se proporciona información sobre las plantillas de datos.

- El usuario puede agrupar, filtrar u ordenar los datos mediante los elementos `CheckBoxes` proporcionados. En la imagen anterior, se seleccionan los elementos `CheckBoxes` **Group by category** (Agrupar por categoría) y **Sort by category and date** (Ordenar por categoría y fecha). Es posible que haya observado que los datos se agrupan en función de la categoría del producto, y el nombre de las categorías se muestra en orden alfabético. Aunque no se aprecia muy bien en la imagen, los artículos están ordenados también por fecha de inicio dentro de cada categoría. La ordenación se realiza mediante una *vista de colección*. En la sección [Enlace a colecciones](#binding-to-collections) se describen las vistas de colección.

- Cuando el usuario selecciona un elemento, <xref:System.Windows.Controls.ContentControl> muestra los detalles del elemento seleccionado. Esta experiencia recibe el nombre de *escenario principal-detalle* . En la sección [Escenario principal-detalle](#master-detail-binding-scenario) se explica este tipo de enlace.

- El tipo de la propiedad *StartDate* es <xref:System.DateTime>, que devuelve una fecha que incluye la hora en milisegundos. En esta aplicación, se ha usado un convertidor personalizado para que se muestre una cadena de fecha más corta. En la sección [Conversión de datos](#data-conversion) se explican los convertidores.

Cuando el usuario selecciona el botón *Add product* (Agregar producto), se muestra este formulario:

![Página "Add Product Listing" (Agregar lista de productos)](./media/data-binding-overview/demo-addproductlisting.png "DataBinding_Demo_AddProductListing")

El usuario puede modificar los campos del formulario, obtener una vista previa de la lista de productos mediante los paneles de vista previa breve o detallada y, después, seleccionar `Submit` para agregar la nueva lista de productos. Todas las opciones de agrupación, filtrado y ordenación existentes se aplicarán a la nueva entrada. En este caso en concreto, el artículo especificado en la imagen anterior se mostrará como el segundo artículo dentro de la categoría *Computer*.

En esta imagen no se muestra la lógica de validación proporcionada en <xref:System.Windows.Controls.TextBox> de *Start Date* (Fecha de inicio). Si el usuario escribe una fecha no válida (formato no válido o fecha pasada), se le notificará con <xref:System.Windows.Controls.ToolTip> y un signo de exclamación rojo junto a <xref:System.Windows.Controls.TextBox>. En la sección [Validación de datos](#data-validation) se describe cómo crear lógica de validación.

Antes de describir las características de enlace de datos que hemos mencionado, primero explicaremos los conceptos fundamentales imprescindibles para comprender el enlace de datos de WPF.

## <a name="basic-data-binding-concepts"></a>Conceptos básicos del enlace de datos

Independientemente del elemento que se vaya a enlazar y de la naturaleza del origen de datos, cada enlace sigue siempre el modelo que se muestra en esta imagen:

![Diagrama que muestra el modelo básico de enlace de datos.](./media/data-binding-overview/basic-data-binding-diagram.png)

Aquí vemos que el enlace de datos es básicamente el puente entre el destino del enlace y el origen del enlace. En la imagen se muestran estos conceptos fundamentales del enlace de datos de WPF:

- Normalmente, cada enlace tiene cuatro componentes:

  - un objeto de destino de enlace;
  - una propiedad de destino;
  - un origen de enlace,
  - una ruta de acceso al valor del origen de enlace que se va a usar.
  
  > Por ejemplo, si quiere enlazar el contenido de `TextBox` a la propiedad `Employee.Name`, el objeto de destino es `TextBox`, la propiedad de destino es la propiedad <xref:System.Windows.Controls.TextBox.Text%2A>, el valor que se va a usar es *Name* y el objeto de origen es el objeto *Employee*.

- La propiedad de destino debe ser una propiedad de dependencia. La mayoría de las propiedades <xref:System.Windows.UIElement> son propiedades de dependencia y la mayoría de las propiedades de dependencia, excepto las de solo lectura, admiten el enlace de datos de forma predeterminada. (Solo los tipos derivados de <xref:System.Windows.DependencyObject> pueden definir propiedades de dependencia, y todos los tipos de <xref:System.Windows.UIElement> derivan de `DependencyObject`).

- Aunque no se especifica en la imagen, hay que destacar que el objeto de origen de enlace no está restringido a ser un objeto .NET personalizado. El enlace de datos de WPF admite datos en forma de objetos .NET y XML. Para proporcionar algunos ejemplos, el origen de enlace puede ser <xref:System.Windows.UIElement>, cualquier objeto de lista, un objeto de servicios web o ADO.NET o un XmlNode que contenga los datos XML. Para más información, vea [Información general sobre orígenes de enlaces](../../framework/wpf/data/binding-sources-overview.md).

Es importante tener en cuenta que cuando establece un enlace, enlaza un destino de enlace *a* un origen de enlace. Por ejemplo, si se muestran algunos datos XML subyacentes en <xref:System.Windows.Controls.ListBox> mediante el enlace de datos, se enlaza `ListBox` a los datos XML.

Para establecer un enlace, se usa el objeto <xref:System.Windows.Data.Binding>. En el resto de este artículo se describen muchos de los conceptos asociados a algunas de las propiedades y el uso del objeto `Binding`.

### <a name="direction-of-the-data-flow"></a>Dirección del flujo de datos

Tal y como indica la flecha de la imagen anterior, el flujo de datos de un enlace puede ir del destino al origen del enlace (por ejemplo, el valor de origen cambia cuando un usuario modifica el valor de `TextBox`) y del origen al destino del enlace (por ejemplo, el contenido de `TextBox` se actualiza con los cambios en el origen del enlace) si el origen del enlace proporciona las notificaciones correspondientes.

Tal vez le interesa que la aplicación permita que los usuarios cambien los datos y los propaguen al objeto de origen. O bien, no puede permitir a los usuarios actualizar los datos de origen. Puede controlar el flujo de datos si configura <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType>.

En esta imagen se muestran los distintos tipos de flujo de datos:

![Flujo de datos de enlace de datos](./media/data-binding-overview/databinding-dataflow.png "DataBinding_DataFlow")

- El enlace <xref:System.Windows.Data.BindingMode.OneWay> permite que los cambios en la propiedad de origen actualicen automáticamente la propiedad de destino, pero los cambios realizados en la propiedad de destino no se propagan hacia la propiedad de origen. Este tipo de enlace es adecuado si el control que se está enlazando es implícitamente de solo lectura. Por ejemplo, podría enlazar a un origen, como un tablero de cotizaciones, o quizás la propiedad de destino no tenga ninguna interfaz de control para realizar modificaciones, como un color de fondo enlazado a datos de una tabla. Si no es necesario supervisar los cambios de la propiedad de destino, el uso del modo de enlace <xref:System.Windows.Data.BindingMode.OneWay> evita la sobrecarga del modo de enlace <xref:System.Windows.Data.BindingMode.TwoWay>.

- El enlace <xref:System.Windows.Data.BindingMode.TwoWay> realiza cambios en la propiedad de origen o en la propiedad de destino para que actualice automáticamente la otra. Este tipo de enlace es adecuado para formularios modificables u otros casos de interfaz de usuario completamente interactiva. La mayoría de las propiedades tienen como valor predeterminado el enlace <xref:System.Windows.Data.BindingMode.OneWay>, pero algunas propiedades de dependencia (normalmente, las propiedades de los controles editables por el usuario, como <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType> y [CheckBox.IsChecked](xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked) tienen como valor predeterminado el enlace <xref:System.Windows.Data.BindingMode.TwoWay>. Una manera de determinar mediante programación si una propiedad de dependencia se enlaza de forma predeterminada de modo unidireccional o bidireccional es obtener los metadatos de la propiedad con <xref:System.Windows.DependencyProperty.GetMetadata%2A?displayProperty=nameWithType> y luego comprobar el valor booleano de la propiedad <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A?displayProperty=nameWithType>.

- <xref:System.Windows.Data.BindingMode.OneWayToSource> es lo contrario del enlace <xref:System.Windows.Data.BindingMode.OneWay>: actualiza la propiedad de origen cuando cambia la propiedad de destino. Podría usar este tipo de enlace si, por ejemplo, solo necesita volver a evaluar el valor de origen de la interfaz de usuario.

- En la imagen no se muestra el enlace <xref:System.Windows.Data.BindingMode.OneTime>, que permite que la propiedad de origen inicialice la propiedad de destino, pero no se propagan los cambios posteriores. Si cambia el contexto de los datos o cambia el objeto del contexto de los datos, este cambio *no* se refleja en la propiedad de destino. Este tipo de enlace es adecuado si una instantánea del estado actual es adecuada o los datos son realmente estáticos. Este tipo de enlace también es útil si quiere inicializar la propiedad de destino con algún valor de una propiedad de origen y no se conoce el contexto de datos de antemano. Este modo es básicamente de una forma más sencilla de enlace <xref:System.Windows.Data.BindingMode.OneWay> que ofrece un mejor rendimiento en casos donde el valor de origen no cambia.

Para detectar cambios en el origen (aplicables a los enlaces <xref:System.Windows.Data.BindingMode.OneWay> y <xref:System.Windows.Data.BindingMode.TwoWay>), el origen debe implementar un mecanismo de notificación de cambio de propiedad adecuado, como <xref:System.ComponentModel.INotifyPropertyChanged>. Vea [Cómo: Implementar la notificación de cambio de propiedad](../../framework/wpf/data/how-to-implement-property-change-notification.md) para obtener un ejemplo de una implementación de <xref:System.ComponentModel.INotifyPropertyChanged>.

La propiedad <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType> proporciona más información sobre los modos de enlace y un ejemplo de cómo especificar la dirección de un enlace.

### <a name="what-triggers-source-updates"></a>Qué desencadena la actualización del origen

Los enlaces que son <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> escuchan los cambios en la propiedad de destino y los propagan de nuevo al origen, lo que se conoce como actualizar el origen. Por ejemplo, puede modificar el texto de un control TextBox para cambiar el valor de origen subyacente.

Pero, ¿el valor del origen se actualiza mientras edita el texto o después de terminar de editarlo y cuando el control pierde el foco? La propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> determina qué desencadena la actualización del origen. En los puntos de las flechas de la derecha en la imagen se muestra el rol de la propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType>.

![Diagrama que muestra el rol de la propiedad UpdateSourceTrigger.](./media/data-binding-overview/data-binding-updatesource-trigger.png)

Si el valor `UpdateSourceTrigger` es <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged?displayProperty=nameWithType>, el valor al que apunta la flecha derecha de <xref:System.Windows.Data.BindingMode.TwoWay> o los enlaces de <xref:System.Windows.Data.BindingMode.OneWayToSource> se actualiza en cuanto cambia la propiedad de destino. Pero si el valor de `UpdateSourceTrigger` es <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>, ese valor solo se actualiza con el nuevo valor cuando la propiedad de destino pierde el foco.

De forma similar a la propiedad <xref:System.Windows.Data.Binding.Mode%2A>, las distintas propiedades de dependencia tienen valores de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> predeterminados diferentes. El valor predeterminado de la mayoría de las propiedades de dependencia es <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, mientras que la propiedad `TextBox.Text` tiene un valor predeterminado de <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. `PropertyChanged` significa que las actualizaciones de origen suelen ocurrir cada vez que cambia la propiedad de destino. Los cambios instantáneos son aceptables para CheckBox y otros controles sencillos. Pero para los campos de texto, la actualización cada vez que se pulsa una tecla puede disminuir el rendimiento y deniega al usuario la oportunidad habitual de retroceder y corregir los errores tipográficos antes confirmar el nuevo valor.

Vea la página de la propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> para obtener información sobre cómo buscar el valor predeterminado de una propiedad de dependencia.

En esta tabla se muestra un escenario de ejemplo para cada valor de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> en el que se usa <xref:System.Windows.Controls.TextBox> como ejemplo.

| Valor UpdateSourceTrigger | Cuándo se actualiza el valor de origen | Escenario de ejemplo de TextBox |
| ------------------------- | ---------------------------------- | ---------------------------- |
| `LostFocus` (valor predeterminado para <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>) | Cuando el control TextBox pierde el foco. | Un control TextBox que está asociado a la lógica de validación (vea [Validación de datos](#data-validation) más adelante). |
| `PropertyChanged` | A medida que escribe en <xref:System.Windows.Controls.TextBox>. | Controles TextBox en una ventana de sala de chat. |
| `Explicit` | Cuando la aplicación llama a <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>. | Controles TextBox en un formulario modificable (solo se actualizan los valores de origen cuando el usuario hace clic en el botón de envío). |

Como ejemplo, vea [Cómo: Controlar cuándo el texto de TextBox actualiza el origen](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).

## <a name="creating-a-binding"></a>Crear un enlace

Para recapitular algunos conceptos descritos en las secciones anteriores, recordemos que un enlace se establece mediante el objeto <xref:System.Windows.Data.Binding> y que cada enlace tiene normalmente cuatro componentes: un destino de enlace, una propiedad de destino, un origen de enlace y una ruta de acceso al valor de origen que se va a usar. En esta sección describe cómo configurar un enlace.

Considere el ejemplo siguiente, en el que el objeto de origen del enlace es una clase denominada *MyData* que se define en el espacio de nombres *SDKSample*. A efectos de demostración, *MyData* tiene una propiedad de cadena denominada *ColorName*, cuyo valor se establece en "Red". Por lo tanto, este ejemplo genera un botón con un fondo rojo.

[!code-xaml[BindNonTextProperty](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColor)]

Para más información sobre la sintaxis de declaración de enlaces y ejemplos sobre cómo configurar un enlace en código, vea [Información general sobre declaraciones de enlaces](../../framework/wpf/data/binding-declarations-overview.md).

Si aplicamos este ejemplo a nuestro diagrama básico, la ilustración resultante tendrá el siguiente aspecto. Aquí se describe un enlace <xref:System.Windows.Data.BindingMode.OneWay> porque la propiedad Background admite el enlace <xref:System.Windows.Data.BindingMode.OneWay> de forma predeterminada.

![Diagrama que muestra Background del enlace de datos.](./media/data-binding-overview/data-binding-button-background-example.png)

Es posible que se pregunte por qué funciona este enlace aunque la propiedad *ColorName* sea de tipo String, mientras que la propiedad <xref:System.Windows.Controls.Control.Background%2A> es de tipo <xref:System.Windows.Media.Brush>. El enlace usa la conversión predeterminada de tipos, que se explica en la sección [Conversión de datos](#data-conversion).

### <a name="specifying-the-binding-source"></a>Especificar el origen del enlace

Si se fija en el ejemplo anterior, para especificar el origen del enlace se establece la propiedad [DockPanel.DataContext](xref:System.Windows.FrameworkElement.DataContext). Después, <xref:System.Windows.Controls.Button> hereda el valor <xref:System.Windows.FrameworkElement.DataContext%2A> de <xref:System.Windows.Controls.DockPanel>, que es su elemento primario. Recordemos que el objeto de origen del enlace es uno de los cuatro componentes necesarios de un enlace. Por tanto, si no se especifica el objeto de origen del enlace, el enlace no funcionará.

Hay varias formas de especificar el objeto de origen del enlace. Es útil usar la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> en un elemento primario cuando se enlazan varias propiedades al mismo origen. Sin embargo, a veces puede ser más adecuado especificar el origen del enlace en declaraciones de enlace individuales. En el ejemplo anterior, en lugar de usar la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A>, puede especificar el origen del enlace si establece la propiedad <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> directamente en la declaración de enlace del botón, como en este ejemplo.

[!code-xaml[BindNonTextPropertyCompactBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColorCompactBinding)]

Además de establecer la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> en un elemento directamente, heredar el valor <xref:System.Windows.FrameworkElement.DataContext%2A> de un antecesor (como el botón del primer ejemplo) y especificar explícitamente el origen de enlace estableciendo la propiedad <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> en el enlace (por ejemplo, el botón del último ejemplo), también puede usar la propiedad <xref:System.Windows.Data.Binding.ElementName?displayProperty=nameWithType> o la propiedad <xref:System.Windows.Data.Binding.RelativeSource?displayProperty=nameWithType> para especificar el origen del enlace. La propiedad <xref:System.Windows.Data.Binding.ElementName%2A> es útil cuando se enlaza a otros elementos de la aplicación, como cuando se usa un control deslizante para ajustar el ancho de un botón. La propiedad <xref:System.Windows.Data.Binding.RelativeSource%2A> es útil cuando el enlace se especifica en <xref:System.Windows.Controls.ControlTemplate> o <xref:System.Windows.Style>. Para obtener más información, vea [Cómo: Especificar el origen de enlace](../../framework/wpf/data/how-to-specify-the-binding-source.md).

### <a name="specifying-the-path-to-the-value"></a>Especificar la ruta de acceso al valor

Si el origen del enlace es un objeto, use la propiedad <xref:System.Windows.Data.Binding.Path?displayProperty=nameWithType> para especificar el valor que se va a usar para el enlace. Si va a enlazar a datos XML, use la propiedad <xref:System.Windows.Data.Binding.XPath?displayProperty=nameWithType> para especificar el valor. En algunos casos, puede aplicarse para usar la propiedad <xref:System.Windows.Data.Binding.Path%2A> incluso cuando los datos son XML. Por ejemplo, si quiere acceder a la propiedad Name de un XmlNode devuelto (como resultado de una consulta XPath), debe usar la propiedad <xref:System.Windows.Data.Binding.Path%2A> además de la propiedad <xref:System.Windows.Data.Binding.XPath%2A>.

Para más información, vea las propiedades <xref:System.Windows.Data.Binding.Path%2A> y <xref:System.Windows.Data.Binding.XPath%2A>.

Aunque hemos recalcado que uno de los cuatro componentes necesarios de un enlace es el valor de <xref:System.Windows.Data.Binding.Path%2A> al valor que se va a usar, en los escenarios en los que se enlaza a un objeto completo, el valor que se usará será el mismo que el objeto de origen del enlace. En esos casos, puede elegir no especificar <xref:System.Windows.Data.Binding.Path%2A>. Considere el ejemplo siguiente.

[!code-xaml[EmptyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/EmptyBinding.xaml#EmptyBinding)]

En el ejemplo anterior se utiliza la sintaxis de enlace vacía: {Binding}. En este caso, <xref:System.Windows.Controls.ListBox> hereda DataContext de un elemento DockPanel primario (no se muestra en este ejemplo). Cuando no se especifica la ruta de acceso, el valor predeterminado es enlazar al objeto completo. En otras palabras, en este ejemplo, la ruta de acceso se ha omitido porque se enlaza la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> a todo el objeto. (Vea la sección [Enlace a colecciones](#binding-to-collections) para saber más).

Además del enlace a una colección, este escenario es útil también cuando se desea enlazar a un objeto completo en lugar de simplemente a una propiedad individual de un objeto. Por ejemplo, si el objeto de origen es de tipo <xref:System.String>, puede que solo quiera enlazar a la propia cadena. Otro escenario común es cuando se desea enlazar un elemento a un objeto con varias propiedades.

Puede ser necesario aplicar lógica personalizada para que los datos sean significativos para la propiedad de destino enlazada. La lógica personalizada puede consistir en un convertidor personalizado si no existe la conversión de tipos predeterminada. Vea [Conversión de datos](#data-conversion) para más información sobre los convertidores.

### <a name="binding-and-bindingexpression"></a>Binding and BindingExpression

Antes de entrar en otras características y usos del enlace de datos, resulta útil presentar la clase <xref:System.Windows.Data.BindingExpression>. Como hemos visto en las secciones anteriores, la clase <xref:System.Windows.Data.Binding> es la clase de alto nivel para la declaración de un enlace; proporciona muchas propiedades que permiten especificar las características de un enlace. Una clase relacionada, <xref:System.Windows.Data.BindingExpression>, es el objeto subyacente que mantiene la conexión entre el origen y el destino. Un enlace contiene toda la información que se puede compartir entre varias expresiones de enlace. Un <xref:System.Windows.Data.BindingExpression> es una expresión de instancia que no se puede compartir y contiene toda la información de instancia del <xref:System.Windows.Data.Binding>.

En el ejemplo siguiente, `myDataObject` es una instancia de la clase `MyData`, `myBinding` es el objeto <xref:System.Windows.Data.Binding> de origen y `MyData` es una clase definida que contiene una propiedad de cadena denominada `MyDataProperty`. Aquí se enlaza el contenido de texto de `myText`, una instancia de <xref:System.Windows.Controls.TextBlock>, a `MyDataProperty`.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ManualBinding.cs#CodeOnlyBinding)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ManualBinding.vb#CodeOnlyBinding)]

Puede usar el mismo objeto *myBinding* para crear otros enlaces. Por ejemplo, puede usar el objeto *myBinding* para enlazar el contenido de texto de una casilla a *MyDataProperty*. En ese escenario, habrá dos instancias de <xref:System.Windows.Data.BindingExpression> que comparten el objeto *myBinding*.

Se devuelve un objeto <xref:System.Windows.Data.BindingExpression> mediante una llamada a <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> en un objeto enlazado a datos. En los artículos siguientes se muestran algunos de los usos de la clase <xref:System.Windows.Data.BindingExpression>:

- [Obtener el objeto de enlace a partir de una propiedad de destino enlazada](../../framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)

- [Controlar cuándo el texto de TextBox actualiza el origen](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)

## <a name="data-conversion"></a>Conversión de datos

En la sección [Crear un enlace](#creating-a-binding), el botón es rojo porque su propiedad <xref:System.Windows.Controls.Control.Background%2A> está enlazada a una propiedad de cadena con el valor "Red". Este valor de cadena funciona porque hay un convertidor de tipos en el tipo <xref:System.Windows.Media.Brush> para convertir el valor de cadena en <xref:System.Windows.Media.Brush>.

Veamos qué ocurre en la imagen de la sección [Crear un enlace](#creating-a-binding) al agregar esta información.

![Diagrama que muestra la propiedad Default del enlace de datos.](./media/data-binding-overview/data-binding-button-default-conversion.png)

Pero ¿y si en lugar de una propiedad de tipo String, el objeto del origen del enlace tiene una propiedad *Color* de tipo <xref:System.Windows.Media.Color>? En ese caso, para que el enlace funcione tendrá que convertir el valor de propiedad *Color* en algo que la propiedad <xref:System.Windows.Controls.Control.Background%2A> pueda aceptar. Necesitaría crear un convertidor personalizado implementando la interfaz <xref:System.Windows.Data.IValueConverter>, como en este ejemplo.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ColorBrushConverter.cs#ColorBrushConverter)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ColorBrushConverter.vb#ColorBrushConverter)]

Vea <xref:System.Windows.Data.IValueConverter> para obtener más información.

Ahora se ha usado el convertidor personalizado en lugar de la conversión predeterminada y este es el aspecto que tiene nuestro diagrama:

![Diagrama que muestra el convertidor personalizado del enlace de datos.](./media/data-binding-overview/data-binding-converter-color-example.png)

Recordemos que las conversiones predeterminadas pueden estar disponibles si el tipo que se va a enlazar contiene convertidores de tipo. Este comportamiento dependerá de los convertidores de tipos disponibles en el destino. Si no está seguro, cree su propio convertidor.

Estos son algunos escenarios típicos en los que sería lógico implementar un convertidor de datos:

- Los datos se muestran de forma diferente, dependiendo de la referencia cultural. Por ejemplo, tal vez quiera implementar un convertidor de monedas o un convertidor de fechas y horas del calendario en función de las convenciones usadas en una determinada referencia cultural.

- Los datos que se utilizan no están diseñados necesariamente para cambiar el valor textual de una propiedad, sino para cambiar otro valor, como el origen de una imagen, o el color o estilo del texto que se va a mostrar. En este caso se pueden utilizar convertidores para convertir el enlace de una propiedad que tal vez no sea adecuada, como el enlace de un campo de texto a la propiedad Background de una celda de tabla.

- Hay varios controles o varias propiedades de controles enlazados a los mismos datos. En ese caso, el enlace principal podría mostrar simplemente el texto, mientras que los otros enlaces controlan los aspectos de presentación, pero se sigue utilizando el mismo enlace como información de origen.

- Una propiedad de destino tiene una colección de enlaces, que se denomina <xref:System.Windows.Data.MultiBinding>. Para <xref:System.Windows.Data.MultiBinding>, se usa un elemento <xref:System.Windows.Data.IMultiValueConverter> personalizado para generar un valor final a partir de los valores de los enlaces. Por ejemplo, el color podría calcularse a partir de los valores de rojo, azul y verde, que pueden ser valores de los mismos o de diferentes objetos de origen del enlace. Vea <xref:System.Windows.Data.MultiBinding> para más ejemplos e información.

## <a name="binding-to-collections"></a>Enlace a colecciones

Un objeto de origen del enlace se puede tratar como un objeto único cuyas propiedades contienen los datos, o como una recolección de datos de objetos polimórficos que suelen estar agrupados (como el resultado de una consulta a una base de datos). Hasta ahora solo hemos hablado del enlace a objetos individuales. Pero es muy común el enlace a una recopilación de datos. Por ejemplo, un escenario común es usar <xref:System.Windows.Controls.ItemsControl> como un elemento <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView> o <xref:System.Windows.Controls.TreeView> para mostrar una recopilación de datos, como en la aplicación que se muestra en la sección [¿Qué es el enlace de datos?](#what-is-data-binding).

Afortunadamente, nuestro diagrama básico aún sigue siendo válido. Si enlaza <xref:System.Windows.Controls.ItemsControl> a una colección, el diagrama tiene este aspecto.

![Diagrama que muestra el objeto ItemsControl del enlace de datos.](./media/data-binding-overview/data-binding-itemscontrol.png)

Como se muestra en este diagrama, para enlazar <xref:System.Windows.Controls.ItemsControl> a un objeto de colección, debe usarse la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A?displayProperty=nameWithType>. Puede considerar `ItemsSource` como el contenido de <xref:System.Windows.Controls.ItemsControl>. El enlace es <xref:System.Windows.Data.BindingMode.OneWay> porque la propiedad `ItemsSource` admite el enlace `OneWay` de forma predeterminada.

### <a name="how-to-implement-collections"></a>Implementación de colecciones

Puede enumerar en cualquier colección que implemente la interfaz <xref:System.Collections.IEnumerable>. Pero para poder configurar enlaces dinámicos para que las inserciones o las eliminaciones en la colección actualicen la interfaz de usuario automáticamente, la colección debe implementar la interfaz <xref:System.Collections.Specialized.INotifyCollectionChanged>. Esta interfaz expone un evento que debe provocarse siempre que se realicen cambios en la colección subyacente.

WPF proporciona la clase <xref:System.Collections.ObjectModel.ObservableCollection%601>, que es una implementación integrada de una recopilación de datos que expone la interfaz <xref:System.Collections.Specialized.INotifyCollectionChanged>. Para permitir totalmente la transferencia de valores de datos de los objetos de origen a los destinos, cada objeto de la colección que admite propiedades enlazables debe implementar también la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>. Para más información, vea [Información general sobre orígenes de enlaces](../../framework/wpf/data/binding-sources-overview.md).

Antes de implementar su propia colección, considere la posibilidad de usar <xref:System.Collections.ObjectModel.ObservableCollection%601> o una de las clases de colección existentes, como <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601> y <xref:System.ComponentModel.BindingList%601>, entre muchas otras. Si cuenta con un escenario avanzado y quiere implementar su propia colección, considere la posibilidad de usar <xref:System.Collections.IList>, que proporciona una colección no genérica de objetos a los que se puede acceder individualmente por índice y, por tanto, proporciona el máximo rendimiento.

### <a name="collection-views"></a>Vistas de colecciones

Una vez que <xref:System.Windows.Controls.ItemsControl> esté enlazado a una recopilación de datos, puede ser interesante ordenar, filtrar o agrupar los datos. Para hacerlo, use las vistas de colección, que son clases que implementan la interfaz <xref:System.ComponentModel.ICollectionView>.

#### <a name="what-are-collection-views"></a>¿Qué son las vistas de colección?

Una vista de colección es un nivel situado encima de la colección de origen del enlace, que le permite navegar y mostrar la colección de origen en función de las consultas de ordenación, filtrado y agrupación, sin tener que cambiar la propia colección de origen subyacente. Una vista de colección también contiene un puntero al elemento actual de la colección. Si la colección de origen implementa la interfaz <xref:System.Collections.Specialized.INotifyCollectionChanged>, los cambios generados por el evento <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> se propagan a las vistas.

Dado que las vistas no cambian las colecciones de origen subyacente, cada colección de origen puede tener varias vistas asociadas. Por ejemplo, puede tener una colección de objetos *Task*. El uso de vistas le permite mostrar los mismos datos de formas diferentes. Por ejemplo, en el lado izquierdo de la página es posible que desee mostrar las tareas ordenadas por prioridad y, en el lado derecho, agrupadas por área.

#### <a name="how-to-create-a-view"></a>Procedimiento para crear una vista

Una manera de crear y utilizar una vista es crear directamente una instancia del objeto de vista y utilizar a continuación esa instancia como el origen del enlace. Por ejemplo, considere la aplicación [Data binding demo][data-binding-demo] que se muestra en la sección [¿Qué es el enlace de datos?](#what-is-data-binding). La aplicación se implementa de tal forma que <xref:System.Windows.Controls.ListBox> se enlaza a una vista sobre la recopilación de datos en lugar de la colección de datos directamente. Este ejemplo se extrae de la aplicación [Data binding demo][data-binding-demo]. La clase <xref:System.Windows.Data.CollectionViewSource> es el proxy XAML de una clase que hereda de <xref:System.Windows.Data.CollectionView>. En este ejemplo concreto, el elemento <xref:System.Windows.Data.CollectionViewSource.Source%2A> de la vista se enlaza a la colección *AuctionItems* (de tipo <xref:System.Collections.ObjectModel.ObservableCollection%601>) del objeto de aplicación actual.

[!code-xaml[CollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#CollectionView)]

Después, el recurso *listingDataView* actúa como el origen del enlace para los elementos de la aplicación, como <xref:System.Windows.Controls.ListBox>.

[!code-xaml[ListBoxCollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxCollectionView)]

Para crear otra vista para la misma colección, puede crear otra instancia de <xref:System.Windows.Data.CollectionViewSource> y asignarle un nombre de `x:Key` diferente.

En la tabla siguiente se muestran los tipos de datos de vista que se crean como vista de colección predeterminada o por <xref:System.Windows.Data.CollectionViewSource>, según el tipo de colección de origen.

| Tipo de colección de origen                    | Tipo de vista de colección | Notas |
| ----------------------------------------- | -------------------- | ----- |
| <xref:System.Collections.IEnumerable>     | Un tipo interno basado en <xref:System.Windows.Data.CollectionView> | No se pueden agrupar los elementos. |
| <xref:System.Collections.IList>           | <xref:System.Windows.Data.ListCollectionView> | Más rápido. |
| <xref:System.ComponentModel.IBindingList> | <xref:System.Windows.Data.BindingListCollectionView> | |

#### <a name="using-a-default-view"></a>Uso de una vista predeterminada

Especificar una vista de colección como origen de enlace es una forma de crear y utilizar una vista de colección. WPF también crea una vista de colección predeterminada para cada colección utilizada como origen de enlace. Si enlaza directamente a una colección, WPF enlaza a su vista predeterminada. Todos los enlaces a una misma colección comparten esta vista predeterminada, de modo que si se realiza un cambio en una vista predeterminada a través de un control enlazado o mediante código (como un cambio de ordenación o en el puntero de elemento actual, que se describe más adelante), este se refleja en el resto de los enlaces a la misma colección.

Para obtener la vista predeterminada, use el método <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A>. Para ver un ejemplo, lea [Cómo: Obtener la vista predeterminada de una recolección de datos](../../framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).

#### <a name="collection-views-with-adonet-datatables"></a>Vistas de colección con DataTables de ADO.NET

Para mejorar el rendimiento, las vistas de colección para objetos <xref:System.Data.DataTable> o <xref:System.Data.DataView> de ADO.NET delegan la ordenación y el filtrado en <xref:System.Data.DataView>; esto hace que la ordenación y el filtrado se compartan entre todas las vistas de colección del origen de datos. Para permitir que cada vista de colección se ordene y se filtre de manera independiente, inicialice cada vista de colección con su propio objeto <xref:System.Data.DataView>.

#### <a name="sorting"></a>Ordenar

Como se mencionó anteriormente, las vistas pueden aplicar un criterio de ordenación a una colección. Cuando este criterio existe en la colección subyacente, los datos pueden o no tener un orden relevante inherente. La vista de la colección le permite aplicar un orden o cambiar el orden predeterminado, en función de los criterios de comparación especificados. Como es una vista de datos basada en un cliente, podría ser habitual que el usuario quisiera ordenar las columnas de los datos de tabla por el valor correspondiente a la columna. Con las vistas, se puede aplicar esta ordenación controlada por el usuario, sin tener que realizar ningún cambio en la colección subyacente ni tener tampoco que volver a consultar el contenido de la colección. Para ver un ejemplo, lea [Procedimiento para ordenar una columna GridView cuando se hace clic en un encabezado](../../framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).

En este ejemplo se muestra la lógica de ordenación de <xref:System.Windows.Controls.CheckBox> "Sort by category and date" (Ordenar por categoría y fecha) de la interfaz de usuario de la aplicación en la sección [¿Qué es el enlace de datos?](#what-is-data-binding).

[!code-csharp[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#AddSortChecked)]
[!code-vb[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#AddSortChecked)]

#### <a name="filtering"></a>Filtrado

Las vistas también pueden aplicar un filtro a una colección, por lo que la vista muestra solo un subconjunto determinado de la colección completa. Podría filtrar los datos en función de una condición. Por ejemplo, como ocurre en la aplicación de la sección [¿Qué es el enlace de datos?](#what-is-data-binding), el control <xref:System.Windows.Controls.CheckBox> "Show only bargains" (Mostrar solo ofertas) contiene lógica para filtrar los artículos que cuestan 25 dólares estadounidenses o más. El código de abajo se ejecuta para establecer *ShowOnlyBargainsFilter* como el controlador de eventos <xref:System.Windows.Data.CollectionViewSource.Filter> cuando se selecciona ese <xref:System.Windows.Controls.CheckBox>.

[!code-csharp[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingViewFilter)]
[!code-vb[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingViewFilter)]

El controlador de eventos *ShowOnlyBargainsFilter* se implementa así:

[!code-csharp[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#FilterEvent)]
[!code-vb[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#FilterEvent)]

Si directamente usa una de las clases de <xref:System.Windows.Data.CollectionView> en lugar de <xref:System.Windows.Data.CollectionViewSource>, usaría la propiedad <xref:System.Windows.Data.CollectionView.Filter%2A> para especificar una devolución de llamada. Para ver un ejemplo, consulte [Filter Data in a View](../../framework/wpf/data/how-to-filter-data-in-a-view.md) (Filtrado de datos en una vista).

#### <a name="grouping"></a>Agrupar

Salvo la clase interna que ve una colección <xref:System.Collections.IEnumerable>, todas las vistas de colección admiten la *agrupación*, que permite al usuario dividir la colección en la vista de colección en grupos lógicos. Los grupos pueden ser explícitos, donde el usuario proporciona una lista de grupos, o implícitos, donde los grupos se generan dinámicamente en función de los datos.

En este ejemplo se muestra la lógica del control <xref:System.Windows.Controls.CheckBox> "Group by category" (Agrupar por categoría).

[!code-csharp[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingGroupCheck)]
[!code-vb[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingGroupCheck)]

Para obtener otro ejemplo de agrupación, consulte [Group Items in a ListView That Implements a GridView](../../framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md) (Agrupación de elementos en un control ListView que implemente un modo).

#### <a name="current-item-pointers"></a>Punteros de elemento actual

Las vistas admiten también la noción de elemento actual. Puede navegar por los objetos en una vista de colección. A medida que navega por los objetos, mueve un puntero de elemento que le permite recuperar el objeto ubicado concretamente en esa posición en la colección. Para ver un ejemplo, lea [Cómo: Navegar por los objetos de una colección de datos mediante CollectionView](../../framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).

Dado que WPF solo se enlaza a una colección mediante una vista (una vista especificada por el usuario o la vista predeterminada de la colección), todos los enlaces a las colecciones tienen un puntero de elemento actual. Al enlazar a una vista, el carácter de barra diagonal ("/") de un valor `Path` designa el elemento actual de la vista. En el ejemplo siguiente, el contexto de datos es una vista de colección. La primera línea enlaza a la colección. La segunda línea enlaza al elemento actual de la colección. La tercera línea enlaza a la propiedad `Description` del elemento actual de la colección.

```xaml
<Button Content="{Binding }" />
<Button Content="{Binding Path=/}" />
<Button Content="{Binding Path=/Description}" />
```

La sintaxis de barra diagonal y propiedad también puede apilarse para recorrer una jerarquía de colecciones. En el ejemplo siguiente se enlaza al elemento actual de una colección denominada `Offices`, que es una propiedad del elemento actual de la colección de origen.

```xaml
<Button Content="{Binding /Offices/}" />
```

Toda ordenación o filtrado que se aplique a la colección puede afectar al puntero del elemento actual. La ordenación conserva el puntero del elemento actual en el último elemento seleccionado, pero se reestructura la vista de colección a su alrededor. (Quizás el elemento seleccionado estaba antes al principio de la lista, pero ahora puede que esté en alguna parte del medio). El filtrado conserva el elemento seleccionado si la selección permanece en la vista después del filtrado. De lo contrario, el puntero del elemento actual se establece en el primer elemento de la vista de colección filtrada.

#### <a name="master-detail-binding-scenario"></a>Escenario de enlace principal-detalle

La noción de elemento actual no es solo útil para la navegación de elementos en una colección, sino también para el escenario de enlace principal-detalle. Piense de nuevo en la interfaz de usuario de aplicación de la sección [¿Qué es el enlace de datos?](#what-is-data-binding). En esa aplicación, la selección dentro de <xref:System.Windows.Controls.ListBox> determina el contenido que se muestra en el control <xref:System.Windows.Controls.ContentControl>. Dicho de otro modo, cuando se selecciona un elemento <xref:System.Windows.Controls.ListBox>, el control <xref:System.Windows.Controls.ContentControl> muestra los detalles del elemento seleccionado.

Puede implementar el escenario principal-detalle simplemente con dos o más controles enlazados a la misma vista. En este ejemplo de la aplicación [Data binding demo][data-binding-demo] se muestra el marcado de <xref:System.Windows.Controls.ListBox> y de <xref:System.Windows.Controls.ContentControl> que se ven en la interfaz de usuario de la aplicación en la sección [¿Qué es el enlace de datos?](#what-is-data-binding).

[!code-xaml[ListBoxContentControl](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxContentControl)]

Observe que ambos controles están enlazados al mismo origen, el recurso estático *listingDataView* (vea la definición de este recurso en la sección [Procedimiento para crear una vista](#how-to-create-a-view)). Este enlace funciona porque cuando se enlaza un objeto singleton (<xref:System.Windows.Controls.ContentControl> en este caso) a una vista de colección, se enlaza automáticamente al objeto <xref:System.Windows.Data.CollectionView.CurrentItem%2A> de la vista. Los objetos <xref:System.Windows.Data.CollectionViewSource> sincronizan automáticamente la moneda y la selección. Si el control de lista no está enlazado a un objeto <xref:System.Windows.Data.CollectionViewSource> como ocurre en este ejemplo, sería necesario establecer su propiedad <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> en `true` para que funcione.

Si quiere ver otros ejemplos, lea [Cómo: Enlazar a una colección y mostrar información basada en la selección](../../framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) y [Cómo: Usar el patrón principal-detalle con datos jerárquicos](../../framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).

Tal vez haya observado que en el ejemplo anterior se utiliza una plantilla. De hecho, los datos no se mostrarían tal y como queremos si no se usan plantillas (la que usa explícitamente <xref:System.Windows.Controls.ContentControl> y la que usa implícitamente <xref:System.Windows.Controls.ListBox>). Trataremos el tema de la inclusión de datos en plantillas en la siguiente sección.

## <a name="data-templating"></a>Plantillas de datos

Si no se usan plantillas de datos, la interfaz de usuario de la aplicación de la sección [¿Qué es el enlace de datos?](#what-is-data-binding) tendría este aspecto:

![Demo de enlace de datos sin plantillas de datos](./media/data-binding-overview/demo-no-template.png)

Como se muestra en el ejemplo de la sección anterior, los controles <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ContentControl> están enlazados al objeto de colección completo (concretamente, a la vista sobre el objeto de colección) de los objetos *AuctionItem*. Sin instrucciones específicas sobre cómo mostrar la recopilación de datos, <xref:System.Windows.Controls.ListBox> muestra la representación de cadena de cada objeto de la colección subyacente y <xref:System.Windows.Controls.ContentControl> muestra la representación de cadena del objeto al que está enlazado.

Para resolver ese problema, la aplicación define <xref:System.Windows.DataTemplate?text=DataTemplates>. Como se muestra en el ejemplo de la sección anterior, <xref:System.Windows.Controls.ContentControl> usa explícitamente la plantilla de datos *detailsProductListingTemplate*. El control <xref:System.Windows.Controls.ListBox> usa implícitamente esta plantilla de datos al mostrar los objetos *AuctionItem* en la colección.

[!code-xaml[AuctionItemDataTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#AuctionItemDataTemplate)]

Al usar estos dos objetos DataTemplate, la interfaz de usuario que se obtiene es la que se muestra en la sección [¿Qué es el enlace de datos?](#what-is-data-binding). Como puede ver en esa captura de pantalla, además de permitir colocar los datos en los controles, los objetos DataTemplate permiten darle un aspecto atractivo a los datos. Por ejemplo, los objetos <xref:System.Windows.DataTrigger> se usan en el objeto <xref:System.Windows.DataTemplate> anterior para que los objetos *AuctionItem* con el valor *SpecialFeatures* en *HighLight* se muestren con un borde naranja y una estrella.

Para más información sobre las plantillas de datos, vea [Información general sobre plantillas de datos](../../framework/wpf/data/data-templating-overview.md).

## <a name="data-validation"></a>Validación de datos

La mayoría de las aplicaciones que toman datos proporcionados por el usuario necesitan lógica de validación para asegurarse de que el usuario ha escrito la información esperada. Las comprobaciones de validación pueden basarse en el tipo, el intervalo, el formato u otros requisitos específicos de la aplicación. En esta sección se describe cómo funciona la validación de datos en WPF.

### <a name="associating-validation-rules-with-a-binding"></a>Asociar reglas de validación a un enlace

El modelo de enlace de datos de WPF permite asociar <xref:System.Windows.Data.Binding.ValidationRules%2A> con el objeto <xref:System.Windows.Data.Binding>. Por ejemplo, en este ejemplo se enlaza un objeto <xref:System.Windows.Controls.TextBox> a una propiedad `StartPrice` y se agrega un objeto <xref:System.Windows.Controls.ExceptionValidationRule> a la propiedad <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType>.

[!code-xaml[TextboxStartPrice](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartPrice)]

Un objeto <xref:System.Windows.Controls.ValidationRule> comprueba si el valor de una propiedad es válido. WPF tiene dos tipos de objetos <xref:System.Windows.Controls.ValidationRule> integrados:

- Un objeto <xref:System.Windows.Controls.ExceptionValidationRule> comprueba las excepciones producidas durante la actualización de la propiedad del origen de enlace. En el ejemplo anterior, `StartPrice` es de tipo entero. Cuando el usuario especifica un valor que no se puede convertir en un entero, se produce una excepción, lo que ocasiona que el enlace se marque como no válido. Una sintaxis alternativa para establecer el objeto <xref:System.Windows.Controls.ExceptionValidationRule> explícitamente consiste en establecer la propiedad <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> en `true` en el objeto <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.MultiBinding>.

- Un objeto <xref:System.Windows.Controls.DataErrorValidationRule> busca errores generados por los objetos que implementan la interfaz <xref:System.ComponentModel.IDataErrorInfo>. Para ver un ejemplo del uso de esta regla de validación, visite <xref:System.Windows.Controls.DataErrorValidationRule>. Una sintaxis alternativa para establecer el objeto <xref:System.Windows.Controls.DataErrorValidationRule> explícitamente consiste en establecer la propiedad <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> en `true` en el objeto <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.MultiBinding>.

También puede crear su propia regla de validación si deriva de la clase <xref:System.Windows.Controls.ValidationRule> e implementa el método <xref:System.Windows.Controls.ValidationRule.Validate%2A>. En este ejemplo se muestra la regla usada por el control <xref:System.Windows.Controls.TextBox> "Start Date" (Fecha de inicio) de *Add Product Listing* (Agregar lista de productos) de la sección [¿Qué es el enlace de datos?](#what-is-data-binding).

[!code-csharp[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/FutureDateRule.cs#FutureDateRule)]
[!code-vb[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/FutureDateRule.vb#FutureDateRule)]

El control <xref:System.Windows.Controls.TextBox> *StartDateEntryForm* se usa este *FutureDateRule*, tal y como se muestra en este ejemplo.

[!code-xaml[TextboxStartDate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartDate)]

Dado que el valor <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> es <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, el motor de enlace actualiza el valor de origen en cada pulsación de tecla, lo que significa que también comprueba todas las reglas de la colección <xref:System.Windows.Data.Binding.ValidationRules%2A> en cada pulsación de tecla. Ofreceremos una descripción más detallada en la sección Proceso de validación.

### <a name="providing-visual-feedback"></a>Proporcionar comentarios visuales

Si el usuario especifica un valor no válido, puede ser interesante proporcionar algunos comentarios sobre el error en la interfaz de usuario de la aplicación. Una manera de proporcionar estos comentarios es establecer la propiedad adjunta <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> en un control <xref:System.Windows.Controls.ControlTemplate> personalizado. Como se muestra en la subsección anterior, el control <xref:System.Windows.Controls.TextBox> *StartDateEntryForm* usa un control <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> denominado *validationTemplate*. En este ejemplo se muestra la definición de *validationTemplate*.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#ControlTemplate)]

El elemento <xref:System.Windows.Controls.AdornedElementPlaceholder> especifica dónde se debe colocar el control que se va a adornar.

Además, también puede usar un <xref:System.Windows.Controls.ToolTip> para mostrar el mensaje de error. Los controles <xref:System.Windows.Controls.TextBox> *StartDateEntryForm* y *StartPriceEntryForm* usan el estilo *textStyleTextBox*, que crea un elemento <xref:System.Windows.Controls.ToolTip> que muestra el mensaje de error. En el ejemplo siguiente se muestra la definición de *textStyleTextBox*. La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` cuando uno o varios de los enlaces de las propiedades del elemento enlazado son erróneos.

[!code-xaml[TextBoxStyle](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextBoxStyle)]

Con los controles <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> y <xref:System.Windows.Controls.ToolTip> personalizados, el elemento <xref:System.Windows.Controls.TextBox> *StartDateEntryForm* tiene un aspecto similar a este cuando se produce un error de validación.

![Error de validación de enlace de datos](./media/data-binding-overview/demo-validation-date.png "DataBindingDemo_Validation")

Si el elemento <xref:System.Windows.Data.Binding> tiene reglas de validación asociadas pero no especifica un elemento <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> en el control enlazado, se usará un elemento <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> predeterminado para notificar a los usuarios cuando se produzca un error de validación. El elemento <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> predeterminado es una plantilla de control que define un borde rojo en la capa de adornos. Con los controles predeterminados <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> y <xref:System.Windows.Controls.ToolTip>, la interfaz de usuario del control <xref:System.Windows.Controls.TextBox> *StartPriceEntryForm* es similar a la siguiente cuando se produce un error de validación.

![Error de validación de enlace de datos](./media/data-binding-overview/demo-validation-price.png "DataBindingDemo_ValidationDefault")

Para ver un ejemplo sobre cómo proporcionar lógica para validar todos los controles de un cuadro de diálogo, vea la sección Cuadros de diálogo personalizados en [Resumen de cuadros de diálogo](../../framework/wpf/app-development/dialog-boxes-overview.md).

### <a name="validation-process"></a>Proceso de validación

La validación normalmente se produce cuando el valor de un destino se transfiere a la propiedad de origen del enlace. Esta transferencia se produce en los enlaces <xref:System.Windows.Data.BindingMode.TwoWay> y <xref:System.Windows.Data.BindingMode.OneWayToSource>. Recuerde que lo que hace una actualización de origen depende del valor de la propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>, tal y como se describe en la sección [Qué desencadena la actualización del origen](#what-triggers-source-updates).

Los elementos siguientes describen el proceso de *validación*. Si se produce un error de validación o de cualquier otro tipo en cualquier momento del proceso, este se detiene:

1. El motor de enlace comprueba si hay definido algún objeto <xref:System.Windows.Controls.ValidationRule> personalizado cuyo <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> esté establecido en <xref:System.Windows.Controls.ValidationStep.RawProposedValue> para ese <xref:System.Windows.Data.Binding>, en cuyo caso llama al método <xref:System.Windows.Controls.ValidationRule.Validate%2A> en cada <xref:System.Windows.Controls.ValidationRule> hasta que uno de ellos genere un error o hasta que todos ellos pasen.

2. A continuación, el motor de enlace llama al convertidor, si existe alguno.

3. Si el convertidor se ejecuta correctamente, el motor de enlace comprueba si hay definido algún objeto <xref:System.Windows.Controls.ValidationRule> personalizado cuyo <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> está establecido en <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> para ese <xref:System.Windows.Data.Binding>, en cuyo caso llama al método <xref:System.Windows.Controls.ValidationRule.Validate%2A> en cada <xref:System.Windows.Controls.ValidationRule> que tiene <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecido en <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue>, hasta que uno de ellos se ejecuta en un error o hasta que todos ellos pasan.

4. El motor de enlace establece la propiedad de origen.

5. El motor de enlace comprueba si hay definido algún objeto <xref:System.Windows.Controls.ValidationRule> personalizado cuyo <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> esté establecido en <xref:System.Windows.Controls.ValidationStep.UpdatedValue> para ese <xref:System.Windows.Data.Binding>, en cuyo caso llama al método <xref:System.Windows.Controls.ValidationRule.Validate%2A> en cada <xref:System.Windows.Controls.ValidationRule> que tenga <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecido en <xref:System.Windows.Controls.ValidationStep.UpdatedValue> hasta que uno de ellos genere un error o hasta que todos ellos pasen. Si un elemento <xref:System.Windows.Controls.DataErrorValidationRule> está asociado a un enlace y <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> está establecido en el valor predeterminado, <xref:System.Windows.Controls.ValidationStep.UpdatedValue>, se comprueba <xref:System.Windows.Controls.DataErrorValidationRule> en este momento. En este punto, se comprueba cualquier enlace que tenga <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> establecido en `true`.

6. El motor de enlace comprueba si hay definido algún objeto <xref:System.Windows.Controls.ValidationRule> personalizado cuyo <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> esté establecido en <xref:System.Windows.Controls.ValidationStep.CommittedValue> para ese <xref:System.Windows.Data.Binding>, en cuyo caso llama al método <xref:System.Windows.Controls.ValidationRule.Validate%2A> en cada <xref:System.Windows.Controls.ValidationRule> que tenga <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecido en <xref:System.Windows.Controls.ValidationStep.CommittedValue> hasta que uno de ellos genere un error o hasta que todos ellos pasen.

Si <xref:System.Windows.Controls.ValidationRule> no pasa en ningún momento de todo este proceso, el motor de enlace crea un objeto <xref:System.Windows.Controls.ValidationError> y lo agrega a la colección <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> del elemento enlazado. Antes de que el motor de enlace ejecute los objetos <xref:System.Windows.Controls.ValidationRule> en cualquier paso, quita cualquier <xref:System.Windows.Controls.ValidationError> que se haya agregado a la propiedad adjunta <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> del elemento enlazado durante ese paso. Por ejemplo, si un elemento <xref:System.Windows.Controls.ValidationRule> cuyo <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> está establecido en <xref:System.Windows.Controls.ValidationStep.UpdatedValue> genera un error, la próxima vez que se produzca el proceso de validación, el motor de enlace quitará ese elemento <xref:System.Windows.Controls.ValidationError> inmediatamente antes de llamar a cualquier <xref:System.Windows.Controls.ValidationRule> que tenga <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecido en <xref:System.Windows.Controls.ValidationStep.UpdatedValue>.

Cuando <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> no está vacío, propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> del elemento se establece en `true`. Además, si la propiedad <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> de <xref:System.Windows.Data.Binding> está establecida en `true`, el motor de enlace genera el evento adjunto <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> en el elemento.

Tenga en cuenta también que una transferencia de valor válida en cualquier dirección (destino a origen u origen a destino) borra la propiedad adjunta <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>.

Si el enlace tiene un elemento <xref:System.Windows.Controls.ExceptionValidationRule> asociado o tiene la propiedad <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> establecida en `true` y se produce una excepción cuando el motor de enlace establece el origen, el motor de enlace comprueba si hay <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>. Tiene la opción de usar la devolución de llamada de <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> para proporcionar un controlador personalizado para controlar excepciones. Si no se especifica <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> en <xref:System.Windows.Data.Binding>, el motor de enlace crea <xref:System.Windows.Controls.ValidationError> con la excepción y lo agrega a la colección <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> del elemento enlazado.

## <a name="debugging-mechanism"></a>Mecanismo de depuración

Puede establecer la propiedad adjunta <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> en un objeto relacionado con el enlace para recibir información sobre el estado de un enlace concreto.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [Enlazar a los resultados de una consulta LINQ](../../framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)
- [Enlace de datos](../../framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Data binding demo][data-binding-demo]
- [Artículos de procedimientos](../../framework/wpf/data/data-binding-how-to-topics.md)
- [Enlazar a un origen de datos ADO.NET](../../framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)

[data-binding-demo]: https://github.com/microsoft/WPF-Samples/tree/master/Sample%20Applications/DataBindingDemo "Aplicación Data binding demo"
