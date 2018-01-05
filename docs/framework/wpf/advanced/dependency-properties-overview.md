---
title: "Información general sobre propiedades de dependencia"
description: "Una propiedad que está respaldada por el sistema de propiedades WPF se conoce como una propiedad de dependencia. Esta información general describe el sistema de propiedades WPF y las capacidades de una propiedad de dependencia."
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-wpf
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [WPF], attached
- properties [WPF], overview
- styles [WPF]
- attached properties [WPF]
- data binding [WPF]
- dependency properties [WPF]
- resources [WPF], references to
ms.assetid: d119d00c-3afb-48d6-87a0-c4da4f83dee5
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d90e47c400f24eb10f2d262f9cb0e757ff472f0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="dependency-properties-overview"></a>Información general sobre propiedades de dependencia

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un conjunto de servicios que puede usarse para ampliar la funcionalidad de una propiedad [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]. Colectivamente, se suele hacer referencia a estos servicios como el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Una propiedad respaldada por el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se conoce como una propiedad de dependencia. Esta información general describe el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y las funcionalidades de una propiedad de dependencia. Esto incluye cómo usar las propiedades de dependencia existentes en XAML y en el código. Esta información general también presenta aspectos especializados de las propiedades de dependencia, como los metadatos de las propiedades de dependencia y el proceso de creación de una propiedad de dependencia propia en una clase personalizada.

## <a name="prerequisites"></a>Requisitos previos
En este tema se supone que tiene conocimientos básicos sobre programación de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y orientada a objetos. Para seguir los ejemplos de este tema, también debe comprender el lenguaje [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y saber cómo escribir aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para obtener más información, consulte [Tutorial: Mi primera aplicación de escritorio de WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="dependency-properties-and-clr-properties"></a>Propiedades de dependencia y las propiedades CLR
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], las propiedades se suelen exponer como propiedades de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]. En un nivel básico, podría interactuar directamente con estas propiedades y no llegar a saber que están implementadas como una propiedad de dependencia. Sin embargo, debería familiarizarse con todas o algunas de las características del sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], a fin de poder aprovechar estas características.

El propósito de las propiedades de dependencia es proporcionar una manera de calcular el valor de una propiedad en función del valor de otras entradas. Estas otras entradas pueden incluir propiedades del sistema, tales como temas y preferencias del usuario, mecanismos de determinación de propiedades Just-In-Time como el enlace de datos y las animaciones o los guiones gráficos, plantillas de usos múltiples como recursos y estilos, o valores conocidos a través de relaciones primario-secundario con otros elementos del árbol de elementos. Además, una propiedad de dependencia se puede implementar para proporcionar una validación autocontenida, valores predeterminados, devoluciones de llamada que controlen los cambios en otras propiedades y un sistema que pueda forzar los valores de propiedad de acuerdo con la información de tiempo de ejecución en potencia. Las clases derivadas también pueden cambiar algunas características concretas de una propiedad existente mediante la invalidación de los metadatos de la propiedad de dependencia, en lugar de invalidar la implementación real de las propiedades existentes o de crear nuevas propiedades.

En la referencia del SDK, puede identificar qué propiedad es una propiedad de dependencia por la presencia de la sección de información de la propiedad de dependencia en la página de referencia administrada de esa propiedad. La sección de información de la propiedad de dependencia incluye un vínculo a la <xref:System.Windows.DependencyProperty> identificador de campo para esa propiedad de dependencia y también incluye una lista de las opciones de metadatos que se establecen para esa propiedad, información de invalidación por clases y otros detalles.

## <a name="dependency-properties-back-clr-properties"></a>Propiedades CLR de respaldo de propiedades de dependencia
Las propiedades de dependencia y el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] extienden la funcionalidad de las propiedades al proporcionar un tipo que respalda una propiedad, como implementación alternativa al patrón estándar de respaldar la propiedad con un campo privado. El nombre de este tipo es <xref:System.Windows.DependencyProperty>. El otro tipo important que define la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de propiedades es <xref:System.Windows.DependencyObject>. <xref:System.Windows.DependencyObject>define la clase base que se puede registrar y poseer una propiedad de dependencia.

A continuación se muestra un resumen de la terminología que se usa en esta documentación de [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] para explicar las propiedades de dependencia:

- **Propiedad de dependencia:** una propiedad que está respaldada por un <xref:System.Windows.DependencyProperty>.

- **Identificador de la propiedad de dependencia:** A <xref:System.Windows.DependencyProperty> instancia, que se obtiene como un valor devuelto al registrar una propiedad de dependencia y, a continuación, se almacena como un miembro estático de una clase. Este identificador se usa como un parámetro para muchas de las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] que interactúan con el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

- **"Contenedor" de CLR:** implementaciones de get y set reales de la propiedad. Estas implementaciones incorporan el identificador de la propiedad de dependencia mediante el uso en el <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> llamadas, lo que proporciona el respaldo para la propiedad mediante el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de propiedades.

En el ejemplo siguiente se define la `IsSpinning` propiedad de dependencia y se muestra la relación de la <xref:System.Windows.DependencyProperty> identificador a la propiedad que realiza copia de seguridad.

[!code-csharp[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic)]
[!code-vb[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#dpformbasic)]  
  
La convención de nomenclatura de la propiedad y su copia de seguridad <xref:System.Windows.DependencyProperty> campo es importante. El nombre del campo siempre es el nombre de la propiedad, con el sufijo `Property` anexado. Para obtener más información acerca de esta convención y las razones para usarla, consulte [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  

## <a name="setting-property-values"></a>Establecer valores de propiedad
Puede establecer propiedades en el código o en XAML.

### <a name="setting-property-values-in-xaml"></a>Establecer valores de propiedad en XAML 
El siguiente ejemplo de XAML especifica el color de fondo de un botón como rojo. Este ejemplo muestra un caso donde el valor de cadena sencilla para un atributo XAML es convertir tipo por el analizador de XAML de WPF en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tipo (un <xref:System.Windows.Media.Color>, por medio de un <xref:System.Windows.Media.SolidColorBrush>) en el código generado.

[!code-xaml[PropertiesOvwSupport#MostBasicProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#mostbasicproperty)]

XAML admite una variedad de formatos de sintaxis para establecer propiedades. La sintaxis que se debe usar para una propiedad determinada dependerá del tipo de valor que use la propiedad, así como de otros factores, tal como la presencia de un convertidor de tipos. Para obtener más información sobre la sintaxis XAML y establecer propiedades, consulte [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) y [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).

Como ejemplo de sintaxis sin atributos, en el ejemplo de XAML siguiente se muestra otro fondo de botón. Esta vez, en lugar de establecer un color sólido simple, el fondo se establece en una imagen, con un elemento que representa esa imagen y el origen de la imagen especificado como un atributo del elemento anidado. Este es un ejemplo de sintaxis de elemento de propiedad.

[!code-xaml[PropertiesOvwSupport#PESyntaxProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#pesyntaxproperty)]

### <a name="setting-properties-in-code"></a>Establecer las propiedades en código
 Establecer valores de propiedad de dependencia en el código solo suele requerir una llamada a la implementación establecida que expone el "contenedor" de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].

[!code-csharp[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyset)]
[!code-vb[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyset)]

Para obtener un valor de propiedad también se requiere esencialmente una llamada a la implementación de get del "contenedor":

[!code-csharp[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyget)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyget)]

También puede llamar el sistema de propiedades [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> directamente. Generalmente, no es necesario si usa las propiedades existentes (los contenedores son más prácticos y ofrecen una mejor exposición de la propiedad para las herramientas de desarrollo), pero llamar a [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] directamente es adecuado en determinados escenarios.

Las propiedades también se pueden establecer en XAML y se puede acceder a ellas más adelante en el código a través del código subyacente. Para obtener información detallada, vea [Código subyacente y XAML en WPF](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

## <a name="property-functionality-provided-by-a-dependency-property"></a>Funcionalidad de propiedad proporcionada por una propiedad de dependencia
Una propiedad de dependencia proporciona una funcionalidad que amplía la funcionalidad de una propiedad, al contrario que una propiedad respaldada por un campo. A menudo, estas funcionalidades representan o admiten una característica del conjunto de características general de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

- [Recursos](#resources)

- [Enlace de datos](#data-binding)

- [Estilos](#styles)

- [Animaciones](#animations)

- [Invalidaciones de metadatos](#metadata-overrides)

- [Herencia de valores de propiedad](#property-value-inheritance)

- [Integración de WPF Designer](#wpf-designer-integration)

### <a name="resources"></a>Recursos
Un valor de propiedad de dependencia se puede establecer mediante una referencia a un recurso. Los recursos se especifican normalmente como el valor de propiedad `Resources` de un elemento de raíz de la página o de la aplicación (estas ubicaciones permiten un acceso más cómodo al recurso). En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Media.SolidColorBrush> recursos.

[!code-xaml[PropertiesOvwSupport#ResourcesResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesresource)]

Una vez que el recurso está definido, puede hacer referencia al recurso y usarlo para proporcionar un valor de propiedad:

[!code-xaml[PropertiesOvwSupport#ResourcesReference](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesreference)]

Se hace referencia a este recurso concreto como una [Extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) (en XAML de WPF, puede usar una referencia a recursos estáticos o dinámicos). Para usar una referencia a recursos dinámicos, debe estar estableciendo una propiedad de dependencia, que es específicamente el uso de referencias a recursos dinámicos que permite el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para obtener más información, consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).

> [!NOTE]
> Los recursos se tratan como un valor local, lo que significa que si establece otro valor local, eliminará la referencia a los recursos. Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

### <a name="data-binding"></a>Enlace de datos
Una propiedad de dependencia puede hacer referencia a un valor mediante el enlace de datos. Enlace de datos funciona a través de una sintaxis de extensión de marcado concreta en XAML, o la <xref:System.Windows.Data.Binding> objeto en el código. Con el enlace de datos, la determinación del valor de propiedad final se aplaza hasta el tiempo de ejecución, momento en el que se obtiene el valor de un origen de datos.

El ejemplo siguiente se establece la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad para un <xref:System.Windows.Controls.Button>, utilizando un enlace declarado en XAML. El enlace usa un contexto de datos heredado y un <xref:System.Windows.Data.XmlDataProvider> (no se muestra) el origen de datos. El propio enlace especifica la propiedad de origen deseado por <xref:System.Windows.Data.Binding.XPath%2A> del origen de datos.

[!code-xaml[PropertiesOvwSupport#BasicInlineBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#basicinlinebinding)]

> [!NOTE]
> Los enlaces se tratan como un valor local, lo que significa que si establece otro valor local, eliminará el enlace. Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

Propiedades de dependencia, o la <xref:System.Windows.DependencyObject> de clases, no de forma nativa no admiten <xref:System.ComponentModel.INotifyPropertyChanged> para fines de generar notificaciones de cambios en <xref:System.Windows.DependencyObject> valor de propiedad para las operaciones de enlace de datos de origen. Para obtener más información acerca de cómo crear propiedades para su uso en un enlace de datos capaz de notificar los cambios en un destino de enlace de datos, consulte [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).

### <a name="styles"></a>Estilos
Los estilos y las plantillas son dos de los principales escenarios que invitan a usar las propiedades de dependencia. Los estilos son particularmente útiles para establecer las propiedades que definen la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de la aplicación. Los estilos se definen normalmente como recursos en XAML. Los estilos interactúan con el sistema de propiedades porque suelen contener "establecedores" para determinadas propiedades, así como "desencadenadores" que cambian un valor de propiedad según el valor en tiempo real de otra propiedad.

En el ejemplo siguiente se crea un estilo muy simple (que se definiría dentro de un <xref:System.Windows.FrameworkElement.Resources%2A> diccionario, no se muestra), a continuación, aplica ese estilo directamente a la <xref:System.Windows.FrameworkElement.Style%2A> propiedad para un <xref:System.Windows.Controls.Button>. El establecedor dentro de los conjuntos de estilo el <xref:System.Windows.Controls.Control.Background%2A> propiedad para un estilo <xref:System.Windows.Controls.Button> a verde.

[!code-xaml[PropertiesOvwSupport#SimpleStyleDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyledef)]

[!code-xaml[PropertiesOvwSupport#SimpleStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyle)]

Para obtener más información, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).

### <a name="animations"></a>Animaciones
Las propiedades de dependencia se pueden animar. Cuando una animación está aplicada y en ejecución, el valor animado funciona con una precedencia más alta que cualquier otro valor (por ejemplo, un valor local) que tenga la propiedad.

En el ejemplo siguiente se anima la <xref:System.Windows.Controls.Control.Background%2A> en un <xref:System.Windows.Controls.Button> propiedad (técnicamente, la <xref:System.Windows.Controls.Control.Background%2A> se anima utilizando la sintaxis de elemento de propiedad para especificar un valor en blanco <xref:System.Windows.Media.SolidColorBrush> como el <xref:System.Windows.Controls.Control.Background%2A>, la <xref:System.Windows.Media.SolidColorBrush.Color%2A> propiedad de ese <xref:System.Windows.Media.SolidColorBrush> es la propiedad que se anima directamente).

[!code-xaml[PropertiesOvwSupport#MiniAnimate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#minianimate)]

Para obtener más información sobre la animación de propiedades, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) e [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).

### <a name="metadata-overrides"></a>Invalidaciones de metadatos
Puede cambiar ciertos comportamientos de una propiedad de dependencia mediante la invalidación de los metadatos de la propiedad cuando se deriva de la clase que originalmente registra la propiedad de dependencia. La invalidación de metadatos se basa en el <xref:System.Windows.DependencyProperty> identificador. Para invalidar los metadatos no es necesario volver a implementar la propiedad. El sistema de propiedades controla de forma nativa el cambio en los metadatos; cada clase puede contener metadatos individuales de todas las propiedades que se heredan de las clases base, por tipo.

En el ejemplo siguiente se invalida metadatos para una propiedad de dependencia <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>. La invalidación de los metadatos de esta propiedad de dependencia concreta forma parte de un patrón de implementación que crea controles que pueden usar estilos predeterminados de temas.

[!code-csharp[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#overridemetadata)]
[!code-vb[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#overridemetadata)]

Para obtener más información sobre cómo invalidar u obtener los metadatos de las propiedades, consulte [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).

### <a name="property-value-inheritance"></a>Herencia del valor de propiedad
Un elemento puede heredar el valor de una propiedad de dependencia de su elemento primario en el árbol de objetos.

> [!NOTE]
> El comportamiento de la herencia de valores de propiedad no está habilitado globalmente para todas las propiedades de dependencia, porque el tiempo de cálculo de la herencia afecta de algún modo al rendimiento. La herencia de valores de propiedad suele habilitarse normalmente solo para las propiedades donde un escenario determinado sugiere que dicha herencia es adecuada. Para determinar si una propiedad de dependencia se hereda, puede consultar la sección de **información sobre las propiedades de dependencia** correspondiente a esa propiedad de dependencia en la referencia del SDK.

En el ejemplo siguiente se muestra un enlace y establece el <xref:System.Windows.FrameworkElement.DataContext%2A> propiedad que especifica el origen del enlace, que no se muestra en el ejemplo de enlace anterior. No es necesario especificar el origen de los enlaces subsiguientes en objetos secundarios, pueden utilizar el valor heredado de <xref:System.Windows.FrameworkElement.DataContext%2A> en el elemento primario <xref:System.Windows.Controls.StackPanel> objeto. (O bien, un objeto secundario en su lugar, puede especificar directamente su propio <xref:System.Windows.FrameworkElement.DataContext%2A> o un <xref:System.Windows.Data.Binding.Source%2A> en el <xref:System.Windows.Data.Binding>y no use deliberadamente el valor heredado para el contexto de datos de sus enlaces.)

[!code-xaml[PropertiesOvwSupport#InheritanceContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#inheritancecontext)]

Para más información, vea [Herencia de valores de propiedad](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).

### <a name="wpf-designer-integration"></a>Integración de WPF designer
Un control personalizado con propiedades que se implementan como propiedades de dependencia recibirá soporte técnico adecuado de [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]. Un ejemplo es la capacidad de editar las propiedades de dependencia directas y adjuntas con la ventana **Propiedades**. Para obtener más información, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).

## <a name="dependency-property-value-precedence"></a>Prioridad de valores de propiedad de dependencia
Cuando se obtiene el valor de una propiedad de dependencia, se está obteniendo potencialmente un valor establecido en esa propiedad mediante cualquiera de las otras entradas basadas en propiedades que se incluyen en el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La precedencia de los valores de propiedad de dependencia existe para que distintos escenarios sobre cómo las propiedades obtienen sus valores puedan interactuar de forma predecible.

Considere el ejemplo siguiente. El ejemplo incluye un estilo que se aplica a todos los botones y sus <xref:System.Windows.Controls.Control.Background%2A> propiedades, sino que también especifique un botón con establecida localmente <xref:System.Windows.Controls.Control.Background%2A> valor.

> [!NOTE]
> La documentación del SDK usa los términos "valor local" o "valor establecido localmente" ocasionalmente al hablar de las propiedades de dependencia. Un valor establecido localmente es un valor de propiedad que se establece directamente en una instancia de objeto en el código, o bien como un atributo en un elemento en XAML.  
  
En principio, para el primer botón, la propiedad se establece dos veces, pero se aplica solo un valor: el valor con la precedencia más alta. Un valor establecido localmente tiene la precedencia más alta (excepto para una animación en ejecución, pero ninguna animación es aplicable en este ejemplo) y, por tanto, el valor establecido localmente se usa en lugar del valor del establecedor de estilo para el fondo del primer botón. El segundo botón no tiene ningún valor local (ni ningún otro valor con una precedencia más alta que un establecedor de estilo) y, por tanto, el fondo de ese botón procede del establecedor de estilo.

[!code-xaml[PropertiesOvwSupport#MiniPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#miniprecedence)]  

### <a name="why-does-dependency-property-precedence-exist"></a>¿Por qué existe la prioridad de la propiedad de dependencia?
Por lo general, no querrá que los estilos siempre apliquen ni oculten siquiera un valor establecido localmente de un elemento individual (de lo contrario, sería muy difícil usar estilos o elementos en general). Por lo tanto, los valores que proceden de estilos funcionan con una precedencia más baja que un valor establecido localmente. Para obtener una lista más completa de las propiedades de dependencia y conocer la procedencia del valor efectivo de una propiedad de dependencia, consulte [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

> [!NOTE]
> Existen varias propiedades definidas en elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que no son propiedades de dependencia. En general, las propiedades se implementaban como propiedades de dependencia solo cuando era necesario admitir al menos uno de los escenarios que habilitaba el sistema de propiedades: enlace de datos, estilos, animación, compatibilidad con los valores predeterminados, herencia, propiedades adjuntas o invalidación.

## <a name="learning-more-about-dependency-properties"></a>Obtener más información acerca de las propiedades de dependencia  

- Una propiedad adjunta es un tipo de propiedad que admite una sintaxis especializada en XAML. Una propiedad adjunta no suele tener una correspondencia de 1:1 con una propiedad [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] y no es necesariamente una propiedad de dependencia. El propósito típico de una propiedad adjunta es permitir que los elementos secundarios comuniquen valores de propiedad a un elemento primario, aunque el elemento primario y el elemento secundario no posean a la vez esa propiedad como parte de las listas de miembros de clase. Un escenario principal es que los elementos secundarios que informen al elemento primario de cómo se debe mostrar en [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]; para obtener un ejemplo, vea <xref:System.Windows.Controls.DockPanel.Dock%2A> o <xref:System.Windows.Controls.Canvas.Left%2A>. Para obtener información detallada, vea [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).

- Los desarrolladores de componentes o de aplicaciones pueden querer crear su propia propiedad de dependencia para habilitar funcionalidades, tales como el enlace de datos o la compatibilidad con estilos, o para admitir la invalidación y la coerción de valores. Para obtener más información, consulte [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).

- Por lo general, las propiedades de dependencia deben considerarse propiedades públicas, accesibles o al menos reconocibles para cualquier llamador que tenga acceso a una instancia. Para obtener más información, consulte [Seguridad de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-security.md).

## <a name="see-also"></a>Vea también
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Propiedades de dependencia de solo lectura](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Arquitectura de WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
