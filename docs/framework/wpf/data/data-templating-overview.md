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
ms.openlocfilehash: 98fff9ba84f386e93549fa94fe84f7b2b0fff5fd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097556"
---
# <a name="data-templating-overview"></a>Información general sobre plantillas de datos
El modelo de plantillas de datos de WPF ofrece gran flexibilidad para definir la presentación de los datos. Los controles WPF tienen funcionalidad integrada que admite la personalización de la presentación de los datos. En este tema muestra primero cómo definir un <xref:System.Windows.DataTemplate> y, a continuación, presenta otras características de plantillas de datos, como la selección de plantillas basadas en la lógica personalizada y la compatibilidad con la presentación de datos jerárquicos.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Este tema se centra en las características de creación de plantillas de datos y no es una introducción a los conceptos de enlace de datos. Para información sobre los conceptos básicos de enlace de datos, vea the [Información general sobre el enlace de datos](data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate> trata la presentación de datos y es una de las muchas características proporcionadas por el modelo de estilos y plantillas WPF. Para obtener una introducción del modelo aplicar estilos y plantillas WPF, por ejemplo, cómo usar un <xref:System.Windows.Style> para establecer propiedades de controles, vea el [aplicar estilos y plantillas](../controls/styling-and-templating.md) tema.  
  
 Además, es importante comprender `Resources`, que son esencialmente lo que permiten a los objetos como <xref:System.Windows.Style> y <xref:System.Windows.DataTemplate> para poder ser reutilizados. Para más información sobre los recursos, vea [Recursos XAML](../advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Conceptos básicos de plantillas de datos  
  
 Para demostrar por qué <xref:System.Windows.DataTemplate> es importante, vamos a recorrer un ejemplo de enlace de datos. En este ejemplo, tenemos un <xref:System.Windows.Controls.ListBox> que está enlazado a una lista de `Task` objetos. Cada objeto `Task` tiene un `TaskName` (cadena), un `Description` (cadena), un `Priority` (int) y una propiedad de tipo `TaskType`, que es un `Enum` con valores `Home` y `Work`.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Sin un DataTemplate  
 Sin un <xref:System.Windows.DataTemplate>, nuestro <xref:System.Windows.Controls.ListBox> actualmente tiene este aspecto:  
  
 ![Captura de pantalla de ejemplo de creación de plantillas de datos](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Lo que sucede es que, sin ninguna instrucción concreta, el <xref:System.Windows.Controls.ListBox> mediante llamadas predeterminada `ToString` al intentar mostrar los objetos de la colección. Por lo tanto, si la `Task` objeto invalidaciones el `ToString` método, el <xref:System.Windows.Controls.ListBox> muestra la representación de cadena de cada objeto de origen en la colección subyacente.  
  
 Por ejemplo, si la clase `Task` invalida el método `ToString` de esta manera, donde `name` es el campo para la propiedad `TaskName`:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 El <xref:System.Windows.Controls.ListBox> el siguiente aspecto:  
  
 ![Captura de pantalla de ejemplo de creación de plantillas de datos](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Pero eso resulta limitante e inflexible. Además, si enlaza a datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], no podrá invalidar `ToString`.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Definir un DataTemplate simple  
 La solución consiste en definir un <xref:System.Windows.DataTemplate>. Una manera de hacerlo es establecer el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad de la <xref:System.Windows.Controls.ListBox> a un <xref:System.Windows.DataTemplate>. Lo que especifique en su <xref:System.Windows.DataTemplate> se convierte en la estructura visual de su objeto de datos. La siguiente <xref:System.Windows.DataTemplate> es bastante sencillo. Le estamos ofreciendo instrucciones que cada elemento aparezca como tres <xref:System.Windows.Controls.TextBlock> elementos dentro de un <xref:System.Windows.Controls.StackPanel>. Cada <xref:System.Windows.Controls.TextBlock> elemento está enlazado a una propiedad de la `Task` clase.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 Los datos subyacentes de los ejemplos de este tema son una colección de objetos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. Si enlaza a datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], los conceptos fundamentales son los mismos, pero existe una ligera diferencia sintáctica. Por ejemplo, en lugar de tener `Path=TaskName`, establecería <xref:System.Windows.Data.Binding.XPath%2A> a `@TaskName` (si `TaskName` es un atributo de su [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] nodo).  
  
 Ahora nuestra <xref:System.Windows.Controls.ListBox> el siguiente aspecto:  
  
 ![Captura de pantalla de ejemplo de creación de plantillas de datos](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Crear el DataTemplate como recurso  
 En el ejemplo anterior, hemos definido la <xref:System.Windows.DataTemplate> en línea. Es más frecuente definirlo en la sección de recursos para que pueda ser un objeto reutilizable, como en el ejemplo siguiente:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Ahora puede usar `myTaskTemplate` como recurso, como en el ejemplo siguiente:  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Dado que `myTaskTemplate` es un recurso, ahora se puede utilizar en otros controles que tienen una propiedad que toma un <xref:System.Windows.DataTemplate> tipo. Como se muestra anteriormente, para <xref:System.Windows.Controls.ItemsControl> objetos, como el <xref:System.Windows.Controls.ListBox>, es el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad. Para <xref:System.Windows.Controls.ContentControl> objetos, es el <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>La propiedad DataType  
 El <xref:System.Windows.DataTemplate> clase tiene un <xref:System.Windows.DataTemplate.DataType%2A> propiedad que es muy similar a la <xref:System.Windows.Style.TargetType%2A> propiedad de la <xref:System.Windows.Style> clase. Por lo tanto, en lugar de especificar un `x:Key` para el <xref:System.Windows.DataTemplate> en el ejemplo anterior, puede hacer lo siguiente:  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Esto <xref:System.Windows.DataTemplate> se aplica automáticamente a todos los `Task` objetos. Tenga en cuenta que en este caso el `x:Key` se establece implícitamente. Por lo tanto, si se asigna esta <xref:System.Windows.DataTemplate> una `x:Key` valor, se va a reemplazar implícito `x:Key` y <xref:System.Windows.DataTemplate> no se aplicaría automáticamente.  
  
 Si va a enlazar un <xref:System.Windows.Controls.ContentControl> a una colección de `Task` objetos, el <xref:System.Windows.Controls.ContentControl> no utiliza el anterior <xref:System.Windows.DataTemplate> automáticamente. Esto es porque el enlace en un <xref:System.Windows.Controls.ContentControl> necesita más información para distinguir si desea enlazar a una colección completa o los objetos individuales. Si su <xref:System.Windows.Controls.ContentControl> seguimiento de la selección de un <xref:System.Windows.Controls.ItemsControl> tipo, puede establecer el <xref:System.Windows.Data.Binding.Path%2A> propiedad de la <xref:System.Windows.Controls.ContentControl> enlazar a "`/`" para indicar que estás interesado en el elemento actual. Para obtener un ejemplo, vea [Bind to a Collection and Display Information Based on Selection](how-to-bind-to-a-collection-and-display-information-based-on-selection.md) (Cómo: Enlazar a una colección y mostrar información basada en la selección). En caso contrario, deberá especificar el <xref:System.Windows.DataTemplate> explícitamente estableciendo la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad.  
  
 El <xref:System.Windows.DataTemplate.DataType%2A> propiedad resulta especialmente útil cuando tenga un <xref:System.Windows.Data.CompositeCollection> de diferentes tipos de objetos de datos. Para obtener un ejemplo, vea [Implement a CompositeCollection](how-to-implement-a-compositecollection.md) (Cómo: Implementar una CompositeCollection).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Agregar más elementos al DataTemplate  
 Actualmente los datos aparecen con la información necesaria, pero sin duda hay margen de mejora. Vamos a mejorar la presentación agregando un <xref:System.Windows.Controls.Border>, un <xref:System.Windows.Controls.Grid>y algunos <xref:System.Windows.Controls.TextBlock> elementos que describen los datos que se va a mostrar.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 La siguiente captura de pantalla muestra la <xref:System.Windows.Controls.ListBox> con esto se puede modificar <xref:System.Windows.DataTemplate>:  
  
 ![Captura de pantalla de ejemplo de creación de plantillas de datos](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 Podemos establecer <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> a <xref:System.Windows.HorizontalAlignment.Stretch> en el <xref:System.Windows.Controls.ListBox> para asegurarse de que el ancho de los elementos ocupe todo el espacio:  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Con el <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> propiedad establecida en <xref:System.Windows.HorizontalAlignment.Stretch>, el <xref:System.Windows.Controls.ListBox> ahora tiene este aspecto:  
  
 ![Captura de pantalla de ejemplo de creación de plantillas de datos](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Usar DataTriggers para aplicar valores de propiedad  
 La presentación actual no nos indica si una `Task` es una tarea doméstica o una tarea de oficina. Recuerde que el objeto `Task` tiene una propiedad `TaskType` de tipo `TaskType`, que es una enumeración con valores `Home` y `Work`.  
  
 En el ejemplo siguiente, la <xref:System.Windows.DataTrigger> establece la <xref:System.Windows.Controls.Border.BorderBrush%2A> del elemento denominado `border` a `Yellow` si el `TaskType` propiedad es `TaskType.Home`.  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Nuestra aplicación tiene ahora el aspecto siguiente. Las tareas domésticas aparecen con un borde amarillo y las tareas de oficina, con un borde aguamarina:  
  
 ![Captura de pantalla de ejemplo de creación de plantillas de datos](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 En este ejemplo el <xref:System.Windows.DataTrigger> usa un <xref:System.Windows.Setter> para establecer un valor de propiedad. Las clases de desencadenador tienen también la <xref:System.Windows.TriggerBase.EnterActions%2A> y <xref:System.Windows.TriggerBase.ExitActions%2A> propiedades que le permiten iniciar un conjunto de acciones, como animaciones. Además, también hay un <xref:System.Windows.MultiDataTrigger> clase que le permite aplicar los cambios en función de varios valores de propiedad enlazada a datos.  
  
 Una manera alternativa de conseguir el mismo efecto es enlazar el <xref:System.Windows.Controls.Border.BorderBrush%2A> propiedad a la `TaskType` propiedad y use un convertidor de valores para devolver el color según el `TaskType` valor. La creación del efecto anterior mediante un convertidor es ligeramente más eficiente en términos de rendimiento. Además, la creación de su propio convertidor le brinda mayor flexibilidad porque usted proporciona su propia lógica. En última instancia, la técnica que elija depende de su escenario y de sus preferencias. Para obtener información sobre cómo escribir un convertidor de tipos, vea <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Lo que corresponde a un DataTemplate  

En el ejemplo anterior, situamos el desencadenador dentro de la <xref:System.Windows.DataTemplate> mediante el <xref:System.Windows.DataTemplate>.<xref:System.Windows.DataTemplate.Triggers%2A> Propiedad. El <xref:System.Windows.Setter> del desencadenador establece el valor de una propiedad de un elemento (el <xref:System.Windows.Controls.Border> elemento) que está dentro de la <xref:System.Windows.DataTemplate>. Sin embargo, si las propiedades que su `Setters` les preocupa no son propiedades de elementos que están dentro del actual <xref:System.Windows.DataTemplate>, puede ser más adecuado establecer las propiedades mediante un <xref:System.Windows.Style> que es para el <xref:System.Windows.Controls.ListBoxItem> clase (si el control que se va a enlazar es un <xref:System.Windows.Controls.ListBox>). Por ejemplo, si desea que su <xref:System.Windows.Trigger> para animar la <xref:System.Windows.UIElement.Opacity%2A> valor del elemento cuando un mouse apunta a un elemento, defina desencadenadores en una <xref:System.Windows.Controls.ListBoxItem> estilo. Para obtener un ejemplo, vea [Introducción a la aplicación de estilos y plantillas de ejemplo](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).
  
 En general, tenga en cuenta que el <xref:System.Windows.DataTemplate> se aplica a cada uno de los generados <xref:System.Windows.Controls.ListBoxItem> (para obtener más información acerca de cómo y dónde se aplica realmente, vea la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> página.). Su <xref:System.Windows.DataTemplate> se refiere a solo la presentación y la apariencia de los objetos de datos. En la mayoría de los casos, es similar a todos los demás aspectos de presentación, como un elemento cuando se selecciona o cómo la <xref:System.Windows.Controls.ListBox> establece los elementos, no pertenecen a la definición de un <xref:System.Windows.DataTemplate>. Para obtener un ejemplo, vea la sección [Aplicar estilos y plantillas con un ItemsControl](#DataTemplating_ItemsControl).  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Elegir un DataTemplate en función de las propiedades del objeto de datos  
 En la sección [La propiedad DataType](#Styling_DataType), explicamos que se pueden definir distintas plantillas de datos para objetos de datos diferentes. Esto resulta especialmente útil cuando tenga un <xref:System.Windows.Data.CompositeCollection> de diferentes tipos o colecciones con elementos de diferentes tipos. En el [usar DataTriggers para aplicar valores de propiedad](#DataTrigger_to_Apply_Property_Values) sección, hemos mostrado que si tiene una colección del mismo tipo de objetos de datos puede crear un <xref:System.Windows.DataTemplate> y, a continuación, utilizar desencadenadores para aplicar cambios basados en los valores de propiedad cada objeto de datos. Aunque los desencadenadores le permiten aplicar valores de propiedad o iniciar animaciones, no le ofrecen la flexibilidad de reconstruir la estructura de los objetos de datos. Algunos escenarios pueden requerir que crear otra <xref:System.Windows.DataTemplate> para datos de objetos que son del mismo tipo pero tienen propiedades diferentes.  
  
 Por ejemplo, puede que cuando un objeto `Task` tenga un valor `Priority` de `1` quiera darle un aspecto completamente distinto para que actúe como alerta para usted mismo. En ese caso, crea un <xref:System.Windows.DataTemplate> para la presentación de alta prioridad `Task` objetos. Vamos a agregar la siguiente <xref:System.Windows.DataTemplate> a la sección de recursos:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Tenga en cuenta este ejemplo se utiliza el <xref:System.Windows.DataTemplate>.<xref:System.Windows.FrameworkTemplate.Resources%2A> Propiedad. Los recursos definidos en esa sección son compartidos por los elementos dentro de la <xref:System.Windows.DataTemplate>.  
  
 Para proporcionar lógica para elegir qué <xref:System.Windows.DataTemplate> utilizar según la `Priority` valor del objeto de datos, cree una subclase de <xref:System.Windows.Controls.DataTemplateSelector> e invalidar la <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> método. En el ejemplo siguiente, la <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> método proporciona la lógica para devolver la plantilla adecuada en función del valor de la `Priority` propiedad. La plantilla que se devuelve se encuentra en los recursos de la envoltura <xref:System.Windows.Window> elemento.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 Podemos declarar el `TaskListDataTemplateSelector` como recurso:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Para usar el recurso del selector de plantillas, asígnelo a la <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> propiedad de la <xref:System.Windows.Controls.ListBox>. El <xref:System.Windows.Controls.ListBox> llamadas la <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> método de la `TaskListDataTemplateSelector` para cada uno de los elementos de la colección subyacente. La llamada pasa el objeto de datos como parámetro del elemento. El <xref:System.Windows.DataTemplate> devuelta por el método, a continuación, se aplica al objeto de datos.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 Con el selector de plantillas en su lugar, el <xref:System.Windows.Controls.ListBox> aparece ahora como sigue:  
  
 ![Captura de pantalla de ejemplo de creación de plantillas de datos](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

Con esto concluye la explicación de este ejemplo. Para obtener el ejemplo completo, vea [Introducción a la aplicación de plantillas de ejemplo](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Aplicar estilos y plantillas con un ItemsControl  
 Aunque el <xref:System.Windows.Controls.ItemsControl> no es el único tipo de control que puede usar un <xref:System.Windows.DataTemplate> con, es un escenario muy común para enlazar un <xref:System.Windows.Controls.ItemsControl> a una colección. En el [lo que corresponde a un DataTemplate](#what_belongs_in_datatemplate) sección analizamos que la definición de su <xref:System.Windows.DataTemplate> solo debe tener en cuenta la presentación de datos. Para saber cuándo no es adecuado usar un <xref:System.Windows.DataTemplate> es importante comprender las distintas propiedades de estilo y plantilla proporcionadas por el <xref:System.Windows.Controls.ItemsControl>. El ejemplo siguiente se ha diseñado para ilustrar la función de cada una de dichas propiedades. El <xref:System.Windows.Controls.ItemsControl> en este ejemplo se enlaza a la misma `Tasks` colección del ejemplo anterior. A efectos de demostración, los estilos y las plantillas de este ejemplo se declaran todas como inline.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 La siguiente captura de pantalla muestra el ejemplo cuando se representa:  
  
 ![Captura de pantalla de ejemplo ItemsControl](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Tenga en cuenta que en lugar de usar el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, puede usar el <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>. Consulte la sección anterior para obtener un ejemplo. De forma similar, en lugar de usar el <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>, tiene la opción para usar el <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>.  
  
 Dos otras propiedades relacionadas con el estilo de la <xref:System.Windows.Controls.ItemsControl> que no se muestran aquí son <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> y <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Compatibilidad con datos jerárquicos  
 Hasta ahora solo hemos examinado cómo enlazar a una sola colección y mostrarla. A veces se tiene una colección que contiene otras colecciones. El <xref:System.Windows.HierarchicalDataTemplate> clase está diseñada para usarse con <xref:System.Windows.Controls.HeaderedItemsControl> tipos para mostrar esos datos. En el ejemplo siguiente, `ListLeagueList` es una lista de objetos `League`. Cada objeto `League` tiene un `Name` y una colección de objetos `Division`. Cada `Division` tiene un `Name` y una colección de objetos `Team` y cada objeto `Team` tiene un `Name`.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 En el ejemplo se muestra que, con el uso de <xref:System.Windows.HierarchicalDataTemplate>, puede mostrar fácilmente datos de la lista que contiene otras listas. La siguiente captura de pantalla muestra el ejemplo.  
  
 ![HierarchicalDataTemplate sample screenshot](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>Vea también

- [Enlace de datos](../advanced/optimizing-performance-data-binding.md)
- [Find DataTemplate-Generated Elements](how-to-find-datatemplate-generated-elements.md) (Cómo buscar elementos generados por una clase DataTemplate)
- [Aplicar estilos y plantillas](../controls/styling-and-templating.md)
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [GridView Column Header Styles and Templates Overview](../controls/gridview-column-header-styles-and-templates-overview.md) (Información general sobre plantillas y estilos de encabezado de columna en modo GridView)
