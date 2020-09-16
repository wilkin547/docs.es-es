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
ms.openlocfilehash: ddaa35b18d1c632fc49b18dabf0d992dc1c78fcc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549488"
---
# <a name="xname-directive"></a>x:Name (Directiva)

Identifica de forma única los elementos definidos por XAML en un ámbito de nombres XAML. Los ámbitos de ejecución XAML y sus modelos de unicidad se pueden aplicar a los objetos con instancias, cuando los marcos de trabajo proporcionan API o implementan comportamientos que tienen acceso al gráfico de objetos creado por XAML en tiempo de ejecución.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object x:Name="XAMLNameValue".../>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`XAMLNameValue`|Cadena que se ajusta a las restricciones de la [Gramática XamlName](xamlname-grammar.md).|

## <a name="remarks"></a>Comentarios

Una vez `x:Name` que se aplica al modelo de programación de respaldo de un marco de trabajo, el nombre es equivalente a la variable que contiene una referencia de objeto o una instancia de devuelta por un constructor.

El valor de uso de una `x:Name` Directiva debe ser único dentro de un ámbito de nombres XAML. De forma predeterminada, cuando lo usa la API de servicios XAML de .NET, el ámbito de nombres XAML primario se define en el elemento raíz XAML de una sola producción XAML y engloba los elementos contenidos en esa producción XAML. Los marcos de trabajo de XAML discretos adicionales que pueden producirse en una sola producción de XAML pueden definirse mediante marcos para abordar escenarios concretos. Por ejemplo, en WPF, los ámbitos de nuevo XAML se definen y crean en cualquier plantilla que también se define en esa producción de XAML. Para obtener más información sobre los ámbitos de nombres XAML (escritos para WPF pero relevantes para muchos conceptos de ámbito de nombres XAML), vea ámbitos de nombres [XAML de WPF](/dotnet/desktop/wpf/advanced/wpf-xaml-namescopes).

En general, `x:Name` no se debe aplicar en situaciones que también usan `x:Key` . Las implementaciones de XAML de los marcos de trabajo existentes específicos han introducido conceptos de sustitución entre `x:Key` y `x:Name` , pero no es una práctica recomendada. Los servicios XAML de .NET no admiten estos conceptos de sustitución al tratar la información de nombre o clave como <xref:System.Windows.Markup.INameScope> o <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute> .

Las reglas de permisión de `x:Name` , así como la aplicación de la unicidad del nombre, pueden definirse mediante marcos de implementación específicos. Sin embargo, para poder usarlos con los servicios XAML de .NET, las definiciones de Framework de la singularidad del ámbito de nombres XAML deben ser coherentes con la definición de la <xref:System.Windows.Markup.INameScope> información de esta documentación y deben utilizar las mismas reglas en cuanto a dónde se aplica la información. Por ejemplo, la [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] implementación divide varios elementos de marcado en <xref:System.Windows.NameScope> intervalos independientes, como diccionarios de recursos, el árbol lógico creado por el XAML de nivel de página, plantillas y otro contenido aplazado y, a continuación, aplica la singularidad del nombre XAML dentro de cada uno de esos ámbitos de nombres XAML.

En el caso de los tipos personalizados que usan los escritores de objetos XAML de los servicios XAML de .NET, `x:Name` se puede establecer o cambiar una propiedad que se asigna a en un tipo. Este comportamiento se define haciendo referencia al nombre de la propiedad que se va a asignar a <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> en el código de definición de tipo.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> es un atributo de nivel de tipo.

Using.NET los servicios XAML, la lógica de respaldo para la compatibilidad con el ámbito de nombres XAML se puede definir en un modo independiente del marco implementando la <xref:System.Windows.Markup.INameScope> interfaz.

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

En la configuración de compilación estándar para una [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] aplicación que utiliza XAML, clases parciales y código subyacente, el especificado `x:Name` se convierte en el nombre de un campo que se crea en el código subyacente cuando [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] se procesa mediante una tarea de compilación de compilación de marcado y ese campo contiene una referencia al objeto. De forma predeterminada, el campo creado es interno. Puede cambiar el acceso al campo especificando el [atributo x:FieldModifier (](xfieldmodifier-directive.md). En WPF y Silverlight, la secuencia es que la compilación de marcado define y nombra el campo en una clase parcial, pero el valor está inicialmente vacío. A continuación, se llama a un método generado denominado `InitializeComponent` desde dentro del constructor de clase. `InitializeComponent` consta de `FindName` llamadas mediante cada uno de los `x:Name` valores que existen en la parte definida por XAML de la clase parcial como cadenas de entrada. Los valores devueltos se asignan a la referencia del campo con el mismo nombre para rellenar los valores de campo con los objetos que se crearon a partir del análisis de XAML. La ejecución de `InitializeComponent` permite hacer referencia al gráfico de objetos en tiempo de ejecución con el `x:Name` nombre de campo/directamente, en lugar de tener que llamar `FindName` explícitamente a cada vez que se necesita una referencia a un objeto definido en XAML.

Para una aplicación de WPF que usa los destinos de Microsoft Visual Basic e incluye archivos XAML con la `Page` acción de compilación, se crea una propiedad de referencia independiente durante la compilación que agrega la `WithEvents` palabra clave a todos los elementos que tienen un `x:Name` , para admitir la `Handles` Sintaxis de los delegados de controladores de eventos. Esta propiedad siempre es pública. Para más información, vea [Control de eventos en Visual Basic y WPF](/dotnet/desktop/wpf/advanced/visual-basic-and-wpf-event-handling).

`x:Name` lo usa el procesador XAML de WPF para registrar un nombre en un ámbito de nombres XAML en tiempo de carga, incluso en los casos en los que la página no está compilada por acciones de compilación (por ejemplo, XAML dinámico de un diccionario de recursos). Una razón para este comportamiento se debe a que `x:Name` es posible que sea necesario para el <xref:System.Windows.Data.Binding.ElementName%2A> enlace. Para obtener más información, vea [información general sobre el enlace de datos](../data/data-binding-overview.md).

Como se mencionó anteriormente, `x:Name` `Name` no se debe aplicar (o) en situaciones que también usan `x:Key` . [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> Tiene un comportamiento especial de definirse como un ámbito de nombres XAML, pero devolver valores no implementados o null para las <xref:System.Windows.Markup.INameScope> API como una manera de aplicar este comportamiento. Si el analizador XAML de WPF encuentra `Name` o `x:Name` en un definido por XAML <xref:System.Windows.ResourceDictionary> , el nombre no se agrega a ningún ámbito de nombres XAML. Si se intenta encontrar ese nombre desde cualquier ámbito de nombres XAML, los `FindName` métodos no devolverán resultados válidos.

### <a name="xname-and-name"></a>x:Name y Name

Muchos escenarios de aplicaciones de WPF pueden evitar el uso del `x:Name` atributo, ya que la `Name` propiedad de dependencia tal como se especifica en el espacio de nombres XAML predeterminado para varias de las clases base importantes como <xref:System.Windows.FrameworkElement> y <xref:System.Windows.FrameworkContentElement> satisface este mismo propósito. Todavía hay algunos escenarios comunes de XAML y WPF en los que es importante el acceso del código a un elemento sin ninguna `Name` propiedad en el nivel de marco. Por ejemplo, algunas clases de compatibilidad con animaciones y guiones gráficos no admiten una `Name` propiedad, pero a menudo es necesario hacer referencia a ellas en el código para controlar la animación. Debe especificar `x:Name` como atributo en las escalas de tiempo y las transformaciones que se crean en XAML, si tiene previsto hacer referencia a ellos desde el código más adelante.

Si <xref:System.Windows.FrameworkElement.Name%2A> está disponible como propiedad en la clase, <xref:System.Windows.FrameworkElement.Name%2A> y `x:Name` se puede usar indistintamente como atributos, pero se producirá una excepción de análisis si ambos se especifican en el mismo elemento. Si se compila el marcado XAML, la excepción se producirá en la compilación de marcado; en caso contrario, se producirá en la carga.

<xref:System.Windows.FrameworkElement.Name%2A> se puede establecer mediante la sintaxis de atributo XAML y en <xref:System.Windows.DependencyObject.SetValue%2A> el código que usa; tenga en cuenta que si se establece la <xref:System.Windows.FrameworkElement.Name%2A> propiedad en el código, no se crea la referencia de campo representativa dentro del ámbito de nombres XAML en la mayoría de los casos en los que el XAML ya está cargado. En lugar de intentar establecer <xref:System.Windows.FrameworkElement.Name%2A> en el código, use <xref:System.Windows.NameScope> métodos del código, en el ámbito de nombres adecuado.

<xref:System.Windows.FrameworkElement.Name%2A> también se puede establecer mediante la sintaxis de elementos de propiedad con texto interno, pero esto no es habitual. Por el contrario, `x:Name` no se puede establecer en la sintaxis de elementos de propiedad XAML o en <xref:System.Windows.DependencyObject.SetValue%2A> el código que usa; solo se puede establecer mediante la sintaxis de atributo en objetos porque es una directiva.

## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight

`x:Name` para Silverlight se documenta por separado. Para obtener más información, vea [espacio de nombres XAML (x:) Características del lenguaje (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [Árboles en WPF](/dotnet/desktop/wpf/advanced/trees-in-wpf)
