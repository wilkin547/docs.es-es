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
ms.openlocfilehash: 08594d9757596eed470ffba8b5b63a01c493c358
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583943"
---
# <a name="xname-directive"></a>x:Name (Directiva)
Identifica los elementos definidos por XAML en un ámbito de nombres XAML. Ámbitos de nombres XAML y sus modelos de unicidad pueden aplicarse a los objetos con instancias, cuando marcos proporcionan API o implementan comportamientos que tienen acceso al gráfico de objetos creados por XAML en tiempo de ejecución.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`XAMLNameValue`|Una cadena que se ajusta a las restricciones de la [gramática de XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md).|  
  
## <a name="remarks"></a>Comentarios  
 Después de `x:Name` se aplica a un marco de trabajo de respaldo del modelo de programación, el nombre es equivalente a la variable que contiene una referencia de objeto o una instancia devuelta por un constructor.  
  
 El valor de un `x:Name` la directiva de uso debe ser única dentro de un ámbito de nombres XAML. De forma predeterminada cuando se usa mediante la API de servicios XAML de .NET Framework, el ámbito de nombres XAML primario se define en el elemento raíz XAML de una sola producción de XAML y abarca los elementos que se encuentran en ese producción de XAML. Más ámbitos de nombres XAML discretos que se produzcan dentro de una sola producción de XAML pueden definirse mediante marcos para abordar escenarios concretos. Por ejemplo, en WPF, nuevos ámbitos de nombres XAML se definen y creados por una plantilla que también se define en esa producción de XAML. Para obtener más información acerca de los ámbitos de nombres XAML (escritos para WPF pero pertinente para muchos conceptos de ámbito de nombres XAML), consulte [ámbitos de nombres de XAML de WPF](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 En general, `x:Name` no se debe aplicar en situaciones que también usan `x:Key`. Implementaciones de XAML específicas marcos existentes han introducido los conceptos de sustitución entre `x:Key` y `x:Name`, pero que no es una práctica recomendada. Servicios XAML de .NET framework no admite estos conceptos de sustitución cuando se administran como información de clave de nombre/ <xref:System.Windows.Markup.INameScope> o <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 Las reglas para permitir de `x:Name` , así como el cumplimiento de unicidad nombre potencialmente se definen mediante marcos de aplicación específicos. Sin embargo, para poder usarlo con los servicios XAML de .NET Framework, las definiciones de marco de trabajo de la unicidad de ámbito de nombres XAML deben ser coherentes con la definición de <xref:System.Windows.Markup.INameScope> información en esta documentación y debe usar las mismas reglas sobre dónde el la información se aplica. Por ejemplo, el [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] implementación distintos elementos de marcado divide en diferentes <xref:System.Windows.NameScope> intervalos, como diccionarios de recursos, el árbol lógico creado por el nivel de página XAML, plantillas y otros aplazada contenido y, a continuación, aplica XAML exclusividad del nombre dentro de cada uno de los ámbitos de nombres XAML.  
  
 Para los tipos personalizados que usan los escritores de objetos XAML de los servicios XAML de .NET Framework, una propiedad que se asigna a `x:Name` en tipo se puede establecer o cambiar. Definir este comportamiento mediante referencia al nombre de la propiedad para asignar el <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> en el código de la definición de tipo.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> es un atributo de nivel de tipo.  
  
 Servicios de XAML Using.NET Framework, la lógica de respaldo para la compatibilidad de ámbito de nombres XAML se pueden definir en una manera independiente del marco de trabajo mediante la implementación de la <xref:System.Windows.Markup.INameScope> interfaz.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 En la configuración de compilación estándar para un [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] aplicación que utiliza XAML, clases parciales y código subyacente, especificado `x:Name` se convierte en el nombre de un campo que se crea en la base de código al [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] procesados por un elemento de marcado tarea de compilación de la compilación y ese campo contiene una referencia al objeto. De forma predeterminada, el campo creado es interno. Puede cambiar el acceso al campo especificando el [x: FieldModifier (atributo)](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md). En WPF y Silverlight, la secuencia es que define la compilación de marcado y los nombres de campo en una clase parcial, pero el valor inicialmente está vacío. A continuación, un método generado denominado `InitializeComponent` se llama desde dentro del constructor de clase. `InitializeComponent` consta de `FindName` llama con cada uno de los `x:Name` valores que existen en el elemento definido por XAML de la clase parcial, como las cadenas de entrada. Los valores devueltos, a continuación, se asignan a la referencia del campo con el mismo nombre para rellenar los valores de campo con los objetos que se crearon a partir de XAML de análisis. La ejecución de `InitializeComponent` hacer posible la referencia que el gráfico de objeto de tiempo de ejecución utilizando la `x:Name` / nombre de campo directamente, en lugar de tener que llamar a `FindName` explícitamente cada vez que necesite una referencia a un objeto definido por XAML.  
  
 Para un WPF aplicación que utiliza Microsoft Visual Basic tiene como destino e incluye los archivos XAML con `Page` acción de compilación, una propiedad de referencia independiente se crea durante la compilación que agrega el `WithEvents` palabra clave a todos los elementos que tienen un `x:Name`, para admitir `Handles` sintaxis para los delegados de controlador de eventos. Esta propiedad siempre es pública. Para más información, vea [Control de eventos en Visual Basic y WPF](../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 `x:Name` se usa el procesador de WPF XAML para registrar un nombre en un ámbito de nombres XAML en tiempo de carga, incluso en aquellos casos donde la página no está compilado por marcado mediante acciones de compilación (por ejemplo, XAML flexible de un diccionario de recursos). Una razón para este comportamiento es que el `x:Name` potencialmente es necesaria para <xref:System.Windows.Data.Binding.ElementName%2A> enlace. Para obtener más información, consulte [Data Binding Overview](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Como se mencionó anteriormente, `x:Name` (o `Name`) no se debe aplicar en situaciones que también usan `x:Key`. El [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> tiene un comportamiento especial de definición de sí mismo como un ámbito de nombres XAML, pero devolver no implementado o valores nulos para <xref:System.Windows.Markup.INameScope> API como una manera de aplicar este comportamiento. Si el analizador de WPF XAML encuentra `Name` o `x:Name` en definida en XAML <xref:System.Windows.ResourceDictionary>, el nombre no se agrega a cualquier ámbito de nombres XAML. Intentando buscar ese nombre en cualquier ámbito de nombres XAML y el `FindName` métodos no devolverán resultados válidos.  
  
### <a name="xname-and-name"></a>x: Name y nombre  
 Muchos escenarios de aplicación de WPF pueden evitar cualquier uso de la `x:Name` atributo, porque el `Name` propiedad de dependencia como especificadas en el valor predeterminado el espacio de nombres XAML para varias de las clases bases importantes como <xref:System.Windows.FrameworkElement> y <xref:System.Windows.FrameworkContentElement> cumple este mismo propósito. Todavía hay algunos escenarios comunes de XAML y WPF acceso a un elemento sin ningún código donde `Name` propiedad en el nivel de marco es importante. Por ejemplo, no admiten ciertas clases de soporte técnico de animación y guiones gráficos una `Name` propiedad, pero a menudo es necesario hacer referencia en el código con el fin de controlar la animación. Se debe especificar `x:Name` como un atributo en escalas de tiempo y transformaciones que se crean en XAML, si va a hacer referencia a ellos desde el código más adelante.  
  
 Si <xref:System.Windows.FrameworkElement.Name%2A> está disponible como una propiedad en la clase, <xref:System.Windows.FrameworkElement.Name%2A> y `x:Name` pueden usarse indistintamente como atributos, pero se producirá una excepción de análisis si se especifican ambos en el mismo elemento. Si el XAML es compilado por marcado, se producirá la excepción en la compilación de marcado, en caso contrario, se produce en la carga.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> se puede establecer mediante sintaxis de atributo XAML y en el código mediante <xref:System.Windows.DependencyObject.SetValue%2A>; sin embargo, observe esa configuración la <xref:System.Windows.FrameworkElement.Name%2A> propiedad en el código no crea la referencia del campo representativo dentro del ámbito de nombres XAML en la mayoría de los casos donde el XAML ya está puede cargar. En lugar de intentar establecer <xref:System.Windows.FrameworkElement.Name%2A> en código, utilice <xref:System.Windows.NameScope> métodos desde el código, en el ámbito de nombres adecuado.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> También se puede establecer utilizando la sintaxis de elemento de propiedad con el texto interno, pero que es poco habitual. En cambio, `x:Name` no se puede establecer en la sintaxis de elemento de propiedad XAML o en el código mediante <xref:System.Windows.DependencyObject.SetValue%2A>; solo se puede establecer utilizando la sintaxis de atributo en objetos porque es una directiva.  
  
## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight  
 `x:Name` para Silverlight se documenta por separado. Para obtener más información, consulte [XAML Namespace (x:) Características del lenguaje (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>  
 <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>  
 [Árboles en WPF](../../../docs/framework/wpf/advanced/trees-in-wpf.md)
