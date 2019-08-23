---
title: Recursos XAML
ms.date: 03/30/2017
helpviewer_keywords:
- reusing resources [WPF]
- resources [WPF], reusing
- reusing commonly defined objects [WPF]
- XAML [WPF], reusing resources
ms.assetid: 91580b89-a0a8-4889-aecb-fddf8e63175f
ms.openlocfilehash: 738a4f397b1677b867126c7bb439b027f951baa0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958813"
---
# <a name="xaml-resources"></a>Recursos XAML
Un recurso es un objeto que se puede volver a usar en diferentes sitios de la aplicación. Pinceles y estilos son ejemplos de recursos. En esta información general se describe cómo usar [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]los recursos de. También puede crear y obtener acceso a recursos mediante código, o bien de forma intercambiable entre código y [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Para obtener más información, vea [recursos y código](resources-and-code.md).  
  
> [!NOTE]
> Los archivos de recursos que se describen en este tema son diferentes de los archivos de recursos que se describen en [archivos de recursos, contenido y datos de aplicaciones de WPF](../app-development/wpf-application-resource-content-and-data-files.md) y distintos de los recursos incrustados o vinculados que se describen en administración de recursos de [aplicación (.net). ](/visualstudio/ide/managing-application-resources-dotnet).  

<a name="usingresources"></a>   
## <a name="using-resources-in-xaml"></a>Uso de recursos en XAML  
 En el ejemplo siguiente se <xref:System.Windows.Media.SolidColorBrush> define como un recurso en el elemento raíz de una página. A continuación, el ejemplo hace referencia al recurso y lo usa para establecer las propiedades de varios elementos <xref:System.Windows.Shapes.Ellipse>secundarios, <xref:System.Windows.Controls.TextBlock>incluidos, y <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]  
  
 Cada elemento de nivel de marco<xref:System.Windows.FrameworkElement> ( <xref:System.Windows.FrameworkContentElement>o) tiene <xref:System.Windows.FrameworkElement.Resources%2A> una propiedad, que es la propiedad que contiene los recursos (como <xref:System.Windows.ResourceDictionary>un) que un recurso define. Puede definir recursos en cualquier elemento. Sin embargo, los recursos se definen con mayor frecuencia en el elemento raíz <xref:System.Windows.Controls.Page> , que se encuentra en el ejemplo.  
  
 Cada recurso en un diccionario de recursos debe tener una clave única. Al definir recursos en el marcado, se asigna la clave única a través de la [Directiva x:Key](../../xaml-services/x-key-directive.md). Normalmente, la clave es una cadena; pero puede también establecerla para otros tipos de objetos usando las extensiones de marcado apropiadas. Las claves que no son de cadena para los recursos se utilizan [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]en algunas áreas de características de, especialmente para los estilos, los recursos de componentes y el estilo de los datos.  
  
 Después de definir un recurso, puede hacer referencia a los recursos que se usarán para un valor de propiedad mediante una sintaxis de extensión de marcado de recursos que especifica el nombre de clave, por ejemplo:  
  
 [!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]  
  
 En el ejemplo anterior, cuando el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cargador procesa el valor `{StaticResource MyBrush}` de la <xref:System.Windows.Controls.Control.Background%2A> propiedad en <xref:System.Windows.Controls.Button>, la lógica de búsqueda de recursos comprueba primero el Diccionario de <xref:System.Windows.Controls.Button> recursos para el elemento. Si <xref:System.Windows.Controls.Button> no tiene una definición de la clave `MyBrush` de recurso (no la tiene; su colección de recursos está vacía), la búsqueda siguiente comprueba el elemento primario <xref:System.Windows.Controls.Button>de, que <xref:System.Windows.Controls.Page>es. Por lo tanto, al definir un recurso en <xref:System.Windows.Controls.Page> el elemento raíz, todos los elementos del árbol lógico <xref:System.Windows.Controls.Page> de pueden tener acceso a él y puede volver a usar el mismo recurso para establecer el valor de cualquier propiedad que acepte <xref:System.Type> el que el recurso representa. En el ejemplo anterior, el mismo `MyBrush` recurso establece dos propiedades diferentes <xref:System.Windows.Controls.Control.Background%2A> : <xref:System.Windows.Shapes.Shape.Fill%2A> de <xref:System.Windows.Controls.Button>y <xref:System.Windows.Shapes.Rectangle>de.  
  
<a name="staticdynamic"></a>   
## <a name="static-and-dynamic-resources"></a>Recursos estáticos y dinámicos  
 Puede hacer referencia a un recurso como un recurso estático o un recurso dinámico. Esto se hace mediante la extensión de [marcado StaticResource](staticresource-markup-extension.md) o la [extensión de marcado DynamicResource](dynamicresource-markup-extension.md). Una extensión de marcado es una característica [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de por la que se puede especificar una referencia de objeto al hacer que la extensión de marcado procese la cadena de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributo y devuelva el objeto a un cargador. Para obtener más información sobre el comportamiento de la extensión de marcado, vea [extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
 Cuando se usa una extensión de marcado, normalmente proporciona uno o varios parámetros en forma de cadena que son procesados por dicha extensión de marcado, en lugar de que se evalúe en el contexto de la propiedad que se va a establecer. La [extensión de marcado StaticResource](staticresource-markup-extension.md) procesa una clave buscando el valor de esa clave en todos los diccionarios de recursos disponibles. Esto sucede durante la carga, que es el punto en el tiempo cuando el proceso de carga necesita asignar el valor de propiedad que acepta la referencia de recurso estático. La [extensión de marcado DynamicResource](dynamicresource-markup-extension.md) procesa en su lugar una clave mediante la creación de una expresión y esa expresión permanece sin evaluar hasta que la aplicación se ejecuta realmente, momento en el que se evalúa la expresión y proporciona un valor.  
  
 Al hacer referencia a un recurso, independientemente de si usa una referencia de recurso estático o una referencia de recurso dinámico, pueden influir las siguientes consideraciones:  
  
- El diseño general de cómo crear los recursos de la aplicación (por página, en la aplicación, de forma dinámica [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], en un ensamblado de solo recursos).  
  
- La función de la aplicación: ¿la actualización de recursos en tiempo real forma parte de los requisitos de la aplicación?  
  
- El comportamiento de búsqueda respectivo de ese tipo de referencia de recurso.  
  
- La propiedad o tipo de recurso determinado y el comportamiento nativo de esos tipos.  
  
### <a name="static-resources"></a>Recursos estáticos  
 Las referencias de recursos estáticos trabajan mejor en las siguientes circunstancias:  
  
- El diseño de la aplicación concentra la mayoría de todos sus recursos en la página o en los diccionarios de recursos en el nivel de aplicación. Las referencias de recursos estáticos no se vuelven a evaluar en función de comportamientos en tiempo de ejecución, como recargar una página y, por tanto, puede haber algunas ventajas de rendimiento para evitar grandes cantidades de referencias de recursos dinámicos cuando no son necesarios por su diseño de aplicaciones y recursos.  
  
- Está estableciendo el valor de una propiedad que no está en <xref:System.Windows.DependencyObject> <xref:System.Windows.Freezable>o.  
  
- Está creando un diccionario de recursos que se compilará en un archivo DLL y que se empaqueta como parte de la aplicación o se comparte entre aplicaciones.  
  
- Está creando un tema para un control personalizado y está definiendo recursos que se usan dentro de los temas. En este caso, normalmente no quiere el comportamiento de búsqueda de referencia de recursos dinámicos, sino el comportamiento de referencia de recursos estáticos, de manera que la búsqueda sea predecible e independiente para el tema. Con una referencia de recursos dinámicos, incluso una referencia dentro de un tema se deja sin evaluar hasta el tiempo de ejecución y es probable que, cuando se aplica el tema, algún elemento local vuelva a definir una clave a la que el tema está intentando hacer referencia, y el elemento local se detectará antes que el propio tema en la búsqueda. Si esto sucede, el tema no se comportará de la manera esperada.  
  
- Está usando recursos para establecer grandes cantidades de propiedades de dependencia. Las propiedades de dependencia tienen un almacenamiento en caché de valores efectivos habilitado por el sistema de propiedades, así que si proporciona un valor para una propiedad de dependencia que pueda evaluarse en tiempo de carga, la propiedad de dependencia no tiene que comprobar una expresión que se ha vuelto a evaluar y puede devolver el último valor efectivo. Esta técnica puede suponer una ventaja de rendimiento.  
  
- Desea cambiar el recurso subyacente para todos los consumidores o desea mantener instancias de escritura independientes para cada consumidor mediante el [atributo x:Shared](../../xaml-services/x-shared-attribute.md).  
  
#### <a name="static-resource-lookup-behavior"></a>Comportamiento de búsqueda de recursos estáticos  
  
1. El proceso de búsqueda comprueba la clave solicitada en el diccionario de recursos que ha definido el elemento que establece la propiedad.  
  
2. Después, el proceso de búsqueda recorre el árbol lógico hacia arriba, hasta el elemento primario y su diccionario de recursos. Esto continúa hasta que se alcanza el elemento raíz.  
  
3. Después, se comprueban los recursos de la aplicación. Los recursos de la aplicación son los recursos del Diccionario de recursos definidos por <xref:System.Windows.Application> el objeto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la aplicación.  
  
 Las referencias de recursos estáticos del interior de un diccionario de recursos deben hacer referencia a un recurso que ya se haya definido léxicamente antes que la referencia de recurso. No se pueden resolver las referencias adelantadas mediante una referencia de recursos estáticos. Por este motivo, si usa referencias de recursos estáticos, debe diseñar la estructura del diccionario de recursos de manera que los recursos previstos para su uso mediante recurso se definan en o cerca del principio de cada diccionario de recursos respectivo.  
  
 La búsqueda de recursos estáticos puede extenderse a los temas o a los recursos del sistema, pero [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esto solo se admite porque el cargador pospone la solicitud. El aplazamiento es necesario, de manera que el tema en tiempo de ejecución en el momento de la carga de la página se aplique correctamente en la aplicación. En cambio, no se recomiendan las referencias de recursos estáticos a las claves que se sabe que solo existen en temas o como recursos del sistema. Esto se debe a que dichas referencias no se vuelven a evaluar si el usuario modifica el tema en tiempo real. Una referencia de recurso dinámico es más confiable cuando solicita un tema o recursos del sistema. La excepción se produce cuando un elemento de tema solicita otro recurso. Estas referencias deben ser referencias de recursos estáticos, por los motivos que se han mencionado anteriormente.  
  
 El comportamiento de excepción si no se detecta una referencia de recursos estáticos varía. Si el recurso se ha aplazado, entonces la excepción se produce en tiempo de ejecución. Si el recurso no se ha aplazado, la excepción se produce en tiempo de carga.  
  
### <a name="dynamic-resources"></a>Recursos dinámicos  
 Los recursos dinámicos trabajan mejor en las siguientes circunstancias:  
  
- El valor del recurso depende de las condiciones que no se conocen hasta el tiempo de ejecución. Esto incluye los recursos del sistema o recursos que, de otro modo, son configurables por el usuario. Por ejemplo, puede crear valores de establecedor que hagan referencia a las propiedades del sistema <xref:System.Windows.SystemColors>, <xref:System.Windows.SystemFonts>tal como <xref:System.Windows.SystemParameters>las expone, o. Estos valores son verdaderamente dinámicos porque proceden en definitiva del entorno en tiempo de ejecución del usuario y del sistema operativo. También puede tener temas en el nivel de aplicación que pueden cambiar, donde el acceso a los recursos de nivel de página también debe capturar el cambio.  
  
- Está creando o haciendo referencia a estilos del tema para un control personalizado.  
  
- Tiene previsto ajustar el contenido de un <xref:System.Windows.ResourceDictionary> durante la duración de la aplicación.  
  
- Tiene una estructura de recursos complicada que tiene interdependencias, donde puede necesitarse una referencia adelantada. Las referencias de recursos estáticos no admiten referencias adelantadas, pero las referencias de recursos dinámicos las admiten porque no es necesario evaluar el recurso hasta el tiempo de ejecución y, por lo tanto, las referencias adelantadas no son un concepto relevante.  
  
- Está haciendo referencia a un recursos que es especialmente grande desde la perspectiva de una compilación o espacio de trabajo, y el recurso puede no usarse inmediatamente cuando se carga la página. Las referencias de recursos estáticos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] siempre se cargan desde que se carga la página; sin embargo, una referencia de recursos dinámicos no se carga hasta que realmente se usa.  
  
- Está creando un estilo donde los valores del establecedor pueden provenir de otros valores que están influenciados por temas u otra configuración del usuario.  
  
- Está aplicando recursos en elementos en los que se puede cambiar el elemento primario en el árbol lógico durante la vigencia de la aplicación. Cambiar el elemento primario también cambia potencialmente el ámbito de búsqueda de recursos, por lo que si quiere que el recurso de un elemento primario que se puede cambiar se vuelva a evaluar basándose en el nuevo ámbito, use siempre una referencia de recurso dinámico.  
  
#### <a name="dynamic-resource-lookup-behavior"></a>Comportamiento de búsqueda de recursos dinámicos  
 El comportamiento de búsqueda de recursos para una referencia de recursos dinámicos es paralelo al comportamiento de búsqueda <xref:System.Windows.FrameworkElement.FindResource%2A> en <xref:System.Windows.FrameworkElement.SetResourceReference%2A>el código si se llama a o.  
  
1. El proceso de búsqueda comprueba la clave solicitada en el diccionario de recursos que ha definido el elemento que establece la propiedad.  
  
    - Si el elemento define una <xref:System.Windows.FrameworkElement.Style%2A> propiedad, <xref:System.Windows.Style> se <xref:System.Windows.Style.Resources%2A> comprueba el Diccionario dentro de.  
  
    - Si el elemento define una <xref:System.Windows.Controls.Control.Template%2A> propiedad, <xref:System.Windows.FrameworkTemplate> se <xref:System.Windows.FrameworkTemplate.Resources%2A> comprueba el Diccionario dentro de.  
  
2. Después, el proceso de búsqueda recorre el árbol lógico hacia arriba, hasta el elemento primario y su diccionario de recursos. Esto continúa hasta que se alcanza el elemento raíz.  
  
3. Después, se comprueban los recursos de la aplicación. Los recursos de la aplicación son los recursos del Diccionario de recursos definidos por <xref:System.Windows.Application> el objeto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la aplicación.  
  
4. Se comprueba el diccionario de recursos de temas para el tema activo actualmente. Si el tema cambia en tiempo de ejecución, el valor se vuelve a evaluar.  
  
5. Se comprueban los recursos del sistema.  
  
 El comportamiento de excepción (si existe) varía:  
  
- Si una <xref:System.Windows.FrameworkElement.FindResource%2A> llamada solicitó un recurso y no se encontró, se produce una excepción.  
  
- Si una <xref:System.Windows.FrameworkElement.TryFindResource%2A> llamada solicitó un recurso y no se encontró, no se produce ninguna excepción, pero el valor devuelto es `null`. Si la propiedad que se está configurando no acepta `null`, sigue siendo posible que se genere una excepción más profunda (esto depende de la propiedad individual que se establece).  
  
- Si una referencia de recursos dinámicos solicitó un recurso [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]en y no se encontró, el comportamiento depende del sistema de propiedades general, pero el comportamiento general es como si no se produjera ninguna operación de configuración de propiedad en el nivel en el que existe el recurso. Por ejemplo, si intenta establecer el fondo en un elemento de botón individual con un recurso que no puede evaluarse, entonces no se establece ningún valor, pero el valor efectivo todavía puede provenir de otros participantes del sistema de propiedades y la precedencia de valores. Por ejemplo, el valor de fondo todavía puede provenir de un estilo de botón definido localmente, o desde el estilo del tema. Para las propiedades que no se definen mediante los estilos del tema, el valor efectivo después de una evaluación de recursos incorrecta puede provenir del valor predeterminado de los metadatos de la propiedad.  
  
#### <a name="restrictions"></a>Restricciones  
 Las referencias de recursos dinámicos tienen algunas restricciones importantes. Debe cumplirse al menos una de las siguientes:  
  
- La propiedad que se establece debe ser una propiedad en <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Esa propiedad debe estar respaldada por un <xref:System.Windows.DependencyProperty>.  
  
- La referencia es para un valor dentro <xref:System.Windows.Style> <xref:System.Windows.Setter>de.  
  
- La propiedad que se establece debe ser una propiedad en <xref:System.Windows.Freezable> que se proporciona como un valor de una <xref:System.Windows.FrameworkElement> propiedad o <xref:System.Windows.FrameworkContentElement> , o bien un <xref:System.Windows.Setter> valor.  
  
 Dado que la propiedad que se establece debe <xref:System.Windows.DependencyProperty> ser <xref:System.Windows.Freezable> una propiedad o, la mayoría de los cambios de propiedad se pueden propagar a la interfaz de usuario porque el sistema de propiedades confirma un cambio de propiedad (el valor de recurso dinámico cambiado). La mayoría de los controles incluyen lógica que forzará otro diseño de un <xref:System.Windows.DependencyProperty> control si un cambio y esa propiedad pueden afectar al diseño. Sin embargo, no se garantiza que todas las propiedades que tienen una [extensión de marcado DynamicResource](dynamicresource-markup-extension.md) como valor proporcionen el valor de tal forma que se actualicen en tiempo real en la interfaz de usuario. Esa función todavía puede variar dependiendo de la propiedad, así como dependiendo del tipo que posea la propiedad, o incluso de la estructura lógica de la aplicación.  
  
<a name="stylesimplicitkeys"></a>   
## <a name="styles-datatemplates-and-implicit-keys"></a>Estilos, plantillas de datos y claves implícitas  
 Anteriormente, se indicó que todos los elementos de un <xref:System.Windows.ResourceDictionary> deben tener una clave. Sin embargo, esto no significa que todos los recursos deben tener un `x:Key`explícito. Varios tipos de objetos admiten una clave implícita cuando se definen como un recurso, donde el valor de clave está vinculado al valor de otra propiedad. Esto se conoce como una clave implícita, mientras que `x:Key` un atributo es una clave explícita. Puede sobrescribir cualquier clave implícita especificando una clave explícita.  
  
 Un escenario muy importante para los recursos es cuando se define <xref:System.Windows.Style>un. De hecho, un <xref:System.Windows.Style> se define casi siempre como una entrada en un diccionario de recursos, porque los estilos están pensados de forma inherente para reutilizarlos. Para obtener más información sobre los estilos, vea [aplicar estilos y plantillas](../controls/styling-and-templating.md).  
  
 Los estilos para los controles pueden crearse y hacerse referencia con una clave implícita. Los estilos de tema que definen la apariencia predeterminada de un control se basan en esta clave implícita. La clave implícita desde el punto de vista de solicitarlo es <xref:System.Type> el del propio control. La clave implícita desde el punto de vista de definir el recurso <xref:System.Windows.Style.TargetType%2A> es el del estilo. Por lo tanto, si está creando temas para controles personalizados, creando estilos que interactúen con los estilos de tema existentes, no es necesario especificar una [Directiva x:Key](../../xaml-services/x-key-directive.md) para eso <xref:System.Windows.Style>. Y si quiere usar los estilos temáticos, no necesita especificar ningún estilo. Por ejemplo, la siguiente definición de estilo funciona, aunque el <xref:System.Windows.Style> recurso no parezca tener una clave:  
  
 [!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]  
  
 Ese estilo realmente tiene una clave: la clave `typeof(` <xref:System.Windows.Controls.Button> `)`implícita. En el marcado, puede especificar <xref:System.Windows.Style.TargetType%2A> directamente como el nombre de tipo (o puede usar opcionalmente [{x:Type...}](../../xaml-services/x-type-markup-extension.md) para devolver un <xref:System.Type>valor.  
  
 A través de los mecanismos de estilo de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]tema predeterminados que usa, ese estilo se aplica <xref:System.Windows.Controls.Button> como estilo en tiempo de ejecución de <xref:System.Windows.Controls.Button> un en la página, aunque el <xref:System.Windows.FrameworkElement.Style%2A> propio no intenta especificar su propiedad o un recurso específico. referencia al estilo. El estilo definido en la página se encuentra anteriormente en la secuencia de búsqueda que el estilo del Diccionario de temas, con la misma clave que el estilo del Diccionario de temas. Podría especificar `<Button>Hello</Button>` solo cualquier lugar de la página y el estilo que definió con <xref:System.Windows.Style.TargetType%2A> de `Button` se aplicaría a ese botón. Si lo desea, todavía puede especificar explícitamente el estilo con el mismo valor de tipo <xref:System.Windows.Style.TargetType%2A>que, para mayor claridad en el marcado, pero esto es opcional.  
  
 Las claves implícitas para los estilos no se aplican en <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> un `true` control si es ( <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> también tenga en cuenta que se puede establecer como parte del comportamiento nativo de la clase de control, en lugar de explícitamente en una instancia del control). Además, para admitir claves implícitas para escenarios de clase derivada, el control debe invalidar <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> (todos los controles existentes que se proporcionan [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como parte de esto). Para obtener más información sobre los estilos, los temas y el diseño de controles, vea [instrucciones para el diseño de controles con estilo](../controls/guidelines-for-designing-stylable-controls.md).  
  
 <xref:System.Windows.DataTemplate>también tiene una clave implícita. La clave implícita de un <xref:System.Windows.DataTemplate> es el <xref:System.Windows.DataTemplate.DataType%2A> valor de propiedad. <xref:System.Windows.DataTemplate.DataType%2A>también se puede especificar como el nombre del tipo en lugar de usar explícitamente [{x:Type...}](../../xaml-services/x-type-markup-extension.md). Para obtener más información, vea [información general sobre plantillas de datos](../data/data-templating-overview.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.ResourceDictionary>
- [Recursos de la aplicación](optimizing-performance-application-resources.md)
- [Recursos y código](resources-and-code.md)
- [Definir y hacer referencia a un recurso](how-to-define-and-reference-a-resource.md)
- [Información general sobre la administración de aplicaciones](../app-development/application-management-overview.md)
- [x:Type (extensión de marcado)](../../xaml-services/x-type-markup-extension.md)
- [StaticResource (extensión de marcado)](staticresource-markup-extension.md)
- [DynamicResource (extensión de marcado)](dynamicresource-markup-extension.md)
