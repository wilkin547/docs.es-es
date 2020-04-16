---
title: Definir recursos XAML
description: Obtén información sobre los recursos XAML en WPF para .NET Core. Comprender los tipos de recursos XAML y aprender a definir recursos XAML.
author: thraka
ms.author: adegeo
ms.date: 08/21/2019
ms.openlocfilehash: b278bb92afc308578d60e347871e0150b26a95db
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "81432573"
---
# <a name="overview-of-xaml-resources"></a>Descripción general de los recursos XAML

Un recurso es un objeto que se puede reutilizar en diferentes lugares de la aplicación. Pinceles y estilos son ejemplos de recursos. Esta información general describe cómo usar recursos en Lenguaje XAML (Extensible Application Markup Language)Extensible Application Markup Language (XAML). También puede crear y tener acceso a los recursos mediante código.

> [!NOTE]
> Los recursos XAML descritos en este artículo son diferentes de los recursos de *la aplicación* que generalmente son archivos agregados a una aplicación, como contenido, datos o archivos incrustados.

<!-- TODO: File redirect from docs\framework\wpf\advanced\xaml-resources.md -->

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="using-resources-in-xaml"></a>Uso de recursos en XAML

En el ejemplo <xref:System.Windows.Media.SolidColorBrush> siguiente se define a como un recurso en el elemento raíz de una página. A continuación, el ejemplo hace referencia al recurso y <xref:System.Windows.Shapes.Ellipse>lo <xref:System.Windows.Controls.TextBlock>utiliza para <xref:System.Windows.Controls.Button>establecer las propiedades de varios elementos secundarios, incluidos un archivo , a y un archivo .

[!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]

Cada elemento de<xref:System.Windows.FrameworkElement> nivel <xref:System.Windows.FrameworkContentElement>de <xref:System.Windows.FrameworkElement.Resources%2A> marco ( o <xref:System.Windows.ResourceDictionary> ) tiene una propiedad, que es un tipo que contiene recursos definidos. Puede definir recursos en cualquier elemento, como un <xref:System.Windows.Controls.Button>archivo . Sin embargo, los recursos se definen <xref:System.Windows.Controls.Page> con mayor frecuencia en el elemento raíz, que está en el ejemplo.

Cada recurso en un diccionario de recursos debe tener una clave única. Al definir recursos en el marcado, se asigna la clave única a través de la [directiva x:Key](../xaml-services/xkey-directive.md). Normalmente, la clave es una cadena; pero puede también establecerla para otros tipos de objetos usando las extensiones de marcado apropiadas. Ciertas áreas de características de WPFWPF usan claves que no son de cadena para los recursos, especialmente para estilos, recursos de componentes y estilos de datos.

Puede usar un recurso definido con la sintaxis de extensión de marcado de recursos que especifica el nombre de clave del recurso. Por ejemplo, utilice el recurso como el valor de una propiedad en otro elemento.

[!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]

En el ejemplo anterior, cuando el `{StaticResource MyBrush}` cargador <xref:System.Windows.Controls.Control.Background%2A> XAML <xref:System.Windows.Controls.Button>procesa el valor de la propiedad en <xref:System.Windows.Controls.Button> , la lógica de búsqueda de recursos comprueba primero el diccionario de recursos para el elemento. Si <xref:System.Windows.Controls.Button> no tiene una definición `MyBrush` de la clave de recurso (en ese ejemplo no lo hace; <xref:System.Windows.Controls.Button>su colección de recursos está vacía), la búsqueda comprueba a continuación el elemento primario de , que es <xref:System.Windows.Controls.Page>. Si define un recurso <xref:System.Windows.Controls.Page> en el elemento raíz, todos <xref:System.Windows.Controls.Page> los elementos del árbol lógico del pueden tener acceso a él. Y puede reutilizar el mismo recurso para establecer el valor de cualquier propiedad que acepte el mismo tipo que representa el recurso. En el ejemplo anterior, `MyBrush` el mismo recurso <xref:System.Windows.Controls.Control.Background%2A> establece <xref:System.Windows.Controls.Button>dos <xref:System.Windows.Shapes.Shape.Fill%2A> propiedades <xref:System.Windows.Shapes.Rectangle>diferentes: la de un archivo , y la de un archivo .

## <a name="static-and-dynamic-resources"></a>Recursos estáticos y dinámicos

Se puede hacer referencia a un recurso como estático o dinámico. Las referencias se crean mediante la extensión de [marcado StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md) o la extensión de [marcado DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md). Una extensión de marcado es una característica XAML que le permite especificar una referencia de objeto haciendo que la extensión de marcado procese la cadena de atributo y devuelva el objeto a un cargador XAML. Para obtener más información sobre el comportamiento de la extensión de marcado, vea [Extensiones](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)de marcado y XAML de WPF .

Cuando se usa una extensión de marcado, normalmente se proporcionan uno o varios parámetros en forma de cadena que se procesan mediante esa extensión de marcado determinada. La extensión de [marcado StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md) procesa una clave buscando el valor de esa clave en todos los diccionarios de recursos disponibles. El procesamiento se produce durante la carga, que es cuando el proceso de carga necesita asignar el valor de propiedad. En su lugar, la extensión de [marcado DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md) procesa una clave mediante la creación de una expresión y esa expresión permanece sin evaluar hasta que se ejecuta la aplicación, momento en el que se evalúa la expresión y proporciona un valor.

Al hacer referencia a un recurso, independientemente de si usa una referencia de recurso estático o una referencia de recurso dinámico, pueden influir las siguientes consideraciones:

- Al determinar el diseño general de cómo crear los recursos para la aplicación (por página, en la aplicación, en XAML suelto o en un ensamblado de solo recursos), tenga en cuenta lo siguiente:

- Funcionalidad de la aplicación. ¿La actualización de recursos en tiempo real forma parte de los requisitos de la aplicación?
- El comportamiento de búsqueda respectivo de ese tipo de referencia de recurso.
- La propiedad o tipo de recurso determinado y el comportamiento nativo de esos tipos.

## <a name="static-resources"></a>Recursos estáticos

Las referencias de recursos estáticos trabajan mejor en las siguientes circunstancias:

- El diseño de la aplicación concentra la mayoría de sus recursos en diccionarios de recursos de nivel de página o de aplicación. Las referencias de recursos estáticos no se vuelven a evaluar en función de los comportamientos en tiempo de ejecución, como volver a cargar una página. Por lo tanto, puede haber alguna ventaja de rendimiento para evitar un gran número de referencias de recursos dinámicos cuando no son necesarias en función del diseño de recursos y aplicaciones.

- Está estableciendo el valor de una propiedad <xref:System.Windows.DependencyObject> que <xref:System.Windows.Freezable>no está en un archivo o un archivo .

- Está creando un diccionario de recursos que se compilará en un archivo DLL y se empaquetará como parte de la aplicación o se compartirá entre aplicaciones.

- Está creando un tema para un control personalizado y está definiendo los recursos que se usan dentro de los temas. En este caso, normalmente no desea el comportamiento de búsqueda de referencia de recursos dinámicos; en su lugar, desea que el comportamiento de referencia de recursos estáticos para que la búsqueda sea predecible y independiente al tema. Con una referencia de recurso dinámico, incluso una referencia dentro de un tema se deja sin evaluar hasta el tiempo de ejecución. y existe la posibilidad de que cuando se aplique el tema, algún elemento local redefina una clave a la que el tema está intentando hacer referencia, y el elemento local caerá antes del propio tema en la búsqueda. Si eso sucede, su tema no se comportará como se esperaba.

- Está utilizando recursos para establecer un gran número de propiedades de dependencia. Las propiedades de dependencia tienen almacenamiento en caché de valores efectivo según lo habilitado por el sistema de propiedades, por lo que si proporciona un valor para una propiedad de dependencia que se puede evaluar en tiempo de carga, la propiedad de dependencia no tiene que comprobar si hay una expresión reevaluada y puede devolver el último valor efectivo. Esta técnica puede suponer una ventaja de rendimiento.

- Desea cambiar el recurso subyacente para todos los consumidores o desea mantener instancias de escritura independientes para cada consumidor mediante [x:Shared Attribute](../xaml-services/xshared-attribute.md).

### <a name="static-resource-lookup-behavior"></a>Comportamiento de búsqueda de recursos estáticos

A continuación se describe el proceso de búsqueda que se produce automáticamente cuando una propiedad o elemento hace referencia a un recurso estático:

01. El proceso de búsqueda comprueba la clave solicitada en el diccionario de recursos que ha definido el elemento que establece la propiedad.

01. A continuación, el proceso de búsqueda recorre el árbol lógico hacia arriba hasta el elemento primario y su diccionario de recursos. Este proceso continúa hasta que se alcanza el elemento raíz.

01. Se comprueban los recursos de la aplicación. Los recursos de la aplicación son los <xref:System.Windows.Application> recursos del diccionario de recursos definido por el objeto para la aplicación WPFWPF.

Las referencias de recursos estáticos del interior de un diccionario de recursos deben hacer referencia a un recurso que ya se haya definido léxicamente antes que la referencia de recurso. No se pueden resolver las referencias adelantadas mediante una referencia de recursos estáticos. Por este motivo, diseñe la estructura del diccionario de recursos de forma que los recursos se definan al principio o cerca del principio de cada diccionario de recursos respectivo.

La búsqueda de recursos estáticos puede extenderse a temas o a recursos del sistema, pero esta búsqueda solo se admite porque el cargador XAML aplaza la solicitud. El aplazamiento es necesario para que el tema en tiempo de ejecución en el momento en que se carga la página se aplica correctamente a la aplicación. Sin embargo, no se recomiendan las referencias de recursos estáticos a claves que solo existen en temas o como recursos del sistema, ya que estas referencias no se vuelven a evaluar si el usuario cambia el tema en tiempo real. Una referencia de recurso dinámico es más confiable cuando solicita un tema o recursos del sistema. La excepción se produce cuando un elemento de tema solicita otro recurso. Estas referencias deben ser referencias de recursos estáticos, por los motivos que se han mencionado anteriormente.

El comportamiento de excepción si no se encuentra una referencia de recurso estático varía. Si el recurso se ha aplazado, entonces la excepción se produce en tiempo de ejecución. Si el recurso no se ha aplazado, la excepción se produce en tiempo de carga.

## <a name="dynamic-resources"></a>Recursos dinámicos

Los recursos dinámicos funcionan mejor cuando:

- El valor del recurso, incluidos los recursos del sistema o los recursos que de otro modo son configurables por el usuario, depende de las condiciones que no se conocen hasta el tiempo de ejecución. Por ejemplo, puede crear valores de establecedor <xref:System.Windows.SystemColors>que <xref:System.Windows.SystemFonts>hagan <xref:System.Windows.SystemParameters>referencia a las propiedades del sistema expuestas por , , o . Estos valores son verdaderamente dinámicos porque proceden en definitiva del entorno en tiempo de ejecución del usuario y del sistema operativo. También puede tener temas en el nivel de aplicación que pueden cambiar, donde el acceso a los recursos de nivel de página también debe capturar el cambio.

- Está creando o haciendo referencia a estilos de tema para un control personalizado.

- Tiene la intención de <xref:System.Windows.ResourceDictionary> ajustar el contenido de una durante la duración de una aplicación.

- Tiene una estructura de recursos complicada que tiene interdependencias, donde puede necesitarse una referencia adelantada. Las referencias de recursos estáticos no admiten referencias directas, pero las referencias de recursos dinámicos sí las admiten porque no es necesario evaluar el recurso hasta el tiempo de ejecución y, por lo tanto, las referencias directas no son un concepto relevante.

- Hace referencia a un recurso que es grande desde la perspectiva de una compilación o un conjunto de trabajo, y es posible que el recurso no se use inmediatamente cuando se cargue la página. Las referencias de recursos estáticos siempre se cargan desde XAML cuando se carga la página. Sin embargo, una referencia de recurso dinámico no se carga hasta que se usa.

- Está creando un estilo en el que los valores de establecedor pueden provenir de otros valores que están influenciados por temas u otros valores de usuario.

- Está aplicando recursos a elementos que podrían volver a ser padres en el árbol lógico durante la duración de la aplicación. Cambiar el elemento primario también cambia potencialmente el ámbito de búsqueda de recursos, por lo que si quiere que el recurso de un elemento primario que se puede cambiar se vuelva a evaluar basándose en el nuevo ámbito, use siempre una referencia de recurso dinámico.

### <a name="dynamic-resource-lookup-behavior"></a>Comportamiento de búsqueda de recursos dinámicos

El comportamiento de búsqueda de recursos para una referencia de <xref:System.Windows.FrameworkElement.FindResource%2A> <xref:System.Windows.FrameworkElement.SetResourceReference%2A>recursos dinámicos es paralelo al comportamiento de búsqueda en el código si se llama o:

01. La búsqueda comprueba la clave solicitada dentro del diccionario de recursos definido por el elemento que establece la propiedad:

    - Si el elemento <xref:System.Windows.FrameworkElement.Style%2A> define <xref:System.Windows.FrameworkElement.Style?displayProperty=fullName> una propiedad, <xref:System.Windows.Style.Resources> el del elemento tiene su diccionario comprobado.

    - Si el elemento <xref:System.Windows.Controls.Control.Template%2A> define <xref:System.Windows.FrameworkTemplate.Resources?displayProperty=fullName> una propiedad, se comprueba el diccionario del elemento.

01. La búsqueda recorre el árbol lógico hacia arriba hasta el elemento primario y su diccionario de recursos. Este proceso continúa hasta que se alcanza el elemento raíz.

01. Se comprueban los recursos de la aplicación. Los recursos de la aplicación son los <xref:System.Windows.Application> recursos del diccionario de recursos definidos por el objeto para la aplicación WPFWPF.

01. El diccionario de recursos de tema se comprueba para el tema activo actualmente. Si el tema cambia en tiempo de ejecución, el valor se vuelve a evaluar.

01. Se comprueban los recursos del sistema.

El comportamiento de excepción (si existe) varía:

- Si una llamada solicitó un <xref:System.Windows.FrameworkElement.FindResource%2A> recurso y no se encontró, se produce una excepción.

- Si una llamada solicitó un <xref:System.Windows.FrameworkElement.TryFindResource%2A> recurso y no se encontró, no `null`se produce ninguna excepción y el valor devuelto es . Si la propiedad que se `null`establece no acepta , todavía es posible que se produzca una excepción más profunda, dependiendo de la propiedad individual que se establezca.

- Si una referencia de recurso dinámico en XAML solicitó un recurso y no se encontró, el comportamiento depende del sistema de propiedades general. El comportamiento general es como si no se hubiera producido ninguna operación de configuración de propiedad en el nivel donde existe el recurso. Por ejemplo, si intenta establecer el fondo en un elemento de botón individual mediante un recurso que no se pudo evaluar, no hay resultados de conjunto de valores, pero el valor efectivo todavía puede proceder de otros participantes en el sistema de propiedades y la prioridad de valor. Por ejemplo, el valor de fondo todavía puede provenir de un estilo de botón definido localmente o del estilo de tema. Para las propiedades que no están definidas por los estilos de tema, el valor efectivo después de una evaluación de recursos con errores puede provenir del valor predeterminado en los metadatos de la propiedad.

### <a name="restrictions"></a>Restricciones

Las referencias de recursos dinámicos tienen algunas restricciones importantes. Debe cumplirse al menos una de las siguientes condiciones:

- La propiedad que se establece <xref:System.Windows.FrameworkElement> debe <xref:System.Windows.FrameworkContentElement>ser una propiedad en un o . Esa propiedad debe estar <xref:System.Windows.DependencyProperty>respaldada por un archivo .

- La referencia es para `StyleSetter`un valor dentro de un archivo .

- La propiedad que se establece <xref:System.Windows.Freezable> debe ser una propiedad en <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> una que <xref:System.Windows.Setter> se proporciona como un valor de una propiedad o, o un valor.

Dado que la propiedad <xref:System.Windows.DependencyProperty> que <xref:System.Windows.Freezable> se establece debe ser una propiedad o, la mayoría de los cambios de propiedad se pueden propagar a la interfaz de usuario porque el sistema de propiedades reconoce un cambio de propiedad (el valor de recurso dinámico modificado). La mayoría de los controles incluyen lógica <xref:System.Windows.DependencyProperty> que forzará otro diseño de un control si un cambio y esa propiedad pueden afectar al diseño. Sin embargo, no todas las propiedades que tienen una extensión de [marcado DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md) como su valor se garantiza que proporcionan actualizaciones en tiempo real en la interfaz de usuario. Esa funcionalidad todavía puede variar en función de la propiedad, así como del tipo que posee la propiedad, o incluso la estructura lógica de la aplicación.

## <a name="styles-datatemplates-and-implicit-keys"></a>Estilos, DataTemplates y claves implícitas

Aunque todos los <xref:System.Windows.ResourceDictionary> elementos de un deben tener una clave, `x:Key`eso no significa que todos los recursos deben tener un archivo . Varios tipos de objetos admiten una clave implícita cuando se definen como un recurso, donde el valor de clave está vinculado al valor de otra propiedad. Este tipo de clave se conoce como `x:Key` una clave implícita, mientras que un atributo es una clave explícita. Puede sobrescribir cualquier clave implícita especificando una clave explícita.

Un escenario importante para los <xref:System.Windows.Style>recursos es cuando se define un archivo . De hecho, <xref:System.Windows.Style> a casi siempre se define como una entrada en un diccionario de recursos, porque los estilos están inherentemente diseñados para su reutilización. Para obtener más información acerca de los estilos, vea [Estilo y plantillas](styles-templates-overview.md).

Los estilos para los controles pueden crearse y hacerse referencia con una clave implícita. Los estilos de tema que definen la apariencia predeterminada de un control se basan en esta clave implícita. Desde el punto de vista de solicitarlo, la clave implícita es la <xref:System.Type> del propio control. Desde el punto de vista de la definición de los recursos, la clave implícita es el <xref:System.Windows.Style.TargetType%2A> estilo. Por lo tanto, si va a crear temas para controles personalizados o crear estilos que interactúan <xref:System.Windows.Style>con estilos de tema existentes, no es necesario especificar una [directiva x:Key](../xaml-services/xkey-directive.md) para eso. Y si quiere usar los estilos temáticos, no necesita especificar ningún estilo. Por ejemplo, la siguiente definición <xref:System.Windows.Style> de estilo funciona, aunque el recurso no parezca tener una clave:

[!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]

Ese estilo realmente tiene una clave: la clave `typeof(System.Windows.Controls.Button)`implícita . En el marcado, <xref:System.Windows.Style.TargetType%2A> puede especificar un código directo como el nombre de tipo (o puede usar opcionalmente [.x:Type...](../xaml-services/xtype-markup-extension.md) para devolver <xref:System.Type>un archivo .

A través de los mecanismos de estilo de tema predeterminados <xref:System.Windows.Controls.Button> utilizados por WPFWPF, ese estilo se aplica como el estilo de tiempo de ejecución de un en la página, aunque el <xref:System.Windows.Controls.Button> propio no intenta especificar su <xref:System.Windows.FrameworkElement.Style%2A> propiedad o una referencia de recurso específico al estilo. El estilo definido en la página se encuentra anteriormente en la secuencia de búsqueda que el estilo de diccionario de temas, utilizando la misma clave que tiene el estilo de diccionario de temas. Puede especificar `<Button>Hello</Button>` cualquier parte de la página y <xref:System.Windows.Style.TargetType%2A> `Button` el estilo que definió con of se aplicaría a ese botón. Si lo desea, todavía puede escribir explícitamente el <xref:System.Windows.Style.TargetType%2A> estilo con el mismo valor de tipo que para mayor claridad en el marcado, pero eso es opcional.

Las claves implícitas para estilos <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> `true`no se aplican a un control si es . (Tenga en <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> cuenta también que se puede establecer como parte del comportamiento nativo para la clase de control, en lugar de explícitamente en una instancia del control.) Además, para admitir claves implícitas para escenarios <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> de clase derivados, el control debe invalidar (todos los controles existentes proporcionados como parte de WPFWPF incluyen esta invalidación). Para obtener más información acerca de los estilos, temas y diseño de controles, vea [Directrices para diseñar controles estilables](../../framework/wpf/controls/guidelines-for-designing-stylable-controls.md).

<xref:System.Windows.DataTemplate>también tiene una clave implícita. La clave implícita <xref:System.Windows.DataTemplate> para <xref:System.Windows.DataTemplate.DataType%2A> a es el valor de propiedad. <xref:System.Windows.DataTemplate.DataType%2A>También se puede especificar como el nombre del tipo en lugar de usar explícitamente el valor de [.x:Type...](../xaml-services/xtype-markup-extension.md). Para obtener más información, consulte Información general sobre [plantillas de](../../framework/wpf/data/data-templating-overview.md)datos .

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.ResourceDictionary>
- [Recursos de aplicación](../../framework/wpf/advanced/optimizing-performance-application-resources.md)
- [Recursos y código](../../framework/wpf/advanced/resources-and-code.md)
- [Definir y hacer referencia a un recurso](../../framework/wpf/advanced/how-to-define-and-reference-a-resource.md)
- [Visión general de la gestión de aplicaciones](../../framework/wpf/app-development/application-management-overview.md)
- [x:Extensión de marcado de tipo](../xaml-services/xtype-markup-extension.md)
- [Extensión de marcado StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md)
- [Extensión de marcado DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md)
