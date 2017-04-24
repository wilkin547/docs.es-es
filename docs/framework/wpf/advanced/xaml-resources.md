---
title: "Recursos XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "reutilizar recursos"
  - "recursos, reutilizar"
  - "reutilizar los objetos que se definen habitualmente"
  - "XAML, reutilizar recursos"
ms.assetid: 91580b89-a0a8-4889-aecb-fddf8e63175f
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# Recursos XAML
Un recurso es un objeto que se puede reutilizar en diferentes lugares de la aplicación. Pinceles y estilos son ejemplos de recursos. Esta introducción describe cómo utilizar los recursos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. También puede crear y tener acceso a recursos mediante código o indistintamente entre código y [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Para obtener más información, consulte [recursos y código](../../../../docs/framework/wpf/advanced/resources-and-code.md).  
  
> [!NOTE]
>  Los archivos de recursos que se describen en este tema son diferentes de los archivos de recursos se describen en [archivos de datos, el contenido y el recurso de aplicación de WPF](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md) y diferente de los recursos incrustados o vinculados se describe en [administración de recursos (. NET)](../Topic/Managing%20Application%20Resources%20\(.NET\).md).  
  
   
  
<a name="usingresources"></a>   
## <a name="using-resources-in-xaml"></a>Uso de recursos en XAML  
 En el ejemplo siguiente se define un <xref:System.Windows.Media.SolidColorBrush> como un recurso en el elemento raíz de una página. En el ejemplo, a continuación, hace referencia al recurso y lo usa para establecer las propiedades de varios elementos secundarios, incluidos una <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Controls.TextBlock>y un <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[FEResourceSH_snip#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]  
  
 Cada elemento de nivel de marco ( <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>) tiene un <xref:System.Windows.FrameworkElement.Resources%2A> propiedad, que es la propiedad que contiene los recursos (como un <xref:System.Windows.ResourceDictionary>) que define un recurso. Puede definir recursos en cualquier elemento. Sin embargo, los recursos normalmente se definen en el elemento raíz, que es <xref:System.Windows.Controls.Page> en el ejemplo.  
  
 Cada recurso en un diccionario de recursos debe tener una clave única. Al definir los recursos en el marcado, le asigna la clave única a través de la [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md). Normalmente, la clave es una cadena; Sin embargo, puede también establecer para otros tipos de objetos utilizando las extensiones de marcado apropiado. Las claves que no son cadenas de recursos utiliza ciertas áreas de características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], en particular para los estilos, recursos de componente y estilos de datos.  
  
 Después de definir un recurso, puede hacer referencia a los recursos que se usará para un valor de propiedad mediante una sintaxis de extensión de marcado de recursos que especifica el nombre de clave, por ejemplo:  
  
 [!code-xml[FEResourceSH_snip#KeyNameUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]  
  
 En el ejemplo anterior, cuando el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cargador procesa el valor `{StaticResource MyBrush}` para el <xref:System.Windows.Controls.Control.Background%2A> propiedad <xref:System.Windows.Controls.Button>, la lógica de búsqueda de recursos comprueba en primer lugar el diccionario de recursos para la <xref:System.Windows.Controls.Button> elemento. Si <xref:System.Windows.Controls.Button> no tiene una definición de la clave de recurso `MyBrush` (no la tiene; su colección de recursos está vacía), a continuación, la búsqueda comprueba el elemento primario del <xref:System.Windows.Controls.Button>, que es <xref:System.Windows.Controls.Page>. Por lo tanto, al definir un recurso en el <xref:System.Windows.Controls.Page> elemento raíz, todos los elementos en el árbol lógico de la <xref:System.Windows.Controls.Page> puede tener acceso a él y puede reutilizar el mismo recurso para establecer el valor de cualquier propiedad que acepta el <xref:System.Type> que representa el recurso. En el ejemplo anterior, el mismo `MyBrush` recursos establecen dos propiedades diferentes: la <xref:System.Windows.Controls.Control.Background%2A> de un <xref:System.Windows.Controls.Button>y el <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle>.  
  
<a name="staticdynamic"></a>   
## <a name="static-and-dynamic-resources"></a>Recursos estáticos y dinámicos  
 Puede hacer referencia a un recurso como un recurso estático o un recurso dinámico. Esto se hace utilizando la [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) o [extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md). Una extensión de marcado es una característica de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] según el cual se puede especificar una referencia de objeto que tiene la extensión de marcado procesar la cadena del atributo y devolver el objeto a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cargador. Para obtener más información sobre el comportamiento de la extensión de marcado, consulte [las extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Cuando se utiliza una extensión de marcado, normalmente se proporciona uno o varios parámetros en forma de cadena que son procesados por dicha extensión de marcado, en lugar de que se evalúa en el contexto de la propiedad que se va a establecer. El [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) procesa una clave buscando el valor para esa clave en todos los diccionarios de recursos disponibles. Esto sucede durante la carga, que es el punto en el tiempo cuando el proceso de carga necesita asignar el valor de propiedad que acepta la referencia de recurso estático. El [extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) en su lugar los procesos una clave mediante la creación de una expresión y dicha expresión permanece sin evaluar hasta que realmente se ejecuta la aplicación, momento en que la expresión se evalúa y proporciona un valor.  
  
 Al hacer referencia a un recurso, independientemente de si usa una referencia de recurso estático o una referencia de recurso dinámico pueden influir en las siguientes consideraciones:  
  
-   El diseño general de cómo crear los recursos de la aplicación (por página, en la aplicación, sueltos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], en un ensamblado sólo de recursos).  
  
-   ¿La funcionalidad de la aplicación: actualización de recursos en tiempo real forma parte de los requisitos de la aplicación?  
  
-   El comportamiento de búsqueda respectivos de ese tipo de referencia de recurso.  
  
-   La propiedad o tipo de recurso y el comportamiento nativo de esos tipos.  
  
### <a name="static-resources"></a>Recursos estáticos  
 Las referencias de recursos estáticos trabajo mejor en las siguientes circunstancias:  
  
-   El diseño de la aplicación concentra la mayoría de todos sus recursos en la página o recurso de nivel de aplicación diccionarios. Referencias de recursos estáticos no se reevalúa en función de comportamientos en tiempo de ejecución, como recargar una página y, por tanto, puede haber algunas ventajas de rendimiento para evitar grandes cantidades de referencias de recursos dinámicos cuando no son necesarios por su diseño de aplicaciones y recursos.  
  
-   Se establece el valor de una propiedad que no se encuentra en un <xref:System.Windows.DependencyObject> o un <xref:System.Windows.Freezable>.  
  
-   Se crea un diccionario de recursos que se compilan en un archivo DLL y empaqueta como parte de la aplicación o compartido entre aplicaciones.  
  
-   Se está creando un tema para un control personalizado y está definiendo recursos que se utilizan dentro de los temas. En este caso, normalmente no desea el comportamiento de búsqueda de referencia de recursos dinámicos, sino el comportamiento de referencia de recurso estático para que la búsqueda sea predecible e independiente para el tema. Con un recurso dinámico referencia, incluso que una referencia dentro de un tema se deja sin evaluar hasta el tiempo de ejecución y es probable que, cuando se aplica el tema, algún elemento local redefina una clave a la que el tema está intentando hacer referencia a y el elemento local se encontrará antes que el tema en la búsqueda. Si esto sucede, el tema no se comportará de la manera esperada.  
  
-   Recursos que usa para establecer un gran número de propiedades de dependencia. Propiedades de dependencia tienen valor efectivo la memoria caché habilitada en el sistema de propiedades, por lo que si proporciona un valor para una propiedad de dependencia que se puede evaluar en tiempo de carga, la propiedad de dependencia no tiene que comprobar si una expresión que se ha vuelto a evaluar y puede devolver el último valor efectivo. Esta técnica puede ser una ventaja de rendimiento.  
  
-   Para cambiar el recurso subyacente para todos los consumidores o desea mantener instancias modificables independientes para cada consumidor utilizando la [x: Shared Attribute](../../../../docs/framework/xaml-services/x-shared-attribute.md).  
  
#### <a name="static-resource-lookup-behavior"></a>Comportamiento de búsqueda de recursos estáticos  
  
1.  El proceso de búsqueda comprueba la clave solicitada en el diccionario de recursos definida por el elemento que establece la propiedad.  
  
2.  El proceso de búsqueda, a continuación, recorre el árbol lógico hacia arriba, el elemento primario y su diccionario de recursos. Este proceso continúa hasta que se alcanza el elemento raíz.  
  
3.  A continuación, se comprueban los recursos de la aplicación. Recursos de la aplicación son aquellos recursos dentro del diccionario de recursos definido por el <xref:System.Windows.Application> objeto para su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación.  
  
 Referencias de recursos estáticos desde dentro de un diccionario de recursos deben hacer referencia a un recurso que ya se ha definido léxicamente antes que la referencia de recurso. No se puede resolver las referencias adelantadas mediante una referencia de recurso estático. Por este motivo, si utiliza referencias de recursos estáticos, debe diseñar la estructura de diccionario de recursos que se definen los recursos pensados para uso en o cerca del principio de los respectivos diccionarios.  
  
 Puede ampliar la búsqueda de recursos estáticos en temas o en los recursos del sistema, pero esto sólo se admite porque el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cargador aplaza la solicitud. El aplazamiento es necesario para que se aplica el tema en tiempo de ejecución en el momento en que la página se carga correctamente a la aplicación. Sin embargo, referencias de recursos estáticos a claves que se sabe que sólo existen en temas o como no se recomiendan los recursos del sistema. Esto es porque esas referencias no se vuelven a evaluar si el tema cambia por el usuario en tiempo real. Una referencia de recurso dinámico es más confiable cuando solicitan recursos del tema o del sistema. La excepción es cuando el propio elemento del tema solicita otro recurso. Estas referencias deberían ser referencias de recursos estáticos, por las razones mencionadas anteriormente.  
  
 El comportamiento de excepción si no se encuentra una referencia de recurso estático varía. Si se aplaza el recurso, la excepción se produce en tiempo de ejecución. Si no se difirió el recurso, la excepción se produce en tiempo de carga.  
  
### <a name="dynamic-resources"></a>Recursos dinámicos  
 Recursos dinámicos funcionan mejor en las circunstancias siguientes:  
  
-   El valor del recurso depende de condiciones que no se conocen hasta el tiempo de ejecución. Esto incluye los recursos del sistema o recursos que son configurables por el usuario en caso contrario. Por ejemplo, puede crear valores de establecedor que hacen referencia a propiedades del sistema, tal como lo expone <xref:System.Windows.SystemColors>, <xref:System.Windows.SystemFonts>, o <xref:System.Windows.SystemParameters>. Estos valores son auténticamente dinámicos porque proceden el entorno en tiempo de ejecución del usuario y del sistema operativo. También es posible que tenga temas de nivel de aplicación que pueden cambiar, donde el acceso a recursos de nivel de página también debe capturar el cambio.  
  
-   Está creando o hacer referencia a los estilos del tema para un control personalizado.  
  
-   Se va a ajustar el contenido de un <xref:System.Windows.ResourceDictionary> durante un período de duración de la aplicación.  
  
-   Tiene una estructura de recursos compleja que tiene interdependencias, donde puede requerirse una referencia adelantada. Referencias de recursos estáticos no admiten referencias adelantadas, pero las referencias de recursos dinámicos son compatibles con ellos porque no es necesario que el recurso se evalúan hasta el tiempo de ejecución y referencias adelantadas, por tanto, no son un concepto relevante.  
  
-   Hace referencia a un recurso que es especialmente grande desde la perspectiva de compilación o espacio de trabajo y el recurso no podría utilizarse inmediatamente cuando se carga la página. Referencias de recursos estáticos siempre se cargan desde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cuando se cargue la página; sin embargo, una referencia de recurso dinámico no se carga hasta que se usa realmente.  
  
-   Se crea un estilo donde valores establecedor podrían provenir de otros valores que se ven afectadas por los temas u otra configuración de usuario.  
  
-   Está aplicando recursos a elementos que podrían ser cambia de elemento primario en el árbol lógico durante la duración de la aplicación. Cambiar el elemento primario potencialmente también cambia el ámbito de búsqueda de recursos, por lo que si desea que el recurso de un elemento primario a evaluarse según el nuevo ámbito, utilice siempre una referencia de recurso dinámico.  
  
#### <a name="dynamic-resource-lookup-behavior"></a>Comportamiento de búsqueda de recursos dinámicos  
 Comportamiento de búsqueda de recursos de una referencia de recurso dinámico es similar al comportamiento de búsqueda en el código a si se llama a <xref:System.Windows.FrameworkElement.FindResource%2A> o <xref:System.Windows.FrameworkElement.SetResourceReference%2A>.  
  
1.  El proceso de búsqueda comprueba la clave solicitada en el diccionario de recursos definida por el elemento que establece la propiedad.  
  
    -   Si el elemento define un <xref:System.Windows.FrameworkElement.Style%2A> propiedad, el <xref:System.Windows.Style.Resources%2A> diccionario dentro de la <xref:System.Windows.Style> está activada.  
  
    -   Si el elemento define un <xref:System.Windows.Controls.Control.Template%2A> propiedad, el <xref:System.Windows.FrameworkTemplate.Resources%2A> diccionario dentro de la <xref:System.Windows.FrameworkTemplate> está activada.  
  
2.  El proceso de búsqueda, a continuación, recorre el árbol lógico hacia arriba, el elemento primario y su diccionario de recursos. Este proceso continúa hasta que se alcanza el elemento raíz.  
  
3.  A continuación, se comprueban los recursos de la aplicación. Recursos de la aplicación son aquellos recursos dentro del diccionario de recursos definido por el <xref:System.Windows.Application> objeto para su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación.  
  
4.  Diccionario de recursos está activada, el tema activo actualmente. Si el tema cambia en tiempo de ejecución, se vuelve a evaluar el valor.  
  
5.  Se comprueban los recursos del sistema.  
  
 Comportamiento de excepción (si existe) varía:  
  
-   Si se solicita un recurso mediante un <xref:System.Windows.FrameworkElement.FindResource%2A> llamar y no se encuentra, se produce una excepción.  
  
-   Si se solicita un recurso mediante un <xref:System.Windows.FrameworkElement.TryFindResource%2A> llamada y no se encontró ninguna excepción, pero el valor devuelto es `null`. Si la propiedad establecida no acepta `null`, es posible que se producirá una excepción más profunda (Esto depende de la propiedad individual que se va a establecer).  
  
-   Si se solicita un recurso mediante una referencia de recurso dinámico en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]y fue no se encuentra, a continuación, el comportamiento depende del sistema de propiedades general, pero el comportamiento general es como si se ha producido ninguna operación de configuración de la propiedad en el nivel donde existe el recurso. Por ejemplo, si se intenta establecer el fondo de un elemento de botón individual utilizando un recurso que no se pudo evaluar, a continuación, ningún conjunto de valores, pero el valor efectivo todavía puede proceder de otros participantes en la prioridad de sistema y el valor de propiedad. Por ejemplo, el valor del fondo todavía podría proceder de un estilo de botón definido localmente o del estilo del tema. Para las propiedades que no están definidos en los estilos del tema, el valor efectivo después de una evaluación de recursos con errores podría proceder del valor predeterminado en los metadatos de propiedad.  
  
#### <a name="restrictions"></a>Restricciones  
 Referencias de recursos dinámicos tienen algunas restricciones importantes. Debe cumplirse al menos uno de los siguientes:  
  
-   La propiedad que se establece debe ser una propiedad en un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Que la propiedad debe estar respaldada por un <xref:System.Windows.DependencyProperty>.  
  
-   La referencia es para un valor dentro de un <xref:System.Windows.Style><xref:System.Windows.Setter>.  
  
-   La propiedad que se establece debe ser una propiedad en un <xref:System.Windows.Freezable> que se proporciona como un valor de un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> propiedad, o un <xref:System.Windows.Setter> valor.  
  
 Dado que la propiedad que se establece debe ser una <xref:System.Windows.DependencyProperty> o <xref:System.Windows.Freezable> propiedad, pueden propagar la mayoría de los cambios de propiedad a la interfaz de usuario porque un cambio de propiedad (el valor de recurso dinámico modificado) está confirmado por el sistema de propiedades. La mayoría de los controles incluyen lógica que forzará otro diseño de un control si un <xref:System.Windows.DependencyProperty> cambios y que propiedad podría afectar al diseño. Sin embargo, no todas las propiedades que tienen un [extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) como su valor se garantiza que proporcione el valor de tal manera que actualizar en tiempo real en la interfaz de usuario. Esa funcionalidad podría variar dependiendo de la propiedad, así como del tipo que posee la propiedad, o incluso la estructura lógica de la aplicación.  
  
<a name="stylesimplicitkeys"></a>   
## <a name="styles-datatemplates-and-implicit-keys"></a>Las claves implícitas, estilos y DataTemplates  
 Anteriormente, hemos dicho que todos los elementos de un <xref:System.Windows.ResourceDictionary> deben tener una clave. Sin embargo, eso no significa que todos los recursos deben tener una explícita `x:Key`. Varios tipos de objetos admiten una clave implícita cuando se define como un recurso, donde el valor de clave está vinculado al valor de otra propiedad. Esto se conoce como una clave implícita, mientras que un `x:Key` atributo es una clave explícita. Puede sobrescribir cualquier clave implícita especificando una clave explícita.  
  
 Un escenario muy importante para los recursos es al definir una <xref:System.Windows.Style>. De hecho, un <xref:System.Windows.Style> casi siempre se define como una entrada en un diccionario de recursos, porque los estilos están pensados intrínsecamente para su reutilización. Para obtener más información sobre los estilos, consulte [estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Estilos para los controles se pueden crear con y hace referencia a una clave implícita. Los estilos del tema que definen la apariencia predeterminada de un control se basan en esta clave implícita. La clave implícita desde el punto de vista de solicitarlo es el <xref:System.Type> del propio control. La clave implícita desde el punto de vista de la definición del recurso es el <xref:System.Windows.Style.TargetType%2A> del estilo. Por lo tanto, si está creando temas para controles personalizados, crear estilos que interactúan con estilos de tema existentes no necesita especificar un [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) para que <xref:System.Windows.Style>. Y si desea utilizar los estilos de tema, no necesitará especificar cualquier estilo en absoluto. Por ejemplo, la definición de estilo siguiente funciona, aunque el <xref:System.Windows.Style> recursos no parecen tener una clave:  
  
 [!code-xml[FEResourceSH_snip#ImplicitStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]  
  
 Que estilo realmente tiene una clave: la clave implícita `typeof(` <xref:System.Windows.Controls.Button>`)`. En el marcado, puede especificar un <xref:System.Windows.Style.TargetType%2A> directamente como el tipo de nombre (o puede utilizar opcionalmente [{x: Type...}](../../../../docs/framework/xaml-services/x-type-markup-extension.md) para devolver un <xref:System.Type>.  
  
 A través de los mecanismos de estilo del tema predeterminado utilizados por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que se aplica el estilo como estilo de tiempo de ejecución de un <xref:System.Windows.Controls.Button> en la página, incluso aunque el <xref:System.Windows.Controls.Button> propio no intenta especificar su <xref:System.Windows.FrameworkElement.Style%2A> propiedad o una referencia de recurso específicos al estilo. El estilo definido en la página se encuentra anteriormente en la secuencia de búsqueda anteriores a estilo, con la misma clave que tiene el estilo de diccionario de tema. También podría especificar `<Button>Hello</Button>` en cualquier parte de la página y el estilo definido con <xref:System.Windows.Style.TargetType%2A> de `Button` se aplicaría a ese botón. Si lo desea, puede clave explícitamente el estilo con el mismo tipo de valor como <xref:System.Windows.Style.TargetType%2A>, para mayor claridad en el marcado, pero que es opcional.  
  
 Las claves implícitas para los estilos no se aplican en un control si <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> es `true` (tenga en cuenta también que <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> se podría establecer como parte del comportamiento nativo para la clase de control, en lugar de explícitamente en una instancia del control). Además, para admitir las claves implícitas para los escenarios de clase derivada, el control debe invalidar <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> (todos los controles existentes proporcionados como parte de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hacerlo). Para obtener más información sobre los estilos, temas y diseño de control, consulte [directrices para diseñar controles con estilos](../../../../docs/framework/wpf/controls/guidelines-for-designing-stylable-controls.md).  
  
 <xref:System.Windows.DataTemplate> también tiene una clave implícita. La clave implícita para un <xref:System.Windows.DataTemplate> es el <xref:System.Windows.DataTemplate.DataType%2A> valor de propiedad.                  <xref:System.Windows.DataTemplate.DataType%2A> también puede especificarse como el nombre del tipo en lugar de forma explícita mediante [{x: Type...} ](../../../../docs/framework/xaml-services/x-type-markup-extension.md). Para obtener más información, consulte [información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.ResourceDictionary>   
 [Recursos de la aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Recursos y código](../../../../docs/framework/wpf/advanced/resources-and-code.md)   
 [Definir y hacer referencia a un recurso](../../../../docs/framework/wpf/advanced/how-to-define-and-reference-a-resource.md)   
 [Introducción a Application Management](../../../../docs/framework/wpf/app-development/application-management-overview.md)   
 [Extensión de marcado x: Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md)   
 [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)   
 [Extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)