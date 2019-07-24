---
title: Información general sobre plantillas de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], templates
- binding data [WPF], templates
- templates [WPF], data
- data templates [WPF]
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
ms.openlocfilehash: 556ce7b42f13d7c5ba7fba36b09277cda9bcae5d
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400660"
---
# <a name="data-templating-overview"></a>Información general sobre plantillas de datos
El modelo de plantillas de datos de WPF ofrece gran flexibilidad para definir la presentación de los datos. Los controles WPF tienen funcionalidad integrada que admite la personalización de la presentación de los datos. En este tema se muestra primero cómo definir <xref:System.Windows.DataTemplate> un y, a continuación, se introducen otras características de plantillas de datos, como la selección de plantillas basadas en la lógica personalizada y la compatibilidad para la presentación de datos jerárquicos.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Este tema se centra en las características de creación de plantillas de datos y no es una introducción a los conceptos de enlace de datos. Para información sobre los conceptos básicos de enlace de datos, vea the [Información general sobre el enlace de datos](data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate>se refiere a la presentación de datos y es una de las numerosas características proporcionadas por el modelo de estilos y plantillas de WPF. Para obtener una introducción al modelo de estilos y plantillas de WPF, como el uso <xref:System.Windows.Style> de para establecer propiedades en controles, vea el tema [aplicar estilos y plantillas](../controls/styling-and-templating.md) .  
  
 Además, es importante comprender `Resources`, que son esencialmente lo que permite que se puedan reutilizar objetos <xref:System.Windows.DataTemplate> <xref:System.Windows.Style> como y. Para más información sobre los recursos, vea [Recursos XAML](../advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Conceptos básicos de plantillas de datos  
  
 Para demostrar por <xref:System.Windows.DataTemplate> qué es importante, veamos un ejemplo de enlace de datos. En este ejemplo, tenemos un <xref:System.Windows.Controls.ListBox> que está enlazado a una lista de `Task` objetos. Cada objeto `Task` tiene un `TaskName` (cadena), un `Description` (cadena), un `Priority` (int) y una propiedad de tipo `TaskType`, que es un `Enum` con valores `Home` y `Work`.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Sin un DataTemplate  
 Sin un <xref:System.Windows.DataTemplate>, nuestro <xref:System.Windows.Controls.ListBox> tiene actualmente el siguiente aspecto:  
  
 ![Captura de pantalla de ejemplo de plantillas de datos](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Lo que sucede es que sin instrucciones específicas, <xref:System.Windows.Controls.ListBox> llama `ToString` a de forma predeterminada al intentar mostrar los objetos de la colección. Por consiguiente, si `Task` el objeto invalida el `ToString` método, <xref:System.Windows.Controls.ListBox> muestra la representación de cadena de cada objeto de origen en la colección subyacente.  
  
 Por ejemplo, si la clase `Task` invalida el método `ToString` de esta manera, donde `name` es el campo para la propiedad `TaskName`:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 A continuación <xref:System.Windows.Controls.ListBox> , el tiene el aspecto siguiente:  
  
 ![Captura de pantalla de ejemplo de plantillas de datos](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Pero eso resulta limitante e inflexible. Además, si enlaza a datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], no podrá invalidar `ToString`.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Definir un DataTemplate simple  
 La solución consiste en definir un <xref:System.Windows.DataTemplate>. Una forma de hacerlo consiste en establecer la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad <xref:System.Windows.Controls.ListBox> de en <xref:System.Windows.DataTemplate>. Lo que especifique en el <xref:System.Windows.DataTemplate> se convierte en la estructura visual del objeto de datos. Lo siguiente <xref:System.Windows.DataTemplate> es bastante sencillo. Estamos ofreciendo instrucciones que indican que cada elemento aparece como <xref:System.Windows.Controls.TextBlock> tres elementos dentro <xref:System.Windows.Controls.StackPanel>de. Cada <xref:System.Windows.Controls.TextBlock> elemento se enlaza a una propiedad de la `Task` clase.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 Los datos subyacentes de los ejemplos de este tema son una colección de objetos CLR. Si enlaza a datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], los conceptos fundamentales son los mismos, pero existe una ligera diferencia sintáctica. Por ejemplo, en lugar de tener `Path=TaskName`, establecería <xref:System.Windows.Data.Binding.XPath%2A> en `@TaskName` (si `TaskName` es un atributo del [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] nodo).  
  
 Ahora nuestro <xref:System.Windows.Controls.ListBox> es similar al siguiente:  
  
 ![Captura de pantalla de ejemplo de plantillas de datos](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Crear el DataTemplate como recurso  
 En el ejemplo anterior, hemos definido la <xref:System.Windows.DataTemplate> línea. Es más frecuente definirlo en la sección de recursos para que pueda ser un objeto reutilizable, como en el ejemplo siguiente:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Ahora puede usar `myTaskTemplate` como recurso, como en el ejemplo siguiente:  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Dado `myTaskTemplate` que es un recurso, ahora puede usarlo en otros controles que tienen una propiedad que toma un <xref:System.Windows.DataTemplate> tipo. Como se mostró anteriormente, <xref:System.Windows.Controls.ItemsControl> para los objetos, <xref:System.Windows.Controls.ListBox>como, es la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad. En <xref:System.Windows.Controls.ContentControl> el caso de los objetos <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> , es la propiedad.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>La propiedad DataType  
 La <xref:System.Windows.DataTemplate> clase tiene una <xref:System.Windows.DataTemplate.DataType%2A> propiedad que es muy similar a la <xref:System.Windows.Style.TargetType%2A> propiedad de la <xref:System.Windows.Style> clase. Por lo tanto, en lugar de especificar `x:Key` un <xref:System.Windows.DataTemplate> para en el ejemplo anterior, puede hacer lo siguiente:  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Esto <xref:System.Windows.DataTemplate> se aplica automáticamente a todos `Task` los objetos. Tenga en cuenta que en este caso el `x:Key` se establece implícitamente. Por lo tanto, si asigna <xref:System.Windows.DataTemplate> este `x:Key` valor, <xref:System.Windows.DataTemplate> invalidará el implícito `x:Key` y no se aplicará automáticamente.  
  
 Si enlaza un <xref:System.Windows.Controls.ContentControl> a una colección de `Task` objetos, el <xref:System.Windows.Controls.ContentControl> no utiliza automáticamente el anterior <xref:System.Windows.DataTemplate> . Esto se debe a que el enlace <xref:System.Windows.Controls.ContentControl> en un necesita más información para distinguir si desea enlazar a una colección completa o a los objetos individuales. `/` <xref:System.Windows.Controls.ContentControl> <xref:System.Windows.Data.Binding.Path%2A> <xref:System.Windows.Controls.ItemsControl> Si está realizando el seguimiento de la selección de un tipo, puede establecer la propiedad del enlace en "" para indicar que está interesado en el elemento actual. <xref:System.Windows.Controls.ContentControl> Para obtener un ejemplo, vea [Bind to a Collection and Display Information Based on Selection](how-to-bind-to-a-collection-and-display-information-based-on-selection.md) (Cómo: Enlazar a una colección y mostrar información basada en la selección). De lo contrario, debe especificar <xref:System.Windows.DataTemplate> explícitamente estableciendo la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad.  
  
 La <xref:System.Windows.DataTemplate.DataType%2A> propiedad es especialmente útil cuando se tiene un <xref:System.Windows.Data.CompositeCollection> de distintos tipos de objetos de datos. Para obtener un ejemplo, vea [Implement a CompositeCollection](how-to-implement-a-compositecollection.md) (Cómo: Implementar una CompositeCollection).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Agregar más elementos al DataTemplate  
 Actualmente los datos aparecen con la información necesaria, pero sin duda hay margen de mejora. Vamos a mejorar la presentación agregando <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.Grid>, y algunos <xref:System.Windows.Controls.TextBlock> elementos que describen los datos que se muestran.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 En la captura de pantalla <xref:System.Windows.Controls.ListBox> siguiente se muestra <xref:System.Windows.DataTemplate>el con este modificado:  
  
 ![Captura de pantalla de ejemplo de plantillas de datos](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 Podemos establecer <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.HorizontalAlignment.Stretch> en en<xref:System.Windows.Controls.ListBox> para asegurarse de que el ancho de los elementos ocupa todo el espacio:  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Con la <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> propiedad establecida en <xref:System.Windows.HorizontalAlignment.Stretch>, ahora <xref:System.Windows.Controls.ListBox> tiene el siguiente aspecto:  
  
 ![Captura de pantalla de ejemplo de plantillas de datos](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Usar DataTriggers para aplicar valores de propiedad  
 La presentación actual no nos indica si una `Task` es una tarea doméstica o una tarea de oficina. Recuerde que el objeto `Task` tiene una propiedad `TaskType` de tipo `TaskType`, que es una enumeración con valores `Home` y `Work`.  
  
 En <xref:System.Windows.DataTrigger> el ejemplo siguiente, establece el <xref:System.Windows.Controls.Border.BorderBrush%2A> del elemento denominado `border` en `Yellow` si la `TaskType` propiedad es `TaskType.Home`.  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Nuestra aplicación tiene ahora el aspecto siguiente. Las tareas domésticas aparecen con un borde amarillo y las tareas de oficina, con un borde aguamarina:  
  
 ![Captura de pantalla de ejemplo de plantillas de datos](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 En este ejemplo <xref:System.Windows.DataTrigger> , utiliza un <xref:System.Windows.Setter> para establecer un valor de propiedad. Las clases de desencadenador también <xref:System.Windows.TriggerBase.EnterActions%2A> tienen <xref:System.Windows.TriggerBase.ExitActions%2A> las propiedades y que permiten iniciar un conjunto de acciones como animaciones. Además, también hay una <xref:System.Windows.MultiDataTrigger> clase que permite aplicar cambios basados en varios valores de propiedad enlazados a datos.  
  
 Una manera alternativa de lograr el mismo efecto es enlazar la <xref:System.Windows.Controls.Border.BorderBrush%2A> propiedad a la `TaskType` propiedad y usar un convertidor de valores para devolver el color basado en `TaskType` el valor. La creación del efecto anterior mediante un convertidor es ligeramente más eficiente en términos de rendimiento. Además, la creación de su propio convertidor le brinda mayor flexibilidad porque usted proporciona su propia lógica. En última instancia, la técnica que elija depende de su escenario y de sus preferencias. Para obtener información acerca de cómo escribir un convertidor, <xref:System.Windows.Data.IValueConverter>vea.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Lo que corresponde a un DataTemplate  

En el ejemplo anterior, colocamos el desencadenador <xref:System.Windows.DataTemplate> dentro de <xref:System.Windows.DataTemplate>mediante.<xref:System.Windows.DataTemplate.Triggers%2A> propiedad. El <xref:System.Windows.Setter> del desencadenador establece el valor de una propiedad de un elemento (el <xref:System.Windows.Controls.Border> elemento <xref:System.Windows.DataTemplate>) que se encuentra dentro de. Sin embargo, si las propiedades de `Setters` las que se preocupa no son propiedades de los elementos que están dentro <xref:System.Windows.DataTemplate>de la actual, puede ser más adecuado establecer las propiedades mediante <xref:System.Windows.Style> un que es para <xref:System.Windows.Controls.ListBoxItem> la clase (si el el control que se va a <xref:System.Windows.Controls.ListBox>enlazar es un). Por ejemplo, si desea <xref:System.Windows.Trigger> que anime el <xref:System.Windows.UIElement.Opacity%2A> valor del elemento cuando un mouse señale a un elemento, defina desencadenadores dentro de un <xref:System.Windows.Controls.ListBoxItem> estilo. Para obtener un ejemplo, vea [Introducción a la aplicación de estilos y plantillas de ejemplo](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).
  
 En general, tenga en cuenta que <xref:System.Windows.DataTemplate> se aplica a cada uno de los generados <xref:System.Windows.Controls.ListBoxItem> (para obtener más información sobre cómo y dónde se aplica realmente, vea la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> página). Su <xref:System.Windows.DataTemplate> le preocupa solo la presentación y el aspecto de los objetos de datos. En la mayoría de los casos, todos los demás aspectos de la presentación, como el aspecto de un elemento cuando se selecciona <xref:System.Windows.Controls.ListBox> o el modo en que el coloca los elementos, no pertenecen a <xref:System.Windows.DataTemplate>la definición de. Para obtener un ejemplo, vea la sección [Aplicar estilos y plantillas con un ItemsControl](#DataTemplating_ItemsControl).  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Elegir un DataTemplate en función de las propiedades del objeto de datos  
 En la sección [La propiedad DataType](#Styling_DataType), explicamos que se pueden definir distintas plantillas de datos para objetos de datos diferentes. Esto es especialmente útil cuando se tiene un <xref:System.Windows.Data.CompositeCollection> de distintos tipos o colecciones con elementos de tipos diferentes. En la sección usar desencadenadores de datos [para aplicar valores de propiedad](#DataTrigger_to_Apply_Property_Values) , hemos mostrado que si tiene una colección del mismo tipo de objetos de datos, puede crear <xref:System.Windows.DataTemplate> y, a continuación, utilizar desencadenadores para aplicar los cambios en función de los valores de propiedad de cada objeto de datos. Aunque los desencadenadores le permiten aplicar valores de propiedad o iniciar animaciones, no le ofrecen la flexibilidad de reconstruir la estructura de los objetos de datos. En algunos escenarios, es posible que sea necesario <xref:System.Windows.DataTemplate> crear un diferente para los objetos de datos que son del mismo tipo pero que tienen propiedades diferentes.  
  
 Por ejemplo, puede que cuando un objeto `Task` tenga un valor `Priority` de `1` quiera darle un aspecto completamente distinto para que actúe como alerta para usted mismo. En ese caso, se crea un <xref:System.Windows.DataTemplate> para la presentación de los objetos de alta `Task` prioridad. Vamos a agregar lo siguiente <xref:System.Windows.DataTemplate> a la sección de recursos:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Observe que en este ejemplo <xref:System.Windows.DataTemplate>se usa el.<xref:System.Windows.FrameworkTemplate.Resources%2A> propiedad. Los recursos definidos en esa sección son compartidos por los <xref:System.Windows.DataTemplate>elementos de.  
  
 Para <xref:System.Windows.DataTemplate> proporcionar la `Priority` lógica que se va a usar en función del valor del objeto de datos, cree una subclase <xref:System.Windows.Controls.DataTemplateSelector> de e invalide el <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> método. En el ejemplo siguiente, el <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> método proporciona la lógica para devolver la plantilla adecuada en función del valor de `Priority` la propiedad. La plantilla que se va a devolver se encuentra en los recursos del <xref:System.Windows.Window> elemento de envoltura.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 Podemos declarar el `TaskListDataTemplateSelector` como recurso:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Para usar el recurso <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> <xref:System.Windows.Controls.ListBox>de selector de plantilla, asígnelo a la propiedad de. Llama al <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> método de`TaskListDataTemplateSelector` para cada uno de los elementos de la colección subyacente. <xref:System.Windows.Controls.ListBox> La llamada pasa el objeto de datos como parámetro del elemento. El <xref:System.Windows.DataTemplate> devuelto por el método se aplica a ese objeto de datos.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 Con el selector de plantillas en su lugar <xref:System.Windows.Controls.ListBox> , ahora aparece de la siguiente manera:  
  
 ![Captura de pantalla de ejemplo de plantillas de datos](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

Con esto concluye la explicación de este ejemplo. Para obtener el ejemplo completo, vea [Introducción a la aplicación de plantillas de ejemplo](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Aplicar estilos y plantillas con un ItemsControl  
 Aunque no <xref:System.Windows.DataTemplate> <xref:System.Windows.Controls.ItemsControl> es el único tipo de control con el que se puede usar, es un escenario muy común para enlazar un a una colección. <xref:System.Windows.Controls.ItemsControl> En la sección [¿qué pertenece a una plantilla](#what_belongs_in_datatemplate) de datos? se explicó que la <xref:System.Windows.DataTemplate> definición de su solo debe preocuparse por la presentación de datos. Para saber cuándo no es adecuado utilizar <xref:System.Windows.DataTemplate> , es importante comprender las distintas propiedades de estilo y plantilla que proporciona. <xref:System.Windows.Controls.ItemsControl> El ejemplo siguiente se ha diseñado para ilustrar la función de cada una de dichas propiedades. En este ejemplo, se enlaza a la misma `Tasks` colección que en el ejemplo anterior. <xref:System.Windows.Controls.ItemsControl> A efectos de demostración, los estilos y las plantillas de este ejemplo se declaran todas como inline.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 La siguiente captura de pantalla muestra el ejemplo cuando se representa:  
  
 ![Captura de pantalla de ejemplo ItemsControl](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Tenga en cuenta que <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, en lugar de usar, puede <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>utilizar. Consulte la sección anterior para obtener un ejemplo. Del mismo modo, en lugar de <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>usar, tiene la opción de <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>usar.  
  
 Otras dos propiedades relacionadas con el <xref:System.Windows.Controls.ItemsControl> estilo que no se muestran aquí son <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> y <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Compatibilidad con datos jerárquicos  
 Hasta ahora solo hemos examinado cómo enlazar a una sola colección y mostrarla. A veces se tiene una colección que contiene otras colecciones. La <xref:System.Windows.HierarchicalDataTemplate> clase está diseñada para usarse con <xref:System.Windows.Controls.HeaderedItemsControl> tipos para mostrar estos datos. En el ejemplo siguiente, `ListLeagueList` es una lista de objetos `League`. Cada objeto `League` tiene un `Name` y una colección de objetos `Division`. Cada `Division` tiene un `Name` y una colección de objetos `Team` y cada objeto `Team` tiene un `Name`.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 En el ejemplo se muestra que, con <xref:System.Windows.HierarchicalDataTemplate>el uso de, puede mostrar fácilmente los datos de la lista que contiene otras listas. La siguiente captura de pantalla muestra el ejemplo.  
  
 ![Captura de pantalla de ejemplo HierarchicalDataTemplate](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>Vea también

- [Enlace de datos](../advanced/optimizing-performance-data-binding.md)
- [Find DataTemplate-Generated Elements](how-to-find-datatemplate-generated-elements.md) (Cómo buscar elementos generados por una clase DataTemplate)
- [Aplicar estilos y plantillas](../controls/styling-and-templating.md)
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [GridView Column Header Styles and Templates Overview](../controls/gridview-column-header-styles-and-templates-overview.md) (Información general sobre plantillas y estilos de encabezado de columna en modo GridView)
