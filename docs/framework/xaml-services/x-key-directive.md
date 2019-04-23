---
title: x:Key (Directiva)
ms.date: 03/30/2017
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
ms.openlocfilehash: 6ac878f24de594f8557ded8b0c3356217021b035
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223724"
---
# <a name="xkey-directive"></a>x:Key (Directiva)
Identifica los elementos que se crean y se hace referencia en un diccionario definido por XAML. Agregar un `x:Key` valor a un elemento de objeto XAML es la manera más común para identificar un recurso en un diccionario de recursos, por ejemplo, en un WPF <xref:System.Windows.ResourceDictionary>.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>Uso de atributos XAML (específico de WPF)  
  
```  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`stringKeyValue`|Una cadena de texto que se usará como una clave. La cadena de texto debe ajustarse a la [gramática de XamlName](xamlname-grammar.md).|  
|`markupExtensionUsage`|Dentro de los delimitadores de extensión de marcado {}, uso de una extensión de marcado que proporciona un objeto que se va a usar como clave. Vea la sección Comentarios.|  
  
## <a name="remarks"></a>Comentarios  
 `x:Key` admite el concepto de diccionario de recursos XAML. XAML como un lenguaje no define una implementación de diccionario de recursos, que es de izquierda a los marcos de interfaz de usuario específicos. Para obtener más información acerca de cómo se implementan los diccionarios de recursos XAML en WPF, vea [recursos XAML](../wpf/advanced/xaml-resources.md).  
  
 En XAML 2006 y WPF, `x:Key` debe proporcionarse como un atributo. Todavía puede usar las claves que no son cadenas, pero esto requiere el uso de una extensión de marcado para proporcionar el valor de no cadena en forma de atributo. Si utiliza XAML 2009, `x:Key` puede especificarse como un elemento admitir explícitamente diccionarios con clave por tipos de objetos distintos de cadenas sin necesidad de un intermediario de extensión de marcado. Consulte la sección "XAML 2009" de este tema. El resto de la sección de comentarios se aplica específicamente a la implementación de XAML 2006.  
  
 El valor del atributo `x:Key` puede ser cualquier cadena definida en el [gramática de XamlName](xamlname-grammar.md) o puede ser un objeto evaluado mediante una extensión de marcado. Para obtener un ejemplo de WPF, vea "Notas de uso de WPF".  
  
 Los elementos secundarios de un elemento primario que es un <xref:System.Collections.IDictionary> implementación normalmente debe incluir un `x:Key` atributo que especifica un valor de clave única dentro de ese diccionario. .NET Framework podría implementar propiedades de clave con alias para sustituir `x:Key` sobre determinados tipos; los tipos que definen tales propiedades deben atribuirse con <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 El equivalente de código de la especificación de `x:Key` es la clave que se usa para subyacente <xref:System.Collections.IDictionary>. Por ejemplo, un `x:Key` que se aplica en el marcado para un recurso en WPF es equivalente al valor de la `key` parámetro de <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> al agregar el recurso a un WPF <xref:System.Windows.ResourceDictionary> en el código.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 Objeto de objetos secundarios de un elemento primario que se una <xref:System.Collections.IDictionary> implementación, como WPF <xref:System.Windows.ResourceDictionary>, normalmente debe incluir un `x:Key` atributo y el valor de clave deben ser único dentro de ese diccionario. Existen dos excepciones notables:  
  
-   Algunos tipos WPF declaran una clave implícita para el uso del diccionario. Por ejemplo, un <xref:System.Windows.Style> con un <xref:System.Windows.Style.TargetType%2A>, o un <xref:System.Windows.DataTemplate> con un <xref:System.Windows.DataTemplate.DataType%2A>, puede estar en un <xref:System.Windows.ResourceDictionary> y usar la clave implícita.  
  
-   WPF admite un concepto de diccionario de recursos combinados. Las claves se pueden compartir entre diccionarios combinados y el comportamiento de la clave compartido se puede acceder mediante <xref:System.Windows.FrameworkContentElement.FindResource%2A>. Para más información, consulte [Merged Resource Dictionaries](../wpf/advanced/merged-resource-dictionaries.md) (Diccionarios de recursos combinados).  
  
 WPF XAML a la aplicación modelo general, la unicidad de las claves no se comprueba el compilador de marcado XAML. En su lugar, falta o no únicos `x:Key` valores provocar errores del analizador de XAML en tiempo de carga. Sin embargo, un control Visual Studio de diccionarios para WPF puede anotar a menudo tales errores en la fase de diseño.  
  
 Tenga en cuenta que en la sintaxis mostrada, el <xref:System.Windows.ResourceDictionary> objeto está implícito en cómo el procesador de WPF XAML genera una colección para rellenar un <xref:System.Windows.FrameworkElement.Resources%2A> colección. Un <xref:System.Windows.ResourceDictionary> no se suele proporcionar explícitamente como un elemento en el marcado, aunque podría serlo en algunos casos, si se desea para mayor claridad (sería un elemento de objeto de colección entre el <xref:System.Windows.FrameworkElement.Resources%2A> rellenan el elemento de propiedad y los elementos que contiene el diccionario). Para obtener información sobre por qué un objeto de colección casi siempre es un elemento implícito en el marcado, vea [XAML detalles de la sintaxis](../wpf/advanced/xaml-syntax-in-detail.md).  
  
 En la implementación WPF XAML, se define el control para las claves del diccionario de recursos el <xref:System.Windows.ResourceKey> clase abstracta. Sin embargo, el procesador de WPF XAML genera tipos de extensión subyacentes diferentes para las claves en función de sus usos. Por ejemplo, la clave para un <xref:System.Windows.DataTemplate> o cualquier clase derivada se administra por separado y genera una distinct <xref:System.Windows.DataTemplateKey> objeto.  
  
 Claves y nombres usan elementos de lenguaje y las distintas directivas (`x:Key` frente a `x:Name`) en la definición de XAML básica. Las claves y los nombres también se usan en situaciones diferentes mediante la definición y aplicación WPF de estos conceptos. Para obtener más información, consulte [ámbitos de nombres de XAML de WPF](../wpf/advanced/wpf-xaml-namescopes.md).  
  
 Como se indicó anteriormente, el valor de una clave puede proporcionarse a través de una extensión de marcado y puede ser distinto de un valor de cadena. Un escenario de WPF de ejemplo es que el valor de `x:Key` puede ser un [ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md). Algunos controles exponen una clave de estilo de ese tipo para un recurso de estilo personalizado que influye en parte de la apariencia y comportamiento de ese control sin reemplazar el estilo completamente. Un ejemplo de este tipo de clave es <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.  
  
 La característica de diccionario combinado de WPF presenta algunas consideraciones adicionales para la unicidad de las claves y el comportamiento de búsqueda de claves. Para más información, consulte [Merged Resource Dictionaries](../wpf/advanced/merged-resource-dictionaries.md) (Diccionarios de recursos combinados).  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 relaja la restricción que `x:Key` siempre se proporcione en forma de atributo.  
  
 En WPF, puede usar las características de XAML 2009, pero solo para XAML que no está compilado por marcado. XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.  
  
 En XAML 2009, puede especificar `x:Key` elementos mediante el uso de la siguiente:  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>Uso de elementos XAML (XAML 2009 solo)  
  
```  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`keyObject`|Elemento de objeto para el objeto que se utiliza como clave para un determinado `object` en un diccionario especializado.|  
  
-   Contenedor/elemento primario de este tipo de uso no se muestra aquí. `object` se espera que un elemento secundario de un elemento de objeto que representa una implementación del diccionario especializado. `keyObject` se espera que sea una instancia de objeto (o un valor de un tipo de valor) adecuada como la clave para esa implementación del diccionario especializado particular.  
  
-   WPF no implementa diccionarios que requieren este uso. Las claves de objeto es más una característica general del lenguaje XAML, posiblemente útil para ciertos escenarios de diccionario personalizado donde es deseable crear el diccionario en XAML. Para las características de WPF como los estilos implícitos que utilizan las claves no son de cadena para los recursos, existen otras técnicas para establecer o especificar las claves, por lo que no es necesario utilizar una clave de objeto.  
  
-   *keyObject* también podría ser el uso de una extensión de marcado en formulario de elemento de objeto, en lugar de una instancia de objeto directa.  
  
## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight  
 `x:Key` para Silverlight se documenta por separado. Para obtener más información, consulte [XAML Namespace (x:) Características del lenguaje (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vea también

- [Recursos XAML](../wpf/advanced/xaml-resources.md)
- [Recursos y código](../wpf/advanced/resources-and-code.md)
- [StaticResource (extensión de marcado)](../wpf/advanced/staticresource-markup-extension.md)
