---
title: Introducción a las propiedades de dependencia
description: Una propiedad respaldada por el sistema de propiedades de WPF se conoce como una propiedad de dependencia. En esta información general se describe el sistema de propiedades de WPF y las funcionalidades de una propiedad de dependencia.
ms.date: 06/06/2018
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
ms.openlocfilehash: 9a911b99b4543ae7957b685df06b4d85f13c7790
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762245"
---
# <a name="dependency-properties-overview"></a>Introducción a las propiedades de dependencia

Windows Presentation Foundation (WPF) proporciona un conjunto de servicios que se pueden usar para ampliar la funcionalidad de la [propiedad](../../../standard/base-types/common-type-system.md#properties) de un tipo. Colectivamente, se suele hacer referencia a estos servicios como el sistema de propiedades de WPF. Una propiedad respaldada por el sistema de propiedades de WPF se conoce como una propiedad de dependencia. En esta información general se describe el sistema de propiedades de WPF y las funcionalidades de una propiedad de dependencia. Esto incluye cómo usar las propiedades de dependencia existentes en XAML y en el código. Esta información general también presenta aspectos especializados de las propiedades de dependencia, como los metadatos de las propiedades de dependencia y el proceso de creación de una propiedad de dependencia propia en una clase personalizada.

## <a name="prerequisites"></a>Prerrequisitos
En este tema se supone que tiene conocimientos básicos sobre el sistema de tipos de .NET y la programación orientada a objetos. Para seguir los ejemplos de este tema, también debe comprender el lenguaje XAML y saber cómo escribir aplicaciones de WPF. Para obtener más información, vea [Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="dependency-properties-and-clr-properties"></a>Propiedades de dependencia y propiedades CLR
 En WPF, las propiedades se suelen exponer como [propiedades estándar](../../../standard/base-types/common-type-system.md#properties) de .NET. En un nivel básico, podría interactuar directamente con estas propiedades y no llegar a saber que están implementadas como una propiedad de dependencia. Pero debería familiarizarse con todas o algunas de las características del sistema de propiedades de WPF, a fin de poder aprovechar estas características.

El propósito de las propiedades de dependencia es proporcionar una manera de calcular el valor de una propiedad en función del valor de otras entradas. Estas otras entradas pueden incluir propiedades del sistema, tales como temas y preferencias del usuario, mecanismos de determinación de propiedades Just-In-Time como el enlace de datos y las animaciones o los guiones gráficos, plantillas de usos múltiples como recursos y estilos, o valores conocidos a través de relaciones primario-secundario con otros elementos del árbol de elementos. Además, una propiedad de dependencia se puede implementar para proporcionar una validación autocontenida, valores predeterminados, devoluciones de llamada que controlen los cambios en otras propiedades y un sistema que pueda forzar los valores de propiedad de acuerdo con la información de tiempo de ejecución en potencia. Las clases derivadas también pueden cambiar algunas características concretas de una propiedad existente mediante la invalidación de los metadatos de la propiedad de dependencia, en lugar de invalidar la implementación real de las propiedades existentes o de crear nuevas propiedades.

En la referencia del SDK, puede identificar qué propiedad es una propiedad de dependencia por la presencia de la sección de información de la propiedad de dependencia en la página de referencia administrada de esa propiedad. En la sección de información de las propiedades de dependencia se incluye un vínculo al campo de identificador <xref:System.Windows.DependencyProperty> de esa propiedad de dependencia, así como una lista de las opciones de metadatos establecidas para esa propiedad, información de invalidación por clases y otros detalles.

## <a name="dependency-properties-back-clr-properties"></a>Las propiedades de dependencia respaldan las propiedades CLR
Las propiedades de dependencia y el sistema de propiedades de WPF extienden la funcionalidad de las propiedades al proporcionar un tipo que respalda una propiedad, como una implementación alternativa al patrón estándar de respaldar la propiedad con un campo privado. El nombre de este tipo es <xref:System.Windows.DependencyProperty>. El otro tipo importante que define el sistema de propiedades de WPF es <xref:System.Windows.DependencyObject>. <xref:System.Windows.DependencyObject> define la clase base que puede registrar y poseer una propiedad de dependencia.

A continuación se enumera la terminología que se usa con las propiedades de dependencia:

- **Propiedad de dependencia:** una propiedad que está respaldada por una <xref:System.Windows.DependencyProperty>.

- **Identificador de la propiedad de dependencia:** una instancia de <xref:System.Windows.DependencyProperty>, que se obtiene como un valor devuelto al registrar una propiedad de dependencia y, después, se almacena como un miembro estático de una clase. Este identificador se usa como un parámetro para muchas de las API que interactúan con el sistema de propiedades de WPF.

- **"Contenedor" de CLR:** implementaciones de get y set reales de la propiedad. Estas implementaciones incorporan el identificador de la propiedad de dependencia usándolo en las llamadas a <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A>, proporcionando así el respaldo para la propiedad que usa el sistema de propiedades WPF.

En el ejemplo siguiente se define la propiedad de dependencia `IsSpinning` y se muestra la relación del identificador <xref:System.Windows.DependencyProperty> con la propiedad que respalda.

[!code-csharp[PropertiesOvwSupport#DPFormBasic](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic)]
[!code-vb[PropertiesOvwSupport#DPFormBasic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#dpformbasic)]  
  
La convención de nomenclatura de la propiedad y su campo de respaldo <xref:System.Windows.DependencyProperty> es importante. El nombre del campo siempre es el nombre de la propiedad, con el sufijo `Property` anexado. Para obtener más información acerca de esta convención y las razones para usarla, consulte [Propiedades de dependencia personalizadas](custom-dependency-properties.md).  

## <a name="setting-property-values"></a>Establecimiento de valores de propiedad
Puede establecer propiedades en el código o en XAML.

### <a name="setting-property-values-in-xaml"></a>Establecimiento de valores de propiedad en XAML
El siguiente ejemplo de XAML especifica el color de fondo de un botón como rojo. En este ejemplo se muestra un caso donde el analizador de XAML de WPF convirtió el tipo del valor de cadena simple de un atributo XAML en un tipo WPF (<xref:System.Windows.Media.Color>, por medio de <xref:System.Windows.Media.SolidColorBrush>) en el código generado.

[!code-xaml[PropertiesOvwSupport#MostBasicProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#mostbasicproperty)]

XAML admite una variedad de formatos de sintaxis para establecer propiedades. La sintaxis que se debe usar para una propiedad determinada dependerá del tipo de valor que use la propiedad, así como de otros factores, tal como la presencia de un convertidor de tipos. Para obtener más información sobre la sintaxis XAML y establecer propiedades, consulte [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) y [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md).

Como ejemplo de sintaxis sin atributos, en el ejemplo de XAML siguiente se muestra otro fondo de botón. Esta vez, en lugar de establecer un color sólido simple, el fondo se establece en una imagen, con un elemento que representa esa imagen y el origen de la imagen especificado como un atributo del elemento anidado. Este es un ejemplo de sintaxis de elemento de propiedad.

[!code-xaml[PropertiesOvwSupport#PESyntaxProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#pesyntaxproperty)]

### <a name="setting-properties-in-code"></a>Establecimiento de propiedades en el código
 Establecer los valores de propiedad de dependencia en el código suele ser simplemente una llamada a la implementación de conjunto expuesta por el "contenedor" de CLR.

[!code-csharp[PropertiesOvwSupport#ProceduralPropertySet](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyset)]
[!code-vb[PropertiesOvwSupport#ProceduralPropertySet](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyset)]

Para obtener un valor de propiedad también se requiere esencialmente una llamada a la implementación de get del "contenedor":

[!code-csharp[PropertiesOvwSupport#ProceduralPropertyGet](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyget)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertyGet](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyget)]

También puede llamar a las API del sistema de propiedades <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> directamente. Normalmente, esto no es necesario si se usan propiedades existentes (los contenedores son más cómodos y proporcionan una mejor exposición de la propiedad para las herramientas de desarrollo), pero la llamada directa a las API es adecuada para determinados escenarios.

Las propiedades también se pueden establecer en XAML y se puede acceder a ellas más adelante en el código a través del código subyacente. Para obtener información detallada, vea [Código subyacente y XAML en WPF](code-behind-and-xaml-in-wpf.md).

## <a name="property-functionality-provided-by-a-dependency-property"></a>Funcionalidad de propiedad proporcionada por una propiedad de dependencia
Una propiedad de dependencia proporciona una funcionalidad que amplía la funcionalidad de una propiedad, al contrario que una propiedad respaldada por un campo. A menudo, esta funcionalidad representa o admite una de las características específicas siguientes:

- [Recursos](#resources)

- [Enlace de datos](#data-binding)

- [Estilos](#styles)

- [Animaciones](#animations)

- [Invalidaciones de metadatos](#metadata-overrides)

- [Herencia de valores de propiedad](#property-value-inheritance)

- [Integración de WPF Designer](#wpf-designer-integration)

### <a name="resources"></a>Recursos
Un valor de propiedad de dependencia se puede establecer mediante una referencia a un recurso. Los recursos se especifican normalmente como el valor de propiedad `Resources` de un elemento de raíz de la página o de la aplicación (estas ubicaciones permiten un acceso más cómodo al recurso). En el ejemplo siguiente se muestra cómo definir un recurso <xref:System.Windows.Media.SolidColorBrush>.

[!code-xaml[PropertiesOvwSupport#ResourcesResource](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesresource)]

Una vez que el recurso está definido, puede hacer referencia al recurso y usarlo para proporcionar un valor de propiedad:

[!code-xaml[PropertiesOvwSupport#ResourcesReference](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesreference)]

Se hace referencia a este recurso concreto como una [Extensión de marcado DynamicResource](dynamicresource-markup-extension.md) (en XAML de WPF, puede usar una referencia a recursos estáticos o dinámicos). Para usar una referencia a recursos dinámicos, se debe establecer una propiedad de dependencia, que es específicamente el uso de referencias a recursos dinámicos que permite el sistema de propiedades de WPF. Para obtener más información, consulte [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

> [!NOTE]
> Los recursos se tratan como un valor local, lo que significa que si establece otro valor local, eliminará la referencia a los recursos. Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](dependency-property-value-precedence.md).

### <a name="data-binding"></a>Enlace de datos
Una propiedad de dependencia puede hacer referencia a un valor mediante el enlace de datos. El enlace de datos funciona mediante una sintaxis de extensión de marcado específica en XAML, o bien mediante el objeto <xref:System.Windows.Data.Binding> en el código. Con el enlace de datos, la determinación del valor de propiedad final se aplaza hasta el tiempo de ejecución, momento en el que se obtiene el valor de un origen de datos.

En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> para un <xref:System.Windows.Controls.Button>, mediante un enlace declarado en XAML. El enlace usa un contexto de datos heredado y un origen de datos <xref:System.Windows.Data.XmlDataProvider> (no se muestra). El propio enlace especifica la propiedad de origen deseada mediante <xref:System.Windows.Data.Binding.XPath%2A> en el origen de datos.

[!code-xaml[PropertiesOvwSupport#BasicInlineBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#basicinlinebinding)]

> [!NOTE]
> Los enlaces se tratan como un valor local, lo que significa que si establece otro valor local, eliminará el enlace. Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](dependency-property-value-precedence.md).

Las propiedades de dependencia, o bien la clase <xref:System.Windows.DependencyObject>, no admiten de forma nativa <xref:System.ComponentModel.INotifyPropertyChanged> para fines de generación de notificaciones de cambios en el valor de propiedad de origen <xref:System.Windows.DependencyObject> para las operaciones de enlace de datos. Para obtener más información acerca de cómo crear propiedades para su uso en un enlace de datos capaz de notificar los cambios en un destino de enlace de datos, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).

### <a name="styles"></a>Estilos
Los estilos y las plantillas son dos de los principales escenarios que invitan a usar las propiedades de dependencia. Los estilos son particularmente útiles para establecer las propiedades que definen la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de la aplicación. Los estilos se definen normalmente como recursos en XAML. Los estilos interactúan con el sistema de propiedades porque suelen contener "establecedores" para determinadas propiedades, así como "desencadenadores" que cambian un valor de propiedad según el valor en tiempo real de otra propiedad.

En el ejemplo siguiente se crea un estilo simple (que se definiría dentro de un <xref:System.Windows.FrameworkElement.Resources%2A> Diccionario, que no se muestra) y, a continuación, se aplica ese estilo directamente a la <xref:System.Windows.FrameworkElement.Style%2A> propiedad de <xref:System.Windows.Controls.Button> . El establecedor dentro del estilo establece la propiedad <xref:System.Windows.Controls.Control.Background%2A> de un <xref:System.Windows.Controls.Button> con estilo en el color verde.

[!code-xaml[PropertiesOvwSupport#SimpleStyleDef](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyledef)]

[!code-xaml[PropertiesOvwSupport#SimpleStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyle)]

Para obtener más información, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

### <a name="animations"></a>Animaciones
Las propiedades de dependencia se pueden animar. Cuando una animación está aplicada y en ejecución, el valor animado funciona con una precedencia más alta que cualquier otro valor (por ejemplo, un valor local) que tenga la propiedad.

En el ejemplo siguiente se anima el atributo <xref:System.Windows.Controls.Control.Background%2A> de una propiedad <xref:System.Windows.Controls.Button> (técnicamente, se anima <xref:System.Windows.Controls.Control.Background%2A> mediante la sintaxis de elemento de propiedad para especificar un <xref:System.Windows.Media.SolidColorBrush> en blanco para <xref:System.Windows.Controls.Control.Background%2A>, y después la propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> de ese <xref:System.Windows.Media.SolidColorBrush> es la que se anima directamente).

[!code-xaml[PropertiesOvwSupport#MiniAnimate](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#minianimate)]

Para obtener más información sobre la animación de propiedades, consulte [Información general sobre animaciones](../graphics-multimedia/animation-overview.md) e [Información general sobre objetos Storyboard](../graphics-multimedia/storyboards-overview.md).

### <a name="metadata-overrides"></a>Invalidaciones de metadatos
Puede cambiar ciertos comportamientos de una propiedad de dependencia mediante la invalidación de los metadatos de la propiedad cuando se deriva de la clase que originalmente registra la propiedad de dependencia. La invalidación de metadatos se basa en el identificador <xref:System.Windows.DependencyProperty>. Para reemplazar los metadatos, no es necesario volver a implementar la propiedad. El sistema de propiedades controla de forma nativa el cambio en los metadatos; cada clase puede contener metadatos individuales de todas las propiedades que se heredan de las clases base, por tipo.

En el ejemplo siguiente se invalidan los metadatos para una propiedad de dependencia <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>. La invalidación de los metadatos de esta propiedad de dependencia concreta forma parte de un patrón de implementación que crea controles que pueden usar estilos predeterminados de temas.

[!code-csharp[PropertiesOvwSupport#OverrideMetadata](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#overridemetadata)]
[!code-vb[PropertiesOvwSupport#OverrideMetadata](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#overridemetadata)]

Para obtener más información sobre cómo invalidar u obtener los metadatos de las propiedades, consulte [Metadatos de las propiedades de dependencia](dependency-property-metadata.md).

### <a name="property-value-inheritance"></a>Herencia de valores de propiedad
Un elemento puede heredar el valor de una propiedad de dependencia de su elemento primario en el árbol de objetos.

> [!NOTE]
> El comportamiento de la herencia de valores de propiedad no está habilitado globalmente para todas las propiedades de dependencia, porque el tiempo de cálculo de la herencia afecta de algún modo al rendimiento. La herencia de valores de propiedad suele habilitarse normalmente solo para las propiedades donde un escenario determinado sugiere que dicha herencia es adecuada. Para determinar si una propiedad de dependencia se hereda, puede consultar la sección de **información sobre las propiedades de dependencia** correspondiente a esa propiedad de dependencia en la referencia del SDK.

En el ejemplo siguiente se muestra un enlace y se establece la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> que especifica el origen del enlace, que no se mostró en el ejemplo del enlace anterior. No es necesario que los enlaces siguientes en los objetos secundarios especifiquen el origen; pueden usar el valor heredado de <xref:System.Windows.FrameworkElement.DataContext%2A> en el objeto <xref:System.Windows.Controls.StackPanel> primario. (Como alternativa, un objeto secundario podría especificar directamente su propio <xref:System.Windows.FrameworkElement.DataContext%2A> o un <xref:System.Windows.Data.Binding.Source%2A> en <xref:System.Windows.Data.Binding>, y no usar deliberadamente el valor heredado para el contexto de datos de sus enlaces).

[!code-xaml[PropertiesOvwSupport#InheritanceContext](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#inheritancecontext)]

Para más información, vea [Herencia de valores de propiedad](property-value-inheritance.md).

### <a name="wpf-designer-integration"></a>Integración de WPF Designer
Un control personalizado con propiedades que se implementan como propiedades de dependencia recibirá el diseñador de WPF adecuado para la compatibilidad con Visual Studio. Un ejemplo es la capacidad de editar las propiedades de dependencia directas y adjuntas con la ventana **Propiedades**. Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).

## <a name="dependency-property-value-precedence"></a>Prioridad de los valores de propiedades de dependencia
Cuando se obtiene el valor de una propiedad de dependencia, potencialmente se está obteniendo un valor establecido en esa propiedad mediante cualquiera de las otras entradas basadas en propiedades que se incluyen en el sistema de propiedades de WPF. La precedencia de los valores de propiedad de dependencia existe para que distintos escenarios sobre cómo las propiedades obtienen sus valores puedan interactuar de forma predecible.

Considere el ejemplo siguiente. El ejemplo incluye un estilo que se aplica a todos los botones y sus propiedades <xref:System.Windows.Controls.Control.Background%2A>, pero después también especifica un botón con un valor <xref:System.Windows.Controls.Control.Background%2A> establecido localmente.

> [!NOTE]
> La documentación del SDK usa los términos "valor local" o "valor establecido localmente" ocasionalmente al hablar de las propiedades de dependencia. Un valor establecido localmente es un valor de propiedad que se establece directamente en una instancia de objeto en el código, o bien como un atributo en un elemento en XAML.  
  
En principio, para el primer botón, la propiedad se establece dos veces, pero se aplica solo un valor: el valor con la precedencia más alta. Un valor establecido localmente tiene la precedencia más alta (excepto para una animación en ejecución, pero ninguna animación es aplicable en este ejemplo) y, por tanto, el valor establecido localmente se usa en lugar del valor del establecedor de estilo para el fondo del primer botón. El segundo botón no tiene ningún valor local (ni ningún otro valor con una precedencia más alta que un establecedor de estilo) y, por tanto, el fondo de ese botón procede del establecedor de estilo.

[!code-xaml[PropertiesOvwSupport#MiniPrecedence](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#miniprecedence)]  

### <a name="why-does-dependency-property-precedence-exist"></a>¿Por qué existe la precedencia de las propiedades de dependencia?
Normalmente, no querrá que los estilos se apliquen siempre y oculten incluso un valor establecido localmente de un elemento individual (de lo contrario, sería difícil usar estilos o elementos en general). Por lo tanto, los valores que proceden de estilos funcionan con una precedencia más baja que un valor establecido localmente. Para obtener una lista más completa de las propiedades de dependencia y conocer la procedencia del valor efectivo de una propiedad de dependencia, consulte [Prioridad de los valores de propiedades de dependencia](dependency-property-value-precedence.md).

> [!NOTE]
> Existen varias propiedades definidas en elementos de WPF que no son propiedades de dependencia. En general, las propiedades se implementaban como propiedades de dependencia solo cuando era necesario admitir al menos uno de los escenarios que habilitaba el sistema de propiedades: enlace de datos, estilos, animación, compatibilidad con los valores predeterminados, herencia, propiedades adjuntas o invalidación.

## <a name="learning-more-about-dependency-properties"></a>Más información sobre las propiedades de dependencia  

- Una propiedad adjunta es un tipo de propiedad que admite una sintaxis especializada en XAML. Una propiedad adjunta no suele tener una correspondencia de 1:1 con una propiedad de Common Language Runtime (CLR) y no es necesariamente una propiedad de dependencia. El propósito típico de una propiedad adjunta es permitir que los elementos secundarios informen los valores de propiedad de un elemento primario, aunque el elemento primario y el elemento secundario no posean esa propiedad como parte de los listados de miembros de clase. Un escenario principal es habilitar los elementos secundarios para que informen al elemento primario de cómo se deben mostrar en [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]; para obtener un ejemplo, vea <xref:System.Windows.Controls.DockPanel.Dock%2A> o <xref:System.Windows.Controls.Canvas.Left%2A>. Para obtener información detallada, vea [Información general sobre propiedades asociadas](attached-properties-overview.md).

- Los desarrolladores de componentes o de aplicaciones pueden querer crear su propia propiedad de dependencia para habilitar funcionalidades, tales como el enlace de datos o la compatibilidad con estilos, o para admitir la invalidación y la coerción de valores. Para obtener más información, consulte [Propiedades de dependencia personalizadas](custom-dependency-properties.md).

- Considere las propiedades de dependencia como propiedades públicas, accesibles o al menos reconocible por cualquier llamador que tenga acceso a una instancia de. Para obtener más información, consulte [Seguridad de las propiedades de dependencia](dependency-property-security.md).

## <a name="see-also"></a>Consulte también:

- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Propiedades de dependencia de sólo lectura](read-only-dependency-properties.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Arquitectura de WPF](wpf-architecture.md)
