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
ms.openlocfilehash: b9e55eac1c72cd3deec21754373da4364a7cfed2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646457"
---
# <a name="data-templating-overview"></a>Información general sobre plantillas de datos
El modelo de plantillas de datos de WPF ofrece gran flexibilidad para definir la presentación de los datos. Los controles WPF tienen funcionalidad integrada que admite la personalización de la presentación de los datos. En este tema se muestra <xref:System.Windows.DataTemplate> primero cómo definir a y, a continuación, se presentan otras características de plantillas de datos, como la selección de plantillas basadas en la lógica personalizada y la compatibilidad con la visualización de datos jerárquicos.

<a name="Prerequisites"></a>
## <a name="prerequisites"></a>Prerrequisitos
 Este tema se centra en las características de creación de plantillas de datos y no es una introducción a los conceptos de enlace de datos. Para información sobre los conceptos básicos de enlace de datos, vea the [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).

 <xref:System.Windows.DataTemplate>se trata de la presentación de datos y es una de las muchas características proporcionadas por el WPFWPF estilo y modelo de plantillas. Para obtener una introducción de la WPFWPF estilo y <xref:System.Windows.Style> el modelo de plantillas, como cómo usar a para establecer propiedades en controles, vea el [estilo y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md) tema.

 Además, es importante `Resources`entender, que son esencialmente <xref:System.Windows.Style> <xref:System.Windows.DataTemplate> lo que permiten que objetos como y ser reutilizables. Para más información sobre los recursos, vea [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

<a name="DataTemplating_Basic"></a>
## <a name="data-templating-basics"></a>Conceptos básicos de plantillas de datos

 Para demostrar <xref:System.Windows.DataTemplate> por qué es importante, vamos a recorrer un ejemplo de enlace de datos. En este ejemplo, <xref:System.Windows.Controls.ListBox> tenemos un que `Task` está enlazado a una lista de objetos. Cada objeto `Task` tiene un `TaskName` (cadena), un `Description` (cadena), un `Priority` (int) y una propiedad de tipo `TaskType`, que es un `Enum` con valores `Home` y `Work`.

 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]

<a name="without_a_datatemplate"></a>
### <a name="without-a-datatemplate"></a>Sin un DataTemplate
 Sin <xref:System.Windows.DataTemplate>un <xref:System.Windows.Controls.ListBox> , nuestro actualmente se ve así:

 ![Captura de pantalla de muestra de plantillas de datos](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")

 Lo que sucede es que sin <xref:System.Windows.Controls.ListBox> ninguna `ToString` instrucción específica, las llamadas de forma predeterminada al intentar mostrar los objetos de la colección. Por lo `Task` tanto, si `ToString` el objeto <xref:System.Windows.Controls.ListBox> reemplaza el método, muestra la representación de cadena de cada objeto de origen en la colección subyacente.

 Por ejemplo, si la clase `Task` invalida el método `ToString` de esta manera, donde `name` es el campo para la propiedad `TaskName`:

 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]

 Entonces <xref:System.Windows.Controls.ListBox> el aspecto es el siguiente:

 ![Captura de pantalla de muestra de plantillas de datos](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")

 Pero eso resulta limitante e inflexible. Además, si va a enlazar a datos XML, no podrá invalidar `ToString`.

<a name="defining_simple_datatemplate"></a>
### <a name="defining-a-simple-datatemplate"></a>Definir un DataTemplate simple
 La solución es <xref:System.Windows.DataTemplate>definir un archivo . Una forma de hacerlo es <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> establecer <xref:System.Windows.Controls.ListBox> la <xref:System.Windows.DataTemplate>propiedad de la en un archivo . Lo que especifique <xref:System.Windows.DataTemplate> en su se convierte en la estructura visual del objeto de datos. Lo <xref:System.Windows.DataTemplate> siguiente es bastante simple. Estamos dando instrucciones de que <xref:System.Windows.Controls.TextBlock> cada elemento <xref:System.Windows.Controls.StackPanel>aparece como tres elementos dentro de un archivo . Cada <xref:System.Windows.Controls.TextBlock> elemento está enlazado a `Task` una propiedad de la clase.

 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]

 Los datos subyacentes de los ejemplos de este tema son una colección de objetos CLR. Si va a enlazar a datos XML, los conceptos fundamentales son los mismos, pero hay una ligera diferencia sintáctica. Por ejemplo, en `Path=TaskName`lugar de <xref:System.Windows.Data.Binding.XPath%2A> `@TaskName` tener `TaskName` , establecería en (si es un atributo del nodo XML).

 Ahora <xref:System.Windows.Controls.ListBox> nuestro aspecto es el siguiente:

 ![Captura de pantalla de muestra de plantillas de datos](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")

<a name="defining_datatemplate_as_a_resource"></a>
### <a name="creating-the-datatemplate-as-a-resource"></a>Crear el DataTemplate como recurso
 En el ejemplo anterior, <xref:System.Windows.DataTemplate> definimos el en línea. Es más frecuente definirlo en la sección de recursos para que pueda ser un objeto reutilizable, como en el ejemplo siguiente:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 Ahora puede usar `myTaskTemplate` como recurso, como en el ejemplo siguiente:

 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]

 Dado `myTaskTemplate` que es un recurso, ahora puede usarlo en otros <xref:System.Windows.DataTemplate> controles que tienen una propiedad que toma un tipo. Como se muestra <xref:System.Windows.Controls.ItemsControl> arriba, para <xref:System.Windows.Controls.ListBox>los objetos, como el , es la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad. Para <xref:System.Windows.Controls.ContentControl> los objetos, es la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad.

<a name="Styling_DataType"></a>
### <a name="the-datatype-property"></a>La propiedad DataType
 La <xref:System.Windows.DataTemplate> clase <xref:System.Windows.DataTemplate.DataType%2A> tiene una propiedad que <xref:System.Windows.Style.TargetType%2A> es <xref:System.Windows.Style> muy similar a la propiedad de la clase. Por lo tanto, `x:Key` en <xref:System.Windows.DataTemplate> lugar de especificar un para el ejemplo anterior, puede hacer lo siguiente:

 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]

 Esto <xref:System.Windows.DataTemplate> se aplica automáticamente `Task` a todos los objetos. Tenga en cuenta que en este caso el `x:Key` se establece implícitamente. Por lo tanto, <xref:System.Windows.DataTemplate> `x:Key` si asigna un valor, `x:Key` va <xref:System.Windows.DataTemplate> a reemplazar el implícito y el no se aplicaría automáticamente.

 Si va a <xref:System.Windows.Controls.ContentControl> enlazar a `Task` una <xref:System.Windows.Controls.ContentControl> colección de <xref:System.Windows.DataTemplate> objetos, no se utiliza lo anterior automáticamente. Esto se debe a <xref:System.Windows.Controls.ContentControl> que el enlace en un necesita más información para distinguir si desea enlazar a una colección completa o a los objetos individuales. Si <xref:System.Windows.Controls.ContentControl> su está realizando <xref:System.Windows.Controls.ItemsControl> un seguimiento de <xref:System.Windows.Data.Binding.Path%2A> la <xref:System.Windows.Controls.ContentControl> selección de`/`un tipo, puede establecer la propiedad del enlace en " " para indicar que está interesado en el elemento actual. Para obtener un ejemplo, vea [Bind to a Collection and Display Information Based on Selection](how-to-bind-to-a-collection-and-display-information-based-on-selection.md) (Cómo: Enlazar a una colección y mostrar información basada en la selección). De lo contrario, <xref:System.Windows.DataTemplate> debe especificar explícitamente el estableciendo la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad.

 La <xref:System.Windows.DataTemplate.DataType%2A> propiedad es especialmente útil <xref:System.Windows.Data.CompositeCollection> cuando se tiene uno de diferentes tipos de objetos de datos. Para obtener un ejemplo, vea [Implement a CompositeCollection](how-to-implement-a-compositecollection.md) (Cómo: Implementar una CompositeCollection).

<a name="adding_more_to_datatemplate"></a>
## <a name="adding-more-to-the-datatemplate"></a>Agregar más elementos al DataTemplate
 Actualmente los datos aparecen con la información necesaria, pero sin duda hay margen de mejora. Vamos a mejorar la presentación <xref:System.Windows.Controls.Border>agregando <xref:System.Windows.Controls.Grid>un <xref:System.Windows.Controls.TextBlock> , a , y algunos elementos que describen los datos que se muestran.

 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 La siguiente captura <xref:System.Windows.Controls.ListBox> de <xref:System.Windows.DataTemplate>pantalla muestra el con este modificado :

 ![Captura de pantalla de muestra de plantillas de datos](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")

 Podemos establecer <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.HorizontalAlignment.Stretch> en <xref:System.Windows.Controls.ListBox> el para asegurarnos de que el ancho de los elementos ocupa todo el espacio:

 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]

 Con <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> la propiedad <xref:System.Windows.HorizontalAlignment.Stretch>establecida <xref:System.Windows.Controls.ListBox> en , el ahora tiene este aspecto:

 ![Captura de pantalla de muestra de plantillas de datos](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")

<a name="DataTrigger_to_Apply_Property_Values"></a>
### <a name="use-datatriggers-to-apply-property-values"></a>Usar DataTriggers para aplicar valores de propiedad
 La presentación actual no nos indica si una `Task` es una tarea doméstica o una tarea de oficina. Recuerde que el objeto `Task` tiene una propiedad `TaskType` de tipo `TaskType`, que es una enumeración con valores `Home` y `Work`.

 En el ejemplo <xref:System.Windows.DataTrigger> siguiente, <xref:System.Windows.Controls.Border.BorderBrush%2A> el establece `border` `Yellow` el `TaskType` elemento `TaskType.Home`del elemento denominado si la propiedad es .

 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 Nuestra aplicación tiene ahora el aspecto siguiente. Las tareas domésticas aparecen con un borde amarillo y las tareas de oficina, con un borde aguamarina:

 ![Captura de pantalla de muestra de plantillas de datos](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")

 En este <xref:System.Windows.DataTrigger> ejemplo, <xref:System.Windows.Setter> se utiliza a para establecer un valor de propiedad. Las clases de <xref:System.Windows.TriggerBase.EnterActions%2A> <xref:System.Windows.TriggerBase.ExitActions%2A> desencadenador también tienen las propiedades y que le permiten iniciar un conjunto de acciones como animaciones. Además, también <xref:System.Windows.MultiDataTrigger> hay una clase que le permite aplicar cambios basados en varios valores de propiedad enlazados a datos.

 Una forma alternativa de lograr el <xref:System.Windows.Controls.Border.BorderBrush%2A> mismo efecto `TaskType` es enlazar la propiedad a la `TaskType` propiedad y usar un convertidor de valores para devolver el color en función del valor. La creación del efecto anterior mediante un convertidor es ligeramente más eficiente en términos de rendimiento. Además, la creación de su propio convertidor le brinda mayor flexibilidad porque usted proporciona su propia lógica. En última instancia, la técnica que elija depende de su escenario y de sus preferencias. Para obtener información sobre cómo <xref:System.Windows.Data.IValueConverter>escribir un convertidor, consulte .

<a name="what_belongs_in_datatemplate"></a>
### <a name="what-belongs-in-a-datatemplate"></a>Lo que corresponde a un DataTemplate

En el ejemplo anterior, colocamos <xref:System.Windows.DataTemplate> el <xref:System.Windows.DataTemplate.Triggers%2A?displayProperty=nameWithType> desencadenador dentro de la propiedad using. El <xref:System.Windows.Setter> desencadenador establece el valor de una propiedad <xref:System.Windows.Controls.Border> de un elemento <xref:System.Windows.DataTemplate>(el elemento) que se encuentra dentro del archivo . Sin embargo, si `Setters` las propiedades que le preocupan no <xref:System.Windows.DataTemplate>son propiedades de elementos que están <xref:System.Windows.Style> dentro de <xref:System.Windows.Controls.ListBoxItem> la actual , puede ser <xref:System.Windows.Controls.ListBox>más adecuado establecer las propiedades mediante a que es para la clase (si el control que está enlazando es un ). Por ejemplo, si <xref:System.Windows.Trigger> desea animar <xref:System.Windows.UIElement.Opacity%2A> el valor del elemento cuando un mouse apunta a <xref:System.Windows.Controls.ListBoxItem> un elemento, defina desencadenadores dentro de un estilo. Para obtener un ejemplo, vea [Introducción a la aplicación de estilos y plantillas de ejemplo](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

 En general, tenga en <xref:System.Windows.DataTemplate> cuenta que se está <xref:System.Windows.Controls.ListBoxItem> aplicando a cada uno de los generados <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> (para obtener más información sobre cómo y dónde se aplica realmente, consulte la página.). Solo <xref:System.Windows.DataTemplate> le preocupa la presentación y la apariencia de los objetos de datos. En la mayoría de los casos, todos los demás aspectos de <xref:System.Windows.Controls.ListBox> la presentación, como el aspecto de un <xref:System.Windows.DataTemplate>elemento cuando se selecciona o cómo se establecen los elementos, no pertenecen a la definición de un archivo . Para obtener un ejemplo, vea la sección [Aplicar estilos y plantillas con un ItemsControl](#DataTemplating_ItemsControl).

<a name="Styling_StyleSelection"></a>
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Elegir un DataTemplate en función de las propiedades del objeto de datos
 En la sección [La propiedad DataType](#Styling_DataType), explicamos que se pueden definir distintas plantillas de datos para objetos de datos diferentes. Esto es especialmente útil <xref:System.Windows.Data.CompositeCollection> cuando tiene uno de diferentes tipos o colecciones con elementos de diferentes tipos. En la sección [Usar DataTriggers para aplicar valores](#DataTrigger_to_Apply_Property_Values) de propiedad, hemos demostrado que si tiene <xref:System.Windows.DataTemplate> una colección del mismo tipo de objetos de datos puede crear y, a continuación, usar desencadenadores para aplicar cambios basados en los valores de propiedad de cada objeto de datos. Aunque los desencadenadores le permiten aplicar valores de propiedad o iniciar animaciones, no le ofrecen la flexibilidad de reconstruir la estructura de los objetos de datos. Algunos escenarios pueden requerir que <xref:System.Windows.DataTemplate> cree un objeto de datos diferente que son del mismo tipo pero tienen propiedades diferentes.

 Por ejemplo, puede que cuando un objeto `Task` tenga un valor `Priority` de `1` quiera darle un aspecto completamente distinto para que actúe como alerta para usted mismo. En ese caso, <xref:System.Windows.DataTemplate> se crea un para `Task` la visualización de los objetos de alta prioridad. Agreguemos lo siguiente <xref:System.Windows.DataTemplate> a la sección de recursos:

 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]

En este ejemplo se utiliza la propiedad [DataTemplate.Resources.](xref:System.Windows.FrameworkTemplate.Resources%2A) Los recursos definidos en esa <xref:System.Windows.DataTemplate>sección son compartidos por los elementos dentro del archivo .

 Para proporcionar lógica <xref:System.Windows.DataTemplate> para elegir qué `Priority` usar en función del valor <xref:System.Windows.Controls.DataTemplateSelector> del <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> objeto de datos, cree una subclase de e invalide el método. En el ejemplo <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> siguiente, el método proporciona lógica para devolver `Priority` la plantilla adecuada en función del valor de la propiedad. La plantilla que se va a devolver se <xref:System.Windows.Window> encuentra en los recursos del elemento envolvente.

 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]

 Podemos declarar el `TaskListDataTemplateSelector` como recurso:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 Para utilizar el recurso selector de <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> plantilla, <xref:System.Windows.Controls.ListBox>asígnelo a la propiedad del archivo . El <xref:System.Windows.Controls.ListBox> llama <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> al `TaskListDataTemplateSelector` método de la para cada uno de los elementos de la colección subyacente. La llamada pasa el objeto de datos como parámetro del elemento. El <xref:System.Windows.DataTemplate> que devuelve el método, a continuación, se aplica a ese objeto de datos.

 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]

 Con el selector de <xref:System.Windows.Controls.ListBox> plantillas en su lugar, el ahora aparece de la siguiente manera:

 ![Captura de pantalla de muestra de plantillas de datos](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")

Con esto concluye la explicación de este ejemplo. Para obtener el ejemplo completo, vea [Introducción a la aplicación de plantillas de ejemplo](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>
## <a name="styling-and-templating-an-itemscontrol"></a>Aplicar estilos y plantillas con un ItemsControl
 Aunque el <xref:System.Windows.Controls.ItemsControl> no es el único tipo <xref:System.Windows.DataTemplate> de control que se puede usar <xref:System.Windows.Controls.ItemsControl> a con, es un escenario muy común para enlazar un a una colección. En la sección [Qué pertenece a un DataTemplate,](#what_belongs_in_datatemplate) discutimos que la definición de su <xref:System.Windows.DataTemplate> sólo debe preocuparse por la presentación de datos. Para saber cuándo no es adecuado <xref:System.Windows.DataTemplate> utilizar un es importante entender las diferentes <xref:System.Windows.Controls.ItemsControl>propiedades de estilo y plantilla proporcionadas por el . El ejemplo siguiente se ha diseñado para ilustrar la función de cada una de dichas propiedades. El <xref:System.Windows.Controls.ItemsControl> ejemplo de este ejemplo `Tasks` está enlazado a la misma colección que en el ejemplo anterior. A efectos de demostración, los estilos y las plantillas de este ejemplo se declaran todas como inline.

 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]

 La siguiente captura de pantalla muestra el ejemplo cuando se representa:

 ![Captura de pantalla de ejemplo de ItemsControl](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")

 Tenga en cuenta <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>que en lugar <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>de utilizar el archivo , puede utilizar el archivo . Consulte la sección anterior para obtener un ejemplo. Del mismo modo, <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>en lugar de utilizar <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>el archivo , tiene la opción de utilizar el archivo .

 Otras dos propiedades relacionadas <xref:System.Windows.Controls.ItemsControl> con el estilo <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>de los que no se muestran aquí son y .

<a name="DataTemplating_HeirarchicalDataTemplate"></a>
## <a name="support-for-hierarchical-data"></a>Compatibilidad con datos jerárquicos
 Hasta ahora solo hemos examinado cómo enlazar a una sola colección y mostrarla. A veces se tiene una colección que contiene otras colecciones. La <xref:System.Windows.HierarchicalDataTemplate> clase está diseñada <xref:System.Windows.Controls.HeaderedItemsControl> para usarse con tipos para mostrar dichos datos. En el ejemplo siguiente, `ListLeagueList` es una lista de objetos `League`. Cada objeto `League` tiene un `Name` y una colección de objetos `Division`. Cada `Division` tiene un `Name` y una colección de objetos `Team` y cada objeto `Team` tiene un `Name`.

 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]

 En el ejemplo se <xref:System.Windows.HierarchicalDataTemplate>muestra que con el uso de , puede mostrar fácilmente los datos de lista que contienen otras listas. La siguiente captura de pantalla muestra el ejemplo.

 ![Captura de pantalla de ejemplo HierarchicalDataTemplate](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")

## <a name="see-also"></a>Consulte también

- [Enlace de datos](../advanced/optimizing-performance-data-binding.md)
- [Encontrar elementos generados por DataTemplate](how-to-find-datatemplate-generated-elements.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Descripción general del enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre plantillas y estilos de encabezado de columna en modo GridView](../controls/gridview-column-header-styles-and-templates-overview.md)
