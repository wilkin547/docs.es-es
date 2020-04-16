---
title: Información general sobre el enlace de datos
description: Obtenga información sobre los diferentes orígenes de datos que puede agregar al proyecto en Windows Presentation Foundation para .NET Core. Los orígenes de datos se pueden enlazar a elementos XAML para crear aplicaciones dinámicas.
author: thraka
ms.date: 09/19/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
ms.openlocfilehash: 7f17ff094a35c04ba880c87c6966d7d249817516
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433257"
---
# <a name="data-binding-overview-in-wpf"></a>Información general sobre el enlace de datos en WPFWPF

El enlace de datos en Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) proporciona una forma sencilla y coherente para que las aplicaciones presenten e interactúen con los datos. Los elementos se pueden enlazar a datos de una variedad de orígenes de datos en forma de objetos .NET y XML. Cualquiera <xref:System.Windows.Controls.ContentControl> como <xref:System.Windows.Controls.Button> y <xref:System.Windows.Controls.ItemsControl>cualquiera, <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ListView>como y , tienen funcionalidad integrada para habilitar el estilo flexible de elementos de datos individuales o colecciones de elementos de datos. Se pueden generar vistas de ordenación, filtrado ya agrupación encima de los datos.

La funcionalidad de enlace de datos en WPFWPF tiene varias ventajas sobre los modelos tradicionales, incluida la compatibilidad inherente para el enlace de datos mediante una amplia gama de propiedades, la representación flexible de la interfaz de usuario de los datos y la separación limpia de la lógica empresarial de la interfaz de usuario.

En este artículo se describen primero los conceptos <xref:System.Windows.Data.Binding> fundamentales para el enlace de datos wpfWPF y, a continuación, se describe el uso de la clase y otras características del enlace de datos.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-data-binding"></a>¿Qué es el enlace de datos?

El enlace de datos es el proceso que establece una conexión entre la interfaz de usuario de la aplicación y los datos que muestra. Si el enlace está configurado correctamente y los datos proporcionan la notificaciones adecuadas, al cambiar los valores de los datos, los elementos enlazados a los mismos reflejarán de manera automática dichos cambios. El enlace de datos también puede implicar la actualización automática de los datos que subyacen a una representación externa de los datos de un elemento, cuando esta representación cambia. Por ejemplo, si el usuario edita el valor en un `TextBox` elemento, el valor de datos subyacente se actualiza automáticamente para reflejar ese cambio.

Un uso típico del enlace de datos es colocar datos de configuración local o de servidor en formularios u otros controles de interfaz de usuario. En WPFWPF, este concepto se expande para incluir el enlace de una amplia gama de propiedades a una variedad de orígenes de datos. En WPFWPF, las propiedades de dependencia de los elementos se pueden enlazar a objetos .NET (incluidos ADO.NET objetos u objetos asociados con servicios web y propiedades Web) y datos XML.

Para obtener un ejemplo de enlace de datos, eche un vistazo a la siguiente interfaz de usuario de la aplicación desde la [demostración][data-binding-demo]de enlace de datos , que muestra una lista de elementos de subasta.

![Captura de pantalla de ejemplo de enlace de datos](./media/data-binding-overview/demo.png "DataBinding_DataBindingDemo")

La aplicación muestra las siguientes características del enlace de datos:

- El contenido de la ListBox está enlazado a una colección de *AuctionItem* objetos. Un objeto *AuctionItem* tiene propiedades como *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures*, etc.

- Los datos (*objetos AuctionItem)* que se muestran en la `ListBox` plantilla se conforman para que la descripción y el precio actual se muestran para cada artículo. La plantilla se crea <xref:System.Windows.DataTemplate>mediante un archivo . Además, la apariencia de cada artículo depende del valor de *SpecialFeatures* del elemento *AuctionItem* que se muestra. Si el valor de *SpecialFeatures* de *AuctionItem* es *Color*, el artículo tiene un borde azul. Si el valor es *Highlight*, el artículo tiene un borde naranja y una estrella. En la sección [Plantillas de datos](#data-templating) se proporciona información sobre las plantillas de datos.

- El usuario puede agrupar, filtrar u `CheckBoxes` ordenar los datos mediante el proporcionado. En la imagen anterior, se seleccionan **Agrupar por categoría** y Ordenar por categoría y **fecha.** `CheckBoxes` Es posible que haya observado que los datos se agrupan en función de la categoría del producto, y el nombre de las categorías se muestra en orden alfabético. Aunque no se aprecia muy bien en la imagen, los artículos están ordenados también por fecha de inicio dentro de cada categoría. La ordenación se realiza mediante una vista de *colección.* La sección [Enlace a colecciones](#binding-to-collections) describe las vistas de colección.

- Cuando el usuario selecciona un <xref:System.Windows.Controls.ContentControl> elemento, muestra los detalles del elemento seleccionado. Esta experiencia se denomina *escenario de detalle maestro.* La sección [Escenario de detalles maestros](#master-detail-binding-scenario) proporciona información sobre este tipo de enlace.

- El tipo de la <xref:System.DateTime>propiedad *StartDate* es , que devuelve una fecha que incluye la hora al milisegundo. En esta aplicación, se ha utilizado un convertidor personalizado para que se muestre una cadena de fecha más corta. La sección [Conversión](#data-conversion) de datos proporciona información sobre los convertidores.

Cuando el usuario selecciona el botón *Agregar producto,* aparece el siguiente formulario.

![Agregar página de listado de productos](./media/data-binding-overview/demo-addproductlisting.png "DataBinding_Demo_AddProductListing")

El usuario puede editar los campos del formulario, obtener una vista previa `Submit` de la lista de productos mediante los paneles de vista previa cortos o detallados y seleccionar agregar la nueva lista de productos. Cualquier configuración de agrupación, filtrado y ordenación existente se aplicará a la nueva entrada. En este caso en concreto, el artículo especificado en la imagen anterior se mostrará como el segundo artículo dentro de la categoría *Computer*.

No se muestra en esta imagen es la lógica de validación proporcionada en la fecha <xref:System.Windows.Controls.TextBox>de *inicio.* Si el usuario introduce una fecha no válida (formato no válido o <xref:System.Windows.Controls.ToolTip> una fecha anterior), se <xref:System.Windows.Controls.TextBox>notificará al usuario con un signo de exclamación y un signo de exclamación rojo junto al archivo . En la sección [Validación de datos](#data-validation) se describe cómo crear lógica de validación.

Antes de entrar en las diferentes características de enlace de datos descritas anteriormente, primero discutiremos los conceptos fundamentales que son críticos para comprender el enlace de datos WPFWPF.

## <a name="basic-data-binding-concepts"></a>Conceptos básicos de enlace de datos

Independientemente del elemento que se va a enlazar y la naturaleza del origen de datos, cada enlace siempre sigue el modelo ilustrado por la siguiente figura.

![Diagrama que muestra el modelo de enlace de datos básico.](./media/data-binding-overview/basic-data-binding-diagram.png)

Como se muestra en la figura, el enlace de datos es esencialmente el puente entre el destino de enlace y el origen de enlace. La figura muestra los siguientes conceptos fundamentales de enlace de datos WPFWPF:

- Normalmente, cada enlace tiene cuatro componentes:

  - Un objeto de destino de enlace.
  - Una propiedad de destino.
  - Un origen de enlace.
  - Una ruta de acceso al valor en el origen de enlace que se va a usar.
  
  > Por ejemplo, si desea enlazar el `TextBox` contenido `Employee.Name` de a a `TextBox`la propiedad, el <xref:System.Windows.Controls.TextBox.Text%2A> objeto de destino es el , la propiedad de destino es la propiedad, el valor que se va a usar es *Name*y el objeto de origen es el objeto *Employee.*

- La propiedad de destino debe ser una propiedad de dependencia. La <xref:System.Windows.UIElement> mayoría de las propiedades son propiedades de dependencia y la mayoría de las propiedades de dependencia, excepto las de solo lectura, admiten el enlace de datos de forma predeterminada. (Solo los tipos <xref:System.Windows.DependencyObject> derivados pueden definir <xref:System.Windows.UIElement> propiedades `DependencyObject`de dependencia; y todos los tipos derivan de .)

- Aunque no se muestra en la figura, debe tenerse en cuenta que el objeto de origen de enlace no está restringido a ser un objeto .NET personalizado. El enlace de datos WPFWPF admite datos en forma de objetos .NET y XML. Para proporcionar algunos ejemplos, el <xref:System.Windows.UIElement>origen de enlace puede ser un objeto de lista , un objeto de ADO.NET o Servicios web o un XmlNode que contenga los datos XML. Para obtener más información, vea Información general sobre [orígenes](../../framework/wpf/data/binding-sources-overview.md)de enlace .

Es importante recordar que cuando se establece un enlace, se enlaza un destino de enlace *a* un origen de enlace. Por ejemplo, si muestra algunos datos XML <xref:System.Windows.Controls.ListBox> subyacentes en un `ListBox` enlace de datos using, va a enlazar los datos XML.

Para establecer un enlace, <xref:System.Windows.Data.Binding> utilice el objeto. El resto de este artículo describe muchos de los conceptos asociados con y algunas de las propiedades y el uso del `Binding` objeto.

### <a name="direction-of-the-data-flow"></a>Dirección del flujo de datos

Como indica la flecha de la figura anterior, el flujo de datos de un enlace puede ir desde el destino de enlace `TextBox`al origen de enlace (por ejemplo, el `TextBox` valor de origen cambia cuando un usuario edita el valor de un ) y/o desde el origen de enlace al destino de enlace (por ejemplo, el contenido se actualiza con cambios en el origen de enlace) si el origen de enlace proporciona las notificaciones adecuadas.

Es posible que desee que la aplicación permita a los usuarios cambiar los datos y propagarlos de nuevo al objeto de origen. O bien, no puede permitir a los usuarios actualizar los datos de origen. Puede controlar el flujo de <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType>datos estableciendo el archivo .

Esta figura ilustra los diferentes tipos de flujo de datos:

![Flujo de datos de enlace de datos](./media/data-binding-overview/databinding-dataflow.png "DataBinding_DataFlow")

- <xref:System.Windows.Data.BindingMode.OneWay>El enlace hace que los cambios en la propiedad de origen actualicen automáticamente la propiedad de destino, pero los cambios en la propiedad de destino no se propagan de nuevo a la propiedad de origen. Este tipo de enlace es adecuado si el control que se está enlazando es implícitamente de solo lectura. Por ejemplo, puede enlazar a un origen como un ticker de acciones, o tal vez la propiedad de destino no tiene ninguna interfaz de control proporcionada para realizar cambios, como un color de fondo enlazado a datos de una tabla. Si no es necesario supervisar los cambios de la propiedad de destino, el uso del modo de enlace <xref:System.Windows.Data.BindingMode.OneWay> evita la sobrecarga del modo de enlace <xref:System.Windows.Data.BindingMode.TwoWay>.

- <xref:System.Windows.Data.BindingMode.TwoWay>El enlace hace que los cambios en la propiedad de origen o la propiedad de destino actualicen automáticamente la otra. Este tipo de enlace es adecuado para formularios editables u otros escenarios de interfaz de usuario totalmente interactivos. La mayoría <xref:System.Windows.Data.BindingMode.OneWay> de las propiedades tienen como valor predeterminado el enlace, <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType> pero algunas propiedades <xref:System.Windows.Data.BindingMode.TwoWay> de dependencia (normalmente propiedades de controles editables por el usuario, como el y [CheckBox.IsChecked](xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked) valor predeterminado para el enlace. Una forma mediante programación de determinar si una propiedad de dependencia enlaza unidireccional o <xref:System.Windows.DependencyProperty.GetMetadata%2A?displayProperty=nameWithType> bidireccional de forma predeterminada <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A?displayProperty=nameWithType> es obtener los metadatos de propiedad con y, a continuación, comprobar el valor booleano de la propiedad.

- <xref:System.Windows.Data.BindingMode.OneWayToSource>es el <xref:System.Windows.Data.BindingMode.OneWay> reverso de la unión; actualiza la propiedad de origen cuando cambia la propiedad de destino. Un escenario de ejemplo es si solo necesita volver a evaluar el valor de origen de la interfaz de usuario.

- No se muestra en <xref:System.Windows.Data.BindingMode.OneTime> la figura es el enlace, lo que hace que la propiedad de origen inicialice la propiedad de destino, pero no propaga los cambios posteriores. Si el contexto de datos cambia o el objeto en el contexto de datos cambia, el cambio *no* se refleja en la propiedad de destino. Este tipo de enlace es adecuado si una instantánea del estado actual es adecuada o los datos son realmente estáticos. Este tipo de enlace también es útil si quiere inicializar la propiedad de destino con algún valor de una propiedad de origen y no se conoce el contexto de datos de antemano. Este modo es esencialmente una <xref:System.Windows.Data.BindingMode.OneWay> forma más sencilla de enlace que proporciona un mejor rendimiento en los casos en que el valor de origen no cambia.

Para detectar cambios <xref:System.Windows.Data.BindingMode.OneWay> de <xref:System.Windows.Data.BindingMode.TwoWay> origen (aplicables a y enlaces), <xref:System.ComponentModel.INotifyPropertyChanged>el origen debe implementar un mecanismo de notificación de cambio de propiedad adecuado, como . Consulte [Cómo: implementar la notificación](../../framework/wpf/data/how-to-implement-property-change-notification.md) de <xref:System.ComponentModel.INotifyPropertyChanged> cambio de propiedad para obtener un ejemplo de una implementación.

La <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType> propiedad proporciona más información sobre los modos de enlace y un ejemplo de cómo especificar la dirección de un enlace.

### <a name="what-triggers-source-updates"></a>Qué desencadena las actualizaciones de origen

Enlaces que <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> son o escuchan los cambios en la propiedad de destino y los propagan de nuevo al origen, conocido como actualización del origen. Por ejemplo, puede modificar el texto de un control TextBox para cambiar el valor de origen subyacente.

Sin embargo, ¿se actualiza el valor de origen mientras edita el texto o después de terminar de editar el texto y el control pierde el foco? La <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> propiedad determina qué desencadena la actualización del origen. Los puntos de las flechas derechas de <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> la figura siguiente ilustran el rol de la propiedad.

![Diagrama que muestra el rol de la UpdateSourceTrigger propiedad.](./media/data-binding-overview/data-binding-updatesource-trigger.png)

Si `UpdateSourceTrigger` el <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged?displayProperty=nameWithType>valor es , a continuación, <xref:System.Windows.Data.BindingMode.TwoWay> el <xref:System.Windows.Data.BindingMode.OneWayToSource> valor señalado por la flecha derecha de o los enlaces se actualiza tan pronto como cambia la propiedad de destino. Sin embargo, si el `UpdateSourceTrigger` valor es <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>, ese valor solo se actualiza con el nuevo valor cuando la propiedad de destino pierde el foco.

Al igual <xref:System.Windows.Data.Binding.Mode%2A> que la propiedad, <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> diferentes propiedades de dependencia tienen valores predeterminados diferentes. El valor predeterminado de la mayoría de las propiedades de dependencia es <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, mientras que la propiedad `TextBox.Text` tiene un valor predeterminado de <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. `PropertyChanged`significa que las actualizaciones de origen suelen producirse cada vez que cambia la propiedad de destino. Los cambios instantáneos están bien para CheckBoxes y otros controles simples. Sin embargo, para los campos de texto, la actualización después de cada pulsación de tecla puede disminuir el rendimiento y deniega al usuario la oportunidad habitual de retroceder y corregir errores de escritura antes de confirmar el nuevo valor.

Consulte <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> la página de propiedades para obtener información sobre cómo encontrar el valor predeterminado de una propiedad de dependencia.

En la tabla siguiente se <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proporciona <xref:System.Windows.Controls.TextBox> un escenario de ejemplo para cada valor mediante el como ejemplo.

| Valor UpdateSourceTrigger | Cuando se actualiza el valor de origen | Escenario de ejemplo para TextBox |
| ------------------------- | ---------------------------------- | ---------------------------- |
| `LostFocus`(predeterminado <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>para ) | Cuando el TextBox control pierde el foco. | Un cuadro de texto que está asociado con la lógica de validación (consulte [validación](#data-validation) de datos a continuación). |
| `PropertyChanged` | A medida que <xref:System.Windows.Controls.TextBox>escribe en el archivo . | Controles de cuadro de texto en una ventana de sala de chat. |
| `Explicit` | Cuando la <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>aplicación llama . | Controles TextBox en un formulario editable (actualiza los valores de origen solo cuando el usuario hace clic en el botón Enviar). |

Para obtener un ejemplo, vea [Cómo: Controlar cuando el text TextBox actualiza el origen](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).

## <a name="creating-a-binding"></a>Creación de un enlace

Para volver a establecer algunos de los conceptos descritos <xref:System.Windows.Data.Binding> en las secciones anteriores, establezca un enlace mediante el objeto y cada enlace normalmente tiene cuatro componentes: un destino de enlace, una propiedad de destino, un origen de enlace y una ruta de acceso al valor de origen que se va a usar. En esta sección describe cómo configurar un enlace.

Considere el ejemplo siguiente, en el que el objeto de origen del enlace es una clase denominada *MyData* que se define en el espacio de nombres *SDKSample*. Para fines de demostración, *MyData* tiene una propiedad de cadena denominada *ColorName* cuyo valor se establece en "Rojo". Por lo tanto, este ejemplo genera un botón con un fondo rojo.

[!code-xaml[BindNonTextProperty](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColor)]

Para obtener más información sobre la sintaxis de la declaración de enlace y ejemplos de cómo configurar un enlace en el código, vea Información general sobre [declaraciones](../../framework/wpf/data/binding-declarations-overview.md)de enlace .

Si aplicamos este ejemplo a nuestro diagrama básico, la ilustración resultante tendrá el siguiente aspecto. Esta figura describe <xref:System.Windows.Data.BindingMode.OneWay> un enlace porque <xref:System.Windows.Data.BindingMode.OneWay> el Background propiedad admite el enlace de forma predeterminada.

![Diagrama que muestra el enlace de datos Background propiedad.](./media/data-binding-overview/data-binding-button-background-example.png)

Puede preguntarse por qué funciona este enlace aunque la <xref:System.Windows.Controls.Control.Background%2A> propiedad *ColorName* sea de tipo string mientras la propiedad sea de tipo <xref:System.Windows.Media.Brush>. Este enlace usa la conversión de tipos predeterminada, que se describe en la sección [Conversión](#data-conversion) de datos.

### <a name="specifying-the-binding-source"></a>Especificar el origen de enlace

Tenga en cuenta que en el ejemplo anterior, el origen de enlace se especifica estableciendo el [DockPanel.DataContext](xref:System.Windows.FrameworkElement.DataContext) propiedad. A <xref:System.Windows.Controls.Button> continuación, <xref:System.Windows.FrameworkElement.DataContext%2A> hereda <xref:System.Windows.Controls.DockPanel>el valor del , que es su elemento primario. Recordemos que el objeto de origen del enlace es uno de los cuatro componentes necesarios de un enlace. Por tanto, si no se especifica el objeto de origen del enlace, el enlace no funcionará.

Hay varias formas de especificar el objeto de origen del enlace. El <xref:System.Windows.FrameworkElement.DataContext%2A> uso de la propiedad en un elemento primario es útil cuando se enlazan varias propiedades al mismo origen. Sin embargo, a veces puede ser más adecuado especificar el origen del enlace en declaraciones de enlace individuales. Para el ejemplo anterior, <xref:System.Windows.FrameworkElement.DataContext%2A> en lugar de usar la propiedad, puede especificar el origen de enlace estableciendo la <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> propiedad directamente en la declaración de enlace del botón, como en el ejemplo siguiente.

[!code-xaml[BindNonTextPropertyCompactBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColorCompactBinding)]

Aparte de <xref:System.Windows.FrameworkElement.DataContext%2A> establecer la propiedad en <xref:System.Windows.FrameworkElement.DataContext%2A> un elemento directamente, heredar el valor de un antecesor (como <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> el botón en el primer ejemplo) y especificar <xref:System.Windows.Data.Binding.ElementName?displayProperty=nameWithType> explícitamente <xref:System.Windows.Data.Binding.RelativeSource?displayProperty=nameWithType> el origen de enlace estableciendo la propiedad en el enlace (por ejemplo, el botón el último ejemplo), también puede usar la propiedad o la propiedad para especificar el origen de enlace. La <xref:System.Windows.Data.Binding.ElementName%2A> propiedad es útil cuando se enlaza a otros elementos de la aplicación, como cuando se usa un control deslizante para ajustar el ancho de un botón. La <xref:System.Windows.Data.Binding.RelativeSource%2A> propiedad es útil cuando el <xref:System.Windows.Controls.ControlTemplate> enlace <xref:System.Windows.Style>se especifica en un archivo . Para obtener más información, vea [Cómo: especificar el origen de enlace](../../framework/wpf/data/how-to-specify-the-binding-source.md).

### <a name="specifying-the-path-to-the-value"></a>Especificar la ruta de acceso al valor

Si el origen de enlace es <xref:System.Windows.Data.Binding.Path?displayProperty=nameWithType> un objeto, utilice la propiedad para especificar el valor que se usará para el enlace. Si va a enlazar a datos <xref:System.Windows.Data.Binding.XPath?displayProperty=nameWithType> XML, utilice la propiedad para especificar el valor. En algunos casos, puede ser <xref:System.Windows.Data.Binding.Path%2A> aplicable el uso de la propiedad incluso cuando los datos son XML. Por ejemplo, si desea tener acceso a la propiedad Name de un XmlNode devuelto <xref:System.Windows.Data.Binding.Path%2A> (como resultado <xref:System.Windows.Data.Binding.XPath%2A> de una consulta XPath), debe usar la propiedad además de la propiedad.

Para obtener más <xref:System.Windows.Data.Binding.Path%2A> información, consulte las propiedades y. <xref:System.Windows.Data.Binding.XPath%2A>

Aunque hemos hecho hincapié en que el <xref:System.Windows.Data.Binding.Path%2A> valor a usar es uno de los cuatro componentes necesarios de un enlace, en los escenarios que desea enlazar a un objeto completo, el valor que se va a usar sería el mismo que el objeto de origen de enlace. En esos casos, es aplicable <xref:System.Windows.Data.Binding.Path%2A>no especificar un archivo . Considere el ejemplo siguiente.

[!code-xaml[EmptyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/EmptyBinding.xaml#EmptyBinding)]

En el ejemplo anterior se utiliza la sintaxis de enlace vacía: {Binding}. En este caso, hereda el <xref:System.Windows.Controls.ListBox> DataContext de un elemento DockPanel primario (no se muestra en este ejemplo). Cuando no se especifica la ruta de acceso, el valor predeterminado es enlazar al objeto completo. En otras palabras, en este ejemplo, la ruta <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de acceso se ha dejado fuera porque estamos enlazando la propiedad a todo el objeto. (Consulte la sección [Enlace a colecciones](#binding-to-collections) para obtener una discusión en profundidad.)

Además del enlace a una colección, este escenario es útil también cuando se desea enlazar a un objeto completo en lugar de simplemente a una propiedad individual de un objeto. Por ejemplo, si el objeto <xref:System.String>de origen es de tipo , es posible que simplemente desee enlazar a la propia cadena. Otro escenario común es cuando se desea enlazar un elemento a un objeto con varias propiedades.

Es posible que deba aplicar lógica personalizada para que los datos sean significativos para la propiedad de destino enlazada. La lógica personalizada puede tener la forma de un convertidor personalizado si no existe la conversión de tipos predeterminada. Consulte [Conversión de](#data-conversion) datos para obtener información sobre los convertidores.

### <a name="binding-and-bindingexpression"></a>Binding and BindingExpression

Antes de entrar en otras características y usos del <xref:System.Windows.Data.BindingExpression> enlace de datos, es útil introducir la clase. Como se ha visto en <xref:System.Windows.Data.Binding> secciones anteriores, la clase es la clase de alto nivel para la declaración de un enlace; proporciona muchas propiedades que permiten especificar las características de un enlace. Una clase <xref:System.Windows.Data.BindingExpression>relacionada, , es el objeto subyacente que mantiene la conexión entre el origen y el destino. Un enlace contiene toda la información que se puede compartir entre varias expresiones de enlace. A <xref:System.Windows.Data.BindingExpression> es una expresión de instancia que no se <xref:System.Windows.Data.Binding>puede compartir y contiene toda la información de instancia del archivo .

Considere el ejemplo `myDataObject` siguiente, donde `MyData` es `myBinding` una instancia <xref:System.Windows.Data.Binding> de `MyData` la clase, es el objeto `MyDataProperty`de origen y es una clase definida que contiene una propiedad de cadena denominada . En este ejemplo se `myText`enlaza el <xref:System.Windows.Controls.TextBlock>contenido `MyDataProperty`de texto de , una instancia de , a .

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ManualBinding.cs#CodeOnlyBinding)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ManualBinding.vb#CodeOnlyBinding)]

Puede usar el mismo objeto *myBinding* para crear otros enlaces. Por ejemplo, puede usar el objeto *myBinding* para enlazar el contenido de texto de una casilla de verificación a *MyDataProperty*. En ese escenario, habrá dos <xref:System.Windows.Data.BindingExpression> instancias de compartir el objeto *myBinding.*

Un <xref:System.Windows.Data.BindingExpression> objeto se <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> devuelve mediante una llamada a un objeto enlazado a datos. Los siguientes artículos muestran algunos <xref:System.Windows.Data.BindingExpression> de los usos de la clase:

- [Obtener el objeto de enlace a partir de una propiedad de destino enlazada](../../framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)

- [Control Cuando el text TextBox actualiza el origen](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)

## <a name="data-conversion"></a>Conversión de datos

En la sección Creación de [un enlace,](#creating-a-binding) el botón es rojo porque su <xref:System.Windows.Controls.Control.Background%2A> propiedad está enlazada a una propiedad de cadena con el valor "Rojo". Este valor de cadena funciona porque <xref:System.Windows.Media.Brush> un convertidor de tipos <xref:System.Windows.Media.Brush>está presente en el tipo para convertir el valor de cadena en un archivo .

Agregar esta información a la figura la sección [Crear un enlace](#creating-a-binding) tiene este aspecto.

![Diagrama que muestra la propiedad Default del enlace de datos.](./media/data-binding-overview/data-binding-button-default-conversion.png)

Sin embargo, ¿qué sucede si en lugar de *Color* tener una <xref:System.Windows.Media.Color>propiedad de tipo string el objeto de origen de enlace tiene una propiedad Color de tipo ? En ese caso, para que el enlace funcione, *Color* primero tendría que convertir <xref:System.Windows.Controls.Control.Background%2A> el valor de la propiedad Color en algo que la propiedad acepte. Necesitaría crear un convertidor personalizado implementando la <xref:System.Windows.Data.IValueConverter> interfaz, como en el ejemplo siguiente.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ColorBrushConverter.cs#ColorBrushConverter)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ColorBrushConverter.vb#ColorBrushConverter)]

Consulte <xref:System.Windows.Data.IValueConverter> para obtener más información.

Ahora el convertidor personalizado se utiliza en lugar de la conversión predeterminada, y nuestro diagrama se ve así.

![Diagrama que muestra el convertidor personalizado de enlace de datos.](./media/data-binding-overview/data-binding-converter-color-example.png)

Recordemos que las conversiones predeterminadas pueden estar disponibles si el tipo que se va a enlazar contiene convertidores de tipo. Este comportamiento dependerá de los convertidores de tipos disponibles en el destino. Si no está seguro, cree su propio convertidor.

Los siguientes son algunos escenarios típicos en los que tiene sentido implementar un convertidor de datos:

- Los datos se muestran de forma diferente, dependiendo de la referencia cultural. Por ejemplo, es posible que desee implementar un convertidor de moneda o un convertidor de fecha y hora de calendario basado en las convenciones utilizadas en una referencia cultural determinada.

- Los datos que se utilizan no están diseñados necesariamente para cambiar el valor textual de una propiedad, sino para cambiar otro valor, como el origen de una imagen, o el color o estilo del texto que se va a mostrar. En este caso se pueden utilizar convertidores para convertir el enlace de una propiedad que tal vez no sea adecuada, como el enlace de un campo de texto a la propiedad Background de una celda de tabla.

- Más de un control o varias propiedades de controles están enlazadas a los mismos datos. En ese caso, el enlace principal podría mostrar simplemente el texto, mientras que los otros enlaces controlan los aspectos de presentación, pero se sigue utilizando el mismo enlace como información de origen.

- Una propiedad de destino tiene una colección <xref:System.Windows.Data.MultiBinding>de enlaces, que se denomina . Para <xref:System.Windows.Data.MultiBinding>, se <xref:System.Windows.Data.IMultiValueConverter> usa un personalizado para generar un valor final a partir de los valores de los enlaces. Por ejemplo, el color podría calcularse a partir de los valores de rojo, azul y verde, que pueden ser valores de los mismos o de diferentes objetos de origen del enlace. Consulte <xref:System.Windows.Data.MultiBinding> ejemplos e información.

## <a name="binding-to-collections"></a>Enlace a colecciones

Un objeto de origen de enlace se puede tratar como un único objeto cuyas propiedades contienen datos o como una colección de datos de objetos polimórficos que a menudo se agrupan (como el resultado de una consulta a una base de datos). Hasta ahora sólo hemos discutido el enlace a objetos individuales. Sin embargo, el enlace a una colección de datos es un escenario común. Por ejemplo, un escenario común <xref:System.Windows.Controls.ItemsControl> es <xref:System.Windows.Controls.ListBox>usar <xref:System.Windows.Controls.ListView>un <xref:System.Windows.Controls.TreeView> ejemplo , , o mostrar una colección de datos, como en la aplicación que se muestra en la sección Qué es el enlace de [datos.](#what-is-data-binding)

Afortunadamente, nuestro diagrama básico aún sigue siendo válido. Si va a <xref:System.Windows.Controls.ItemsControl> enlazar una colección, el diagrama tiene este aspecto.

![Diagrama que muestra el enlace de datos ItemsControl objeto.](./media/data-binding-overview/data-binding-itemscontrol.png)

Como se muestra en este <xref:System.Windows.Controls.ItemsControl> diagrama, para <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A?displayProperty=nameWithType> enlazar un a un objeto de colección, propiedad es la propiedad que se va a utilizar. Se puede `ItemsSource` pensar como el <xref:System.Windows.Controls.ItemsControl>contenido de la . El enlace <xref:System.Windows.Data.BindingMode.OneWay> se `ItemsSource` debe `OneWay` a que la propiedad admite el enlace de forma predeterminada.

### <a name="how-to-implement-collections"></a>Cómo implementar colecciones

Puede enumerar sobre cualquier colección <xref:System.Collections.IEnumerable> que implemente la interfaz. Sin embargo, para configurar enlaces dinámicos para que las inserciones o <xref:System.Collections.Specialized.INotifyCollectionChanged> eliminaciones de la colección actualicen la interfaz de usuario automáticamente, la colección debe implementar la interfaz. Esta interfaz expone un evento que debe provocarse siempre que se realicen cambios en la colección subyacente.

WPFWPF <xref:System.Collections.ObjectModel.ObservableCollection%601> proporciona la clase, que es una implementación integrada <xref:System.Collections.Specialized.INotifyCollectionChanged> de una colección de datos que expone la interfaz. Para admitir completamente la transferencia de valores de datos de objetos de origen <xref:System.ComponentModel.INotifyPropertyChanged> a destinos, cada objeto de la colección que admite propiedades enlazables también debe implementar la interfaz. Para obtener más información, vea Información general sobre [orígenes](../../framework/wpf/data/binding-sources-overview.md)de enlace .

Antes de implementar su <xref:System.Collections.ObjectModel.ObservableCollection%601> propia colección, considere la <xref:System.Collections.Generic.List%601>posibilidad <xref:System.Collections.ObjectModel.Collection%601>de <xref:System.ComponentModel.BindingList%601>usar o una de las clases de colección existentes, como , , y , entre muchas otras. Si tiene un escenario avanzado y desea implementar <xref:System.Collections.IList>su propia colección, considere la posibilidad de usar , que proporciona una colección no genérica de objetos a los que el índice puede tener acceso individualmente y, por lo tanto, proporciona el mejor rendimiento.

### <a name="collection-views"></a>Collection views

Una <xref:System.Windows.Controls.ItemsControl> vez que está enlazado a una recopilación de datos, es posible que desee ordenar, filtrar o agrupar los datos. Para ello, utilice vistas de colección, <xref:System.ComponentModel.ICollectionView> que son clases que implementan la interfaz.

#### <a name="what-are-collection-views"></a>¿Qué son las vistas de colección?

Una vista de colección es un nivel situado encima de la colección de origen del enlace, que le permite navegar y mostrar la colección de origen en función de las consultas de ordenación, filtrado y agrupación, sin tener que cambiar la propia colección de origen subyacente. Una vista de colección también contiene un puntero al elemento actual de la colección. Si la colección <xref:System.Collections.Specialized.INotifyCollectionChanged> de origen implementa la <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> interfaz, los cambios generados por el evento se propagan a las vistas.

Dado que las vistas no cambian las colecciones de origen subyacente, cada colección de origen puede tener varias vistas asociadas. Por ejemplo, puede tener una colección de objetos *Task*. El uso de vistas le permite mostrar los mismos datos de formas diferentes. Por ejemplo, en el lado izquierdo de la página es posible que desee mostrar las tareas ordenadas por prioridad y, en el lado derecho, agrupadas por área.

#### <a name="how-to-create-a-view"></a>Cómo crear una vista

Una manera de crear y utilizar una vista es crear directamente una instancia del objeto de vista y utilizar a continuación esa instancia como el origen del enlace. Por ejemplo, considere la aplicación de [demostración de enlace][data-binding-demo] de datos que se muestra en la sección Qué es enlace de [datos.](#what-is-data-binding) La aplicación se implementa <xref:System.Windows.Controls.ListBox> de forma que los enlaces a una vista sobre la colección de datos en lugar de la recopilación de datos directamente. El ejemplo siguiente se extrae de la aplicación de [demostración de enlace][data-binding-demo] de datos. La <xref:System.Windows.Data.CollectionViewSource> clase es el proxy XAML de <xref:System.Windows.Data.CollectionView>una clase que hereda de . En este ejemplo <xref:System.Windows.Data.CollectionViewSource.Source%2A> concreto, la vista de la vista <xref:System.Collections.ObjectModel.ObservableCollection%601>está enlazada a la colección *AuctionItems* (de tipo ) del objeto de aplicación actual.

[!code-xaml[CollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#CollectionView)]

A continuación, el listado de *recursosDataView* sirve como origen <xref:System.Windows.Controls.ListBox>de enlace para los elementos de la aplicación, como el archivo .

[!code-xaml[ListBoxCollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxCollectionView)]

Para crear otra vista para la misma <xref:System.Windows.Data.CollectionViewSource> colección, puede `x:Key` crear otra instancia y asignarle un nombre diferente.

En la tabla siguiente se muestran los tipos <xref:System.Windows.Data.CollectionViewSource> de datos de vista que se crean como la vista de colección predeterminada o en función del tipo de colección de origen.

| Tipo de colección de origen                    | Tipo de vista de colección | Notas |
| ----------------------------------------- | -------------------- | ----- |
| <xref:System.Collections.IEnumerable>     | Un tipo interno basado en<xref:System.Windows.Data.CollectionView> | No se pueden agrupar los elementos. |
| <xref:System.Collections.IList>           | <xref:System.Windows.Data.ListCollectionView> | Más rápido. |
| <xref:System.ComponentModel.IBindingList> | <xref:System.Windows.Data.BindingListCollectionView> | |

#### <a name="using-a-default-view"></a>Uso de una vista predeterminada

Especificar una vista de colección como origen de enlace es una forma de crear y utilizar una vista de colección. WPF también crea una vista de colección predeterminada para cada colección utilizada como origen de enlace. Si enlaza directamente a una colección, WPF enlaza a su vista predeterminada. Esta vista predeterminada es compartida por todos los enlaces a la misma colección, por lo que un cambio realizado en una vista predeterminada por un control enlazado o código (como ordenar o un cambio en el puntero de elemento actual, que se describe más adelante) se refleja en todos los demás enlaces a la misma colección.

Para obtener la vista predeterminada, utilice el <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> método. Para obtener un ejemplo, vea [Obtener la vista predeterminada de una colección de datos.](../../framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)

#### <a name="collection-views-with-adonet-datatables"></a>Vistas de colección con ADO.NET DataTables

Para mejorar el rendimiento, <xref:System.Data.DataTable> <xref:System.Data.DataView> las vistas de colección de ADO.NET u objetos delegan la ordenación y el filtrado en el archivo , lo que hace que la <xref:System.Data.DataView>ordenación y el filtrado se compartan en todas las vistas de colección del origen de datos. Para permitir que cada vista de colección ordene y <xref:System.Data.DataView> filtre de forma independiente, inicialice cada vista de colección con su propio objeto.

#### <a name="sorting"></a>Ordenación

Como se mencionó anteriormente, las vistas pueden aplicar un criterio de ordenación a una colección. Cuando este criterio existe en la colección subyacente, los datos pueden o no tener un orden relevante inherente. La vista de la colección le permite aplicar un orden o cambiar el orden predeterminado, en función de los criterios de comparación especificados. Como es una vista de datos basada en un cliente, podría ser habitual que el usuario quisiera ordenar las columnas de los datos de tabla por el valor correspondiente a la columna. Con las vistas, se puede aplicar esta ordenación controlada por el usuario, sin tener que realizar ningún cambio en la colección subyacente ni tener tampoco que volver a consultar el contenido de la colección. Para obtener un ejemplo, vea [Ordenar una columna GridView cuando se hace clic en un encabezado](../../framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).

En el ejemplo siguiente se muestra la lógica <xref:System.Windows.Controls.CheckBox> de ordenación de la "Ordenar por categoría y fecha" de la interfaz de usuario de la aplicación en la sección Qué es el enlace de [datos.](#what-is-data-binding)

[!code-csharp[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#AddSortChecked)]
[!code-vb[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#AddSortChecked)]

#### <a name="filtering"></a>Filtros

Las vistas también pueden aplicar un filtro a una colección, de modo que la vista muestre solo un subconjunto determinado de la colección completa. Podría filtrar los datos en función de una condición. Por ejemplo, como se hace por la aplicación en el Qué es <xref:System.Windows.Controls.CheckBox> enlace de [datos,](#what-is-data-binding) el "Mostrar solo gangas" contiene lógica para filtrar los elementos que cuestan $25 o más. El código siguiente se ejecuta para establecer <xref:System.Windows.Data.CollectionViewSource.Filter> *ShowOnlyBargainsFilter* como el controlador de eventos cuando <xref:System.Windows.Controls.CheckBox> se selecciona.

[!code-csharp[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingViewFilter)]
[!code-vb[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingViewFilter)]

El controlador de eventos *ShowOnlyBargainsFilter* tiene la siguiente implementación.

[!code-csharp[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#FilterEvent)]
[!code-vb[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#FilterEvent)]

Si utiliza una de <xref:System.Windows.Data.CollectionView> las clases directamente en lugar de <xref:System.Windows.Data.CollectionViewSource>, usaría la <xref:System.Windows.Data.CollectionView.Filter%2A> propiedad para especificar una devolución de llamada. Para ver un ejemplo, consulte [Filter Data in a View](../../framework/wpf/data/how-to-filter-data-in-a-view.md) (Filtrado de datos en una vista).

#### <a name="grouping"></a>Agrupación

Excepto por la clase <xref:System.Collections.IEnumerable> interna que ve una colección, todas las vistas de colección admiten la *agrupación,* lo que permite al usuario particionar la colección en la vista de colección en grupos lógicos. Los grupos pueden ser explícitos, donde el usuario proporciona una lista de grupos, o implícitos, donde los grupos se generan dinámicamente en función de los datos.

En el ejemplo siguiente se muestra la <xref:System.Windows.Controls.CheckBox>lógica del "Agrupar por categoría".

[!code-csharp[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingGroupCheck)]
[!code-vb[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingGroupCheck)]

Para obtener otro ejemplo de agrupación, consulte [Group Items in a ListView That Implements a GridView](../../framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md) (Agrupación de elementos en un control ListView que implemente un modo).

#### <a name="current-item-pointers"></a>Punteros de elementos actuales

Las vistas admiten también la noción de elemento actual. Puede navegar por los objetos en una vista de colección. A medida que navega por los objetos, mueve un puntero de elemento que le permite recuperar el objeto ubicado concretamente en esa posición en la colección. Para obtener un ejemplo, vea [Navegar por los objetos](../../framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md)de un data CollectionView .

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

Toda ordenación o filtrado que se aplique a la colección puede afectar al puntero del elemento actual. La ordenación conserva el puntero del elemento actual en el último elemento seleccionado, pero se reestructura la vista de colección a su alrededor. (Tal vez el elemento seleccionado estaba al principio de la lista antes, pero ahora el elemento seleccionado podría estar en algún lugar en el medio.) El filtrado conserva el elemento seleccionado si esa selección permanece a la vista después del filtrado. De lo contrario, el puntero del elemento actual se establece en el primer elemento de la vista de colección filtrada.

#### <a name="master-detail-binding-scenario"></a>Escenario de enlace maestro-detalle

La noción de elemento actual no es solo útil para la navegación de elementos en una colección, sino también para el escenario de enlace principal-detalle. Considere la interfaz de usuario de la aplicación en la sección [Qué es](#what-is-data-binding) el enlace de datos de nuevo. En esa aplicación, <xref:System.Windows.Controls.ListBox> la selección dentro de <xref:System.Windows.Controls.ContentControl>la determina el contenido que se muestra en el archivo . Para ponerlo de otra manera, cuando se selecciona un <xref:System.Windows.Controls.ListBox> elemento, el <xref:System.Windows.Controls.ContentControl> muestra los detalles del elemento seleccionado.

Puede implementar el escenario principal-detalle simplemente con dos o más controles enlazados a la misma vista. En el ejemplo siguiente de la [demostración Enlace][data-binding-demo] de datos se muestra el marcado de la <xref:System.Windows.Controls.ListBox> interfaz de usuario de la aplicación y se <xref:System.Windows.Controls.ContentControl> ve en la sección Qué es el enlace de [datos.](#what-is-data-binding)

[!code-xaml[ListBoxContentControl](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxContentControl)]

Observe que ambos controles están enlazados al mismo origen, el recurso estático *listingDataView* (consulte la definición de este recurso en la [sección Cómo crear una vista](#how-to-create-a-view)). Este enlace funciona porque cuando un <xref:System.Windows.Controls.ContentControl> objeto singleton (el en este caso) está <xref:System.Windows.Data.CollectionView.CurrentItem%2A> enlazado a una vista de colección, se enlaza automáticamente a la vista de la vista. Los <xref:System.Windows.Data.CollectionViewSource> objetos sincronizan automáticamente la moneda y la selección. Si el control de lista <xref:System.Windows.Data.CollectionViewSource> no está enlazado a un objeto <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> como `true` en este ejemplo, deberá establecer su propiedad para que esto funcione.

Para ver otros ejemplos, consulte [Enlazar a una colección y mostrar información basada en](../../framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) la selección y Usar el [patrón maestro-detalle con datos jerárquicos.](../../framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)

Tal vez haya observado que en el ejemplo anterior se utiliza una plantilla. De hecho, los datos no se mostrarían de la manera que deseamos <xref:System.Windows.Controls.ContentControl> sin el uso de <xref:System.Windows.Controls.ListBox>plantillas (la utilizada explícitamente por el y el utilizado implícitamente por el ). Trataremos el tema de la inclusión de datos en plantillas en la siguiente sección.

## <a name="data-templating"></a>Plantillas de datos

Sin el uso de plantillas de datos, nuestra interfaz de usuario de la aplicación en la sección [Qué es](#what-is-data-binding) el enlace de datos tendría el siguiente aspecto.

![Demo de enlace de datos sin plantillas de datos](./media/data-binding-overview/demo-no-template.png)

Como se muestra en el ejemplo <xref:System.Windows.Controls.ListBox> de la <xref:System.Windows.Controls.ContentControl> sección anterior, tanto el control como el están enlazados a todo el objeto de colección (o más específicamente, la vista sobre el objeto de colección) de *AuctionItem*s. Sin instrucciones específicas de cómo <xref:System.Windows.Controls.ListBox> mostrar la colección de datos, muestra la <xref:System.Windows.Controls.ContentControl> representación de cadena de cada objeto de la colección subyacente y muestra la representación de cadena del objeto al que está enlazado.

Para resolver ese problema, <xref:System.Windows.DataTemplate?text=DataTemplates>la aplicación define . Como se muestra en el ejemplo <xref:System.Windows.Controls.ContentControl> de la sección anterior, el usa explícitamente la plantilla de datos *detailsProductListingTemplate.* El <xref:System.Windows.Controls.ListBox> control utiliza implícitamente la siguiente plantilla de datos al mostrar el *AuctionItem* objetos en la colección.

[!code-xaml[AuctionItemDataTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#AuctionItemDataTemplate)]

Con el uso de esas dos DataTemplates, la interfaz de usuario resultante es la que se muestra en la sección [¿Qué es](#what-is-data-binding) el enlace de datos. Como puede ver en esa captura de pantalla, además de permitirle colocar datos en los controles, DataTemplates le permite definir objetos visuales atractivos para los datos. Por <xref:System.Windows.DataTrigger>ejemplo, s se <xref:System.Windows.DataTemplate> utilizan en lo anterior para que *AuctionItem*s con *SpecialFeatures* valor de *HighLight* se mostraría con un borde naranja y una estrella.

Para obtener más información acerca de las plantillas de datos, consulte Información general sobre [plantillas](../../framework/wpf/data/data-templating-overview.md)de datos .

## <a name="data-validation"></a>Validación de datos

La mayoría de las aplicaciones que toman la entrada del usuario deben tener lógica de validación para asegurarse de que el usuario ha especificado la información esperada. Las comprobaciones de validación se pueden basar en el tipo, el intervalo, el formato u otros requisitos específicos de la aplicación. En esta sección se describe cómo funciona la validación de datos en WPFWPF.

### <a name="associating-validation-rules-with-a-binding"></a>Asociar reglas de validación con un enlace

El modelo de enlace de <xref:System.Windows.Data.Binding.ValidationRules%2A> datos <xref:System.Windows.Data.Binding> WPFWPF permite asociar con el objeto. Por ejemplo, en el <xref:System.Windows.Controls.TextBox> ejemplo siguiente `StartPrice` se enlaza <xref:System.Windows.Controls.ExceptionValidationRule> a una <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> propiedad denominada y se agrega un objeto a la propiedad.

[!code-xaml[TextboxStartPrice](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartPrice)]

Un <xref:System.Windows.Controls.ValidationRule> objeto comprueba si el valor de una propiedad es válido. WPFWPF tiene dos tipos <xref:System.Windows.Controls.ValidationRule> de objetos integrados:

- Una <xref:System.Windows.Controls.ExceptionValidationRule> comprobación de las excepciones producidas durante la actualización de la propiedad de origen de enlace. En el ejemplo anterior, `StartPrice` es de tipo entero. Cuando el usuario especifica un valor que no se puede convertir en un entero, se produce una excepción, lo que ocasiona que el enlace se marque como no válido. Una sintaxis alternativa <xref:System.Windows.Controls.ExceptionValidationRule> a establecer explícitamente `true` es <xref:System.Windows.Data.Binding> establecer <xref:System.Windows.Data.MultiBinding> la <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> propiedad en el objeto o en el objeto.

- Un <xref:System.Windows.Controls.DataErrorValidationRule> objeto comprueba si hay errores generados <xref:System.ComponentModel.IDataErrorInfo> por los objetos que implementan la interfaz. Para obtener un ejemplo del <xref:System.Windows.Controls.DataErrorValidationRule>uso de esta regla de validación, consulte . Una sintaxis alternativa <xref:System.Windows.Controls.DataErrorValidationRule> a establecer explícitamente `true` es <xref:System.Windows.Data.Binding> establecer <xref:System.Windows.Data.MultiBinding> la <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> propiedad en el objeto o en el objeto.

También puede crear su propia regla de <xref:System.Windows.Controls.ValidationRule> validación <xref:System.Windows.Controls.ValidationRule.Validate%2A> derivando de la clase e implementando el método. En el ejemplo siguiente se muestra la regla <xref:System.Windows.Controls.TextBox> utilizada por el Agregar *listado* de productos "Fecha de inicio" de la Sección Qué es enlace de [datos.](#what-is-data-binding)

[!code-csharp[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/FutureDateRule.cs#FutureDateRule)]
[!code-vb[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/FutureDateRule.vb#FutureDateRule)]

*StartDateEntryForm* <xref:System.Windows.Controls.TextBox> utiliza este *FutureDateRule*, como se muestra en el ejemplo siguiente.

[!code-xaml[TextboxStartDate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartDate)]

Dado <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> que <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>el valor es , el motor de enlace actualiza el valor de <xref:System.Windows.Data.Binding.ValidationRules%2A> origen en cada pulsación de tecla, lo que significa que también comprueba todas las reglas de la colección en cada pulsación de tecla. Ofreceremos una descripción más detallada en la sección Proceso de validación.

### <a name="providing-visual-feedback"></a>Proporcionar retroalimentación visual

Si el usuario escribe un valor no válido, es posible que desee proporcionar algunos comentarios sobre el error en la interfaz de usuario de la aplicación. Una forma de proporcionar estos <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> comentarios es <xref:System.Windows.Controls.ControlTemplate>establecer la propiedad adjunta en un archivo . Como se muestra en la subsección anterior, <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> utiliza un *validationTemplate*llamado . En el ejemplo siguiente se muestra la definición de *validationTemplate*.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#ControlTemplate)]

El <xref:System.Windows.Controls.AdornedElementPlaceholder> elemento especifica dónde se debe colocar el control que se va a adornar.

Además, también puede <xref:System.Windows.Controls.ToolTip> usar a para mostrar el mensaje de error. Tanto *StartDateEntryForm* como *StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>es usan el estilo *textStyleTextBox*, que crea un <xref:System.Windows.Controls.ToolTip> que muestra el mensaje de error. En el ejemplo siguiente se muestra la definición de *textStyleTextBox*. La propiedad <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> `true` adjunta es cuando uno o varios de los enlaces en las propiedades del elemento enlazado están en error.

[!code-xaml[TextBoxStyle](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextBoxStyle)]

Con el <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> personalizado <xref:System.Windows.Controls.ToolTip>y el , el *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> tiene el siguiente cuando hay un error de validación.

![Error de validación de enlace de datos](./media/data-binding-overview/demo-validation-date.png "DataBindingDemo_Validation")

Si <xref:System.Windows.Data.Binding> tiene reglas de validación asociadas pero no especifica un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> control enlazado, se usará un valor predeterminado <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> para notificar a los usuarios cuando haya un error de validación. El <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> valor predeterminado es una plantilla de control que define un borde rojo en la capa de adorno. Con el <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> valor <xref:System.Windows.Controls.ToolTip>predeterminado y el , la interfaz de usuario de la *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox> es similar a la siguiente cuando hay un error de validación.

![Error de validación de enlace de datos](./media/data-binding-overview/demo-validation-price.png "DataBindingDemo_ValidationDefault")

Para obtener un ejemplo de cómo proporcionar lógica para validar todos los controles de un cuadro de diálogo, vea la sección Cuadros de diálogo personalizados en la [información general de cuadros](../../framework/wpf/app-development/dialog-boxes-overview.md)de diálogo .

### <a name="validation-process"></a>Proceso de validación

La validación normalmente se produce cuando el valor de un destino se transfiere a la propiedad de origen del enlace. Esta transferencia <xref:System.Windows.Data.BindingMode.TwoWay> se <xref:System.Windows.Data.BindingMode.OneWayToSource> produce y los enlaces. Para reiterar, lo que provoca una <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> actualización de origen depende del valor de la propiedad, como se describe en la sección [Qué desencadena las actualizaciones](#what-triggers-source-updates) de origen.

Los siguientes elementos describen el proceso de *validación.* Si se produce un error de validación u otro tipo de error en cualquier momento durante este proceso, el proceso se detiene:

1. El motor de enlace comprueba <xref:System.Windows.Controls.ValidationRule> si hay <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> algún <xref:System.Windows.Controls.ValidationStep.RawProposedValue> objeto <xref:System.Windows.Data.Binding>personalizado definido en <xref:System.Windows.Controls.ValidationRule.Validate%2A> el que <xref:System.Windows.Controls.ValidationRule> se establece para eso , en cuyo caso llama al método en cada uno de ellos hasta que uno de ellos se ejecuta en un error o hasta que todos ellos pasan.

2. A continuación, el motor de enlace llama al convertidor, si existe alguno.

3. Si el convertidor se realiza correctamente, el motor <xref:System.Windows.Controls.ValidationRule> de <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> enlace comprueba <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> si <xref:System.Windows.Data.Binding>hay algún objeto <xref:System.Windows.Controls.ValidationRule.Validate%2A> personalizado <xref:System.Windows.Controls.ValidationRule> definido <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> cuyo <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> se establece para eso , en cuyo caso llama al método en cada uno que se ha establecido en uno de ellos en un error o hasta que todos ellos pasen.

4. El motor de enlace establece la propiedad de origen.

5. El motor de enlace comprueba <xref:System.Windows.Controls.ValidationRule> si hay <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> objetos <xref:System.Windows.Controls.ValidationStep.UpdatedValue> personalizados definidos en los que se establece para ese <xref:System.Windows.Data.Binding> <xref:System.Windows.Controls.ValidationRule.Validate%2A> , en cuyo caso llama al método en cada <xref:System.Windows.Controls.ValidationRule> uno que se ha <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecido <xref:System.Windows.Controls.ValidationStep.UpdatedValue> en hasta que uno de ellos se ejecuta en un error o hasta que todos ellos pasan. Si <xref:System.Windows.Controls.DataErrorValidationRule> a está asociado a <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> un enlace y <xref:System.Windows.Controls.ValidationStep.UpdatedValue>su <xref:System.Windows.Controls.DataErrorValidationRule> se establece en el valor predeterminado, , se comprueba en este punto. En este punto <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> `true` se comprueba cualquier enlace que tenga el conjunto en.

6. El motor de enlace comprueba <xref:System.Windows.Controls.ValidationRule> si hay <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> objetos <xref:System.Windows.Controls.ValidationStep.CommittedValue> personalizados definidos en los que se establece para ese <xref:System.Windows.Data.Binding> <xref:System.Windows.Controls.ValidationRule.Validate%2A> , en cuyo caso llama al método en cada <xref:System.Windows.Controls.ValidationRule> uno que se ha <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecido <xref:System.Windows.Controls.ValidationStep.CommittedValue> en hasta que uno de ellos se ejecuta en un error o hasta que todos ellos pasan.

Si <xref:System.Windows.Controls.ValidationRule> a no pasa en cualquier momento a lo <xref:System.Windows.Controls.ValidationError> largo de este proceso, el motor de enlace crea un objeto y lo agrega a la <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> colección del elemento enlazado. Antes de que <xref:System.Windows.Controls.ValidationRule> el motor de enlace ejecute <xref:System.Windows.Controls.ValidationError> los objetos <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> en un paso determinado, quita los que se agregaron a la propiedad adjunta del elemento enlazado durante ese paso. Por ejemplo, <xref:System.Windows.Controls.ValidationRule> si <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> un <xref:System.Windows.Controls.ValidationStep.UpdatedValue> cuyo se establece en error, la próxima vez <xref:System.Windows.Controls.ValidationError> que se <xref:System.Windows.Controls.ValidationRule> produce <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> el <xref:System.Windows.Controls.ValidationStep.UpdatedValue>proceso de validación, el motor de enlace lo quita inmediatamente antes de llamar a cualquiera que se haya establecido en .

Cuando <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> no está <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> vacía, la propiedad adjunta `true`del elemento se establece en . Además, <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> si <xref:System.Windows.Data.Binding> la propiedad `true`de la se establece <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> en , a continuación, el motor de enlace genera el evento adjunto en el elemento.

Tenga en cuenta también que una transferencia de valor válida en <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> cualquier dirección (destino a origen o origen a destino) borra la propiedad adjunta.

Si el enlace <xref:System.Windows.Controls.ExceptionValidationRule> tiene un asociado o <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> tiene la `true` propiedad establecida en y se produce una excepción cuando el motor de <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>enlace establece el origen, el motor de enlace comprueba si hay un archivo . Tiene la opción de <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> usar la devolución de llamada para proporcionar un controlador personalizado para controlar las excepciones. Si <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> no se especifica <xref:System.Windows.Data.Binding>un en el <xref:System.Windows.Controls.ValidationError> , el motor de enlace <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> crea un con la excepción y lo agrega a la colección del elemento enlazado.

## <a name="debugging-mechanism"></a>Mecanismo de depuración

Puede establecer la <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> propiedad adjunta en un objeto relacionado con el enlace para recibir información sobre el estado de un enlace específico.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [Enlazar a los resultados de una consulta LINQ](../../framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)
- [Enlace de datos](../../framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Demostración de enlace de datos][data-binding-demo]
- [Artículos de información como](../../framework/wpf/data/data-binding-how-to-topics.md)
- [Enlazar a un origen de datos ADO.NET](../../framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)

[data-binding-demo]: https://github.com/microsoft/WPF-Samples/tree/master/Sample%20Applications/DataBindingDemo "aplicación de demostración de enlace de datos"
