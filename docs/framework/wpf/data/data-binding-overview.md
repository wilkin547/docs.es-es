---
title: Información general sobre el enlace de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data conversion for binding [WPF]
- binding data [WPF], about data binding
- data binding [WPF], about data binding
- conversion for data binding [WPF]
ms.assetid: c707c95f-7811-401d-956e-2fffd019a211
ms.openlocfilehash: 0b58cde738e2584662fa5f9ad90634931674f48b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558179"
---
# <a name="data-binding-overview"></a>Información general sobre el enlace de datos
El enlace de datos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una manera sencilla y coherente para que las aplicaciones presenten datos e interactúen con ellos. Los elementos se pueden enlazar a datos desde una variedad de orígenes de datos en forma de objetos [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] y [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]. <xref:System.Windows.Controls.ContentControl>Por ejemplo, <xref:System.Windows.Controls.Button> y <xref:System.Windows.Controls.ItemsControl>s como <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ListView> tiene funciones integradas para habilitar un estilo flexible de elementos de datos individuales o colecciones de elementos de datos. Se pueden generar vistas de ordenación, filtrado ya agrupación encima de los datos.  
  
 La funcionalidad de enlace de datos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presenta varias ventajas con respecto a los modelos tradicionales, como un mayor número de propiedades que admiten de forma inherente el enlace de datos, una representación flexible de los datos en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y la separación bien definida de la lógica del negocio de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 En este tema primero se explica los conceptos fundamentales para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enlace de datos y, a continuación, baje sobre el uso de la <xref:System.Windows.Data.Binding> clase y otras características de enlace de datos.  
  
  
<a name="what_is_data_binding"></a>   
## <a name="what-is-data-binding"></a>¿Qué es el enlace de datos?  
 El enlace de datos es el proceso que establece una conexión entre la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación y la lógica de negocios. Si el enlace está configurado correctamente y los datos proporcionan las notificaciones adecuadas, al cambiar los valores de los datos, los elementos enlazados a los datos reflejarán de manera automática dichos cambios. El enlace de datos también puede implicar la actualización automática de los datos que subyacen a una representación externa de los datos de un elemento, cuando esta representación cambia. Por ejemplo, si el usuario edita el valor de un <xref:System.Windows.Controls.TextBox> elemento, el valor de datos subyacente se actualiza automáticamente para reflejar ese cambio.  
  
 Un uso típico del enlace de datos es colocar los datos de configuración locales o de servidor en formularios o en otros controles de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], este concepto se expande para incluir el enlace de un gran número de propiedades a una gran variedad de orígenes de datos. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], las propiedades de dependencia de los elementos se pueden enlazar a objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] (incluidos los objetos [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] u objetos asociados a propiedades web y servicios web) y datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 Para obtener un ejemplo de enlace de datos, examine la siguiente [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703):  
  
 ![Captura de pantalla de ejemplo de enlace de datos](../../../../docs/framework/wpf/data/media/databinding-databindingdemo.png "DataBinding_DataBindingDemo")  
  
 El ejemplo anterior es la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de una aplicación que muestra una lista de artículos subastados. La aplicación muestra las características siguientes de enlace de datos:  
  
-   El contenido de la <xref:System.Windows.Controls.ListBox> está enlazado a una colección de *AuctionItem* objetos. Un objeto *AuctionItem* tiene propiedades como *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures*, etc.  
  
-   Los datos (*AuctionItem* objetos) aparece en el <xref:System.Windows.Controls.ListBox> tiene asignada una plantilla para que la descripción y el precio actual se muestran para cada elemento. Esto se realiza mediante un <xref:System.Windows.DataTemplate>. Además, la apariencia de cada artículo depende del valor de *SpecialFeatures* del elemento *AuctionItem* que se muestra. Si el valor de *SpecialFeatures* de *AuctionItem* es *Color*, el artículo tiene un borde azul. Si el valor es *Highlight*, el artículo tiene un borde naranja y una estrella. En la sección [Plantillas de datos](#data_templating) se proporciona información sobre las plantillas de datos.  
  
-   El usuario puede agrupar, filtrar u ordenar los datos mediante el <xref:System.Windows.Controls.CheckBox>es proporcionadas. En la imagen anterior, "Group by category" y "Sort by category and date" <xref:System.Windows.Controls.CheckBox>es están seleccionadas. Es posible que haya observado que los datos se agrupan en función de la categoría del producto, y el nombre de las categorías se muestra en orden alfabético. Aunque no se aprecia muy bien en la imagen, los artículos están ordenados también por fecha de inicio dentro de cada categoría. Esto se realiza mediante una *vista de colección*. En la sección [Enlace a colecciones](#binding_to_collections) se describen las vistas de colección.  
  
-   Cuando el usuario selecciona un elemento, el <xref:System.Windows.Controls.ContentControl> muestra los detalles del elemento seleccionado. Esto recibe el nombre de *escenario principal-detalle* . En la sección [Escenario principal-detalle](#master_detail_scenario) se proporciona información sobre este tipo de escenario de enlace.  
  
-   El tipo de la *StartDate* propiedad es <xref:System.DateTime>, que devuelve una fecha que incluye el tiempo en milisegundos. En esta aplicación, se ha utilizado un convertidor personalizado para que se muestre una cadena de fecha más corta. En la sección [Conversión de datos](#data_conversion) se proporciona información sobre los convertidores.  
  
 Cuando el usuario hace clic en el botón *Add product*, se muestra el siguiente formulario:  
  
 ![Página de listado para agregar producto](../../../../docs/framework/wpf/data/media/databinding-demo-addproductlisting.png "DataBinding_Demo_AddProductListing")  
  
 El usuario puede modificar los campos del formulario, obtener una vista previa de la lista de productos mediante la vista previa abreviada y los paneles de vista previa más detallada y, a continuación, hacer clic en *submit* para agregar la nueva lista de productos. Todas las funciones de agrupación, filtrado y ordenación existentes se aplicarán a la nueva entrada. En este caso en concreto, el artículo especificado en la imagen anterior se mostrará como el segundo artículo dentro de la categoría *Computer*.  
  
 No se muestra en esta imagen es la lógica de validación que se proporcionan en el *Start Date* <xref:System.Windows.Controls.TextBox>. Si el usuario escribe no válido fecha (un formato no válido o una fecha pasada), se notificará al usuario con un <xref:System.Windows.Controls.ToolTip> y un signo de exclamación rojo junto a la <xref:System.Windows.Controls.TextBox>. En la sección [Validación de datos](#data_validation) se describe cómo crear lógica de validación.  
  
 Antes de abordar las diferentes características de enlace de datos citadas anteriormente, en la siguiente sección explicaremos los conceptos fundamentales imprescindibles para comprender el enlace de datos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## <a name="basic-data-binding-concepts"></a>Conceptos básicos del enlace de datos  
  
 Independientemente del elemento que se vaya a enlazar y de la naturaleza del origen de datos, cada enlace sigue siempre el modelo que se muestra en la ilustración siguiente:  
  
 ![Diagrama de enlace de datos básico](../../../../docs/framework/wpf/data/media/databindingmostbasic.png "DataBindingMostBasic")  
  
 Como se muestra en la ilustración anterior, el enlace de datos es esencialmente el puente entre el destino del enlace y el origen del enlace. En la ilustración se muestran los siguientes conceptos fundamentales del enlace de datos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   Normalmente, cada enlace tiene estos cuatro componentes: un objeto de destino del enlace, una propiedad de destino, un origen del enlace y una ruta de acceso al valor en el origen del enlace que se va a usar. Por ejemplo, si desea enlazar el contenido de un <xref:System.Windows.Controls.TextBox> a la *nombre* propiedad de un *empleado* de objeto, el objeto de destino es el <xref:System.Windows.Controls.TextBox>, la propiedad de destino es el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad, el valor para usar es *nombre*, y el objeto de origen es el *empleado* objeto.  
  
-   La propiedad de destino debe ser una propiedad de dependencia. La mayoría <xref:System.Windows.UIElement> propiedades son propiedades de dependencia y la mayoría de las propiedades de dependencia, excepto las de solo lectura, admite el enlace de datos de forma predeterminada. (Solo <xref:System.Windows.DependencyObject> pueden definir tipos de propiedades de dependencia y todos <xref:System.Windows.UIElement>s derivan de <xref:System.Windows.DependencyObject>.)  
  
-   Aunque no se especifica en la ilustración, hay que destacar que el objeto de origen de enlace no está restringido a ser un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] personalizado. El enlace de datos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite datos en forma de objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Para proporcionar algunos ejemplos, el origen de enlace puede ser un <xref:System.Windows.UIElement>, cualquier objeto de lista, un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] objeto que está asociado a [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] datos o servicios Web o un valor XmlNode que contiene su [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos. Para más información, consulte [Binding Sources Overview](../../../../docs/framework/wpf/data/binding-sources-overview.md) (Introducción a los orígenes de enlace).  
  
 Cuando consulte otros temas del software [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)], es importante tener en cuenta que cuando establece un enlace, enlaza un destino de enlace *a* un origen de enlace. Por ejemplo, si se muestran algunos subyacente [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos en un <xref:System.Windows.Controls.ListBox> utiliza un enlace de datos, que va a enlazar la <xref:System.Windows.Controls.ListBox> a la [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos.  
  
 Para establecer un enlace, se utiliza la <xref:System.Windows.Data.Binding> objeto. El resto de este tema describe muchos de los conceptos asociados a y algunas de las propiedades y el uso de la <xref:System.Windows.Data.Binding> objeto.  
  
<a name="direction_of_data_flow"></a>   
### <a name="direction-of-the-data-flow"></a>Dirección del flujo de datos  
 Como se mencionó anteriormente y como se indica en la flecha situada en la ilustración anterior, el flujo de datos de un enlace puede ir desde el destino de enlace al origen de enlace (por ejemplo, el valor de origen cambia cuando se edita el valor de un <xref:System.Windows.Controls.TextBox>) o desde el origen de enlace en el destino de enlace (por ejemplo, su <xref:System.Windows.Controls.TextBox> contenido se actualice con los cambios en el origen de enlace) si el origen de enlace proporciona la notificaciones adecuadas.  
  
 Tal vez desee que su aplicación permita que los usuarios cambien los datos y los propaguen al objeto de origen. O bien, no puede permitir a los usuarios actualizar los datos de origen. Puede controlar este comportamiento estableciendo el <xref:System.Windows.Data.Binding.Mode%2A> propiedad de su <xref:System.Windows.Data.Binding> objeto. En la ilustración siguiente se muestran los distintos tipos de flujo de datos:  
  
 ![Flujo de datos de enlace de datos](../../../../docs/framework/wpf/data/media/databinding-dataflow.png "DataBinding_DataFlow")  
  
-   <xref:System.Windows.Data.BindingMode.OneWay> enlace hace cambios en la propiedad de origen para actualizar automáticamente la propiedad de destino, pero los cambios en la propiedad de destino no se propagan a la propiedad de origen. Este tipo de enlace es adecuado si el control que se está enlazando es implícitamente de solo lectura. Por ejemplo, podría enlazar a un origen como un tablero de cotizaciones o quizás su propiedad de destino no tenga ninguna interfaz de control para realizar modificaciones, como un color de fondo enlazado a datos de una tabla. Si no es necesario supervisar los cambios de la propiedad de destino, el uso del modo de enlace <xref:System.Windows.Data.BindingMode.OneWay> evita la sobrecarga del modo de enlace <xref:System.Windows.Data.BindingMode.TwoWay>.  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay> enlace hace cambios en la propiedad de origen o la propiedad de destino se actualice automáticamente la otra. Este tipo de enlace es adecuado para formularios modificables u otros escenarios [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] completamente interactivos. Mayoría de las propiedades de forma predeterminada <xref:System.Windows.Data.BindingMode.OneWay> enlace, pero algunas propiedades de dependencia (normalmente propiedades de controles puede modificar el usuario, como el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad de <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> propiedad de <xref:System.Windows.Controls.CheckBox>) predeterminado para <xref:System.Windows.Data.BindingMode.TwoWay> enlace. Una manera de determinar mediante programación si una propiedad de dependencia se enlaza de forma predeterminada de modo unidireccional o bidireccional es obtener los metadatos de la propiedad mediante <xref:System.Windows.DependencyProperty.GetMetadata%2A> y luego comprobar el valor booleano de la propiedad <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource> es el inverso de <xref:System.Windows.Data.BindingMode.OneWay> enlace; actualiza la propiedad de origen cuando cambia la propiedad de destino. Podría utilizar este tipo de enlace si, por ejemplo, solo necesita volver a evaluar el valor de origen de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
-   No se muestra en la ilustración es <xref:System.Windows.Data.BindingMode.OneTime> enlace, lo que hace que la propiedad de origen para inicializar la propiedad de destino, pero no se propagan los cambios posteriores. Esto significa que si el contexto de los datos sufre un cambio o el objeto del contexto de datos cambia, el cambio no se refleja en la propiedad de destino. Este tipo de enlace es adecuado si usa datos donde una instantánea del estado actual es adecuada para su uso o los datos son realmente estáticos. Este tipo de enlace también es útil si quiere inicializar la propiedad de destino con algún valor de una propiedad de origen y no se conoce el contexto de datos de antemano. Se trata básicamente de una forma más sencilla de enlace <xref:System.Windows.Data.BindingMode.OneWay> que ofrece un mejor rendimiento en casos donde el valor de origen no cambia.  
  
 Tenga en cuenta que para detectar los cambios del origen (aplicable a <xref:System.Windows.Data.BindingMode.OneWay> y <xref:System.Windows.Data.BindingMode.TwoWay> enlaces), el origen debe implementar un mecanismo de notificación de cambio de propiedad adecuado como <xref:System.ComponentModel.INotifyPropertyChanged>. Vea [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) para obtener un ejemplo de un <xref:System.ComponentModel.INotifyPropertyChanged> implementación.  
  
 La <xref:System.Windows.Data.Binding.Mode%2A> página de propiedades proporciona más información sobre los modos de enlace y un ejemplo de cómo especificar la dirección de un enlace.  
  
<a name="what_triggers_source_updates"></a>   
### <a name="what-triggers-source-updates"></a>Qué desencadena la actualización del origen  
 Enlaces que son <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> escucha de cambios en la propiedad de destino y propagarlos hacia el origen. Esto se conoce como el origen de la actualización. Por ejemplo, puede modificar el texto de un control TextBox para cambiar el valor de origen subyacente. Como se describe en la última sección, la dirección del flujo de datos está determinada por el valor de la <xref:System.Windows.Data.Binding.Mode%2A> propiedad del enlace.  
  
 Pero ¿se actualizará su valor de origen mientras edita el texto o después de terminar de editarlo y sacar el mouse fuera del control TextBox? El <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad del enlace determina qué desencadena la actualización del origen. Los puntos de las flechas derecha en la ilustración siguiente muestran la función de la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad:  
  
 ![Diagrama de UpdateSourceTrigger](../../../../docs/framework/wpf/data/media/databindingupdatesourcetrigger.png "DataBindingUpdateSourceTrigger")  
  
 Si el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor es <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, a continuación, el valor que señala la flecha derecha de <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces se actualiza en cuanto cambia la propiedad de destino. Sin embargo, si la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor es <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>, a continuación, ese valor sólo se actualizará con el nuevo valor cuando la propiedad de destino pierde el foco.  
  
 Similar a la <xref:System.Windows.Data.Binding.Mode%2A> propiedad, las propiedades de dependencia diferentes tienen diferentes predeterminado <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valores. El valor predeterminado de la mayoría de las propiedades de dependencia es <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, mientras que la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> tiene un valor predeterminado de <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Esto significa que las actualizaciones del origen suele producen cuando cambia la propiedad de destino, que es el adecuado para <xref:System.Windows.Controls.CheckBox>es y otros controles sencillos. Sin embargo, para los campos de texto, la actualización cada vez que se pulsa una tecla puede disminuir el rendimiento y deniega al usuario la oportunidad usual de retroceder y corregir los errores tipográficos antes confirmar el nuevo valor. Por eso la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad tiene un valor predeterminado de <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> en lugar de <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 Consulte la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> página de propiedades para obtener información sobre cómo buscar el valor predeterminado <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor de una propiedad de dependencia.  
  
 En la tabla siguiente proporciona un escenario de ejemplo para cada <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor mediante el <xref:System.Windows.Controls.TextBox> como un ejemplo:  
  
|Valor UpdateSourceTrigger|Cuándo se actualiza el valor de origen|Escenario de ejemplo de TextBox|  
|-------------------------------|----------------------------------------|----------------------------------|  
|LostFocus (valor predeterminado para <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>)|Cuando el control TextBox pierde el foco|Un <xref:System.Windows.Controls.TextBox> que está asociado a la lógica de validación (consulte la sección de validación de datos)|  
|PropertyChanged|A medida que escribe en el <xref:System.Windows.Controls.TextBox>|<xref:System.Windows.Controls.TextBox> controles de una ventana de salón de chat|  
|Explicit|Cuando la aplicación llama <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>|<xref:System.Windows.Controls.TextBox> controles en un formulario modificable (actualiza los valores de origen solo cuando el usuario hace clic en el botón Enviar)|  
  
 Para ver un ejemplo, consulte [Controlar cuándo el texto de TextBox actualiza el origen](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).  
  
<a name="creating_a_binding"></a>   
## <a name="creating-a-binding"></a>Crear un enlace  
  
 Para recapitulate algunos de los conceptos tratados en las secciones anteriores, establecer un enlace con el <xref:System.Windows.Data.Binding> objeto y cada enlace normalmente tiene cuatro componentes: destino, propiedad de destino, origen de enlace y una ruta de acceso de enlace con el valor de origen para usar. En esta sección describe cómo configurar un enlace.  
  
 Considere el ejemplo siguiente, en el que el objeto de origen del enlace es una clase denominada *MyData* que se define en el espacio de nombres *SDKSample*. Para fines de demostración, la clase *MyData* tiene una propiedad de cadena denominada *ColorName*, cuyo valor se establece en "Red". Por lo tanto, este ejemplo genera un botón con un fondo rojo.  
  
 [!code-xaml[BindNonTextProperty#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 Para más información sobre la sintaxis de declaración de enlaces y ejemplos sobre cómo configurar un enlace en código, consulte [Información general sobre declaraciones de enlaces](../../../../docs/framework/wpf/data/binding-declarations-overview.md).  
  
 Si aplicamos este ejemplo a nuestro diagrama básico, la ilustración resultante tendrá el siguiente aspecto. Se trata de un <xref:System.Windows.Data.BindingMode.OneWay> enlace porque la propiedad Background admite <xref:System.Windows.Data.BindingMode.OneWay> de enlace predeterminada.  
  
 ![Diagrama de enlace de datos](../../../../docs/framework/wpf/data/media/databindingbuttonbackgroundexample.png "DataBindingButtonBackgroundExample")  
  
 Quizás se pregunte por qué esto funciona aunque el *ColorName* propiedad es de tipo cadena mientras el <xref:System.Windows.Controls.Control.Background%2A> propiedad es de tipo <xref:System.Windows.Media.Brush>. Se ha aplicado la conversión predeterminada de tipos, que se explica en la sección [Conversión de datos](#data_conversion).  
  
<a name="specifying_the_binding_source"></a>   
### <a name="specifying-the-binding-source"></a>Especificación del origen de enlace  
 Observe que en el ejemplo anterior, el origen de enlace se especifica estableciendo el <xref:System.Windows.FrameworkElement.DataContext%2A> propiedad en el <xref:System.Windows.Controls.DockPanel> elemento. El <xref:System.Windows.Controls.Button> , a continuación, hereda la <xref:System.Windows.FrameworkElement.DataContext%2A> valor desde el <xref:System.Windows.Controls.DockPanel>, que es su elemento primario. Recordemos que el objeto de origen del enlace es uno de los cuatro componentes necesarios de un enlace. Por tanto, si no se especifica el objeto de origen del enlace, el enlace no funcionará.  
  
 Hay varias formas de especificar el objeto de origen del enlace. Mediante el <xref:System.Windows.FrameworkElement.DataContext%2A> propiedad en un elemento primario es útil cuando se va a enlazar varias propiedades al mismo origen. Sin embargo, a veces puede ser más adecuado especificar el origen del enlace en declaraciones de enlace individuales. En el ejemplo anterior, en lugar de utilizar el <xref:System.Windows.FrameworkElement.DataContext%2A> propiedad, puede especificar el origen de enlace estableciendo el <xref:System.Windows.Data.Binding.Source%2A> propiedad directamente en la declaración de enlace del botón, como en el ejemplo siguiente:  
  
 [!code-xaml[BindNonTextProperty#BackgroundBindingCompact](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 Distinto de establecer el <xref:System.Windows.FrameworkElement.DataContext%2A> propiedad en un elemento directamente, heredan el <xref:System.Windows.FrameworkElement.DataContext%2A> valor de un antecesor (por ejemplo, el botón en el primer ejemplo) y especificar explícitamente el origen de enlace estableciendo el <xref:System.Windows.Data.Binding.Source%2A> propiedad en el <xref:System.Windows.Data.Binding> (por ejemplo, el botón del último ejemplo), también puede usar el <xref:System.Windows.Data.Binding.ElementName%2A> propiedad o <xref:System.Windows.Data.Binding.RelativeSource%2A> propiedad para especificar el origen de enlace. El <xref:System.Windows.Data.Binding.ElementName%2A> propiedad es útil cuando se va a enlazar a otros elementos de la aplicación, como cuando se utiliza un control deslizante para ajustar el ancho de un botón. El <xref:System.Windows.Data.Binding.RelativeSource%2A> propiedad es útil cuando el enlace se especifica en un <xref:System.Windows.Controls.ControlTemplate> o <xref:System.Windows.Style>. Para más información, consulte [Especificación del origen de enlace](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).  
  
<a name="specifying_the_path_to_the_value"></a>   
### <a name="specifying-the-path-to-the-value"></a>Especificación de la ruta de acceso al valor  
 Si el origen de enlace es un objeto, utilice el <xref:System.Windows.Data.Binding.Path%2A> propiedad para especificar el valor que se usará para el enlace. Si va a enlazar a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos, use la <xref:System.Windows.Data.Binding.XPath%2A> propiedad para especificar el valor. En algunos casos, puede ser aplicable a usar el <xref:System.Windows.Data.Binding.Path%2A> propiedad incluso si los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Por ejemplo, si desea tener acceso a la propiedad Name de un XmlNode devuelto (como resultado de una consulta XPath), debe utilizar el <xref:System.Windows.Data.Binding.Path%2A> propiedad además el <xref:System.Windows.Data.Binding.XPath%2A> propiedad.  
  
 Para obtener información sobre la sintaxis y ejemplos, vea el <xref:System.Windows.Data.Binding.Path%2A> y <xref:System.Windows.Data.Binding.XPath%2A> páginas de propiedades.  
  
 Tenga en cuenta que aunque hemos recalcado que el <xref:System.Windows.Data.Binding.Path%2A> con el valor para usar es uno de los cuatro componentes necesarios de un enlace, en los escenarios que se desea enlazar a un objeto completo, el valor para usar sería el mismo que el objeto de origen de enlace. En esos casos, es aplicable para no especificar un <xref:System.Windows.Data.Binding.Path%2A>. Considere el ejemplo siguiente:  
  
 [!code-xaml[MasterDetail#EmptyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 En el ejemplo anterior se utiliza la sintaxis de enlace vacía: {Binding}. En este caso, el <xref:System.Windows.Controls.ListBox> hereda el objeto DataContext de un elemento de DockPanel primario (no se muestra en este ejemplo). Cuando no se especifica la ruta de acceso, el valor predeterminado es enlazar al objeto completo. En otras palabras, en este ejemplo, la ruta de acceso se ha omitido porque estamos enlazando la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad al objeto completo. (Consulte la sección [Enlace a colecciones](#binding_to_collections) para obtener información detallada).  
  
 Además del enlace a una colección, este escenario es útil también cuando se desea enlazar a un objeto completo en lugar de simplemente a una propiedad individual de un objeto. Por ejemplo, si el objeto de origen es de tipo string y simplemente desea enlazar a la propia cadena. Otro escenario común es cuando se desea enlazar un elemento a un objeto con varias propiedades.  
  
 Observe que puede ser necesario aplicar lógica personalizada para que los datos sean significativos para la propiedad de destino enlazada. La lógica personalizada puede consistir en un convertidor personalizado (si no existe la conversión de tipos predeterminada). Consulte [Conversión de datos](#data_conversion) para obtener información sobre los convertidores.  
  
<a name="binding_bindingexpression"></a>   
### <a name="binding-and-bindingexpression"></a>Binding and BindingExpression  
 Antes de entrar en otras características y usos de enlace de datos, sería útil para introducir el <xref:System.Windows.Data.BindingExpression> clase. Como ha visto en las secciones anteriores, el <xref:System.Windows.Data.Binding> es la clase de alto nivel de la declaración de un enlace; el <xref:System.Windows.Data.Binding> clase proporciona muchas propiedades que le permiten especificar las características de un enlace. Una clase relacionada, <xref:System.Windows.Data.BindingExpression>, es el objeto subyacente que mantiene la conexión entre el origen y el destino. Un enlace contiene toda la información que se puede compartir entre varias expresiones de enlace. A <xref:System.Windows.Data.BindingExpression> es una expresión de instancia que no se puede compartir y contiene toda la información de instancia de la <xref:System.Windows.Data.Binding>.  
  
 Por ejemplo, considere lo siguiente, donde *myDataObject* es una instancia de *MyData* (clase), *myBinding* es el origen <xref:System.Windows.Data.Binding> objeto y *MyData* clase es una clase definida que contiene una propiedad de cadena denominada *MyDataProperty*. Este ejemplo enlaza el contenido de texto *mytext*, una instancia de <xref:System.Windows.Controls.TextBlock>a *MyDataProperty*.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Puede usar el mismo objeto *myBinding* para crear otros enlaces. Por ejemplo, puede usar el objeto *myBinding* para enlazar el contenido de texto de una casilla a *MyDataProperty*. En ese caso, habrá dos instancias de <xref:System.Windows.Data.BindingExpression> compartir el *myBinding* objeto.  
  
 A <xref:System.Windows.Data.BindingExpression> objeto puede obtenerse con el valor devuelto de llamar al método <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> en un objeto enlazado a datos. Los temas siguientes muestran algunos de los usos de la <xref:System.Windows.Data.BindingExpression> clase:  
  
-   [Obtener el objeto de enlace a partir de una propiedad de destino enlazada](../../../../docs/framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
-   [Controlar cuándo el texto de TextBox actualiza el origen](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## <a name="data-conversion"></a>Conversión de datos  
 En el ejemplo anterior, el botón está en rojo porque su <xref:System.Windows.Controls.Control.Background%2A> propiedad se enlaza a una propiedad de cadena con el valor "Rojo". Esto funciona porque un convertidor de tipos está presente en el <xref:System.Windows.Media.Brush> tipo se debe convertir el valor de cadena a un <xref:System.Windows.Media.Brush>.  
  
 Al agregar esta información a la ilustración de la sección [Creación de un enlace](#creating_a_binding), obtenemos el diagrama siguiente:  
  
 ![Diagrama de enlace de datos](../../../../docs/framework/wpf/data/media/databindingbuttondefaultconversion.png "DataBindingButtonDefaultConversion")  
  
 Sin embargo, ¿qué ocurre si en lugar de tener una propiedad de tipo cadena, el objeto de origen de enlace tiene un *Color* propiedad de tipo <xref:System.Windows.Media.Color>? En ese caso, en orden para el enlace funcione se debe activar primero la *Color* valor de propiedad en algo que el <xref:System.Windows.Controls.Control.Background%2A> propiedad acepta. Debe crear un convertidor personalizado implementando la <xref:System.Windows.Data.IValueConverter> interfaz, como en el ejemplo siguiente:  
  
 [!code-csharp[ColorPicker_snip#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 La <xref:System.Windows.Data.IValueConverter> página de referencia proporciona más información.  
  
 Ahora que se ha utilizado el convertidor personalizado en lugar de la conversión predeterminada, nuestro diagrama presenta el siguiente aspecto:  
  
 ![Diagrama de enlace de datos](../../../../docs/framework/wpf/data/media/databindingconvertercolorexample.png "DataBindingConverterColorExample")  
  
 Recordemos que las conversiones predeterminadas pueden estar disponibles si el tipo que se va a enlazar contiene convertidores de tipo. Este comportamiento dependerá de los convertidores de tipos disponibles en el destino. Si no está seguro, cree su propio convertidor.  
  
 A continuación, se incluyen algunos escenarios típicos en los que sería lógico implementar un convertidor de datos:  
  
-   Los datos se muestran de forma diferente, dependiendo de la referencia cultural. Por ejemplo, tal vez desee implementar un convertidor de monedas o un convertidor de fechas y horas del calendario en función de los valores o normas utilizados en una determinada referencia cultural.  
  
-   Los datos que se utilizan no están diseñados necesariamente para cambiar el valor textual de una propiedad, sino para cambiar otro valor, como el origen de una imagen, o el color o estilo del texto que se va a mostrar. En este caso se pueden utilizar convertidores para convertir el enlace de una propiedad que tal vez no sea adecuada, como el enlace de un campo de texto a la propiedad Background de una celda de tabla.  
  
-   Hay varios controles o varias propiedades de controles enlazados a los mismos datos. En ese caso, el enlace principal podría mostrar simplemente el texto, mientras que los otros enlaces controlan los aspectos de presentación, pero se sigue utilizando el mismo enlace como información de origen.  
  
-   Hasta ahora no ha analizamos <xref:System.Windows.Data.MultiBinding>, donde una propiedad de destino tiene una colección de enlaces. En el caso de un <xref:System.Windows.Data.MultiBinding>, utilizar un personalizado <xref:System.Windows.Data.IMultiValueConverter> para generar un valor final de los valores de los enlaces. Por ejemplo, el color podría calcularse a partir de los valores de rojo, azul y verde, que pueden ser valores de los mismos o de diferentes objetos de origen del enlace. Consulte la <xref:System.Windows.Data.MultiBinding> página de la clase de información y ejemplos.  
  
<a name="binding_to_collections"></a>   
## <a name="binding-to-collections"></a>Enlace a colecciones  
  
 Un objeto de origen del enlace se puede tratar como un objeto único cuyas propiedades contienen los datos, o como una recolección de datos de objetos polimórficos que suelen estar agrupados (como el resultado de una consulta a una base de datos). Hasta ahora solo hemos explicado el enlace a objetos individuales, pero el enlace a una recolección de datos es un escenario común. Por ejemplo, un escenario común es usar un <xref:System.Windows.Controls.ItemsControl> como un <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView>, o <xref:System.Windows.Controls.TreeView> para mostrar una recolección de datos, como en la aplicación se muestra en el [¿qué es el enlace de datos?](#what_is_data_binding) sección.  
  
 Afortunadamente, nuestro diagrama básico aún sigue siendo válido. Si va a enlazar un <xref:System.Windows.Controls.ItemsControl> en una colección, el diagrama siguiente aspecto:  
  
 ![Diagrama de ItemsControl de enlace de datos](../../../../docs/framework/wpf/data/media/databindingitemscontrol.png "DataBindingItemsControl")  
  
 Como se muestra en este diagrama, para enlazar un <xref:System.Windows.Controls.ItemsControl> a un objeto de colección, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad es la propiedad que se va a usar. Puede pensar en <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad como el contenido de la <xref:System.Windows.Controls.ItemsControl>. Tenga en cuenta que el enlace es <xref:System.Windows.Data.BindingMode.OneWay> porque el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> admite la propiedad <xref:System.Windows.Data.BindingMode.OneWay> de enlace predeterminada.  
  
<a name="how_to_implement_collections"></a>   
### <a name="how-to-implement-collections"></a>Implementación de colecciones  
 Es posible enumerar cualquier colección que implementa el <xref:System.Collections.IEnumerable> interfaz. Sin embargo, para configurar enlaces dinámicos para que las inserciones o eliminaciones en la colección de actualizan el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] automáticamente, la colección debe implementar la <xref:System.Collections.Specialized.INotifyCollectionChanged> interfaz. Esta interfaz expone un evento que debe provocarse siempre que se realicen cambios en la colección subyacente.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona el <xref:System.Collections.ObjectModel.ObservableCollection%601> (clase), que es una implementación integrada de una recolección de datos que expone el <xref:System.Collections.Specialized.INotifyCollectionChanged> interfaz. Tenga en cuenta que para satisfacer por completo transferir valores de datos de objetos de origen a los destinos, cada objeto de la colección que admite propiedades enlazables también debe implementar la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz. Para más información, consulte [Binding Sources Overview](../../../../docs/framework/wpf/data/binding-sources-overview.md) (Introducción a los orígenes de enlace).  
  
 Antes de implementar su propia colección, considere el uso de <xref:System.Collections.ObjectModel.ObservableCollection%601> o uno de la colección existente las clases, como <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>, y <xref:System.ComponentModel.BindingList%601>, entre otros muchos. Si tiene un escenario avanzado y desea implementar su propia colección, considere la posibilidad de usar <xref:System.Collections.IList>, lo que proporciona una colección no genérica de objetos que puede tener acceso individualmente por índice y, por tanto, el mejor rendimiento.  
  
<a name="collection_views"></a>   
### <a name="collection-views"></a>Vistas de colección  
 Una vez el <xref:System.Windows.Controls.ItemsControl> está enlazado a una recolección de datos, puede que desee ordenar, filtrar o agrupar los datos. Para ello, use las vistas de colección, que son clases que implementan la <xref:System.ComponentModel.ICollectionView> interfaz.  
  
  
#### <a name="what-are-collection-views"></a>¿Qué son las vistas de colección?  
 Una vista de colección es un nivel situado encima de la colección de origen del enlace, que le permite navegar y mostrar la colección de origen en función de las consultas de ordenación, filtrado y agrupación, sin tener que cambiar la propia colección de origen subyacente. Una vista de colección también contiene un puntero al elemento actual de la colección. Si la colección de origen implementa la <xref:System.Collections.Specialized.INotifyCollectionChanged> de la interfaz, los cambios provocados por la <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> evento se propaga a las vistas.  
  
 Dado que las vistas no cambian las colecciones de origen subyacente, cada colección de origen puede tener varias vistas asociadas. Por ejemplo, puede tener una colección de objetos *Task*. El uso de vistas le permite mostrar los mismos datos de formas diferentes. Por ejemplo, en el lado izquierdo de la página es posible que desee mostrar las tareas ordenadas por prioridad y, en el lado derecho, agrupadas por área.  
  
<a name="how_to_create_a_view"></a>   
#### <a name="how-to-create-a-view"></a>Creación de una vista  
 Una manera de crear y utilizar una vista es crear directamente una instancia del objeto de vista y utilizar a continuación esa instancia como el origen del enlace. Por ejemplo, considere la aplicación [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703) que se muestra en la sección [¿Qué es el enlace de datos?](#what_is_data_binding). Se implementa la aplicación de modo que la <xref:System.Windows.Controls.ListBox> enlaza a una vista a través de la recopilación de datos en lugar de la recopilación de datos directamente. El ejemplo siguiente se extrae de la aplicación [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703). El <xref:System.Windows.Data.CollectionViewSource> clase es el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] proxy de una clase que hereda de <xref:System.Windows.Data.CollectionView>. En este ejemplo concreto, la <xref:System.Windows.Data.CollectionViewSource.Source%2A> de la vista está enlazada a la *AuctionItems* colección (de tipo <xref:System.Collections.ObjectModel.ObservableCollection%601>) del objeto de aplicación actual.  
  
 [!code-xaml[DataBindingLab#WindowResources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xaml[DataBindingLab#CollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xaml[DataBindingLab#WindowResources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 El recurso *listingDataView* actúa como origen de enlace para los elementos de la aplicación, como el <xref:System.Windows.Controls.ListBox>:  
  
 [!code-xaml[DataBindingLab#Master1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 Para crear otra vista para la misma colección, puede crear otro <xref:System.Windows.Data.CollectionViewSource> instancia y asígnele otro `x:Key` nombre.  
  
 La siguiente tabla muestra qué tipos de datos de vista se crean como la vista de colección predeterminada o por <xref:System.Windows.Data.CollectionViewSource> según el tipo de colección de origen.  
  
|Tipo de colección de origen|Tipo de vista de colección|Notas|  
|----------------------------|--------------------------|-----------|  
|<xref:System.Collections.IEnumerable>|Un tipo interno basado en <xref:System.Windows.Data.CollectionView>|No se pueden agrupar los elementos.|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|Más rápido.|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### <a name="using-a-default-view"></a>Uso de una vista predeterminada  
 Especificar una vista de colección como origen de enlace es una forma de crear y utilizar una vista de colección. WPF también crea una vista de colección predeterminada para cada colección utilizada como origen de enlace. Si enlaza directamente a una colección, WPF enlaza a su vista predeterminada. Tenga en cuenta que todos los enlaces a una misma colección comparten esta vista predeterminada, de modo que si se realiza un cambio en una vista predeterminada a través de un control enlazado o mediante código (como un cambio de ordenación o en el puntero de elemento actual, que se describe más adelante), este se refleja en el resto de los enlaces a la misma colección.  
  
 Para obtener la vista predeterminada, se utiliza el <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> método. Para ver un ejemplo, consulte [Get the Default View of a Data Collection](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md) (Obtención de la vista predeterminada de una colección de datos).  
  
##### <a name="collection-views-with-adonet-datatables"></a>Vistas de colección con DataTables de ADO.NET  
 Para mejorar el rendimiento, vistas de colección para ADO.NET <xref:System.Data.DataTable> o <xref:System.Data.DataView> objetos delegan la ordenación y filtrado a la <xref:System.Data.DataView>. Esto hace que todas las vistas de colección del origen de datos compartan la ordenación y el filtrado. Para habilitar cada vista de colección ordenar y filtrar de forma independiente, inicialice cada vista de colección con su propio <xref:System.Data.DataView> objeto.  
  
#### <a name="sorting"></a>Ordenar  
 Como se mencionó anteriormente, las vistas pueden aplicar un criterio de ordenación a una colección. Cuando este criterio existe en la colección subyacente, los datos pueden o no tener un orden relevante inherente. La vista de la colección le permite aplicar un orden o cambiar el orden predeterminado, en función de los criterios de comparación especificados. Como es una vista de datos basada en un cliente, podría ser habitual que el usuario quisiera ordenar las columnas de los datos de tabla por el valor correspondiente a la columna. Con las vistas, se puede aplicar esta ordenación controlada por el usuario, sin tener que realizar ningún cambio en la colección subyacente ni tener tampoco que volver a consultar el contenido de la colección. Para ver un ejemplo, consulte [Clasificación de una columna GridView cuando se hace clic en un encabezado](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).  
  
 En el ejemplo siguiente se muestra la lógica de ordenación de la "Sort by category and date" <xref:System.Windows.Controls.CheckBox> de la aplicación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en el [¿qué es el enlace de datos?](#what_is_data_binding) sección:  
  
 [!code-csharp[DataBindingLab#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
#### <a name="filtering"></a>Filtrado  
 Las vistas pueden aplicar también un filtro a una colección. Esto significa que aunque un elemento pueda existir en la colección, esta vista en concreto está destinada a mostrar únicamente determinado subconjunto de la colección completa. Podría filtrar los datos en función de una condición. Por ejemplo, al igual que se realiza mediante la aplicación en el [¿qué es el enlace de datos?](#what_is_data_binding) sección, "Mostrar sólo ofertas" <xref:System.Windows.Controls.CheckBox> contiene lógica para filtrar los elementos cuyo costo es $25 o más. Se ejecuta el código siguiente para establecer *ShowOnlyBargainsFilter* como el <xref:System.Windows.Data.CollectionViewSource.Filter> controlador de eventos al que <xref:System.Windows.Controls.CheckBox> está seleccionado:  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 El controlador de eventos *ShowOnlyBargainsFilter* se implementa del modo siguiente:  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 Si está usando uno de los <xref:System.Windows.Data.CollectionView> clases directamente en lugar de <xref:System.Windows.Data.CollectionViewSource>, usaría el <xref:System.Windows.Data.CollectionView.Filter%2A> propiedad para especificar una devolución de llamada. Para ver un ejemplo, consulte [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md) (Filtrado de datos en una vista).  
  
#### <a name="grouping"></a>Agrupar  
 Salvo la clase interna que ve un <xref:System.Collections.IEnumerable> colección, todas las vistas de colección admiten la funcionalidad de agrupación, que permite al usuario para la partición de la colección en la vista de colección en grupos lógicos. Los grupos pueden ser explícitos, donde el usuario proporciona una lista de grupos, o implícitos, donde los grupos se generan dinámicamente en función de los datos.  
  
 En el ejemplo siguiente se muestra la lógica de la "Group by category" <xref:System.Windows.Controls.CheckBox>:  
  
 [!code-csharp[DataBindingLab#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#6)]
 [!code-vb[DataBindingLab#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#6)]  
  
 Para obtener otro ejemplo de agrupación, consulte [Group Items in a ListView That Implements a GridView](../../../../docs/framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md) (Agrupación de elementos en un control ListView que implemente un modo).  
  
#### <a name="current-item-pointers"></a>Punteros de elemento actual  
 Las vistas admiten también la noción de elemento actual. Puede navegar por los objetos en una vista de colección. A medida que navega por los objetos, mueve un puntero de elemento que le permite recuperar el objeto ubicado concretamente en esa posición en la colección. Para ver un ejemplo, consulte [Navigate Through the Objects in a Data CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md) (Desplazamiento por los objetos de una colección de datos mediante CollectionView).  
  
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
  
<a name="master_detail_scenario"></a>   
#### <a name="master-detail-binding-scenario"></a>Escenario de enlace principal-detalle  
 La noción de elemento actual no es solo útil para la navegación de elementos en una colección, sino también para el escenario de enlace principal-detalle. Considere de nuevo la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de aplicación de la sección [¿Qué es el enlace de datos?](#what_is_data_binding). En esa aplicación, la selección dentro de la <xref:System.Windows.Controls.ListBox> determina el contenido que se muestra en el <xref:System.Windows.Controls.ContentControl>. Para colocar de otro modo, cuando un <xref:System.Windows.Controls.ListBox> elemento se selecciona, el <xref:System.Windows.Controls.ContentControl> muestra los detalles del elemento seleccionado.  
  
 Puede implementar el escenario principal-detalle simplemente con dos o más controles enlazados a la misma vista. El siguiente ejemplo de la [Demo de enlace de datos](http://go.microsoft.com/fwlink/?LinkID=163703) muestra el marcado de la <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ContentControl> que se ven en la aplicación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en el [¿qué es el enlace de datos?](#what_is_data_binding) sección:  
  
 [!code-xaml[DataBindingLab#Master1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xaml[DataBindingLab#Detail](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 Observe que ambos controles están enlazados al mismo origen, el recurso estático *listingDataView* (consulte la definición de este recurso en la sección [Creación de una vista](#how_to_create_a_view)). Esto funciona porque cuando un objeto singleton (la <xref:System.Windows.Controls.ContentControl> en este caso) se enlaza a una vista de colección, enlaza automáticamente a la <xref:System.Windows.Data.CollectionView.CurrentItem%2A> de la vista. Tenga en cuenta que <xref:System.Windows.Data.CollectionViewSource> sincronizan automáticamente los objetos de moneda y la selección. Si el control de lista no está enlazado a un <xref:System.Windows.Data.CollectionViewSource> objeto como en este ejemplo, será necesario que establezcas su <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> propiedad `true` para que funcione.  
  
 Para obtener otros ejemplos, consulte [Bind to a Collection and Display Information Based on Selection](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) (Enlace de una colección y visualización de información según selección) y [Use the Master-Detail Pattern with Hierarchical Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) (Uso del patrón principal-detalle con datos jerárquicos).  
  
 Tal vez haya observado que en el ejemplo anterior se utiliza una plantilla. De hecho, los datos no se mostraría la forma deseada sin el uso de plantillas (explícitamente utilizado por el <xref:System.Windows.Controls.ContentControl> y utiliza implícitamente por la <xref:System.Windows.Controls.ListBox>). Trataremos el tema de la inclusión de datos en plantillas en la siguiente sección.  
  
<a name="data_templating"></a>   
## <a name="data-templating"></a>Inclusión de datos en plantillas  
 Sin el uso de plantillas de datos, nuestra [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de aplicación de la sección [¿Qué es el enlace de datos?](#what_is_data_binding) tendría este aspecto:  
  
 ![Data Binding Demo sin plantillas de datos](../../../../docs/framework/wpf/data/media/databindingdemotemplates.png "DataBindingDemoTemplates")  
  
 Como se muestra en el ejemplo en la sección anterior, tanto el <xref:System.Windows.Controls.ListBox> control y la <xref:System.Windows.Controls.ContentControl> se enlazan al objeto de colección completa (o más concretamente, la vista sobre el objeto de colección) de *AuctionItem*s. Sin instrucciones específicas de cómo mostrar la recopilación de datos, el <xref:System.Windows.Controls.ListBox> muestra una representación de cadena de cada objeto en la colección subyacente y el <xref:System.Windows.Controls.ContentControl> muestra una representación de cadena del objeto que está enlazado.  
  
 Para solucionar este problema, la aplicación define <xref:System.Windows.DataTemplate>s. Como se muestra en el ejemplo en la sección anterior, el <xref:System.Windows.Controls.ContentControl> utiliza de forma explícita el *detailsProductListingTemplate*<xref:System.Windows.DataTemplate>. El <xref:System.Windows.Controls.ListBox> control utiliza implícitamente el siguiente <xref:System.Windows.DataTemplate> al mostrar el *AuctionItem* objetos de la colección:  
  
 [!code-xaml[DataBindingLab#AuctionItemDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 Con el uso de esos dos <xref:System.Windows.DataTemplate>s, la interfaz de usuario resultante es el que se muestra en el [¿qué es el enlace de datos?](#what_is_data_binding) sección. Como puede ver en esa captura de pantalla, además de permitir que se coloquen datos en los controles, <xref:System.Windows.DataTemplate>s le permiten definir un aspecto atractivo para sus datos. Por ejemplo, <xref:System.Windows.DataTrigger>se utilizan en los pasos anteriores <xref:System.Windows.DataTemplate> para que *AuctionItem*s con *SpecialFeatures* valo *resaltar* aparecerá con un borde naranja y una estrella.  
  
 Para más información sobre las plantillas de datos, consulte [Data Templating Overview](../../../../docs/framework/wpf/data/data-templating-overview.md) (Introducción a las plantillas de datos).  
  
<a name="data_validation"></a>   
## <a name="data-validation"></a>Validación de datos  
  
 La mayoría de las aplicaciones que toman datos proporcionados por el usuario requieren lógica de validación para asegurarse de que el usuario ha escrito la información esperada. Las comprobaciones de validación pueden basarse en el tipo, intervalo, formato u otros requisitos específicos de la aplicación. En esta sección se describe cómo funciona la validación de datos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="associating-validation-rules-with-a-binding"></a>Asociación de reglas de validación a un enlace  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modelo de enlace de datos le permite asociar <xref:System.Windows.Data.Binding.ValidationRules%2A> con su <xref:System.Windows.Data.Binding> objeto. Por ejemplo, en el ejemplo siguiente se enlaza un <xref:System.Windows.Controls.TextBox> a una propiedad denominada `StartPrice` y agrega un <xref:System.Windows.Controls.ExceptionValidationRule> el objeto a la <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> propiedad.  
  
 [!code-xaml[DataBindingLab#DefaultValidation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 Un <xref:System.Windows.Controls.ValidationRule> objeto comprueba si el valor de una propiedad es válido. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene los siguientes dos tipos integrados de <xref:System.Windows.Controls.ValidationRule> objetos:  
  
-   Un <xref:System.Windows.Controls.ExceptionValidationRule> comprueba las excepciones producidas durante la actualización de la propiedad de origen de enlace. En el ejemplo anterior, `StartPrice` es de tipo entero. Cuando el usuario especifica un valor que no se puede convertir en un entero, se produce una excepción, lo que ocasiona que el enlace se marque como no válido. Una sintaxis alternativa para la configuración de la <xref:System.Windows.Controls.ExceptionValidationRule> explícitamente consiste en establecer el <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> propiedad `true` en su <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.MultiBinding> objeto.  
  
-   A <xref:System.Windows.Controls.DataErrorValidationRule> objeto comprueba si hay errores que se producen los objetos que implementan la <xref:System.ComponentModel.IDataErrorInfo> interfaz. Para obtener un ejemplo del uso de esta regla de validación, consulte <xref:System.Windows.Controls.DataErrorValidationRule>. Una sintaxis alternativa para la configuración de la <xref:System.Windows.Controls.DataErrorValidationRule> explícitamente consiste en establecer el <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> propiedad `true` en su <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.MultiBinding> objeto.  
  
 También puede crear su propia regla de validación derivando de la <xref:System.Windows.Controls.ValidationRule> clase e implementar el <xref:System.Windows.Controls.ValidationRule.Validate%2A> método. En el ejemplo siguiente se muestra la regla usada por la *Add Product Listing* "Start Date" <xref:System.Windows.Controls.TextBox> desde el [¿qué es el enlace de datos?](#what_is_data_binding) sección:  
  
 [!code-csharp[DataBindingLab#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 El *controles* <xref:System.Windows.Controls.TextBox> utiliza este *FutureDateRule*, tal y como se muestra en el ejemplo siguiente:  
  
 [!code-xaml[DataBindingLab#CustomValidation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 Tenga en cuenta que, dado el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor es <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, el motor de enlace actualiza el valor de origen en cada pulsación de tecla, lo que significa también comprueba cada regla en el <xref:System.Windows.Data.Binding.ValidationRules%2A> colección en cada pulsación de tecla. Ofreceremos una descripción más detallada en la sección Proceso de validación.  
  
<a name="invalidation_feedback"></a>   
### <a name="providing-visual-feedback"></a>Proporcionar comentarios visuales  
 Si el usuario especifica un valor no válido, quizás desee proporcionar algunos comentarios sobre el error en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de aplicación. Una manera de proporcionar esos comentarios es establecer el <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> propiedad adjunta a una personalizada <xref:System.Windows.Controls.ControlTemplate>. Como se muestra en la subsección anterior, el *controles* <xref:System.Windows.Controls.TextBox> utiliza un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> llama *validationTemplate*. En el ejemplo siguiente se muestra la definición de *validationTemplate*:  
  
 [!code-xaml[DataBindingLab#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 El <xref:System.Windows.Controls.AdornedElementPlaceholder> elemento especifica dónde se debe colocar el control que se adorna.  
  
 Además, también puede usar un <xref:System.Windows.Controls.ToolTip> para mostrar el mensaje de error. Tanto el *controles* y *StartDateEntryForm*<xref:System.Windows.Controls.TextBox>es usar el estilo de *textStyleTextBox*, lo que se crea un <xref:System.Windows.Controls.ToolTip> que Muestra el mensaje de error. En el ejemplo siguiente se muestra la definición de *textStyleTextBox*. La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` cuando uno o varios de los enlaces en las propiedades del elemento enlazado tienen un error.  
  
 [!code-xaml[DataBindingLab#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 Con la opción de instalación <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> y <xref:System.Windows.Controls.ToolTip>, *controles* <xref:System.Windows.Controls.TextBox> el siguiente aspecto cuando se produce un error de validación:  
  
 ![Error de validación de enlace de datos](../../../../docs/framework/wpf/data/media/databindingdemo-validation.PNG "DataBindingDemo_Validation")  
  
 Si su <xref:System.Windows.Data.Binding> está asociada a las reglas de validación, pero no se especifica un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> en el control enlazado, el valor predeterminado es <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> se usará para notificar a los usuarios cuando se produce un error de validación. El valor predeterminado <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> es una plantilla de control que define un borde rojo en la capa de adornos. Con el valor predeterminado <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> y <xref:System.Windows.Controls.ToolTip>, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> el siguiente aspecto cuando se produce un error de validación:  
  
 ![Error de validación de enlace de datos](../../../../docs/framework/wpf/data/media/databindingdemo-validationdefault.PNG "DataBindingDemo_ValidationDefault")  
  
 Para ver un ejemplo sobre cómo proporcionar lógica para validar todos los controles de un cuadro de diálogo, consulte la sección Cuadros de diálogo personalizados en [Dialog Boxes Overview](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md) (Introducción a los cuadros de diálogo).  
  
### <a name="validation-process"></a>Proceso de validación  
 La validación normalmente se produce cuando el valor de un destino se transfiere a la propiedad de origen del enlace. Esto se realiza con <xref:System.Windows.Data.BindingMode.TwoWay> y <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces. Para reiterar, lo que hace que una actualización de origen depende del valor de la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad, como se describe en el [qué desencadenadores de actualización del origen](#what_triggers_source_updates) sección.  
  
 A continuación se describe el proceso de *validación*. Tenga en cuenta que si se produce un error de validación o de cualquier otro tipo en cualquier momento del proceso, este se detiene.  
  
1.  El motor de enlace comprueba si hay personalizada <xref:System.Windows.Controls.ValidationRule> objetos definidos cuya <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> está establecido en <xref:System.Windows.Controls.ValidationStep.RawProposedValue> para que <xref:System.Windows.Data.Binding>, en cuyo caso llama a la <xref:System.Windows.Controls.ValidationRule.Validate%2A> método en cada <xref:System.Windows.Controls.ValidationRule> hasta que uno de ellos se ejecute en un error o bien hasta que todas ellas pasan.  
  
2.  A continuación, el motor de enlace llama al convertidor, si existe alguno.  
  
3.  Si el convertidor se realiza correctamente, el motor de enlace comprueba si hay personalizada <xref:System.Windows.Controls.ValidationRule> objetos definidos cuya <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> está establecido en <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> para que <xref:System.Windows.Data.Binding>, en cuyo caso llama a la <xref:System.Windows.Controls.ValidationRule.Validate%2A> método en cada <xref:System.Windows.Controls.ValidationRule> cuya <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecido en <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> hasta que uno de ellos se ejecute en un error o hasta que todas ellas pasan.  
  
4.  El motor de enlace establece la propiedad de origen.  
  
5.  El motor de enlace comprueba si hay personalizada <xref:System.Windows.Controls.ValidationRule> objetos definidos cuya <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> está establecido en <xref:System.Windows.Controls.ValidationStep.UpdatedValue> para que <xref:System.Windows.Data.Binding>, en cuyo caso llama a la <xref:System.Windows.Controls.ValidationRule.Validate%2A> método en cada <xref:System.Windows.Controls.ValidationRule> que tiene <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecido en <xref:System.Windows.Controls.ValidationStep.UpdatedValue> hasta que uno de ellos se ejecute en un error o hasta que todas ellas pasan. Si un <xref:System.Windows.Controls.DataErrorValidationRule> está asociado con un enlace y su <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> se establece en el valor predeterminado, <xref:System.Windows.Controls.ValidationStep.UpdatedValue>, el <xref:System.Windows.Controls.DataErrorValidationRule> se activa en este momento. Esto también es el punto cuando enlaces que tienen la <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> establecido en `true` se comprueban.  
  
6.  El motor de enlace comprueba si hay personalizada <xref:System.Windows.Controls.ValidationRule> objetos definidos cuya <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> está establecido en <xref:System.Windows.Controls.ValidationStep.CommittedValue> para que <xref:System.Windows.Data.Binding>, en cuyo caso llama a la <xref:System.Windows.Controls.ValidationRule.Validate%2A> método en cada <xref:System.Windows.Controls.ValidationRule> que tiene <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecido en <xref:System.Windows.Controls.ValidationStep.CommittedValue> hasta que uno de ellos se ejecute en un error o hasta que todas ellas pasan.  
  
 Si un <xref:System.Windows.Controls.ValidationRule> no pasa en cualquier momento durante este proceso, el motor de enlace crea un <xref:System.Windows.Controls.ValidationError> objeto y lo agrega a la <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> colección del elemento enlazado. Antes del enlace motor se ejecuta el <xref:System.Windows.Controls.ValidationRule> objetos en un paso determinado, quita cualquier <xref:System.Windows.Controls.ValidationError> que se ha agregado a la <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> adjunta la propiedad del elemento enlazado durante ese paso. Por ejemplo, si un <xref:System.Windows.Controls.ValidationRule> cuyo <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> está establecido en <xref:System.Windows.Controls.ValidationStep.UpdatedValue> error la próxima vez que se produce el proceso de validación, el motor de enlace que quita <xref:System.Windows.Controls.ValidationError> inmediatamente antes llama a cualquiera <xref:System.Windows.Controls.ValidationRule> que tiene <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecido en <xref:System.Windows.Controls.ValidationStep.UpdatedValue>.  
  
 Cuando <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> no está vacío, el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta del elemento se establece en `true`. Además, si el <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> propiedad de la <xref:System.Windows.Data.Binding> se establece en `true`, a continuación, el motor de enlace provoca el <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> evento en el elemento adjunto.  
  
 También tenga en cuenta que una transferencia de valor válida en cualquier dirección (del destino al origen o de origen y destino) borra la <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> propiedad adjunta.  
  
 Si el enlace tiene una <xref:System.Windows.Controls.ExceptionValidationRule> asociado a él o tenía el <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> propiedad está establecida en `true` y se produce una excepción cuando el motor de enlace establece el origen, el motor de enlace que se comprueba para ver si hay un <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>. Tiene la opción para usar el <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> devolución de llamada para proporcionar un controlador personalizado para controlar las excepciones. Si un <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> no se especifica en el <xref:System.Windows.Data.Binding>, el motor de enlace crea un <xref:System.Windows.Controls.ValidationError> con la excepción y lo agrega a la <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> colección del elemento enlazado.  
  
## <a name="debugging-mechanism"></a>Mecanismo de depuración  
 Puede establecer la propiedad adjunta <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> en un objeto relacionado con el enlace para recibir información sobre el estado de un enlace específico.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.DataErrorValidationRule>  
 [Novedades de WPF versión 4.5](../../../../docs/framework/wpf/getting-started/whats-new.md)  
 [Enlazar a los resultados de una consulta LINQ](../../../../docs/framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)  
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Demo de enlace de datos](http://go.microsoft.com/fwlink/?LinkID=163703)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Bind to an ADO.NET Data Source](../../../../docs/framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md) (Enlace a un origen de datos de ADO.NET)
