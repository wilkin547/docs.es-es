---
title: x:Name (Directiva)
ms.date: 03/30/2017
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
ms.openlocfilehash: 9f812a49a3217a563be1bd7f1d999b641c28463d
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432717"
---
# <a name="xname-directive"></a>x:Name (Directiva)

Identifica de forma única los elementos definidos por XAML en un ámbito de nombres XAML. Los ámbitos de nombres XAML y sus modelos de unicidad se pueden aplicar a los objetos con instancias, cuando los marcos de trabajo proporcionan API o implementan comportamientos que tienen acceso al gráfico de objetos creado por XAML en tiempo de ejecución.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object x:Name="XAMLNameValue".../>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`XAMLNameValue`|Cadena que se ajusta a las restricciones de [La gramática XamlName](xamlname-grammar.md).|

## <a name="remarks"></a>Observaciones

Después `x:Name` se aplica al modelo de programación de respaldo de un marco de trabajo, el nombre es equivalente a la variable que contiene una referencia de objeto o una instancia devuelta por un constructor.

El valor `x:Name` de un uso de directiva debe ser único dentro de un ámbito de nombres XAML. De forma predeterminada, cuando se usa la API de servicios XAML de .NET, el ámbito de nombres XAML principal se define en el elemento raíz XAML de una única producción XAML y abarca los elementos contenidos en esa producción XAML. Los marcos de trabajo pueden definir ámbitos de nombres XAML discretos adicionales que pueden producirse dentro de una única producción XAML para abordar escenarios específicos. Por ejemplo, en WPFWPF, los nuevos ámbitos de nombres XAML se definen y crean mediante cualquier plantilla que también se define en esa producción XAML. Para obtener más información acerca de los ámbitos de nombres XAML (escritos para WPF pero relevantes para muchos conceptos de ámbito de nombres XAML), vea [Ámbitos](../../framework/wpf/advanced/wpf-xaml-namescopes.md)de nombres XAML de WPF .

En general, `x:Name` no debe aplicarse `x:Key`en situaciones que también utilizan . Las implementaciones XAML de marcos existentes específicos han introducido conceptos de sustitución entre `x:Key` y `x:Name`, pero no es una práctica recomendada. Los servicios XAML de .NET no admiten estos <xref:System.Windows.Markup.INameScope> conceptos de sustitución al controlar información de nombre/clave como o <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.

Las normas para `x:Name` la permisividad, así como la aplicación de la exclusividad de los nombres, están definidas potencialmente por marcos de aplicación específicos. Sin embargo, para poder usarse con los servicios XAML de .NET, las <xref:System.Windows.Markup.INameScope> definiciones de marco de trabajo de unicidad del ámbito de nombres XAML deben ser coherentes con la definición de información de esta documentación y deben usar las mismas reglas con respecto a dónde se aplica la información. Por ejemplo, [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] la implementación divide <xref:System.Windows.NameScope> varios elementos de marcado en intervalos independientes, como diccionarios de recursos, el árbol lógico creado por el XAML de nivel de página, plantillas y otro contenido diferido y, a continuación, aplica la unicidad de nombres XAML dentro de cada uno de esos ámbitos de nombres XAML.

Para los tipos personalizados que usan escritores de objetos XAML de servicios XAML de .NET, se puede establecer o cambiar una propiedad que se asigna a `x:Name` un tipo. Este comportamiento se define haciendo referencia al nombre <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> de la propiedad que se asignará con el código de definición de tipo.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>es un atributo de nivel de tipo.

Using.NET servicios XAML, la lógica de respaldo para la compatibilidad con el <xref:System.Windows.Markup.INameScope> ámbito de nombres XAML se puede definir de forma neutral para el marco de trabajo mediante la implementación de la interfaz.

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

En la configuración de [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] compilación estándar para una aplicación que usa XAML, clases parciales y código subyacente, el especificado `x:Name` se convierte en el nombre de un campo que se crea en el código subyacente cuando [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] se procesa mediante una tarea de compilación de compilación de marcado y ese campo contiene una referencia al objeto. De forma predeterminada, el campo creado es interno. Puede cambiar el acceso a campos especificando el [atributo x:FieldModifier](xfieldmodifier-directive.md). En WPFWPF y Silverlight, la secuencia es que la compilación de marcado define y nombra el campo en una clase parcial, pero el valor está inicialmente vacío. A continuación, se `InitializeComponent` llama a un método generado denominado desde dentro del constructor de clase. `InitializeComponent`consiste `FindName` en llamadas `x:Name` que usan cada uno de los valores que existen en la parte definida por XAML de la clase parcial como cadenas de entrada. A continuación, los valores devueltos se asignan a la referencia de campo con nombre similar para rellenar los valores de campo con objetos creados a partir del análisis XAML. La ejecución `InitializeComponent` de hacer posible hacer referencia al `x:Name` gráfico de objetos de `FindName` tiempo de ejecución mediante el nombre de campo / directamente, en lugar de tener que llamar explícitamente cada vez que necesite una referencia a un objeto definido por XAML.

Para una aplicación WPFWPF que usa los destinos `Page` de Microsoft Visual Basic e incluye archivos `WithEvents` XAML con acción de `x:Name`compilación, `Handles` se crea una propiedad de referencia independiente durante la compilación que agrega la palabra clave a todos los elementos que tienen una sintaxis , para admitir la sintaxis para los delegados del controlador de eventos. Esta propiedad es siempre pública. Para más información, vea [Control de eventos en Visual Basic y WPF](../../framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).

`x:Name`El procesador XAML de WPF usa para registrar un nombre en un ámbito de nombres XAML en tiempo de carga, incluso en los casos en los que la página no está compilada por acciones de compilación con marcado (por ejemplo, XAML flexible de un diccionario de recursos). Una razón para este `x:Name` comportamiento es porque <xref:System.Windows.Data.Binding.ElementName%2A> es potencialmente necesario para el enlace. Para obtener más información, vea [Información general sobre el enlace](../data/data-binding-overview.md)de datos .

Como se `x:Name` mencionó `Name`anteriormente, (o ) `x:Key`no debe aplicarse en situaciones que también utilizan . Tiene [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> un comportamiento especial de definirse como un ámbito de nombres XAML <xref:System.Windows.Markup.INameScope> pero devolver valores no implementados o valores nulos para las API como una forma de aplicar este comportamiento. Si el analizador XAML `Name` de `x:Name` WPF encuentra <xref:System.Windows.ResourceDictionary>o en un XAML definido , el nombre no se agrega a ningún ámbito de nombres XAML. Al intentar encontrar ese nombre desde cualquier `FindName` ámbito de nombres XAML y los métodos no se devolverán resultados válidos.

### <a name="xname-and-name"></a>x:Nombre y nombre

Muchos escenarios de aplicación WPFWPF `x:Name` pueden evitar `Name` cualquier uso del atributo, porque la propiedad de dependencia <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> especificada en el espacio de nombres XAML predeterminado para varias de las clases base importantes, como y satisface este mismo propósito. Todavía hay algunos escenarios comunes de XAML y WPF `Name` donde el acceso de código a un elemento sin propiedad en el nivel de marco de trabajo es importante. Por ejemplo, ciertas clases de `Name` compatibilidad con animaciones y guiones gráficos no admiten una propiedad, pero a menudo es necesario hacer referencia a ellas en el código para controlar la animación. Debe especificar `x:Name` como un atributo en las escalas de tiempo y las transformaciones que se crean en XAML, si tiene la intención de hacer referencia a ellos desde el código más adelante.

Si <xref:System.Windows.FrameworkElement.Name%2A> está disponible como una <xref:System.Windows.FrameworkElement.Name%2A> propiedad `x:Name` en la clase y se puede usar indistintamente como atributos, pero se producirá una excepción de análisis si ambos se especifican en el mismo elemento. Si el XAML se compila el marcado, la excepción se producirá en la compilación de marcado, de lo contrario se produce en la carga.

<xref:System.Windows.FrameworkElement.Name%2A>se puede establecer mediante la sintaxis <xref:System.Windows.DependencyObject.SetValue%2A>de atributo XAML y en el código mediante ; Tenga en cuenta, sin embargo, que establecer la <xref:System.Windows.FrameworkElement.Name%2A> propiedad en el código no crea la referencia de campo representativo dentro del ámbito de nombres XAML en la mayoría de las circunstancias donde el XAML ya está cargado. En lugar de <xref:System.Windows.FrameworkElement.Name%2A> intentar establecer <xref:System.Windows.NameScope> en el código, utilice métodos de código, con el ámbito de nombres adecuado.

<xref:System.Windows.FrameworkElement.Name%2A>También se puede establecer mediante la sintaxis de elemento de propiedad con texto interno, pero eso es poco común. Por el `x:Name` contrario, no se puede establecer en <xref:System.Windows.DependencyObject.SetValue%2A>la sintaxis del elemento de propiedad XAML o en el código mediante ; solo se puede establecer mediante la sintaxis de atributo en los objetos porque es una directiva.

## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight

`x:Name`para Silverlight se documenta por separado. Para obtener más información, vea [Espacio de nombres XAML (x:) Características del idioma (Silverlight).](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95))

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [Árboles en WPF](../../framework/wpf/advanced/trees-in-wpf.md)
