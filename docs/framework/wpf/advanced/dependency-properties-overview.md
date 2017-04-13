---
title: "Informaci&#243;n general sobre las propiedades de dependencia | Microsoft Docs"
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
  - "propiedades asociadas"
  - "enlace de datos"
  - "propiedades de dependencia"
  - "propiedades, asociadas"
  - "propiedades, información general"
  - "recursos, referencias a"
  - "estilos"
ms.assetid: d119d00c-3afb-48d6-87a0-c4da4f83dee5
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Informaci&#243;n general sobre las propiedades de dependencia
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un conjunto de servicios que se pueden utilizar para extender la funcionalidad de una propiedad de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  Colectivamente, estos servicios se conocen como el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Una propiedad que está respaldada por el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se conoce como [propiedad de dependencia](GTMT). En esta introducción se describe el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y las funciones de una [propiedad de dependencia](GTMT). Esto incluye cómo utilizar [propiedades de dependencia](GTMT) existentes en XAML y en el código.  Esta información general también presenta aspectos especializados de las propiedades de dependencia, tales como los metadatos de propiedades de dependencia y cómo crear una propiedad de dependencia propia en una clase personalizada.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se asume que tiene conocimientos básicos sobre [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y sobre programación orientada a objetos.  Para seguir los ejemplos de este tema, también debe entender [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y debe saber escribir aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Para obtener más información, consulte [Tutorial: Introducción a WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
<a name="why_dependency_properties"></a>   
## Propiedades de dependencia y propiedades de CLR  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], las propiedades se exponen normalmente como propiedades [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  En un nivel básico, podría interactuar directamente con estas propiedades y nunca sabría que se implementan como una [propiedad de dependencia](GTMT).  Sin embargo, es recomendable conocer algunas o todas las características del sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], para poder aprovechar estas características.  
  
 El propósito de las [propiedades de dependencia](GTMT) es proporcionar una manera de calcular el valor de una propiedad en función del valor de otras entradas.  Estas otras entradas pueden incluir propiedades del sistema tales como temas y preferencias del usuario, mecanismos de determinación de propiedad Just\-In\-Time tales como el enlace de datos y las animaciones o guiones gráficos, plantillas del uso múltiple tales como recursos y estilos, o valores conocidos a través de relaciones de elementos primarios\-secundarios con otros elementos del árbol de elementos.  Además, una [propiedad de dependencia](GTMT) se puede implementar para que proporcione validación autónoma, valores predeterminados, devoluciones de llamada que supervisen los cambios de otras propiedades y un sistema que pueda forzar valores de propiedad en función de información que puede estar disponible en tiempo de ejecución.  Las clases derivadas también pueden cambiar algunas características concretas de una propiedad existente invalidando metadatos de propiedades de dependencia, en lugar de reemplazar la implementación real de propiedades existentes o crear propiedades nuevas.  
  
 En la referencia de SDK, puede identificar qué propiedad es una propiedad de dependencia por la presencia de la sección de Información de propiedad de dependencia en la página de referencia administrada para esa propiedad.  La sección de Información de propiedad de dependencia incluye un vínculo al campo identificador de <xref:System.Windows.DependencyProperty> para esa propiedad de dependencia y también incluye una lista de las opciones de metadatos establecidas para esa propiedad, información de invalidación por clases y otros detalles.  
  
<a name="back_dependency_properties"></a>   
## Propiedades CLR de respaldo de propiedades de dependencia  
 Las [propiedades de dependencia](GTMT) y el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] extienden la funcionalidad de propiedad proporcionando un tipo que respalda una propiedad, como implementación alternativa al modelo estándar de respaldar la propiedad con un campo privado.  El nombre de este tipo es <xref:System.Windows.DependencyProperty>.  El otro tipo importante que define el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es <xref:System.Windows.DependencyObject>.<xref:System.Windows.DependencyObject> define la clase base que puede registrar y poseer una [propiedad de dependencia](GTMT).  
  
 A continuación se ofrece un resumen de la terminología que se utiliza en esta documentación de [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] cuando se tratan las [propiedades de dependencia](GTMT):  
  
-   **Propiedad de dependencia:** una propiedad respaldada por un objeto <xref:System.Windows.DependencyProperty>.  
  
-   **Identificador de propiedad de dependencia:** una instancia de <xref:System.Windows.DependencyProperty>, que se obtiene como valor de retorno al registrar una [propiedad de dependencia](GTMT) y, a continuación, se almacena como miembro estático de una clase.  Este identificador se utiliza como parámetro para muchas de las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] que interactúan con el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   "**"Contenedor" CLR:** implementaciones reales de lectura y escritura de la propiedad.  Estas implementaciones incorporan el identificador de propiedad de dependencia utilizándolo en las llamadas a <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A>, proporcionando así el respaldo para la propiedad utilizando el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 En el ejemplo siguiente se muestra la propiedad [propiedad de dependencia](GTMT) `IsSpinning` y se muestra la relación del identificador <xref:System.Windows.DependencyProperty> con la propiedad a la que respalda.  
  
 [!code-csharp[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic)]
 [!code-vb[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#dpformbasic)]  
[!code-csharp[PropertiesOvwSupport#DPFormBasic2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic2)]  
  
 La convención de nomenclatura de la propiedad y su campo de respaldo <xref:System.Windows.DependencyProperty> es importante.  El nombre del campo siempre es el nombre de la propiedad, con el sufijo `Property`.  Para obtener más información sobre esta convención y sus razones, vea [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
<a name="setting_property_values"></a>   
## Establecer valores de propiedad  
 Puede establecer propiedades en código o en XAML.  
  
<a name="local_property_values"></a>   
### Establecer valores de propiedad en XAML  
 En el siguiente ejemplo de XAML se especifica el rojo como color de fondo de un botón.  En este ejemplo se muestra un caso donde el analizador de XAML de WPF convierte el tipo de un valor de cadena simple de un atributo XAML en un tipo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(<xref:System.Windows.Media.Color>, mediante <xref:System.Windows.Media.SolidColorBrush>\) en el código generado.  
  
 [!code-xml[PropertiesOvwSupport#MostBasicProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#mostbasicproperty)]  
  
 XAML admite diversas formas de sintaxis para establecer propiedades.  La sintaxis a utilizar para una propiedad determinada dependerá del tipo de valor que utilice una propiedad, así como de otros factores tales como la presencia de un convertidor de tipos.  Para obtener más información sobre la sintaxis XAML para establecer propiedades, vea [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) y [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 Como ejemplo de sintaxis sin atributos, en el siguiente ejemplo de XAML se muestra otro fondo de botón.  Esta vez, en lugar de establecer un color sólido simple, el fondo se establece en una imagen, con un elemento que representa esa imagen y el origen de la imagen especificado como un atributo del elemento anidado.  Éste es un ejemplo de sintaxis de elemento de propiedad.  
  
 [!code-xml[PropertiesOvwSupport#PESyntaxProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#pesyntaxproperty)]  
  
<a name="setting_properties_code"></a>   
### Establecer propiedades en código  
 Establecer valores de [propiedad de dependencia](GTMT) en código suele consistir en una simple llamada a la implementación de escritura expuesta por el "contenedor" de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  
  
 [!code-csharp[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyset)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyset)]  
  
 Obtener un valor de propiedad consiste también esencialmente en una llamada a la implementación de lectura del "contenedor":  
  
 [!code-csharp[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyget)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyget)]  
  
 También puede llamar directamente a [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]<xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> del sistema de propiedades.  Habitualmente, no es necesario si se está utilizando propiedades existentes \(los contenedores son más cómodos y ofrecen una mejor exposición de la propiedad para las herramientas de desarrollo\), pero llamar directamente a [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] es lo adecuado para ciertos escenarios.  
  
 También se pueden establecer propiedades en XAML y obtener acceso más tarde en el código mediante código subyacente.  Para obtener información detallada, vea [Código subyacente y XAML en WPF](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
<a name="functionality"></a>   
## Funcionalidad de propiedad proporcionada por una propiedad de dependencia  
 Una propiedad de dependencia proporciona funcionalidad que extiende la funcionalidad de una propiedad, a diferencia de una propiedad respaldada por un campo.  A menudo, cada una de estas funcionalidades representa o admite una característica concreta del conjunto total de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   [Recursos](#setting_properties_resources)  
  
-   [Enlace de datos](#setting_properties_data_binding)  
  
-   [Estilos](#setting_properties_styles)  
  
-   [Animations](#animations)  
  
-   [Invalidaciones de metadatos](#metadata)  
  
-   [Herencia del valor de propiedad](#setting_properties_inheritance)  
  
-   [Integración de WPF Designer](#vs2008_integration)  
  
<a name="setting_properties_resources"></a>   
### Recursos  
 Puede establecerse un valor de propiedad de dependencia haciendo referencia a un recurso.  Los recursos se especifican normalmente como el valor de propiedad `Resources` de un elemento raíz de la página o de la aplicación \(estas ubicaciones permiten el acceso más cómodo al recurso\).  En el ejemplo siguiente se muestra cómo definir un recurso <xref:System.Windows.Media.SolidColorBrush>.  
  
 [!code-xml[PropertiesOvwSupport#ResourcesResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesresource)]  
  
 Una vez definido el recurso, puede hacer referencia al recurso y utilizarlo para proporcionar un valor de propiedad:  
  
 [!code-xml[PropertiesOvwSupport#ResourcesReference](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesreference)]  
  
 Este recurso en especial se conoce como [Extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) \(en XAML de WPF, se puede utilizar una referencia de recurso estática o dinámica\).  Para utilizar una referencia de recurso dinámica debe estar estableciendo una propiedad de dependencia, por lo que es específicamente el uso de la referencia de recurso dinámica lo que habilita el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Para obtener más información, consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
> [!NOTE]
>  Los recursos se tratan como un valor local, lo que significa que si se establece otro valor local, se eliminará la referencia de recurso.  Para obtener más información, vea [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
<a name="setting_properties_data_binding"></a>   
### Enlace de datos  
 Una propiedad de dependencia puede hacer referencia a un valor mediante enlace de datos.  El enlace de datos funciona mediante una sintaxis de extensión de marcado concreta en XAML, o el objeto <xref:System.Windows.Data.Binding> en el código.  Con el enlace de datos, la determinación final del valor de propiedad se aplaza hasta el tiempo de ejecución, momento en el que se obtiene el valor desde un origen de datos.  
  
 En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> de un control <xref:System.Windows.Controls.Button>, utilizando un enlace declarado en XAML.  El enlace usa un contexto de datos heredado y un origen de datos <xref:System.Windows.Data.XmlDataProvider> \(que no se muestra\).  El propio enlace especifica la propiedad de origen deseada por <xref:System.Windows.Data.Binding.XPath%2A> dentro del origen de datos.  
  
 [!code-xml[PropertiesOvwSupport#BasicInlineBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#basicinlinebinding)]  
  
> [!NOTE]
>  Los enlaces se tratan como un valor local, lo que significa que, si establece otro valor local, eliminará el enlace.  Para obtener información detallada, vea [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Las propiedades de dependencia o la clase <xref:System.Windows.DependencyObject> no admiten de forma nativa <xref:System.ComponentModel.INotifyPropertyChanged> para generar notificaciones de cambios de valor de propiedad de origen <xref:System.Windows.DependencyObject> en operaciones de enlace de datos.  Para obtener más información sobre cómo crear propiedades para su uso en enlace de datos que puedan informar de los cambios de un destino de enlace de datos, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
<a name="setting_properties_styles"></a>   
### Estilos  
 Los estilos y las plantillas son dos de los principales escenarios que invitan a usar propiedades de dependencia.  Los estilos son particularmente útiles para establecer propiedades que definen la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de la aplicación.  Los estilos se definen habitualmente como recursos en XAML.  Los estilos interactúan con el sistema de propiedades porque contienen normalmente "establecedores" para determinadas propiedades, así como "desencadenadores" que modifican un valor de propiedad en función del valor en tiempo real de otra propiedad.  
  
 En el ejemplo siguiente se crea un estilo muy simple \(que se definiría dentro de un diccionario <xref:System.Windows.FrameworkElement.Resources%2A>, que no se muestra\) y, a continuación, se aplica directamente a la propiedad <xref:System.Windows.FrameworkElement.Style%2A> de un control <xref:System.Windows.Controls.Button>.  El establecedor que hay dentro del estilo establece la propiedad <xref:System.Windows.Controls.Control.Background%2A> de un control <xref:System.Windows.Controls.Button> con estilo en el color verde.  
  
 [!code-xml[PropertiesOvwSupport#SimpleStyleDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyledef)]  
  
 [!code-xml[PropertiesOvwSupport#SimpleStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyle)]  
  
 Para obtener más información, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
<a name="animations"></a>   
### Animations  
 Las propiedades de dependencia se pueden animar.  Cuando se aplica una animación y se está ejecutando, el valor animado funciona en una prioridad más alta que cualquier valor \(tal como un valor local\) que pueda tener la propiedad.  
  
 En el ejemplo siguiente se anima la propiedad <xref:System.Windows.Controls.Control.Background%2A> de una propiedad <xref:System.Windows.Controls.Button> \(técnicamente, la propiedad <xref:System.Windows.Controls.Control.Background%2A> se anima utilizando la sintaxis de elemento de propiedad para especificar un objeto <xref:System.Windows.Media.SolidColorBrush> en blanco como <xref:System.Windows.Controls.Control.Background%2A>; entonces, la propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> de ese objeto <xref:System.Windows.Media.SolidColorBrush> es la propiedad que se anima directamente\).  
  
 [!code-xml[PropertiesOvwSupport#MiniAnimate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#minianimate)]  
  
 Para obtener más información sobre la animación de propiedades, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) y [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="metadata"></a>   
### Invalidaciones de metadatos  
 Puede cambiar ciertos comportamientos de una [propiedad de dependencia](GTMT) invalidando los metadatos para esa propiedad al derivar de la clase que registra originalmente la [propiedad de dependencia](GTMT).  La invalidación de metadatos se apoya en el identificador <xref:System.Windows.DependencyProperty>.  La invalidación de metadatos, no requiere implementar de nuevo la propiedad.  El sistema de propiedades administra nativamente el cambio de metadatos; cada clase puede contener metadatos individuales para todas las propiedades heredadas de las clases base, tipo por tipo.  
  
 En el ejemplo siguiente se invalidan los metadatos de una propiedad de dependencia <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>.  Invalidar los metadatos de esta propiedad de dependencia concreta forma parte de un modelo de implementación que crea controles que pueden utilizar estilos predeterminados de temas.  
  
 [!code-csharp[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#overridemetadata)]
 [!code-vb[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#overridemetadata)]  
  
 Para obtener más información sobre cómo invalidar u obtener metadatos de propiedades, vea [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="setting_properties_inheritance"></a>   
### Herencia de valores de propiedad  
 Un elemento puede heredar el valor de una propiedad de dependencia de su elemento primario en el árbol de objetos.  
  
> [!NOTE]
>  El comportamiento de herencia del valor de propiedad no está habilitado globalmente para todas las propiedades de dependencia, porque el tiempo de cálculo para la herencia tiene cierto impacto sobre el rendimiento.  La herencia del valor de propiedad solamente está habilitada, normalmente, para las propiedades donde un escenario determinado sugiera que resulta adecuada la herencia del valor de propiedad.  Puede determinar si una propiedad de dependencia se hereda examinando la sección **Información de propiedad de dependencia** de esa propiedad de dependencia en la referencia del SDK.  
  
 En el ejemplo siguiente se muestra un enlace y se establece la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> que especifica el origen del enlace, lo que no se mostraba en el ejemplo de enlace anterior.  Los enlaces subsiguientes en objetos secundarios no necesitan especificar el origen, pueden utilizar el valor heredado de <xref:System.Windows.FrameworkElement.DataContext%2A> en el objeto <xref:System.Windows.Controls.StackPanel> primario.  \(Como alternativa, un objeto secundario podría decidir especificar su propio <xref:System.Windows.FrameworkElement.DataContext%2A> o <xref:System.Windows.Data.Binding.Source%2A> directamente en <xref:System.Windows.Data.Binding> y, deliberadamente, no utilizar el valor heredado para el contexto de datos de sus enlaces.\)  
  
 [!code-xml[PropertiesOvwSupport#InheritanceContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#inheritancecontext)]  
  
 Para obtener más información, vea [Herencia de valores de propiedad](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
<a name="vs2008_integration"></a>   
### Integración de WPF Designer  
 Un control personalizado con propiedades implementadas como propiedades de dependencia recibirá la compatibilidad con [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] adecuada.  Un ejemplo es la capacidad de modificar propiedades de dependencia directas y adjuntas con la ventana **Propiedades**.  Para obtener más información, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
<a name="value_determination"></a>   
## Prioridad de los valores de propiedades de dependencia  
 Al obtener el valor de una [propiedad de dependencia](GTMT), se está obteniendo potencialmente un valor que se estableció en esa propiedad mediante cualquiera de las demás entradas basadas en propiedad que participan en el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  La prioridad de valor de propiedad de dependencia existe para que diversos escenarios de obtención de valores para propiedades puedan interactuar de una manera predecible.  
  
 Considere el ejemplo siguiente.  El ejemplo incluye un estilo que se aplica a todos los botones y sus propiedades <xref:System.Windows.Controls.Control.Background%2A>, pero también especifica un botón con un valor <xref:System.Windows.Controls.Control.Background%2A> establecido localmente.  
  
> [!NOTE]
>  La documentación de SDK utiliza ocasionalmente los términos "valor local" o valor "localmente establecido" para explicar las propiedades de dependencia.  Un valor localmente establecido es un valor de propiedad que se establece directamente en una instancia de objeto en código o como un atributo de un elemento en XAML.  
  
 En principio, para el primer botón, la propiedad se establece dos veces, pero solamente se aplica un valor: el de mayor prioridad.  Un valor localmente establecido tiene la prioridad superior \(excepto para una animación en ejecución, pero no hay ninguna animación en este ejemplo\) y, así, se utiliza el valor establecido localmente en lugar del valor del establecedor del estilo para el segundo plano del primer botón.  El segundo botón no tiene ningún valor local \(y ningún otro valor con prioridad más alta que un establecedor de estilo\) y, así, el fondo de ese botón procede del establecedor del estilo.  
  
 [!code-xml[PropertiesOvwSupport#MiniPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#miniprecedence)]  
  
### ¿Por qué existe la prioridad de propiedad de dependencia?  
 Normalmente, no se desea que los estilos se apliquen siempre y oculten incluso un valor localmente establecido de un elemento individual \(de lo contrario, sería muy difícil utilizar estilos o elementos en general\).  Por consiguiente, los valores que proceden de estilos funcionan con una prioridad más baja que un valor establecido localmente.  Para ver una lista más completa de propiedades de dependencia y de dónde puede proceder el valor efectivo de una propiedad de dependencia, vea [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
> [!NOTE]
>  Hay varias propiedades definidas en elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que no son propiedades de dependencia.  Habitualmente, las propiedades se implementan como propiedades de dependencia solamente cuando es necesario admitir por lo menos uno de los escenarios habilitados por el sistema de propiedades: enlace de datos, estilos, animación, compatibilidad con valor predeterminado, herencia, propiedades adjuntas o invalidación.  
  
<a name="dp_implement_roadmap"></a>   
## Más información sobre propiedades de dependencia  
  
-   Una [propiedad adjunta](GTMT) es un tipo de propiedad que admite una sintaxis especializada en XAML.  Una propiedad adjunta no suele tener una correspondencia 1:1 con una propiedad de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] y no es necesariamente una [propiedad de dependencia](GTMT).  El propósito típico de una [propiedad adjunta](GTMT) es permitir que los elementos secundarios informen de los valores de propiedad a un elemento primario, aunque el elemento primario y los elementos secundarios no posean esa propiedad como parte de las listas de miembros de la clase.  Un escenario primario consiste en permitir que los elementos secundarios informen el elemento primario de cómo se deben presentar en [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]; para ver un ejemplo, vea <xref:System.Windows.Controls.DockPanel.Dock%2A> o <xref:System.Windows.Controls.Canvas.Left%2A>.  Para obtener información detallada, vea [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
-   Los programadores de componentes y los desarrolladores de aplicaciones pueden desear crear [propiedades de dependencia](GTMT) propias para habilitar funciones tales como el enlace de datos o la compatibilidad con estilos, o para la invalidación y la coerción de valor.  Para obtener información detallada, vea [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
-   Generalmente las propiedades de dependencia deben considerarse propiedades públicas, accesibles o, por lo menos, reconocibles por cualquier llamador que tenga acceso a una instancia.  Para obtener más información, consulte [Seguridad de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-security.md).  
  
## Vea también  
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Propiedades de dependencia de sólo lectura](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Arquitectura de WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)