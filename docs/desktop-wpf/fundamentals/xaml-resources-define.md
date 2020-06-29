---
title: Definición de recursos XAML
description: Obtenga información sobre los recursos XAML en WPF para .NET Core. Obtenga información sobre los tipos de recursos XAML y aprenda a definir recursos XAML.
author: adegeo
ms.author: adegeo
ms.date: 08/21/2019
ms.openlocfilehash: f8eaf3fd931aa6804b0b9a9c19c6bcc042678ebf
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325713"
---
# <a name="overview-of-xaml-resources"></a>Información general sobre los recursos XAML

Un recurso es un objeto que se puede volver a usar en diferentes sitios de la aplicación. Pinceles y estilos son ejemplos de recursos. En esta información general se describe cómo usar los recursos en lenguaje XAML. También puede crear y obtener acceso a recursos mediante código.

> [!NOTE]
> Los recursos XAML descritos en este artículo son diferentes de los *recursos de la aplicación*, que normalmente son archivos agregados a una aplicación, como contenido, datos o archivos incrustados.

<!-- TODO: File redirect from docs\framework\wpf\advanced\xaml-resources.md -->

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="using-resources-in-xaml"></a>Uso de recursos en XAML

En el ejemplo siguiente se define <xref:System.Windows.Media.SolidColorBrush> como un recurso en el elemento raíz de una página. Posteriormente, el ejemplo hace referencia al recurso y lo usa para establecer las propiedades de varios elementos secundarios, incluidos los elementos <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Controls.Button>.

[!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]

Cada elemento de nivel de marco (<xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>) tiene una propiedad <xref:System.Windows.FrameworkElement.Resources%2A>, que es un tipo de <xref:System.Windows.ResourceDictionary> que contiene recursos definidos. Puede definir recursos en cualquier elemento, como <xref:System.Windows.Controls.Button>. Sin embargo, los recursos se definen con mayor frecuencia en el elemento raíz, que en el ejemplo es <xref:System.Windows.Controls.Page>.

Cada recurso en un diccionario de recursos debe tener una clave única. Al definir los recursos en el marcado, le asigna la clave única a través de la [directiva x:Key](../xaml-services/xkey-directive.md). Normalmente, la clave es una cadena; pero puede también establecerla para otros tipos de objetos usando las extensiones de marcado apropiadas. Las claves que no son de cadena para recursos se usan por ciertas áreas de características de WPF, en particular para los estilos, los recursos de componente y los estilos de datos.

Puede usar un recurso definido con la sintaxis de extensión de marcado de recursos que especifica el nombre de clave del recurso. Por ejemplo, use el recurso como el valor de una propiedad en otro elemento.

[!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]

En el ejemplo anterior, cuando el cargador de XAML procesa el valor `{StaticResource MyBrush}` para la propiedad <xref:System.Windows.Controls.Control.Background%2A> en <xref:System.Windows.Controls.Button>, la lógica de búsqueda de recursos comprueba primero el diccionario de recursos para el elemento <xref:System.Windows.Controls.Button>. Si <xref:System.Windows.Controls.Button> no tiene una definición de la clave de recurso `MyBrush` (en el ejemplo no la tiene; su colección de recursos está vacía), la búsqueda siguiente comprueba el elemento primario de <xref:System.Windows.Controls.Button>, que es <xref:System.Windows.Controls.Page>. Si define un recurso en el elemento raíz <xref:System.Windows.Controls.Page>, todos los elementos del árbol lógico de <xref:System.Windows.Controls.Page> pueden acceder a él. Y puede reutilizar el mismo recurso para establecer el valor de cualquier propiedad que acepte el mismo tipo que representa el recurso. En el ejemplo anterior, el mismo recurso `MyBrush` establece dos propiedades diferentes: <xref:System.Windows.Controls.Control.Background%2A> de <xref:System.Windows.Controls.Button> y <xref:System.Windows.Shapes.Shape.Fill%2A> de <xref:System.Windows.Shapes.Rectangle>.

## <a name="static-and-dynamic-resources"></a>Recursos estáticos y dinámicos

Se puede hacer referencia a un recurso como estático o dinámico. Las referencias se crean usando la [extensión de marcado StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md) o la [extensión de marcado DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md). Una extensión de marcado es una característica de XAML que permite especificar una referencia de objeto que tiene la extensión de marcado para procesar la cadena del atributo y devolver el objeto a un cargador XAML. Para obtener más información sobre el comportamiento de la extensión de marcado, vea [Extensiones de marcado y XAML de WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

Cuando se usa una extensión de marcado, normalmente proporciona uno o varios parámetros en forma de cadena que son procesados por dicha extensión de marcado. La [extensión de marcado StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md) procesa una clave buscando el valor para esa clave en todos los diccionarios de recursos disponibles. El procesamiento se produce durante la carga, que es cuando el proceso de carga debe asignar el valor de propiedad. La [extensión de marcado DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md), en su lugar, procesa una clave mediante la creación de una expresión, y dicha expresión permanece sin evaluar hasta que se ejecuta la aplicación, momento en el que la expresión se evalúa y proporciona un valor.

Al hacer referencia a un recurso, independientemente de si usa una referencia de recurso estático o una referencia de recurso dinámico, pueden influir las siguientes consideraciones:

- A la hora de determinar el diseño general de cómo crear los recursos de la aplicación (por página, en la aplicación, en XAML dinámico o en un ensamblado solo de recursos), tenga en cuenta lo siguiente:

- La funcionalidad de la aplicación. ¿Está actualizando los recursos en la parte en tiempo real de los requisitos de la aplicación?
- El comportamiento de búsqueda respectivo de ese tipo de referencia de recurso.
- La propiedad o tipo de recurso determinado y el comportamiento nativo de esos tipos.

## <a name="static-resources"></a>Recursos estáticos

Las referencias de recursos estáticos trabajan mejor en las siguientes circunstancias:

- El diseño de la aplicación concentra la mayoría de sus recursos en la página o en los diccionarios de recursos en el nivel de aplicación. Las referencias de recursos estáticos no se vuelven a evaluar en función de los comportamientos en tiempo de ejecución, como volver a cargar una página. Por lo tanto, puede haber una ventaja de rendimiento para evitar un gran número de referencias de recursos dinámicos cuando no son necesarias en función del diseño de la aplicación y el recurso.

- Está estableciendo el valor de una propiedad que no está en <xref:System.Windows.DependencyObject> o en <xref:System.Windows.Freezable>.

- Está creando un diccionario de recursos que se compilará en un archivo DLL y que se empaqueta como parte de la aplicación o se comparte entre aplicaciones.

- Está creando un tema para un control personalizado y está definiendo recursos que se usan dentro de los temas. En este caso, normalmente no quiere el comportamiento de búsqueda de referencia de recursos dinámicos, sino el comportamiento de referencia de recursos estáticos, de manera que la búsqueda sea predecible e independiente para el tema. Con una referencia de recursos dinámicos, incluso una referencia dentro de un tema se deja sin evaluar hasta el tiempo de ejecución. Además, es probable que, cuando se aplica el tema, algún elemento local vuelva a definir una clave a la que el tema está intentando hacer referencia, y el elemento local se detectará antes que el propio tema en la búsqueda. Si esto sucede, el tema no se comportará de la manera esperada.

- Está usando recursos para establecer grandes cantidades de propiedades de dependencia. Las propiedades de dependencia tienen un almacenamiento en caché de valores efectivos habilitado por el sistema de propiedades, así que si proporciona un valor para una propiedad de dependencia que pueda evaluarse en tiempo de carga, la propiedad de dependencia no tiene que comprobar una expresión que se ha vuelto a evaluar y puede devolver el último valor efectivo. Esta técnica puede suponer una ventaja de rendimiento.

- Quiere cambiar el recurso subyacente para todos los consumidores o quiere mantener instancias grabables independientes para cada consumidor con el [atributo x:Shared](../xaml-services/xshared-attribute.md).

### <a name="static-resource-lookup-behavior"></a>Comportamiento de búsqueda de recursos estáticos

En el siguiente ejemplo se describe el proceso de búsqueda que se produce automáticamente cuando una propiedad o un elemento hace referencia a un recurso estático:

01. El proceso de búsqueda comprueba la clave solicitada en el diccionario de recursos que ha definido el elemento que establece la propiedad.

01. Después, el proceso de búsqueda recorre el árbol lógico hacia arriba, hasta el elemento primario y su diccionario de recursos. Este proceso continúa hasta que se alcanza el elemento raíz.

01. Se comprueban los recursos de la aplicación. Los recursos de la aplicación son aquellos recursos dentro del diccionario de recursos definido por el objeto <xref:System.Windows.Application> para su aplicación WPF.

Las referencias de recursos estáticos del interior de un diccionario de recursos deben hacer referencia a un recurso que ya se haya definido léxicamente antes que la referencia de recurso. No se pueden resolver las referencias adelantadas mediante una referencia de recursos estáticos. Por este motivo, debe diseñar la estructura del diccionario de recursos de manera que los recursos se definan en o cerca del principio de cada diccionario de recursos respectivo.

La búsqueda de recursos estáticos puede ampliarse en temas o en recursos del sistema, pero esta búsqueda solo se admite porque el cargador XAML aplaza la solicitud. El aplazamiento es necesario, de manera que el tema en tiempo de ejecución en el momento de la carga de la página se aplique correctamente en la aplicación. Sin embargo, las referencias de recursos estáticos a claves que se sabe que solo existen en los temas o como recursos del sistema no se recomiendan, ya que dichas referencias no se vuelven a evaluar si el usuario cambia el tema en tiempo real. Una referencia de recurso dinámico es más confiable cuando solicita un tema o recursos del sistema. La excepción se produce cuando un elemento de tema solicita otro recurso. Estas referencias deben ser referencias de recursos estáticos, por los motivos que se han mencionado anteriormente.

El comportamiento de excepción, si no se detecta una referencia de recursos estáticos, varía. Si el recurso se ha aplazado, entonces la excepción se produce en tiempo de ejecución. Si el recurso no se ha aplazado, la excepción se produce en tiempo de carga.

## <a name="dynamic-resources"></a>Recursos dinámicos

Los recursos dinámicos funcionan mejor en estos casos:

- El valor del recurso, incluidos los recursos del sistema o los recursos que puede establecer el usuario, depende de las condiciones que no se conocen hasta el tiempo de ejecución. Por ejemplo, puede crear valores de establecedor que hagan referencia a las propiedades del sistema como expuestas por <xref:System.Windows.SystemColors>, <xref:System.Windows.SystemFonts> o <xref:System.Windows.SystemParameters>. Estos valores son verdaderamente dinámicos porque proceden en definitiva del entorno en tiempo de ejecución del usuario y del sistema operativo. También puede tener temas en el nivel de aplicación que pueden cambiar, donde el acceso a los recursos de nivel de página también debe capturar el cambio.

- Está creando o haciendo referencia a estilos del tema para un control personalizado.

- Tiene previsto ajustar el contenido de <xref:System.Windows.ResourceDictionary> durante la duración de una aplicación.

- Tiene una estructura de recursos complicada que tiene interdependencias, donde puede necesitarse una referencia adelantada. Las referencias de recursos estáticos no admiten las referencias adelantadas, pero las referencias de recursos dinámicos sí que lo hacen porque el recurso no necesita volver a evaluarse hasta el tiempo de ejecución y, por consiguiente, las referencias adelantadas no son un concepto relevante.

- Está haciendo referencia a un recurso que es grande desde la perspectiva de una compilación o espacio de trabajo, y el recurso puede no usarse inmediatamente cuando se carga la página. Las referencias de recursos estáticos siempre se cargan desde XAML cuando se carga la página. Sin embargo, una referencia de recursos dinámicos no se carga hasta que se utiliza.

- Está creando un estilo donde los valores del establecedor pueden provenir de otros valores que están influenciados por temas u otra configuración del usuario.

- Está aplicando recursos en elementos en los que se puede cambiar el elemento primario en el árbol lógico durante la vigencia de la aplicación. Cambiar el elemento primario también cambia potencialmente el ámbito de búsqueda de recursos, por lo que si quiere que el recurso de un elemento primario que se puede cambiar se vuelva a evaluar basándose en el nuevo ámbito, use siempre una referencia de recurso dinámico.

### <a name="dynamic-resource-lookup-behavior"></a>Comportamiento de búsqueda de recursos dinámicos

El comportamiento de búsqueda de recursos para una referencia de recursos dinámicos es paralelo al comportamiento de búsqueda en el código si se llama a <xref:System.Windows.FrameworkElement.FindResource%2A> o <xref:System.Windows.FrameworkElement.SetResourceReference%2A>:

01. La búsqueda comprueba la clave solicitada en el diccionario de recursos que ha definido el elemento que establece la propiedad:

    - Si el elemento define una propiedad <xref:System.Windows.FrameworkElement.Style%2A>, el valor <xref:System.Windows.FrameworkElement.Style?displayProperty=fullName> del elemento tiene su diccionario <xref:System.Windows.Style.Resources> seleccionado.

    - Si el elemento define una propiedad <xref:System.Windows.Controls.Control.Template%2A>, el diccionario <xref:System.Windows.FrameworkTemplate.Resources?displayProperty=fullName> del elemento está seleccionado.

01. La búsqueda recorre el árbol lógico hacia arriba, hasta el elemento primario y su diccionario de recursos. Este proceso continúa hasta que se alcanza el elemento raíz.

01. Se comprueban los recursos de la aplicación. Los recursos de la aplicación son los recursos del diccionario de recursos definidos por el objeto <xref:System.Windows.Application> de la aplicación de WPF.

01. Se comprueba el diccionario de recursos de temas para el tema activo actualmente. Si el tema cambia en tiempo de ejecución, el valor se vuelve a evaluar.

01. Se comprueban los recursos del sistema.

El comportamiento de excepción (si existe) varía:

- Si un recurso se solicitó mediante una llamada <xref:System.Windows.FrameworkElement.FindResource%2A> y no se encontró, se genera una excepción.

- Si un recurso se solicitó mediante una llamada <xref:System.Windows.FrameworkElement.TryFindResource%2A> y no se encontró, no se genera ninguna excepción y el valor que se devuelve es `null`. Si la propiedad que se establece no acepta `null`, entonces sigue siendo posible que se genere una excepción más detallada, en función de la propiedad individual que se establece.

- Si un recurso se solicitó mediante una referencia de recurso dinámico en XAML y no se encontró, el comportamiento depende del sistema de propiedades general. El comportamiento general es como si no se produjera ninguna operación de configuración de propiedad en el nivel en el que existe el recurso. Por ejemplo, si intenta establecer el fondo en un elemento de botón individual con un recurso que no puede evaluarse, entonces no se establece ningún valor, pero el valor efectivo todavía puede provenir de otros participantes del sistema de propiedades y la precedencia de valores. Por ejemplo, el valor de fondo todavía puede provenir de un estilo de botón definido localmente o desde el estilo del tema. Para las propiedades que no se definen mediante los estilos del tema, el valor efectivo después de una evaluación de recursos incorrecta puede provenir del valor predeterminado de los metadatos de la propiedad.

### <a name="restrictions"></a>Restricciones

Las referencias de recursos dinámicos tienen algunas restricciones importantes. Se debe dar como mínimo una de las siguientes condiciones:

- La propiedad que se establece debe ser una propiedad en <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. La propiedad debe estar respaldada por <xref:System.Windows.DependencyProperty>.

- La referencia es para un valor dentro de `StyleSetter`.

- La propiedad que se establece debe ser una propiedad en <xref:System.Windows.Freezable> que se proporciona como valor de una propiedad <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, o un valor <xref:System.Windows.Setter>.

Como la propiedad que se establece debe ser una propiedad <xref:System.Windows.DependencyProperty> o <xref:System.Windows.Freezable>, la mayoría de los cambios de propiedad pueden propagarse a la interfaz de usuario porque se reconoce un cambio de propiedad (el valor de recurso dinámico que se ha cambiado) mediante el sistema de propiedades. La mayoría de los controles incluyen lógica que forzará a otro diseño de un control si <xref:System.Windows.DependencyProperty> cambia y esa propiedad puede afectar al diseño. En cambio, no se garantiza que todas las propiedades que tienen una [extensión de marcado DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md) como su valor proporcionen actualizaciones en tiempo en real en la interfaz de usuario. Esa función todavía puede variar dependiendo de la propiedad, así como dependiendo del tipo que posea la propiedad, o incluso de la estructura lógica de la aplicación.

## <a name="styles-datatemplates-and-implicit-keys"></a>Estilos, plantillas de datos y claves implícitas

Aunque todos los elementos de <xref:System.Windows.ResourceDictionary> deben tener una clave, eso no significa que todos los recursos deban tener un valor `x:Key` explícito. Varios tipos de objetos admiten una clave implícita cuando se definen como un recurso, donde el valor de clave está vinculado al valor de otra propiedad. Este tipo de clave se conoce como clave implícita, mientras que un atributo `x:Key` es una clave explícita. Puede sobrescribir cualquier clave implícita especificando una clave explícita.

Un escenario importante para los recursos es cuando se define un elemento <xref:System.Windows.Style>. De hecho, un elemento <xref:System.Windows.Style> casi siempre se define como una entrada en un diccionario de recursos, porque los estilos están previstos propiamente para que se vuelvan a usar. Para más información acerca de los estilos, consulte [Aplicar estilos y plantillas](styles-templates-overview.md).

Los estilos para los controles pueden crearse y hacerse referencia con una clave implícita. Los estilos de tema que definen la apariencia predeterminada de un control se basan en esta clave implícita. La clave implícita desde el punto de vista de su solicitud, la clave implícita es el elemento <xref:System.Type> del propio control. Desde el punto de vista de la definición de los recursos, la clave implícita es el elemento <xref:System.Windows.Style.TargetType%2A> del estilo. Por lo tanto, si está creando temas para los controles personalizados o está creando estilos que interactúen con los estilos de temas existentes, no necesita especificar una [directiva x:Key](../xaml-services/xkey-directive.md) para el elemento <xref:System.Windows.Style>. Y si quiere usar los estilos temáticos, no necesita especificar ningún estilo. Por ejemplo, la siguiente definición de estilo funciona aunque el recurso <xref:System.Windows.Style> no parece tener una clave:

[!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]

Ese estilo en realidad tiene una clave: la clave implícita `typeof(System.Windows.Controls.Button)`. En el marcado, puede especificar <xref:System.Windows.Style.TargetType%2A> directamente como el nombre de tipo (o puede usar opcionalmente [{x:Type...}](../xaml-services/xtype-markup-extension.md) para devolver <xref:System.Type>.

A través de los mecanismos de estilo de tema predeterminados que usa WPF, ese estilo se aplica como estilo en tiempo de ejecución de <xref:System.Windows.Controls.Button> en la página, aunque el propio elemento <xref:System.Windows.Controls.Button> no intente especificar su propiedad <xref:System.Windows.FrameworkElement.Style%2A> o una referencia de recurso específica al estilo. Su estilo definido en la página se ha detectado en la secuencia de búsqueda antes que el estilo del diccionario de temas, con la misma clave que tiene el estilo del diccionario de temas. Puede especificar simplemente `<Button>Hello</Button>` en cualquier parte de la página; el estilo que haya definido con <xref:System.Windows.Style.TargetType%2A> de `Button` se aplicará a ese botón. Si quiere, todavía puede especificar explícitamente el estilo con el mismo valor de tipo que <xref:System.Windows.Style.TargetType%2A>, para mayor claridad en el marcado, pero esto es opcional.

Las claves implícitas para los estilos no se aplican en un control si `true` es <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A>. (Tenga en cuenta también que <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> se puede establecer como parte del comportamiento nativo de la clase de control, en lugar de explícitamente en una instancia del control). Además, para admitir claves implícitas para escenarios de clase derivada, el control debe reemplazar <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> (todos los controles existentes que se proporcionan como parte de WPF incluyen este reemplazo). Para obtener más información sobre estilos, temas y diseño de control, vea [Instrucciones para el diseño de controles con estilos](../../framework/wpf/controls/guidelines-for-designing-stylable-controls.md).

<xref:System.Windows.DataTemplate> también tiene una clave implícita. La clave implícita de <xref:System.Windows.DataTemplate> es el valor de la propiedad <xref:System.Windows.DataTemplate.DataType%2A>. <xref:System.Windows.DataTemplate.DataType%2A> también se puede especificar como nombre del tipo en lugar de usar explícitamente [{x:Type...}](../xaml-services/xtype-markup-extension.md). Para obtener información, vea [Información general sobre plantillas de datos](../../framework/wpf/data/data-templating-overview.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.ResourceDictionary>
- [Recursos de aplicación](../../framework/wpf/advanced/optimizing-performance-application-resources.md)
- [Recursos y código](../../framework/wpf/advanced/resources-and-code.md)
- [Definición de un recurso y referencias](../../framework/wpf/advanced/how-to-define-and-reference-a-resource.md)
- [Información general sobre la administración de aplicaciones](../../framework/wpf/app-development/application-management-overview.md)
- [Extensión de marcado x:Type](../xaml-services/xtype-markup-extension.md)
- [Extensión de marcado StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md)
- [Extensión de marcado DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md)
