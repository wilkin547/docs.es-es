---
title: "Informaci&#243;n general sobre el enlace de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "enlazar datos, acerca de enlace de datos"
  - "conversión para enlace de datos"
  - "enlace de datos, acerca de enlace de datos"
  - "conversión de datos para el enlace"
ms.assetid: c707c95f-7811-401d-956e-2fffd019a211
caps.latest.revision: 78
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 75
---
# Informaci&#243;n general sobre el enlace de datos
El enlace de datos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un método simple y coherente para que las aplicaciones presenten e interactúen con datos.  Los elementos se pueden enlazar a los datos de diversos orígenes de datos en forma de objetos [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] y [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  Los objetos <xref:System.Windows.Controls.ContentControl> como <xref:System.Windows.Controls.Button> y los objetos <xref:System.Windows.Controls.ItemsControl> como <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ListView> tienen funciones integradas que permiten definir de forma flexible elementos de datos individuales o colecciones de elementos de datos.  A partir de estos datos se pueden generar vistas de ordenación, filtro y agrupación.  
  
 La funcionalidad de enlace de datos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presenta varias ventajas con respecto a los modelos tradicionales, como un mayor número de propiedades que admiten de forma inherente el enlace de datos, una representación flexible de los datos en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y la separación bien definida de la lógica del negocio de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 En este tema se describen en primer lugar los conceptos fundamentales del enlace de datos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y, a continuación, se explica el uso de la clase <xref:System.Windows.Data.Binding> y otras características del enlace de datos.  
  
   
  
<a name="what_is_data_binding"></a>   
## ¿Qué es el enlace de datos?  
 El enlace de datos es el proceso que establece una conexión entre la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación y la lógica del negocio.  Si el enlace está correctamente configurado y los datos proporcionan las notificaciones adecuadas, cuando los datos cambian su valor, los elementos que están enlazados a ellos reflejan los cambios automáticamente.  El enlace de datos también puede implicar la actualización automática de los datos que subyacen a una representación externa de los datos de un elemento, cuando esta representación cambia.  Por ejemplo, si el usuario modifica el valor en un elemento <xref:System.Windows.Controls.TextBox>, el valor de los datos subyacentes se actualiza automáticamente para reflejar ese cambio.  
  
 Un uso típico del enlace de datos es colocar los datos de configuración locales o de servidor en formularios o en otros controles de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], este concepto se expande para incluir el enlace de un gran número de propiedades a una gran variedad de orígenes de datos.  En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], las [propiedades de dependencia](GTMT) de los elementos se pueden enlazar a objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] \(incluidos los objetos [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] u objetos asociados a servicios Web y propiedades web\) y datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 Para obtener un ejemplo de enlace de datos, examine la siguiente [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de aplicación de [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703):  
  
 ![Captura de pantalla de ejemplo de enlace de datos](../../../../docs/framework/wpf/data/media/databinding-databindingdemo.png "DataBinding\_DataBindingDemo")  
  
 El ejemplo anterior es la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de una aplicación que muestra una lista de artículos subastados.  La aplicación muestra las características siguientes de enlace de datos:  
  
-   El contenido de <xref:System.Windows.Controls.ListBox> se enlaza a una colección de objetos *AuctionItem*.  Un objeto *AuctionItem* tiene propiedades como *Descripción*, *StartPrice*, *StartDate*, *Categoría*, *SpecialFeatures*, etc.  
  
-   Los datos \(objetos *AuctionItem* \) mostrados en <xref:System.Windows.Controls.ListBox> se incluyen en una plantilla para mostrar la descripción y el precio actual de cada artículo.  Para ello se utiliza un objeto <xref:System.Windows.DataTemplate>.  Asimismo, el aspecto de cada artículo depende del valor *SpecialFeatures* del elemento *AuctionItem* que se va a mostrar.  Si el valor *SpecialFeatures* de *AuctionItem* es *Color*, el artículo tiene un borde azul.  Si el valor es *Highlight*, el artículo tiene un borde naranja y una estrella.  En la sección [Incluir datos en plantillas](#data_templating) se proporciona información sobre las plantillas de datos.  
  
-   El usuario puede agrupar, filtrar u ordenar los datos mediante los controles <xref:System.Windows.Controls.CheckBox> proporcionados.  En la imagen anterior, los controles <xref:System.Windows.Controls.CheckBox> "Group by category" y "Sort by category and date" están seleccionados.  Es posible que haya observado que los datos se agrupan en función de la categoría del producto, y el nombre de las categorías se muestra en orden alfabético.  Aunque no se aprecia muy bien en la imagen, los artículos están ordenados también por fecha de inicio dentro de cada categoría.  Para ello se utiliza una *vista de colección*.  En la sección [Enlace a colecciones](#binding_to_collections) se describe este tipo de vistas.  
  
-   Cuando el usuario selecciona un artículo, <xref:System.Windows.Controls.ContentControl> muestra los detalles del artículo seleccionado.  Esto recibe el nombre de *escenario principal\-detalle*.  En la sección [Escenario principal\-detalle](#master_detail_scenario) se proporciona información sobre este tipo de escenario de enlace.  
  
-   El tipo de la propiedad *StartDate* es <xref:System.DateTime>, que devuelve una fecha que incluye el tiempo en milisegundos.  En esta aplicación, se ha utilizado un convertidor personalizado para que se muestre una cadena de fecha más corta.  En la sección [Conversión de datos](#data_conversion) se proporciona información sobre los convertidores.  
  
 Cuando el usuario hace clic en el botón *Add Product*, se muestra el siguiente formulario:  
  
 ![Agregar página de listado de productos](../../../../docs/framework/wpf/data/media/databinding-demo-addproductlisting.png "DataBinding\_Demo\_AddProductListing")  
  
 El usuario puede modificar los campos del formulario, obtener una vista previa de la lista de productos mediante la vista previa abreviada y los paneles de vista previa más detallada y, a continuación, hacer clic en *submit* para agregar la nueva lista de productos.  Todas las funciones de agrupación, filtrado y ordenación existentes se aplicarán a la nueva entrada.  En este caso en concreto, el artículo especificado en la imagen anterior se mostrará como el segundo artículo dentro de la categoría *Computer*.  
  
 Lo que no se muestra en esta imagen es la lógica de validación proporcionada en el control <xref:System.Windows.Controls.TextBox> *Start Date*.  Si el usuario escribe una fecha no válida \(con un formato no válido o una fecha pasada\), se le notificará con un control <xref:System.Windows.Controls.ToolTip> y un signo de exclamación de color rojo situado junto al control <xref:System.Windows.Controls.TextBox>.  En la sección [Validación de datos](#data_validation) se explica cómo crear lógica de validación.  
  
 Antes de abordar las diferentes características de enlace de datos citadas anteriormente, en la siguiente sección explicaremos los conceptos fundamentales imprescindibles para comprender el enlace de datos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="basic_data_binding_concepts"></a>   
## Conceptos básicos del enlace de datos  
   
  
 Independientemente del elemento que se vaya a enlazar y de la naturaleza del origen de datos, cada enlace sigue siempre el modelo que se muestra en la ilustración siguiente:  
  
 ![Diagrama de enlace de datos básico](../../../../docs/framework/wpf/data/media/databindingmostbasic.png "DataBindingMostBasic")  
  
 Como se muestra en la ilustración anterior, el enlace de datos es esencialmente el puente entre el [destino del enlace](GTMT) y el [origen del enlace](GTMT).  En la ilustración se muestran los siguientes conceptos fundamentales del enlace de datos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   Normalmente, cada enlace tiene estos cuatro componentes: un objeto de [destino del enlace](GTMT), una propiedad de destino, un [origen del enlace](GTMT) y una ruta de acceso al valor en el [origen del enlace](GTMT) que se va a usar.  Por ejemplo, si desea enlazar el contenido de <xref:System.Windows.Controls.TextBox> a la propiedad *Nombre* de un objeto *Empleado*, su objeto de destino es <xref:System.Windows.Controls.TextBox>, la propiedad de destino es la propiedad <xref:System.Windows.Controls.TextBox.Text%2A>, el valor que se va a utilizar es *Nombre* y el objeto de origen es el objeto *Empleado*.  
  
-   La propiedad de destino debe ser una [propiedad de dependencia](GTMT).  La mayoría de las propiedades <xref:System.Windows.UIElement> son [propiedades de dependencia](GTMT) y la mayoría de las [propiedades de dependencia](GTMT), excepto las de sólo lectura, admiten el enlace de datos de forma predeterminada.  \(Sólo los tipos <xref:System.Windows.DependencyObject> pueden definir [propiedades de dependencia](GTMT) y todos los <xref:System.Windows.UIElement> se derivan de <xref:System.Windows.DependencyObject>\).  
  
-   Aunque no se especifica en la figura, hay que destacar que el objeto de [origen de enlace](GTMT) no está restringido a ser un objeto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] personalizado.  El enlace de datos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite datos en forma de objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  Para proporcionar algunos ejemplos, el origen del enlace puede ser un objeto <xref:System.Windows.UIElement>, cualquier objeto de lista, un objeto de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] asociado a datos de [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] o servicios Web, o bien un objeto XMLNode que contiene datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  Para obtener más información, vea [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
 Cuando consulte otros temas del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)], es importante tener en cuenta que cuando establece un enlace, enlaza un [destino del enlace](GTMT) *a* un [origen del enlace](GTMT).  Por ejemplo, si va a mostrar algunos datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] subyacentes en <xref:System.Windows.Controls.ListBox> utilizando el enlace de datos, enlazará <xref:System.Windows.Controls.ListBox> a los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 Para establecer un enlace, se utiliza el objeto <xref:System.Windows.Data.Binding>.  En el resto de este tema se explican muchos de los conceptos asociados al objeto <xref:System.Windows.Data.Binding> y algunas de las propiedades y uso de este objeto  
  
<a name="direction_of_data_flow"></a>   
### Dirección del flujo de datos  
 Como se mencionó anteriormente y como se indica por la flecha de la ilustración anterior, el flujo de datos de un enlace puede ir desde el [destino del enlace](GTMT) al [origen del enlace](GTMT) \(por ejemplo, el valor de origen cambia cuando un usuario modifica el valor de <xref:System.Windows.Controls.TextBox>\) o desde el [origen del enlace](GTMT) al [destino del enlace](GTMT) \(por ejemplo, el contenido de <xref:System.Windows.Controls.TextBox> se actualiza con los cambios en el [origen del enlace](GTMT)\) si el origen del enlace proporciona las notificaciones correspondientes.  
  
 Tal vez desee que su aplicación permita que los usuarios cambien los datos y los propaguen al objeto de origen.  O tal vez no desee permitir que los usuarios actualicen los datos de origen.  Puede controlar este comportamiento estableciendo la propiedad <xref:System.Windows.Data.Binding.Mode%2A> del objeto <xref:System.Windows.Data.Binding>.  En la ilustración siguiente se muestran los tipos diferentes de flujo de datos:  
  
 ![Flujo de datos de enlace de datos](../../../../docs/framework/wpf/data/media/databinding-dataflow.png "DataBinding\_DataFlow")  
  
-   El enlace <xref:System.Windows.Data.BindingMode> permite que los cambios en la propiedad de origen actualicen automáticamente la propiedad de destino, pero los cambios en la propiedad de destino no se propagan de nuevo a la propiedad de origen.  Este tipo de enlace es adecuado si el control que se va a enlazar es de sólo lectura de forma implícita.  Por ejemplo, podría enlazar a un origen como un tablero de cotizaciones o quizás su propiedad de destino no tenga ninguna interfaz de control para realizar modificaciones, como un color de fondo enlazado a datos de una tabla.  Si no hay necesidad de supervisar los cambios de la propiedad de destino, con el modo de enlace <xref:System.Windows.Data.BindingMode> evitará el trabajo adicional que supone usar el modo de enlace <xref:System.Windows.Data.BindingMode>.  
  
-   El enlace <xref:System.Windows.Data.BindingMode> permite que los cambios realizados en la propiedad de origen o en la de destino se actualicen automáticamente en el otro.  Este tipo de enlace es adecuado para formularios modificables u otros escenarios de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] totalmente interactivos.  La mayoría de las propiedades tienen el enlace <xref:System.Windows.Data.BindingMode> de forma predeterminada, pero algunas [propiedades de dependencia](GTMT) \(normalmente las propiedades de controles modificables por el usuario como la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> de <xref:System.Windows.Controls.TextBox> y la propiedad <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> de <xref:System.Windows.Controls.CheckBox>\) tienen el enlace <xref:System.Windows.Data.BindingMode> de manera predeterminada.  Una manera de determinar mediante programación si una [propiedad de dependencia](GTMT) se enlaza de forma predeterminada de modo unidireccional o bidireccional es obtener los metadatos de la propiedad mediante <xref:System.Windows.DependencyProperty.GetMetadata%2A> y, a continuación, comprobar el valor booleano de la propiedad <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>.  
  
-   <xref:System.Windows.Data.BindingMode> es el enlace inverso de <xref:System.Windows.Data.BindingMode>; actualiza la propiedad de origen cuando cambia la propiedad de destino.  Podría utilizar este tipo de enlace si, por ejemplo, sólo necesita volver a evaluar el valor de origen de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
-   El enlace <xref:System.Windows.Data.BindingMode>, no mostrado en la ilustración, permite que la propiedad de origen inicialice la propiedad de destino, pero los demás cambios no se propagan.  Esto significa que si el contexto de los datos sufre un cambio o el objeto del contexto de datos cambia, el cambio no se refleja en la propiedad de destino.  Este tipo de enlace es adecuado si utiliza los datos allí donde es adecuado utilizar una captura del estado actual o cuando los datos son realmente estáticos.  Este tipo de enlace también es útil si desea inicializar la propiedad de destino con algún valor de una propiedad de origen y no se conoce el contexto de los datos de antemano.  Se trata básicamente de una forma más fácil de enlace <xref:System.Windows.Data.BindingMode> que proporciona un mejor rendimiento en los casos en los que no cambia el valor de origen.  
  
 Observe que para detectar los cambios en el origen \(aplicables a los enlaces <xref:System.Windows.Data.BindingMode> y <xref:System.Windows.Data.BindingMode>\), el origen debe implementar un mecanismo apropiado de notificación de cambios de propiedades, como <xref:System.ComponentModel.INotifyPropertyChanged>.  Vea [Implementar la notificación de cambio de propiedad](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) para obtener un ejemplo de implementación de <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 En la página de propiedades de <xref:System.Windows.Data.Binding.Mode%2A> se proporciona más información sobre los modos de enlace y un ejemplo sobre cómo especificar la dirección de un enlace.  
  
<a name="what_triggers_source_updates"></a>   
### Qué desencadena la actualización del origen  
 Los enlaces <xref:System.Windows.Data.BindingMode> u <xref:System.Windows.Data.BindingMode> realizan escuchas para detectar los cambios en la propiedad de destino y los propagan de nuevo al origen.  Esto se conoce como la actualización del origen.  Por ejemplo, puede modificar el texto de un control TextBox para cambiar el valor de origen subyacente.  Como se describe en la última sección, el valor de la propiedad <xref:System.Windows.Data.Binding.Mode%2A> del enlace determina la dirección del flujo de datos.  
  
 Pero ¿se actualizará su valor de origen mientras modifica el texto o después de modificarlo y sacar el mouse fuera del control TextBox?  La propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> del enlace determina qué desencadena la actualización del origen.  Los puntos de las flechas derecha en la ilustración siguiente muestran el rol de la propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>:  
  
 ![Diagrama UpdateSourceTrigger](../../../../docs/framework/wpf/data/media/databindingupdatesourcetrigger.png "DataBindingUpdateSourceTrigger")  
  
 Si el valor de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> es <xref:System.Windows.Data.UpdateSourceTrigger>, el valor al que apunta la fecha derecha del enlace <xref:System.Windows.Data.BindingMode> u <xref:System.Windows.Data.BindingMode> se actualizará en cuanto cambie la propiedad de destino.  Sin embargo, si el valor de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> es <xref:System.Windows.Data.UpdateSourceTrigger>, ese valor sólo se actualizará con el nuevo valor cuando la propiedad de destino pierda el foco.  
  
 Al igual que ocurre con la propiedad <xref:System.Windows.Data.Binding.Mode%2A>, las diferentes [propiedades de dependencia](GTMT) tienen valores de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> predeterminados diferentes.  El valor predeterminado de la mayoría de las [propiedades de dependencia](GTMT) es <xref:System.Windows.Data.UpdateSourceTrigger>, mientras que la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> tiene un valor predeterminado de <xref:System.Windows.Data.UpdateSourceTrigger>.  Esto significa que el origen se suele actualizar cuando la propiedad de destino cambia, lo que es adecuado para controles <xref:System.Windows.Controls.CheckBox> y otros controles sencillos.  Sin embargo, para los campos de texto, la actualización cada vez que se pulsa una tecla puede disminuir el rendimiento y deniega al usuario la oportunidad usual de retroceder y corregir los errores tipográficos antes confirmar el nuevo valor.  Por ese motivo, la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> tiene un valor predeterminado de <xref:System.Windows.Data.UpdateSourceTrigger> en lugar de <xref:System.Windows.Data.UpdateSourceTrigger>.  
  
 Vea la página de propiedades de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> para obtener información sobre cómo determinar el valor de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> predeterminado de una [propiedad de dependencia](GTMT).  
  
 En la tabla siguiente se proporciona un escenario de ejemplo para cada valor de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> utilizando <xref:System.Windows.Controls.TextBox> como ejemplo:  
  
|Valor UpdateSourceTrigger|Cuándo se actualiza el valor de origen|Escenario de ejemplo de TextBox|  
|-------------------------------|--------------------------------------------|-------------------------------------|  
|LostFocus \(valor predeterminado para <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName>\)|Cuando el control TextBox pierde el foco|<xref:System.Windows.Controls.TextBox> asociado a lógica de validación \(vea la sección Datos de validación\)|  
|PropertyChanged|Cuando escribe en el control <xref:System.Windows.Controls.TextBox>|Controles <xref:System.Windows.Controls.TextBox> en una ventana de chat|  
|Explicit|Cuando la aplicación llama a <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>|Controles <xref:System.Windows.Controls.TextBox> en un formulario modificable \(sólo actualiza los valores de origen cuando el usuario hace clic en el botón de envío\)|  
  
 Para obtener un ejemplo, vea [Controlar cuándo el texto de TextBox actualiza el origen](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).  
  
<a name="creating_a_binding"></a>   
## Crear un enlace  
   
  
 Como recapitulación de algunos de los conceptos descritos en las secciones anteriores, recordemos que un enlace se establece mediante el objeto <xref:System.Windows.Data.Binding> y que cada enlace tiene normalmente cuatro componentes: el destino del enlace, la propiedad de destino, el origen del enlace y una ruta de acceso al valor de origen que se va a utilizar.  En esta sección se explica cómo configurar un enlace.  
  
 Considere el ejemplo siguiente, en el que el objeto de origen del enlace es una clase denominada *MyData* que se define en el espacio de nombres *SDKSample*.  En esta demostración, la clase *MyData* tiene una propiedad de cadena denominada *ColorName*, cuyo valor se establece en "Red".  Por tanto, este ejemplo genera un botón con un fondo rojo.  
  
 [!code-xml[BindNonTextProperty#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 Para obtener información más detallada sobre la sintaxis de declaración de enlaces y ejemplos sobre cómo configurar un enlace en código, vea [Información general sobre declaraciones de enlaces](../../../../docs/framework/wpf/data/binding-declarations-overview.md).  
  
 Si aplicamos este ejemplo a nuestro diagrama básico, la ilustración resultante tendrá el siguiente aspecto.  Se trata de un enlace <xref:System.Windows.Data.BindingMode> porque la propiedad Background admite el enlace <xref:System.Windows.Data.BindingMode> de forma predeterminada.  
  
 ![Diagrama de enlace de datos](../../../../docs/framework/wpf/data/media/databindingbuttonbackgroundexample.png "DataBindingButtonBackgroundExample")  
  
 Tal vez se pregunte por qué esto funciona si la propiedad *ColorName* es de tipo string mientras que la propiedad <xref:System.Windows.Controls.Control.Background%2A> es de tipo <xref:System.Windows.Media.Brush>.  Se ha aplicado la conversión predeterminada de tipos, que se explica en la sección [Conversión de datos](#data_conversion).  
  
<a name="specifying_the_binding_source"></a>   
### Especificar el origen del enlace  
 Observe que en el ejemplo anterior, el origen del enlace se especifica estableciendo la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> en el elemento <xref:System.Windows.Controls.DockPanel>.  A continuación, <xref:System.Windows.Controls.Button> hereda el valor <xref:System.Windows.FrameworkElement.DataContext%2A> de <xref:System.Windows.Controls.DockPanel>, que es su elemento primario.  Recordemos que el objeto de origen del enlace es uno de los cuatro componentes necesarios de un enlace.  Por tanto, si no se especifica el objeto de origen del enlace, el enlace no funcionará.  
  
 Hay varias formas de especificar el objeto de origen del enlace.  Utilizar la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> en un elemento primario es útil si va a enlazar varias propiedades al mismo origen.  Sin embargo, a veces puede ser más adecuado especificar el origen del enlace en declaraciones de enlace individuales.  En el ejemplo anterior, en lugar de utilizar la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A>, puede especificar el origen del enlace estableciendo directamente la propiedad <xref:System.Windows.Data.Binding.Source%2A> en la declaración de enlace del botón, como en el ejemplo siguiente:  
  
 [!code-xml[BindNonTextProperty#BackgroundBindingCompact](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 Además de establecer directamente la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> en un elemento, heredar el valor de <xref:System.Windows.FrameworkElement.DataContext%2A> de un antecesor \(como el botón del primer ejemplo\) y especificar explícitamente el origen del enlace estableciendo la propiedad <xref:System.Windows.Data.Binding.Source%2A> en <xref:System.Windows.Data.Binding> \(como el botón del último ejemplo\), también puede utilizar la propiedad <xref:System.Windows.Data.Binding.ElementName%2A> o la propiedad <xref:System.Windows.Data.Binding.RelativeSource%2A> para especificar el origen del enlace.  La propiedad <xref:System.Windows.Data.Binding.ElementName%2A> es útil cuando se enlaza a otros elementos de la aplicación como, por ejemplo, cuando se utiliza un control deslizante para ajustar el ancho de un botón.  La propiedad <xref:System.Windows.Data.Binding.RelativeSource%2A> es útil cuando el enlace se especifica en <xref:System.Windows.Controls.ControlTemplate> o <xref:System.Windows.Style>.  Para obtener más información, vea [Especificar el origen de enlace](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).  
  
<a name="specifying_the_path_to_the_value"></a>   
### Especificar la ruta de acceso al valor  
 Si su origen del enlace es un objeto, utiliza la propiedad <xref:System.Windows.Data.Binding.Path%2A> para especificar el valor que se va a usar para el enlace.  Si va a enlazar a datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], utiliza la propiedad <xref:System.Windows.Data.Binding.XPath%2A> para especificar el valor.  En algunos casos, puede ser pertinente usar la propiedad <xref:System.Windows.Data.Binding.Path%2A> aunque los datos sean [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  Por ejemplo, si desea tener acceso a la propiedad Name de un XMLNode devuelto \(como resultado de una consulta XPath\), debe utilizar la propiedad <xref:System.Windows.Data.Binding.Path%2A> además de la propiedad <xref:System.Windows.Data.Binding.XPath%2A>.  
  
 Para obtener información sobre la sintaxis y algunos ejemplos, vea las páginas de propiedades de <xref:System.Windows.Data.Binding.Path%2A> y <xref:System.Windows.Data.Binding.XPath%2A>.  
  
 Observe que aunque hemos recalcado que el <xref:System.Windows.Data.Binding.Path%2A> al valor que se va a utilizar es uno de los cuatro componentes necesarios de un enlace, en los escenarios en los que se enlaza a un objeto completo, el valor que se utiliza será el mismo que el objeto de [origen del enlace](GTMT).  En esos casos, se puede no especificar un <xref:System.Windows.Data.Binding.Path%2A>.  Considere el ejemplo siguiente:  
  
 [!code-xml[MasterDetail#EmptyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 En el ejemplo anterior se utiliza la sintaxis de enlace vacía: {Binding}.  En este caso, <xref:System.Windows.Controls.ListBox> hereda el objeto DataContext de un elemento DockPanel principal \(no mostrado en este ejemplo\).  Cuando no se especifica la ruta de acceso, el comportamiento predeterminado es enlazar al objeto completo.  Es decir, en este ejemplo, la ruta de acceso se ha omitido porque estamos enlazando la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> al objeto completo.  \(Vea la sección [Enlace a colecciones](#binding_to_collections) para obtener información detallada\).  
  
 Además del enlace a una colección, este escenario es útil también cuando se desea enlazar a un objeto completo en lugar de simplemente a una propiedad individual de un objeto.  Por ejemplo, si el objeto de origen es de tipo string y simplemente desea enlazar a la propia cadena.  Otro escenario común es cuando se desea enlazar un elemento a un objeto con varias propiedades.  
  
 Observe que puede ser necesario aplicar lógica personalizada para que los datos sean significativos para la propiedad de destino enlazada.  La lógica personalizada puede consistir en un convertidor personalizado \(si no existe la conversión de tipos predeterminada\).  Vea [Conversión de datos](#data_conversion) para obtener información sobre los convertidores.  
  
<a name="binding_bindingexpression"></a>   
### Binding y BindingExpression  
 Antes de explicar otras características y usos del enlace de datos, es conveniente presentar la clase <xref:System.Windows.Data.BindingExpression>.  Como ha visto en las secciones anteriores, la clase <xref:System.Windows.Data.Binding> es la clase de alto nivel para la declaración de un enlace; la clase <xref:System.Windows.Data.Binding> proporciona muchas propiedades que permiten especificar las características de un enlace.  Una clase relacionada, <xref:System.Windows.Data.BindingExpression>, es el objeto subyacente que mantiene la conexión entre el origen y el destino.  Un enlace contiene toda la información que se puede compartir entre varias expresiones de enlace.  Una clase <xref:System.Windows.Data.BindingExpression> es una expresión de instancia que no se puede compartir y que contiene toda la información de las instancias de la clase <xref:System.Windows.Data.Binding>.  
  
 Considere, por ejemplo, lo siguiente, donde *myDataObject* es una instancia de la clase *MyData*, *myBinding* es el objeto <xref:System.Windows.Data.Binding> de origen y la clase *MyData* es una clase definida que contiene una propiedad de cadena denominada *MyDataProperty*.  En este ejemplo se enlaza el contenido de texto de *mytext*, una instancia de <xref:System.Windows.Controls.TextBlock>, a *MyDataProperty*.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Puede utilizar el mismo objeto *myBinding* para crear otros enlaces.  Por ejemplo, podría utilizar el objeto *myBinding* para enlazar el contenido de texto de una casilla a *MyDataProperty*.  En ese escenario, habrá dos instancias de <xref:System.Windows.Data.BindingExpression> que comparten el objeto *myBinding*.  
  
 Un objeto <xref:System.Windows.Data.BindingExpression> se puede obtener a través del valor devuelto por la llamada a <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> en un objeto enlazado a datos.  En los temas siguientes se muestran algunos de los usos de la clase <xref:System.Windows.Data.BindingExpression>:  
  
-   [Obtener el objeto de enlace a partir de una propiedad de destino enlazada](../../../../docs/framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
-   [Controlar cuándo el texto de TextBox actualiza el origen](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## Conversión de datos  
 En el ejemplo anterior, el botón es rojo porque su propiedad <xref:System.Windows.Controls.Control.Background%2A> está enlazada a una propiedad de cadena con el valor "Red".  Esto funciona porque hay un convertidor de tipos en el tipo <xref:System.Windows.Media.Brush> para convertir el valor de cadena en <xref:System.Windows.Media.Brush>.  
  
 Al agregar esta información a la ilustración de la sección [Crear un enlace](#creating_a_binding), obtenemos el siguiente diagrama:  
  
 ![Diagrama de enlace de datos](../../../../docs/framework/wpf/data/media/databindingbuttondefaultconversion.png "DataBindingButtonDefaultConversion")  
  
 Pero ¿y si en lugar de una propiedad de tipo string, el objeto de origen del enlace tiene una propiedad *Color* de tipo <xref:System.Windows.Media.Color>?  En ese caso, para que el enlace funcione tendrá que convertir el valor de propiedad *Color* en algún valor que la propiedad <xref:System.Windows.Controls.Control.Background%2A> acepte.  Tendrá que crear un convertidor personalizado implementando la interfaz <xref:System.Windows.Data.IValueConverter>, como en el ejemplo siguiente:  
  
 [!code-csharp[ColorPicker_snip#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 En la página de referencia de <xref:System.Windows.Data.IValueConverter> encontrará más información al respecto.  
  
 Ahora que se ha utilizado el convertidor personalizado en lugar de la conversión predeterminada, nuestro diagrama presenta el siguiente aspecto:  
  
 ![Diagrama de enlace de datos](../../../../docs/framework/wpf/data/media/databindingconvertercolorexample.png "DataBindingConverterColorExample")  
  
 Recordemos que las conversiones predeterminadas pueden estar disponibles si el tipo que se va a enlazar contiene convertidores de tipo.  Este comportamiento dependerá de los convertidores de tipos disponibles en el destino.  Si no está seguro, cree su propio convertidor.  
  
 A continuación, se incluyen algunos escenarios típicos en los que sería lógico implementar un convertidor de datos:  
  
-   Los datos se muestran de forma diferente, dependiendo de la referencia cultural.  Por ejemplo, tal vez desee implementar un convertidor de monedas o un convertidor de fechas y horas del calendario en función de los valores o normas utilizados en una determinada referencia cultural.  
  
-   Los datos que se utilizan no están diseñados necesariamente para cambiar el valor textual de una propiedad, sino para cambiar otro valor, como el origen de una imagen, o el color o estilo del texto que se va a mostrar.  En este caso se pueden utilizar convertidores para convertir el enlace de una propiedad que tal vez no sea adecuada, como el enlace de un campo de texto a la propiedad Background de una celda de tabla.  
  
-   Hay varios controles o varias propiedades de controles enlazados a los mismos datos.  En ese caso, el enlace principal podría mostrar simplemente el texto, mientras que los otros enlaces controlan los aspectos de presentación, pero se sigue utilizando el mismo enlace como información de origen.  
  
-   Hasta el momento, no hemos proporcionado aún una descripción del enlace <xref:System.Windows.Data.MultiBinding>, en el que una propiedad de destino tiene una colección de enlaces.  En el caso de un enlace <xref:System.Windows.Data.MultiBinding>, se utiliza un <xref:System.Windows.Data.IMultiValueConverter> personalizado para generar un valor final a partir de los valores de los enlaces.  Por ejemplo, el color podría calcularse a partir de los valores de rojo, azul y verde, que pueden ser valores de los mismos o de diferentes objetos de origen del enlace.  Vea la página de la clase <xref:System.Windows.Data.MultiBinding> para obtener información y ejemplos al respecto.  
  
<a name="binding_to_collections"></a>   
## Enlace a colecciones  
   
  
 Un objeto de origen del enlace se puede tratar como un objeto único cuyas propiedades contienen los datos, o como una recolección de datos de objetos polimórficos que suelen estar agrupados \(como el resultado de una consulta a una base de datos\).  Hasta ahora sólo hemos explicado el enlace a objetos individuales, pero el enlace a una recolección de datos es un escenario común.  Por ejemplo, es habitual utilizar un <xref:System.Windows.Controls.ItemsControl> como <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView> o <xref:System.Windows.Controls.TreeView> para mostrar una recolección de datos, como en la aplicación que se muestra en la sección [¿Qué es el enlace de datos?](#what_is_data_binding)  
  
 Afortunadamente, nuestro diagrama básico aún sigue siendo válido.  Si enlaza un <xref:System.Windows.Controls.ItemsControl> a una colección, el diagrama tendrá el siguiente aspecto:  
  
 ![Diagrama de ItemsControl de enlace de datos](../../../../docs/framework/wpf/data/media/databindingitemscontrol.png "DataBindingItemsControl")  
  
 Como se muestra en este diagrama, para enlazar <xref:System.Windows.Controls.ItemsControl> a un objeto de colección, la propiedad que se utiliza es <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>.  Puede considerar la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> como el contenido del <xref:System.Windows.Controls.ItemsControl>.  Observe que el enlace es <xref:System.Windows.Data.BindingMode> porque la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> admite el enlace <xref:System.Windows.Data.BindingMode> de forma predeterminada.  
  
<a name="how_to_implement_collections"></a>   
### Cómo implementar colecciones  
 Es posible enumerar cualquier colección que implementa la interfaz <xref:System.Collections.IEnumerable>.  Sin embargo, para configurar enlaces dinámicos de modo que las inserciones o eliminaciones que se realicen en la colección actualicen la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de forma automática, la colección debe implementar la interfaz <xref:System.Collections.Specialized.INotifyCollectionChanged>.  Esta interfaz expone un evento que debe provocarse siempre que se realicen cambios en la colección subyacente.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona la clase <xref:System.Collections.ObjectModel.ObservableCollection%601>, que es una implementación integrada de una recolección de datos que expone la interfaz <xref:System.Collections.Specialized.INotifyCollectionChanged>.  Observe que para permitir totalmente la transferencia de valores de datos de los objetos de origen a los destinos, cada objeto de la colección que admite propiedades enlazables debe implementar también la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>.  Para obtener más información, vea [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
 Antes de implementar su propia colección, considere la posibilidad de utilizar <xref:System.Collections.ObjectModel.ObservableCollection%601> o una de las clases de colección existentes, como <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601> y <xref:System.ComponentModel.BindingList%601>, entre otras muchas.  Si cuenta con un escenario avanzado y desea implementar su propia colección, considere la posibilidad de utilizar <xref:System.Collections.IList>, que proporciona una colección no genérica de objetos a los que se puede obtener acceso individualmente por índice y, por consiguiente, proporciona el máximo rendimiento.  
  
<a name="collection_views"></a>   
### Vistas de colección  
 Una vez que <xref:System.Windows.Controls.ItemsControl> esté enlazado a una recolección de datos, quizás desee ordenar, filtrar o agrupar los datos.  Para ello, se utilizan vistas de colección, que son clases que implementan la interfaz <xref:System.ComponentModel.ICollectionView>.  
  
   
  
<a name="what_are_collection_views"></a>   
#### ¿Qué son las vistas de colección?  
 Una vista de colección es un nivel situado encima de la colección de origen del enlace, que le permite navegar y mostrar la colección de origen en función de las consultas de ordenación, filtrado y agrupación, sin tener que cambiar la propia colección de origen subyacente.  Una vista de colección también contiene un puntero al elemento actual de la colección.  Si la colección de origen implementa la interfaz <xref:System.Collections.Specialized.INotifyCollectionChanged>, los cambios provocados por el evento <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> se propagarán a las vistas.  
  
 Dado que las vistas no cambian las colecciones de origen subyacente, cada colección de origen puede tener varias vistas asociadas.  Por ejemplo, podría tener una colección de objetos *Task*.  El uso de vistas le permite mostrar los mismos datos de formas diferentes.  Por ejemplo, en el lado izquierdo de la página es posible que desee mostrar las tareas ordenadas por prioridad y, en el lado derecho, agrupadas por área.  
  
<a name="how_to_create_a_view"></a>   
#### Cómo crear una vista  
 Una manera de crear y utilizar una vista es crear directamente una instancia del objeto de vista y utilizar a continuación esa instancia como el origen del enlace.  Por ejemplo, considere la aplicación [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703) que se muestra en la sección [¿Qué es el enlace de datos?](#what_is_data_binding) La aplicación se implementa de forma que <xref:System.Windows.Controls.ListBox> se enlaza a una vista a través de la recolección de datos en lugar de la colección de datos directamente.  El ejemplo siguiente se ha extraído de la aplicación [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703).  La clase <xref:System.Windows.Data.CollectionViewSource> es el proxy de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] de una clase que hereda de <xref:System.Windows.Data.CollectionView>.  En este ejemplo en concreto, la propiedad <xref:System.Windows.Data.CollectionViewSource.Source%2A> de la vista se enlaza a la colección *AuctionItems* \(de tipo <xref:System.Collections.ObjectModel.ObservableCollection%601>\) del objeto de aplicación actual.  
  
 [!code-xml[DataBindingLab#WindowResources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xml[DataBindingLab#CollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xml[DataBindingLab#WindowResources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 A continuación, *listingDataView* actúa como el origen del enlace para los elementos de la aplicación, como <xref:System.Windows.Controls.ListBox>:  
  
 [!code-xml[DataBindingLab#Master1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xml[DataBindingLab#Master2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 Para crear otra vista para la misma colección, puede crear otra instancia de <xref:System.Windows.Data.CollectionViewSource> y asignarle un nombre `x:Key` diferente.  
  
 En la tabla siguiente se muestra qué tipos de datos de vista se crean como vista de colección predeterminada o por <xref:System.Windows.Data.CollectionViewSource> en función del tipo de colección de origen.  
  
|Tipo de colección de origen|Tipo de vista de colección|Notas|  
|---------------------------------|--------------------------------|-----------|  
|<xref:System.Collections.IEnumerable>|Un tipo interno basado en <xref:System.Windows.Data.CollectionView>|No se pueden agrupar los elementos.|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|Más rápido.|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### Utilizar una vista predeterminada  
 Especificar una vista de colección como origen de enlace es una forma de crear y utilizar una vista de colección.  WPF también crea una vista de colección predeterminada para cada colección utilizada como origen de enlace.  Si enlaza directamente a una colección, WPF enlaza a su vista predeterminada.  Tenga en cuenta que todos los enlaces a una misma colección comparten esta vista predeterminada, de modo que si se realiza un cambio en una vista predeterminada a través de un control enlazado o mediante código \(como un cambio de ordenación o en el puntero de elemento actual, que se describe más adelante\), éste se refleja en el resto de los enlaces a la misma colección.  
  
 Para obtener la vista predeterminada, se utiliza el método <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A>.  Para obtener un ejemplo, vea [Obtener la vista predeterminada de una recolección de datos](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).  
  
##### Vistas de colección con tablas de datos de ADO.NET  
 Para mejorar el rendimiento, las vistas de colección para objetos <xref:System.Data.DataTable> o <xref:System.Data.DataView> de ADO.NET delegan la ordenación y el filtrado a <xref:System.Data.DataView>.  Esto hace que todas las vistas de colección del origen de datos compartan la ordenación y el filtrado.  Para habilitar la ordenación y el filtrado independientes de cada vista de colección, inicialice cada vista de este tipo con su propio objeto <xref:System.Data.DataView>.  
  
<a name="sorting"></a>   
#### Ordenar  
 Como se mencionó anteriormente, las vistas pueden aplicar un criterio de ordenación a una colección.  Cuando este criterio existe en la colección subyacente, los datos pueden o no tener un orden relevante inherente.  La vista de la colección le permite aplicar un orden o cambiar el orden predeterminado, en función de los criterios de comparación especificados.  Como es una vista de datos basada en un cliente, podría ser habitual que el usuario quisiera ordenar las columnas de los datos de tabla por el valor correspondiente a la columna.  Con las vistas, se puede aplicar esta ordenación controlada por el usuario, sin tener que realizar ningún cambio en la colección subyacente ni tener tampoco que volver a consultar el contenido de la colección.  Para obtener un ejemplo, vea [Ordenar una columna de GridView cuando se hace clic en un encabezado](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).  
  
 En el siguiente ejemplo se muestra la lógica de ordenación del control <xref:System.Windows.Controls.CheckBox> "Sort by category and date" de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de aplicación de la sección [¿Qué es el enlace de datos?](#what_is_data_binding):  
  
 [!code-csharp[DataBindingLab#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
<a name="filtering"></a>   
#### Filtrar  
 Las vistas pueden aplicar también un filtro a una colección.  Esto significa que aunque un elemento pueda existir en la colección, esta vista en concreto está destinada a mostrar únicamente determinado subconjunto de la colección completa.  Podría filtrar los datos en función de una condición.  Por ejemplo, como ocurre en la aplicación de la sección [¿Qué es el enlace de datos?](#what_is_data_binding), el control <xref:System.Windows.Controls.CheckBox> "Show only bargains" contiene lógica para filtrar los artículos con un costo de 25 dólares o más.  El código siguiente se ejecuta para establecer *ShowOnlyBargainsFilter* como el controlador de eventos <xref:System.Windows.Data.CollectionViewSource.Filter> cuando se selecciona <xref:System.Windows.Controls.CheckBox>:  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 El controlador de eventos *ShowOnlyBargainsFilter* se implementa del modo siguiente:  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 Si utiliza directamente alguna de las clases <xref:System.Windows.Data.CollectionView> en lugar de <xref:System.Windows.Data.CollectionViewSource>, deberá usar la propiedad <xref:System.Windows.Data.CollectionView.Filter%2A> para especificar una devolución de llamada.  Para obtener un ejemplo, vea [Filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).  
  
<a name="grouping"></a>   
#### Grupo  
 Salvo la clase interna que ve una colección <xref:System.Collections.IEnumerable>, todas las vistas de colección admiten la funcionalidad de agrupación, que permite al usuario dividir la colección en la vista de colección en grupos lógicos.  Los grupos pueden ser explícitos, donde el usuario proporciona una lista de grupos, o implícitos, donde los grupos se generan dinámicamente en función de los datos.  
  
 En e ejemplo siguiente se muestra la lógica del control <xref:System.Windows.Controls.CheckBox> "Group by category":  
  
 [!code-csharp[DataBindingLab#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#6)]
 [!code-vb[DataBindingLab#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#6)]  
  
 Para obtener otro ejemplo de agrupación, vea [Agrupar elementos en un control ListView que implementa un modo GridView](../../../../docs/framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md).  
  
<a name="current_record_pointers"></a>   
#### Punteros de elemento actual  
 Las vistas admiten también la noción de elemento actual.  Puede navegar por los objetos en una vista de colección.  A medida que navega por los objetos, mueve un puntero de elemento que le permite recuperar el objeto ubicado concretamente en esa posición en la colección.  Para obtener un ejemplo, vea [Navegar por los objetos de una colección de datos mediante CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
 Dado que WPF sólo se enlaza a una colección mediante una vista \(una vista especificada por el usuario o la vista predeterminada de la colección\), todos los enlaces a las colecciones tienen un puntero de elemento actual.  Al enlazar a una vista, el carácter de barra diagonal \("\/"\) de un valor `Path` designa el elemento actual de la vista.  En el ejemplo siguiente, el contexto de datos es una vista de colección.  La primera línea enlaza a la colección.  La segunda línea enlaza al elemento actual de la colección.  La tercera línea enlaza a la propiedad `Description` del elemento actual de la colección.  
  
```xaml  
<Button Content="{Binding }" />  
<Button Content="{Binding Path=/}" />  
<Button Content="{Binding Path=/Description}" />   
```  
  
 La sintaxis de barra diagonal y propiedad también puede apilarse para recorrer una jerarquía de colecciones.  En el ejemplo siguiente se enlaza al elemento actual de una colección denominada `Offices`, que es una propiedad del elemento actual de la colección de origen.  
  
```xaml  
<Button Content="{Binding /Offices/}" />  
```  
  
 Toda ordenación o filtrado que se aplique a la colección puede afectar al puntero del elemento actual.  La ordenación conserva el puntero del elemento actual en el último elemento seleccionado, pero se reestructura la vista de colección a su alrededor.  \(Quizás el elemento seleccionado estaba antes al principio de la lista, pero ahora puede que esté en alguna parte del medio\). El filtrado conserva el elemento seleccionado si la selección permanece en la vista después del filtrado.  De lo contrario, el puntero del elemento actual se establece en el primer elemento de la vista de colección filtrada.  
  
<a name="master_detail_scenario"></a>   
#### Escenario de enlace principal\-detalle  
 La noción de elemento actual no es sólo útil para la navegación de elementos en una colección, sino también para el escenario de enlace principal\-detalle.  Considere de nuevo la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de aplicación de la sección [¿Qué es el enlace de datos?](#what_is_data_binding) En esa aplicación, la selección dentro de <xref:System.Windows.Controls.ListBox>determina el contenido mostrado en <xref:System.Windows.Controls.ContentControl>.  O dicho de otra forma, cuando se selecciona un elemento <xref:System.Windows.Controls.ListBox>, el control <xref:System.Windows.Controls.ContentControl> muestra los detalles del elemento seleccionado.  
  
 Puede implementar el escenario principal\-detalle simplemente con dos o más controles enlazados a la misma vista.  El ejemplo siguiente de [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703) muestra el marcado de los controles <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ContentControl> que ve en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de aplicación de la sección [¿Qué es el enlace de datos?](#what_is_data_binding):  
  
 [!code-xml[DataBindingLab#Master1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xml[DataBindingLab#Master2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xml[DataBindingLab#Detail](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 Observe que ambos controles están enlazados al mismo origen, el recurso estático *listingDataView* \(vea la definición de este recurso en la sección [Cómo crear una vista](#how_to_create_a_view)\).  Esto funciona porque cuando un objeto singleton \(el control <xref:System.Windows.Controls.ContentControl> en este caso\) está enlazado a una vista de colección, se enlaza automáticamente a la propiedad <xref:System.Windows.Data.CollectionView.CurrentItem%2A> de la vista.  Observe que los objetos <xref:System.Windows.Data.CollectionViewSource> sincronizan automáticamente la moneda y la selección.  Si el control de lista no está enlazado a un objeto <xref:System.Windows.Data.CollectionViewSource> como en este ejemplo, tendrá que establecer su propiedad <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> en `true` para que funcione.  
  
 Para obtener otros ejemplos, vea [Enlazar a una colección y mostrar información basada en la selección](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) y [Usar el patrón principal\-detalle con datos jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  
  
 Tal vez haya observado que en el ejemplo anterior se utiliza una plantilla.  De hecho, los datos no se mostrarían de la forma deseada sin el uso de plantillas \(la utilizada explícitamente por el control <xref:System.Windows.Controls.ContentControl> y la utilizada implícitamente por el control <xref:System.Windows.Controls.ListBox>\).  Trataremos el tema de la inclusión de datos en plantillas en la siguiente sección.  
  
<a name="data_templating"></a>   
## Inclusión de datos en plantillas  
 Sin el uso de plantillas de datos, nuestra [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de aplicación de la sección [¿Qué es el enlace de datos?](#what_is_data_binding) tendría el aspecto siguiente:  
  
 ![Demo de enlace de datos sin plantillas de datos](../../../../docs/framework/wpf/data/media/databindingdemotemplates.png "DataBindingDemoTemplates")  
  
 Como se muestra en el ejemplo de la sección anterior, tanto el control <xref:System.Windows.Controls.ListBox> como <xref:System.Windows.Controls.ContentControl> están enlazados a todo el objeto de colección \(o más concretamente, la vista sobre el objeto de colección\) de *AuctionItems*.  Sin instrucciones específicas de cómo mostrar la recolección de datos, el control <xref:System.Windows.Controls.ListBox> muestra una representación de cadena de cada objeto de la colección subyacente y el control <xref:System.Windows.Controls.ContentControl> muestra una representación de cadena del objeto al que está enlazado.  
  
 Para resolver ese problema, la aplicación define objetos <xref:System.Windows.DataTemplate>.  Como se muestra en el ejemplo de la sección anterior, <xref:System.Windows.Controls.ContentControl> usa explícitamente el <xref:System.Windows.DataTemplate> *detailsProductListingTemplate*.  El control <xref:System.Windows.Controls.ListBox> utiliza implícitamente el objeto <xref:System.Windows.DataTemplate> siguiente al mostrar los objetos *AuctionItem* en la colección:  
  
 [!code-xml[DataBindingLab#AuctionItemDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 Con el uso de estos dos objetos <xref:System.Windows.DataTemplate>, la interfaz de usuario resultante es la que se muestra en la sección [¿Qué es el enlace de datos?](#what_is_data_binding) Como puede ver en esa captura de pantalla, además de permitir colocar los datos en los controles, los objetos <xref:System.Windows.DataTemplate> le permiten definir un aspecto atractivo para sus datos.  Por ejemplo, se utilizan objetos <xref:System.Windows.DataTrigger> en el objeto <xref:System.Windows.DataTemplate> anterior para que los elementos *AuctionItem* con el valor *SpecialFeatures* de *HighLight* se muestren con un borde naranja y una estrella.  
  
 Para obtener más información sobre las plantillas de datos, vea [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
<a name="data_validation"></a>   
## Validación de datos  
   
  
 La mayoría de las aplicaciones que toman datos proporcionados por el usuario requieren lógica de validación para asegurarse de que el usuario ha escrito la información esperada.  Las comprobaciones de validación pueden basarse en el tipo, intervalo, formato u otros requisitos específicos de la aplicación.  En esta sección se describe cómo funciona la validación de datos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="validation_rules"></a>   
### Asociar reglas de validación a un enlace  
 El modelo de enlace de datos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite asociar <xref:System.Windows.Data.Binding.ValidationRules%2A> al objeto <xref:System.Windows.Data.Binding>.  Por ejemplo, en el ejemplo siguiente se enlaza un control <xref:System.Windows.Controls.TextBox> a una propiedad denominada `StartPrice` y se agrega un objeto <xref:System.Windows.Controls.ExceptionValidationRule> a la propiedad <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=fullName>.  
  
 [!code-xml[DataBindingLab#DefaultValidation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 Un objeto <xref:System.Windows.Controls.ValidationRule> comprueba si el valor de una propiedad es válido.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene los dos tipos siguientes de objetos <xref:System.Windows.Controls.ValidationRule> integrados:  
  
-   <xref:System.Windows.Controls.ExceptionValidationRule> comprueba las excepciones producidas durante la actualización de la propiedad de origen de enlace.  En el ejemplo anterior, `StartPrice` es de tipo entero.  Cuando el usuario especifica un valor que no se puede convertir en un entero, se produce una excepción, lo que ocasiona que el enlace se marque como no válido.  Una sintaxis alternativa para establecer explícitamente <xref:System.Windows.Controls.ExceptionValidationRule> es establecer la propiedad <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> en `true` en el objeto <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.MultiBinding>.  
  
-   Un objeto <xref:System.Windows.Controls.DataErrorValidationRule> comprueba los errores producidos por objetos que implementan la interfaz <xref:System.ComponentModel.IDataErrorInfo>.  Para obtener un ejemplo del uso de esta regla de validación, vea <xref:System.Windows.Controls.DataErrorValidationRule>.  Una sintaxis alternativa para establecer explícitamente <xref:System.Windows.Controls.DataErrorValidationRule> es establecer la propiedad <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> en `true` en el objeto <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.MultiBinding>.  
  
 Puede crear también su propia regla de validación derivando de la clase <xref:System.Windows.Controls.ValidationRule> e implementando el método <xref:System.Windows.Controls.ValidationRule.Validate%2A>.  En el ejemplo siguiente se muestra la regla utilizada por el control <xref:System.Windows.Controls.TextBox> *Add Product Listing* "Start Date" de la sección [¿Qué es un enlace de datos?](#what_is_data_binding):  
  
 [!code-csharp[DataBindingLab#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox>utiliza *FutureDateRule*, como se muestra en el ejemplo siguiente:  
  
 [!code-xml[DataBindingLab#CustomValidation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 Observe que como el valor de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> es <xref:System.Windows.Data.UpdateSourceTrigger>, el motor de enlace actualiza el valor de origen cada vez que se pulsa una tecla, lo que significa que también comprueba cada regla de la colección <xref:System.Windows.Data.Binding.ValidationRules%2A> cada vez que se pulsa una tecla.  Ofreceremos una descripción más detallada en la sección Proceso de validación.  
  
<a name="invalidation_feedback"></a>   
### Proporcionar comentarios visuales  
 Si el usuario especifica un valor no válido, quizás desee proporcionar algunos comentarios sobre el error en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación.  Una manera de proporcionar esos comentarios es establecer la propiedad adjunta <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=fullName> en un objeto <xref:System.Windows.Controls.ControlTemplate> personalizado.  Como se muestra en el subapartado anterior, el control <xref:System.Windows.Controls.TextBox> *StartDateEntryForm* utiliza una propiedad <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> denominada *validationTemplate*.  En el ejemplo siguiente se muestra la definición de *validationTemplate*:  
  
 [!code-xml[DataBindingLab#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 El elemento <xref:System.Windows.Controls.AdornedElementPlaceholder> especifica dónde se debe colocar el control que se va a adornar.  
  
 Asimismo, podría utilizar un objeto <xref:System.Windows.Controls.ToolTip> para mostrar el mensaje de error.  Los controles <xref:System.Windows.Controls.TextBox> *StartDateEntryForm* y *StartPriceEntryForm* utilizan el estilo *textStyleTextBox*, que crea un objeto <xref:System.Windows.Controls.ToolTip> que muestra el mensaje de error.  En el ejemplo siguiente se muestra la definición de *textStyleTextBox*.  La [propiedad adjunta](GTMT) <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true` cuando uno o varios de los enlaces de las propiedades del elemento enlazado producen un error.  
  
 [!code-xml[DataBindingLab#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 Con la propiedad <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> personalizada y el objeto <xref:System.Windows.Controls.ToolTip>, el control <xref:System.Windows.Controls.TextBox> *StartDateEntryForm* adopta el siguiente aspecto cuando se produce un error de validación:  
  
 ![Error de validación de enlace de datos](../../../../docs/framework/wpf/data/media/databindingdemo-validation.png "DataBindingDemo\_Validation")  
  
 Si el objeto <xref:System.Windows.Data.Binding> tiene reglas de validación asociadas, pero no especifica <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> en el control enlazado, se utilizará una propiedad <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> predeterminada para informar a los usuarios de que se ha producido un error de validación.  La propiedad <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> predeterminada es una plantilla de control que define un borde rojo en la capa de adorno.  Con la propiedad <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> predeterminada y el objeto <xref:System.Windows.Controls.ToolTip>, la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del control <xref:System.Windows.Controls.TextBox> *StartPriceEntryForm* adopta el siguiente aspecto cuando se produce un error de validación:  
  
 ![Error de validación de enlace de datos](../../../../docs/framework/wpf/data/media/databindingdemo-validationdefault.png "DataBindingDemo\_ValidationDefault")  
  
 Para ver un ejemplo sobre cómo proporcionar lógica para validar todos los controles de un cuadro de diálogo, vea la sección Cuadros de diálogo personalizados en [Información general sobre cuadros de diálogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
<a name="validation_process"></a>   
### Proceso de validación  
 La validación normalmente se produce cuando el valor de un destino se transfiere a la propiedad de origen del enlace.  Esto se produce en los enlaces <xref:System.Windows.Data.BindingMode> y <xref:System.Windows.Data.BindingMode>.  Como ya se ha comentado, lo que causa una actualización del origen depende del valor de la propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>, como se describe en la sección [Qué desencadena la actualización del origen](#what_triggers_source_updates).  
  
 A continuación, se describe el proceso de *validación*:  Tenga en cuenta que si se produce un error de validación o de cualquier otro tipo en cualquier momento del proceso, éste se detiene.  
  
1.  El motor de enlace comprueba si se ha definido algún objeto <xref:System.Windows.Controls.ValidationRule> cuya propiedad <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> se haya establecido en <xref:System.Windows.Controls.ValidationStep> para dicho objeto <xref:System.Windows.Data.Binding>, en cuyo caso llama al método <xref:System.Windows.Controls.ValidationRule.Validate%2A> en cada <xref:System.Windows.Controls.ValidationRule> hasta que una de las reglas de validación detecte un error o hasta que se cumplan todas las reglas de validación.  
  
2.  A continuación, el motor de enlace llama al convertidor, si existe alguno.  
  
3.  Si el convertidor funciona correctamente, el motor de enlace comprueba si se ha definido algún objeto <xref:System.Windows.Controls.ValidationRule> cuya propiedad <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> se haya establecido en <xref:System.Windows.Controls.ValidationStep> para dicho objeto <xref:System.Windows.Data.Binding>, en cuyo caso llama al método <xref:System.Windows.Controls.ValidationRule.Validate%2A> en cada <xref:System.Windows.Controls.ValidationRule> que tenga la propiedad <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecida en <xref:System.Windows.Controls.ValidationStep> hasta que una de las reglas de validación detecte un error o hasta que se cumplan todas las reglas de validación.  
  
4.  El motor de enlace establece la propiedad de origen.  
  
5.  El motor de enlace comprueba si se ha definido algún objeto <xref:System.Windows.Controls.ValidationRule> personalizado cuya propiedad <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> se haya establecido en <xref:System.Windows.Controls.ValidationStep> para dicho objeto <xref:System.Windows.Data.Binding>, en cuyo caso llama al método <xref:System.Windows.Controls.ValidationRule.Validate%2A> en cada <xref:System.Windows.Controls.ValidationRule> que tenga la propiedad <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecida en <xref:System.Windows.Controls.ValidationStep> hasta que una de las reglas de validación detecte un error o hasta que se cumplan todas las reglas de validación.  Si un objeto <xref:System.Windows.Controls.DataErrorValidationRule> está asociado a un enlace y su propiedad <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> está establecida en el valor predeterminado, <xref:System.Windows.Controls.ValidationStep>, en este momento se comprueba <xref:System.Windows.Controls.DataErrorValidationRule>.  Este también es el momento en que se comprueban los enlaces que tienen la propiedad <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> establecida en `true`.  
  
6.  El motor de enlace comprueba si se ha definido algún objeto <xref:System.Windows.Controls.ValidationRule> personalizado cuya propiedad <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> se haya establecido en <xref:System.Windows.Controls.ValidationStep> para dicho objeto <xref:System.Windows.Data.Binding>, en cuyo caso llama al método <xref:System.Windows.Controls.ValidationRule.Validate%2A> en cada <xref:System.Windows.Controls.ValidationRule> que tenga la propiedad <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecida en <xref:System.Windows.Controls.ValidationStep> hasta que una de las reglas de validación detecte un error o hasta que se cumplan todas las reglas de validación.  
  
 Si un objeto <xref:System.Windows.Controls.ValidationRule> no pasa en ningún momento por este proceso, el motor de enlace crea un objeto <xref:System.Windows.Controls.ValidationError> y lo agrega a la colección <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> del elemento enlazado.  Antes de que el motor de enlace ejecute los objetos <xref:System.Windows.Controls.ValidationRule> en un paso determinado, éste quita cualquier objeto <xref:System.Windows.Controls.ValidationError> que se haya agregado a la [propiedad adjunta](GTMT) <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> del elemento enlazado durante dicho paso.  Por ejemplo, si se produce un error de un objeto <xref:System.Windows.Controls.ValidationRule> cuya propiedad <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> se ha establecido en <xref:System.Windows.Controls.ValidationStep>, la próxima vez que se realice el proceso de validación, el motor de enlace quitará dicho objeto <xref:System.Windows.Controls.ValidationError> inmediatamente antes de llamar a cualquier objeto <xref:System.Windows.Controls.ValidationRule> que tenga la propiedad <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> establecida en <xref:System.Windows.Controls.ValidationStep>.  
  
 Cuando la propiedad <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> no está vacía, la [propiedad adjunta](GTMT) <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> del elemento se establece en `true`.  Además, si la propiedad <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> de <xref:System.Windows.Data.Binding> se establece en `true`, el motor de enlace provoca el [evento adjunto](GTMT) <xref:System.Windows.Controls.Validation.Error?displayProperty=fullName> en el elemento.  
  
 Asimismo, observe que una transferencia de valor válida en cualquiera de las dos direcciones \(del destino al origen o del origen al destino\) borra la [propiedad adjunta](GTMT) <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName>.  
  
 Si el enlace tiene un objeto <xref:System.Windows.Controls.ExceptionValidationRule> asociado, o tiene la propiedad <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> establecida en `true`, y se produce una excepción cuando el motor de enlace establece el origen, dicho motor comprueba si hay una propiedad <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>.  Puede usar la devolución de llamada de <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> para proporcionar un controlador personalizado que controle las excepciones.  Si no se especifica una propiedad <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> en el objeto <xref:System.Windows.Data.Binding>, el motor de enlaces crea un objeto <xref:System.Windows.Controls.ValidationError> con la excepción y lo agrega a la colección <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> del elemento enlazado.  
  
<a name="debugging_mechanism"></a>   
## Mecanismo de depuración  
 Puede establecer la propiedad adjunta <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=fullName> en un objeto relacionado con el enlace para recibir información sobre el estado de un enlace específico.  
  
## Vea también  
 <xref:System.Windows.Controls.DataErrorValidationRule>   
 [Novedades de WPF versión 4.5](../../../../docs/framework/wpf/getting-started/whats-new.md)   
 [Enlazar a los resultados de una consulta LINQ](../../../../docs/framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Enlazar a un origen de datos ADO.NET](../../../../docs/framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)