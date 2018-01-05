---
title: x:Name (Directiva)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
caps.latest.revision: "27"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 676f7f696fda26ee9d86d14f06dc7b70e2565157
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xname-directive"></a>x:Name (Directiva)
Identifica de forma única los elementos definidos por el XAML en un ámbito de nombres XAML. Ámbitos de nombres XAML y sus modelos de unicidad pueden aplicarse a los objetos con instancias, cuando marcos de trabajo proporcionan API o implementan comportamientos que tienen acceso al gráfico de objetos creados por el XAML en tiempo de ejecución.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`XAMLNameValue`|Una cadena que se ajusta a las restricciones de la [XamlName (gramática)](../../../docs/framework/xaml-services/xamlname-grammar.md).|  
  
## <a name="remarks"></a>Comentarios  
 Después de `x:Name` se aplica a un marco de trabajo de copia de modelo de programación, el nombre es equivalente a la variable que contiene una referencia de objeto o una instancia devuelta por un constructor.  
  
 El valor de un `x:Name` la directiva de uso debe ser única dentro de un ámbito de nombres XAML. De forma predeterminada cuando se usa por la API de servicios XAML de .NET Framework, el ámbito de nombres XAML principal se define en el elemento raíz XAML de una sola producción de XAML y abarca los elementos que se encuentran en ese producción de XAML. Más ámbitos de nombres XAML discretos que pueden producirse en una sola producción de XAML pueden definirse mediante marcos para resolver escenarios concretos. Por ejemplo, en WPF, nuevos ámbitos de nombres XAML están definidos y creados por una plantilla que también se define en esa producción de XAML. Para obtener más información acerca de los ámbitos de nombres XAML (escritos para WPF pero pertinente para muchos conceptos del ámbito de nombres XAML), consulte [ámbitos de nombres de XAML de WPF](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 En general, `x:Name` no se debe aplicar en situaciones que también usan `x:Key`. Las implementaciones de XAML marcos existentes concretos han introducido conceptos de substitución entre `x:Key` y `x:Name`, pero que no es una práctica recomendada. Servicios XAML de .NET framework no admite estos conceptos de sustitución al controlar la información de nombre/clave como <xref:System.Windows.Markup.INameScope> o <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 Las reglas para permitir de `x:Name` , así como el cumplimiento de la singularidad de nombre potencialmente se definen mediante marcos de aplicación específicos. Sin embargo, para poder utilizarlo con los servicios XAML de .NET Framework, el marco de trabajo definiciones de unicidad de ámbito de nombres XAML deben ser coherentes con la definición de <xref:System.Windows.Markup.INameScope> información en esta documentación y debe usar las mismas reglas con respecto a dónde el la información se aplica. Por ejemplo, el [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] implementación divide varios elementos de marcado en diferentes <xref:System.Windows.NameScope> intervalos, como diccionarios de recursos, el árbol lógico creado por el nivel de página XAML, plantillas y otros diferidas contenido y, a continuación, aplica XAML nombres únicos dentro de cada uno de los ámbitos de nombres XAML.  
  
 Para los tipos personalizados que usan los escritores de objetos de servicios XAML de .NET Framework, una propiedad que se asigna a `x:Name` en un tipo se puede establecer o cambiar. Definir este comportamiento haciendo referencia al nombre de la propiedad que se va a asignar a la <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> en el código de definición de tipo.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>es un atributo de nivel de tipo.  
  
 Servicios de XAML de Using.NET Framework, la lógica de respaldo para la compatibilidad de ámbito de nombres XAML puede definirse de forma independiente del marco de trabajo mediante la implementación de la <xref:System.Windows.Markup.INameScope> interfaz.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 En la configuración de compilación estándar de un [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] aplicación que utiliza XAML, clases parciales y código subyacente, especificado `x:Name` se convierte en el nombre de un campo que se crea en subyacente el código cuando [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] es procesado por un marcado tarea de compilación de compilación y que ese campo contiene una referencia al objeto. De forma predeterminada, el campo creado es interno. Puede cambiar el acceso al campo especificando el [x: FieldModifier (atributo)](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md). En WPF y Silverlight, la secuencia es que define la compilación de marcado y los nombres de campo en una clase parcial, pero el valor se muestra inicialmente vacío. A continuación, un método generado con el nombre `InitializeComponent` se llama desde el constructor de clase. `InitializeComponent`consta de `FindName` llama con cada uno de los `x:Name` cadenas de entrada de valores que existen en la parte de la clase parcial como definidas por XAML. Los valores devueltos, a continuación, se asignan a la referencia del campo con el mismo nombre para rellenar los valores de campo con objetos que se crearon a partir de XAML de análisis. La ejecución de `InitializeComponent` permiten referencia el gráfico de objeto de tiempo de ejecución utilizando la `x:Name` / nombre del campo directamente, en lugar de tener que llamar `FindName` explícitamente cada vez necesita una referencia a un objeto definido por el XAML.  
  
 Para una aplicación WPF que utiliza la [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] tiene como destino e incluye archivos XAML con `Page` se crea la acción de compilación, una propiedad de referencia independiente durante la compilación que agrega la `WithEvents` palabra clave a todos los elementos que tienen un `x:Name`a admitir `Handles` sintaxis para los delegados de controladores de eventos. Esta propiedad siempre es pública. Para más información, vea [Control de eventos en Visual Basic y WPF](../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 `x:Name`se usa el procesador XAML de WPF para registrar un nombre en un ámbito de nombres XAML en tiempo de carga, incluso en aquellos casos donde la página no está compilado por marcado mediante acciones de compilación (por ejemplo, XAML dinámico de un diccionario de recursos). Una de las razones para este comportamiento es porque el `x:Name` se podrían necesitarse para <xref:System.Windows.Data.Binding.ElementName%2A> enlace. Para obtener más información, consulte [información general sobre el enlace de datos](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Como se mencionó anteriormente, `x:Name` (o `Name`) no se debe aplicar en situaciones que también usan `x:Key`. El [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> tiene un comportamiento especial de definición de sí mismo como un ámbito de nombres XAML, pero devolver no implementado o valores nulos para <xref:System.Windows.Markup.INameScope> las API de una manera de imponer este comportamiento. Si el analizador de XAML de WPF encuentra `Name` o `x:Name` en un objeto definido en el XAML <xref:System.Windows.ResourceDictionary>, el nombre no se agrega a cualquier ámbito de nombres XAML. Intenta buscar ese nombre en cualquier ámbito de nombres XAML y el `FindName` métodos no devolverá resultados válidos.  
  
### <a name="xname-and-name"></a>x: Name y nombre  
 Muchos escenarios de aplicación de WPF pueden evitar cualquier uso de la `x:Name` atributo, porque la `Name` propiedad de dependencia como especificadas en el valor predeterminado espacio de nombres XAML para algunas de las clases base importantes como <xref:System.Windows.FrameworkElement> y <xref:System.Windows.FrameworkContentElement> satisface este mismo propósito. Todavía hay algunos escenarios XAML y WPF comunes donde código de acceso a un elemento y no tienen ninguna `Name` propiedad en el nivel de marco de trabajo es importante. Por ejemplo, no admiten ciertas clases de soporte de animación y guiones gráficos una `Name` propiedad, pero a menudo necesitan que se haga referencia en el código para controlar la animación. Debe especificar `x:Name` como un atributo de escalas de tiempo y las transformaciones que se crean en XAML, si piensa hacer referencia a ellas desde el código más adelante.  
  
 Si <xref:System.Windows.FrameworkElement.Name%2A> está disponible como una propiedad en la clase, <xref:System.Windows.FrameworkElement.Name%2A> y `x:Name` pueden utilizar indistintamente como atributos, pero se producirá una excepción de análisis si se especifican ambos en el mismo elemento. Si el XAML es compilado por marcado, la excepción se producirá en la compilación de marcado, en caso contrario, produce en la carga.  
  
 <xref:System.Windows.FrameworkElement.Name%2A>se puede establecer utilizando la sintaxis de atributo XAML y en el código mediante <xref:System.Windows.DependencyObject.SetValue%2A>; sin embargo, observe esa configuración el <xref:System.Windows.FrameworkElement.Name%2A> propiedad en el código no crea la referencia de campo representativa dentro del ámbito de nombres XAML en la mayoría de los casos donde el XAML es ya cargar. En lugar de intentar establecer <xref:System.Windows.FrameworkElement.Name%2A> en el código, utilice <xref:System.Windows.NameScope> métodos del código, en el ámbito de nombres adecuado.  
  
 <xref:System.Windows.FrameworkElement.Name%2A>También puede establecerse utilizando la sintaxis de elemento de propiedad con el texto interno, pero que es poco habitual. En cambio, `x:Name` no se puede establecer en la sintaxis de elemento de propiedad XAML o en el código mediante <xref:System.Windows.DependencyObject.SetValue%2A>; sólo se puede establecer utilizando la sintaxis de atributo en objetos porque es una directiva.  
  
## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight  
 `x:Name`para Silverlight se documenta por separado. Para obtener más información, vea [XAML Namespace (x:) Características del lenguaje (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>  
 <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>  
 [Árboles en WPF](../../../docs/framework/wpf/advanced/trees-in-wpf.md)
