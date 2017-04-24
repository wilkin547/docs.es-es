---
title: "Informaci&#243;n general sobre plantillas de datos | Microsoft Docs"
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
  - "enlace de datos, plantillas"
  - "enlace de datos, plantillas"
  - "plantillas de datos"
  - "plantillas de datos"
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Informaci&#243;n general sobre plantillas de datos
El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modelo de plantillas de datos proporciona gran flexibilidad para definir la presentación de los datos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]los controles tienen funcionalidades integradas para admitir la personalización de la presentación de los datos. Este tema muestra primero cómo definir un <xref:System.Windows.DataTemplate> y, a continuación, presenta otras características de creación de plantillas de datos, como la selección de plantillas basadas en la lógica personalizada y la compatibilidad con la presentación de datos jerárquicos.  
  
   
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Este tema se centra en las características de creación de plantillas de datos y no es una introducción de los conceptos de enlace de datos. Para obtener información acerca de los conceptos de enlace de datos básicos, consulte la [información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate> es sobre la presentación de datos y es una de las muchas características proporcionadas por el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modelo de estilos y plantillas. Para obtener una introducción de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modelo de estilos y plantillas, como el uso de un <xref:System.Windows.Style> para establecer propiedades de controles, consulte el [estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md) tema.  
  
 Además, es importante comprender `Resources`, que son esencialmente lo habilite objetos como <xref:System.Windows.Style> y <xref:System.Windows.DataTemplate> sean reutilizables. Para obtener más información sobre recursos, consulte [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Conceptos básicos de plantillas de datos  
   
  
 Para mostrar por qué <xref:System.Windows.DataTemplate> es importante, analicemos un ejemplo de enlace de datos. En este ejemplo, tenemos un <xref:System.Windows.Controls.ListBox> que está enlazado a una lista de `Task` objetos. Cada `Task` objeto tiene una `TaskName` (cadena), un `Description` (cadena), un `Priority` (int) y una propiedad de tipo `TaskType`, que es un `Enum` con valores `Home` y `Work`.  
  
 [!code-xml[DataTemplatingIntro_snip#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xml[DataTemplatingIntro_snip#UI1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xml[DataTemplatingIntro_snip#UI2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Sin un DataTemplate  
 Sin un <xref:System.Windows.DataTemplate>nuestra <xref:System.Windows.Controls.ListBox> actualmente tiene este aspecto:  
  
 ![Captura de pantalla de ejemplo de datos plantillas](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Lo que sucede es que, sin ninguna instrucción concreta, el <xref:System.Windows.Controls.ListBox> por llamadas predeterminado `ToString` al intentar mostrar los objetos de la colección. Por lo tanto, si la `Task` objeto invalidaciones la `ToString` (método), el <xref:System.Windows.Controls.ListBox> muestra la representación de cadena de cada objeto de origen en la colección subyacente.  
  
 Por ejemplo, si la `Task` clase invalidaciones la `ToString` método de este modo, donde `name` es el campo para el `TaskName` propiedad:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 La <xref:System.Windows.Controls.ListBox> el siguiente aspecto:  
  
 ![Captura de pantalla de ejemplo de datos plantillas](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Sin embargo, eso resulta limitante e inflexible. Además, si va a enlazar a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos, no podrá invalidar `ToString`.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Definir una plantilla de datos Simple  
 La solución consiste en definir una <xref:System.Windows.DataTemplate>. Una manera de hacerlo es establecer el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad de la <xref:System.Windows.Controls.ListBox> a una <xref:System.Windows.DataTemplate>. Lo que especifique en la <xref:System.Windows.DataTemplate> se convierte en la estructura visual de su objeto de datos. El siguiente <xref:System.Windows.DataTemplate> es bastante sencillo. Estamos proporcionando instrucciones para que cada elemento aparezca como tres <xref:System.Windows.Controls.TextBlock> elementos dentro de un <xref:System.Windows.Controls.StackPanel>. Cada <xref:System.Windows.Controls.TextBlock> elemento está enlazado a una propiedad de la `Task` clase.  
  
 [!code-xml[DataTemplatingIntro_snip#Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 Los datos subyacentes de los ejemplos de este tema están una colección de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] objetos. Si va a enlazar a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos, los conceptos fundamentales son los mismos, pero hay una ligera diferencia sintáctica. Por ejemplo, en lugar de tener `Path=TaskName`, establecería <xref:System.Windows.Data.Binding.XPath%2A> a `@TaskName` (si `TaskName` es un atributo de su [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] nodo).  
  
 Ahora nuestra <xref:System.Windows.Controls.ListBox> el siguiente aspecto:  
  
 ![Captura de pantalla de ejemplo de datos plantillas](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Crear la plantilla de datos como un recurso  
 En el ejemplo anterior, hemos definido la <xref:System.Windows.DataTemplate> en línea. Es más común para definir en la sección de recursos para que pueda ser un objeto reutilizable, como en el ejemplo siguiente:  
  
 [!code-xml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xml[DataTemplatingIntro_snip#AsResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Ahora puede usar `myTaskTemplate` como un recurso, como en el ejemplo siguiente:  
  
 [!code-xml[DataTemplatingIntro_snip#MyTaskTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Porque `myTaskTemplate` es un recurso, ahora se puede utilizar en otros controles que tienen una propiedad que toma un <xref:System.Windows.DataTemplate> tipo. Como se muestra anteriormente, para <xref:System.Windows.Controls.ItemsControl> objetos, como el <xref:System.Windows.Controls.ListBox>, es el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad. Para <xref:System.Windows.Controls.ContentControl> objetos, es el <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>La propiedad DataType  
 El <xref:System.Windows.DataTemplate> clase tiene un <xref:System.Windows.DataTemplate.DataType%2A> propiedad que es muy similar a la <xref:System.Windows.Style.TargetType%2A> propiedad de la <xref:System.Windows.Style> clase. Por lo tanto, en lugar de especificar un `x:Key` para el <xref:System.Windows.DataTemplate> en el ejemplo anterior, puede hacer lo siguiente:  
  
 [!code-xml[DataTemplatingIntro_snip#DataType](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Esto <xref:System.Windows.DataTemplate> se aplica automáticamente a todos los `Task` objetos. Tenga en cuenta que en este caso el `x:Key` se establece implícitamente. Por lo tanto, si asigna este <xref:System.Windows.DataTemplate> una `x:Key` valor, se va a reemplazar el implícita `x:Key` y <xref:System.Windows.DataTemplate> no se aplica automáticamente.  
  
 Si está enlazando un <xref:System.Windows.Controls.ContentControl> a una colección de `Task` objetos, el <xref:System.Windows.Controls.ContentControl> no se utiliza el comando anterior <xref:System.Windows.DataTemplate> automáticamente. Esto es porque el enlace en un <xref:System.Windows.Controls.ContentControl> necesita más información para distinguir si desea enlazar a una colección completa o a los objetos individuales. Si su <xref:System.Windows.Controls.ContentControl> efectúa el seguimiento de la selección de un <xref:System.Windows.Controls.ItemsControl> tipo, puede establecer la <xref:System.Windows.Data.Binding.Path%2A> propiedad de la <xref:System.Windows.Controls.ContentControl> enlace a "`/`" para indicar que le interesa el elemento actual. Para obtener un ejemplo, vea [enlazar a una colección y mostrar información basada en la selección](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md). De lo contrario, debe especificar el <xref:System.Windows.DataTemplate> explícitamente estableciendo la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad.  
  
 El <xref:System.Windows.DataTemplate.DataType%2A> propiedad resulta especialmente útil cuando tenga un <xref:System.Windows.Data.CompositeCollection> de diferentes tipos de objetos de datos. Para obtener un ejemplo, vea [implementar una CompositeCollection](../../../../docs/framework/wpf/data/how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Agregar a la plantilla de datos  
 Actualmente, los datos aparecen con la información necesaria, pero está claro que hay espacio para la mejora. Vamos a mejorar la presentación agregando un <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Grid>y algunos <xref:System.Windows.Controls.TextBlock> elementos que describen los datos que se va a mostrar.  
  
 [!code-xml[DataTemplatingIntro#AddingMore](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 La siguiente captura de pantalla muestra la <xref:System.Windows.Controls.ListBox> con esta modificación <xref:System.Windows.DataTemplate>:  
  
 ![Captura de pantalla de ejemplo de datos plantillas](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 Podemos establecer <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> a <xref:System.Windows.HorizontalAlignment> en el <xref:System.Windows.Controls.ListBox> para asegurarse de que el ancho de los elementos ocupe todo el espacio:  
  
 [!code-xml[DataTemplatingIntro_snip#Stretch](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Con el <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> propiedad establecida en <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.Controls.ListBox> ahora el siguiente aspecto:  
  
 ![Captura de pantalla de ejemplo de datos plantillas](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Utilizar DataTriggers para aplicar valores de propiedad  
 La presentación actual no Díganos si una `Task` es una tarea de inicio o una tarea de office. Recuerde que la `Task` objeto tiene una `TaskType` propiedad de tipo `TaskType`, que es una enumeración con valores `Home` y `Work`.  
  
 En el ejemplo siguiente, la <xref:System.Windows.DataTrigger> establece la <xref:System.Windows.Controls.Border.BorderBrush%2A> del elemento denominado `border` a `Yellow` si la `TaskType` propiedad es `TaskType.Home`.  
  
 [!code-xml[DataTemplatingIntro#DT](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xml[DataTemplatingIntro#DataTrigger](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Ahora, nuestra aplicación tiene el siguiente aspecto. Las tareas domésticas aparecerán con un borde amarillo y las tareas de office con un borde aguamarina:  
  
 ![Captura de pantalla de ejemplo de datos plantillas](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 En este ejemplo el <xref:System.Windows.DataTrigger> utiliza un <xref:System.Windows.Setter> para establecer un valor de propiedad. Las clases de desencadenador también tienen la <xref:System.Windows.TriggerBase.EnterActions%2A> y <xref:System.Windows.TriggerBase.ExitActions%2A> propiedades que permiten iniciar un conjunto de acciones tales como animaciones. Además, también hay un <xref:System.Windows.MultiDataTrigger> clase que permite aplicar los cambios se basa en varios valores de la propiedad enlazada a datos.  
  
 Una manera alternativa de lograr el mismo efecto es enlazar la <xref:System.Windows.Controls.Border.BorderBrush%2A> propiedad a la `TaskType` propiedad y use un convertidor de valores para devolver el color según el `TaskType` valor. Creación del efecto anterior mediante un convertidor es ligeramente más eficaz en términos de rendimiento. Además, crear su propio convertidor ofrece más flexibilidad porque está proporcionando su propia lógica. En última instancia, la técnica que elija depende de su escenario y de sus preferencias. Para obtener información sobre cómo escribir un convertidor, vea <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>¿Cuáles son los de una plantilla de datos?  
 En el ejemplo anterior, colocamos el desencadenador dentro de la <xref:System.Windows.DataTemplate> utilizando la <xref:System.Windows.DataTemplate>.<xref:System.Windows.DataTemplate.Triggers%2A> propiedad. El <xref:System.Windows.Setter> del desencadenador establece el valor de una propiedad de un elemento (la <xref:System.Windows.Controls.Border> elemento) que está dentro de la <xref:System.Windows.DataTemplate>. Sin embargo, si las propiedades que su `Setters` les preocupa no son propiedades de elementos que están dentro del actual <xref:System.Windows.DataTemplate>, puede ser más adecuado establecer las propiedades mediante un <xref:System.Windows.Style> para el <xref:System.Windows.Controls.ListBoxItem> clase (si es el control que se va a enlazar una <xref:System.Windows.Controls.ListBox>). Por ejemplo, si desea que su <xref:System.Windows.Trigger> para animar el <xref:System.Windows.UIElement.Opacity%2A> valor del elemento cuando un mouse apunta a un elemento, defina desencadenadores dentro de un <xref:System.Windows.Controls.ListBoxItem> estilo. Para obtener un ejemplo, consulte el [Introducción al ejemplo de plantillas y estilos](http://go.microsoft.com/fwlink/?LinkID=160010).  
  
 En general, tenga en cuenta que el <xref:System.Windows.DataTemplate> se aplica a cada uno de los nodos <xref:System.Windows.Controls.ListBoxItem> (para obtener más información acerca de cómo y dónde se aplica realmente, vea la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> página.). La <xref:System.Windows.DataTemplate> está relacionado con solo la presentación y la apariencia de los objetos de datos. En la mayoría de los casos, todos los demás aspectos de presentación, como un elemento de qué aspecto cuando se selecciona o cómo la <xref:System.Windows.Controls.ListBox> establece los elementos no pertenecen a la definición de un <xref:System.Windows.DataTemplate>. Para obtener un ejemplo, consulte el [estilos y plantillas para ItemsControl](#DataTemplating_ItemsControl) sección.  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Elegir una plantilla de datos basándose en las propiedades del objeto de datos  
 En [la propiedad DataType](#Styling_DataType) sección, explicamos que puede definir diferentes plantillas de datos para objetos de datos diferentes. Esto es especialmente útil cuando tenga un <xref:System.Windows.Data.CompositeCollection> de diferentes tipos o colecciones con elementos de diferentes tipos. En el [Utilizar DataTriggers para aplicar valores de propiedad](#DataTrigger_to_Apply_Property_Values) sección, hemos mostrado que si tiene una colección del mismo tipo de objetos de datos puede crear un <xref:System.Windows.DataTemplate> y, a continuación, utilizar desencadenadores para aplicar cambios en función de los valores de propiedad de cada objeto de datos. Sin embargo, los desencadenadores permiten aplicar valores de propiedad o iniciar animaciones, pero no ofrecen la flexibilidad necesaria para reconstruir la estructura de los objetos de datos. Algunos escenarios pueden requerir crear otro <xref:System.Windows.DataTemplate> para datos de objetos que son del mismo tipo pero tienen propiedades diferentes.  
  
 Por ejemplo, cuando un `Task` objeto tiene una `Priority` valor de `1`, puede darle un aspecto completamente diferente para actuar como una alerta para usted. En ese caso, cree una <xref:System.Windows.DataTemplate> para la presentación de alta prioridad `Task` objetos. Vamos a agregar la siguiente <xref:System.Windows.DataTemplate> a la sección de recursos:  
  
 [!code-xml[DataTemplatingIntro_snip#ImportantTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Observe que este ejemplo se utiliza la <xref:System.Windows.DataTemplate>.<xref:System.Windows.FrameworkTemplate.Resources%2A> propiedad. Recursos definidos en esa sección son compartidos por los elementos dentro de la <xref:System.Windows.DataTemplate>.  
  
 Para proporcionar la lógica para elegir qué <xref:System.Windows.DataTemplate> utilizar basándose en la `Priority` valor del objeto de datos, crear una subclase de <xref:System.Windows.Controls.DataTemplateSelector> e invalidar la <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> método. En el ejemplo siguiente, la <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> método proporciona la lógica para devolver la plantilla adecuada en función del valor de la `Priority` propiedad. La plantilla que se devuelve se encuentra en los recursos de la envoltura <xref:System.Windows.Window> elemento.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 Podemos declarar entonces el `TaskListDataTemplateSelector` como un recurso:  
  
 [!code-xml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xml[DataTemplatingIntro_snip#DTS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Para utilizar el recurso selector de plantillas, asígnelo a la <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> propiedad de la <xref:System.Windows.Controls.ListBox>. El <xref:System.Windows.Controls.ListBox> llamadas el <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> método de la `TaskListDataTemplateSelector` para cada uno de los elementos de la colección subyacente. La llamada pasa el objeto de datos como parámetro de elemento. El <xref:System.Windows.DataTemplate> devuelto por el método, a continuación, se aplica a ese objeto de datos.  
  
 [!code-xml[DataTemplatingIntro_snip#ItemTemplateSelector](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 Con el selector de plantilla en su lugar, el <xref:System.Windows.Controls.ListBox> aparece ahora como sigue:  
  
 ![Captura de pantalla de ejemplo de datos plantillas](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  
  
 Esto concluye la explicación de este ejemplo. Para obtener un ejemplo completo, vea [Introducción al ejemplo de creación de plantillas de datos](http://go.microsoft.com/fwlink/?LinkID=160009).  
  
<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Estilos y plantillas para ItemsControl  
 Aunque la <xref:System.Windows.Controls.ItemsControl> no es el único tipo de control que puede utilizar un <xref:System.Windows.DataTemplate> , es un escenario muy común para enlazar un <xref:System.Windows.Controls.ItemsControl> a una colección. En el [lo que pertenece un DataTemplate](#what_belongs_in_datatemplate) sección explicamos que la definición de la <xref:System.Windows.DataTemplate> sólo debe preocuparse por la presentación de datos. Para saber cuándo no es adecuado usar un <xref:System.Windows.DataTemplate> es importante comprender las diferentes propiedades de estilo y la plantilla proporcionadas por el <xref:System.Windows.Controls.ItemsControl>. El ejemplo siguiente está diseñado para ilustrar la función de cada una de estas propiedades. El <xref:System.Windows.Controls.ItemsControl> en este ejemplo se enlaza al mismo `Tasks` colección del ejemplo anterior. Demostración propósitos, los estilos y plantillas en este ejemplo son todas las declaradas inline.  
  
 [!code-xml[DataTemplatingIntro_snip#ItemsControlProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 Ésta es una captura de pantalla del ejemplo cuando se representa:  
  
 ![Captura de pantalla de ejemplo ItemsControl](../../../../docs/framework/wpf/data/media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Tenga en cuenta que en lugar de utilizar el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, puede utilizar el <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>. Consulte la sección anterior para obtener un ejemplo. De forma similar, en lugar de utilizar el <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>, tiene la opción de utilizar la <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>.  
  
 Dos otras propiedades relacionadas con el estilo de la <xref:System.Windows.Controls.ItemsControl> que no se muestran aquí son <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> y <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Compatibilidad con datos jerárquicos  
 Hasta ahora sólo hemos examinado cómo enlazar y mostrar una sola colección. A veces tiene una colección que contiene otras colecciones. El <xref:System.Windows.HierarchicalDataTemplate> clase está diseñada para usarse con <xref:System.Windows.Controls.HeaderedItemsControl> tipos a mostrar dichos datos. En el ejemplo siguiente, `ListLeagueList` es una lista de `League` objetos. Cada `League` objeto tiene una `Name` y una colección de `Division` objetos. Cada `Division` tiene un `Name` y una colección de `Team` objetos y cada `Team` objeto tiene una `Name`.  
  
 [!code-xml[HierarchicalDataTemplateSnippet#HDT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 El ejemplo muestra que, con el uso de <xref:System.Windows.HierarchicalDataTemplate>, puede mostrar fácilmente datos de la lista que contiene otras listas. La siguiente es una captura de pantalla del ejemplo.  
  
 ![Captura de pantalla de ejemplo HierarchicalDataTemplate](../../../../docs/framework/wpf/data/media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>Vea también  
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Buscar elementos generados por el DataTemplate](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)   
 [Estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre plantillas y estilos de encabezado de columna de GridView](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)