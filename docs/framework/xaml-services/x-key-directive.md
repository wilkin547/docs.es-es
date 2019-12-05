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
ms.openlocfilehash: 4ffd7a2922c7f3ba35ccb9ac7ce29a6a00cd99af
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837212"
---
# <a name="xkey-directive"></a>x:Key (Directiva)
Identifica de forma exclusiva los elementos que se crean y a los que se hace referencia en un diccionario definido por XAML. Agregar un valor `x:Key` a un elemento de objeto XAML es la manera más habitual de identificar un recurso en un diccionario de recursos, como en un WPF <xref:System.Windows.ResourceDictionary>.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>Uso de atributos XAML (específico de WPF)  
  
```xaml  
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
|`stringKeyValue`|Una cadena de texto que se va a usar como clave. La cadena de texto debe ajustarse a la [Gramática XamlName](xamlname-grammar.md).|  
|`markupExtensionUsage`|Dentro de los delimitadores de la extensión de marcado {}, un uso de la extensión de marcado que proporciona un objeto que se va a usar como clave. Vea la sección Comentarios.|  
  
## <a name="remarks"></a>Notas  
 `x:Key` es compatible con el concepto de diccionario de recursos XAML. XAML como lenguaje no define una implementación de diccionario de recursos, que se deja para los marcos de IU. Para obtener más información sobre cómo se implementan los diccionarios de recursos XAML en WPF, vea [recursos XAML](../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 En XAML 2006 y WPF, `x:Key` se debe proporcionar como un atributo. Todavía puede usar las claves de no cadena, pero esto requiere un uso de la extensión de marcado para proporcionar el valor de no cadena en formulario de atributo. Si usa XAML 2009, `x:Key` se puede especificar como un elemento, para admitir explícitamente diccionarios con clave de tipos de objeto que no sean cadenas sin requerir una extensión de marcado intermedia. Vea la sección "XAML 2009" en este tema. El resto de la sección comentarios se aplica específicamente a la implementación de XAML 2006.  
  
 El valor de atributo de `x:Key` puede ser cualquier cadena definida en la [gramática de XamlName](xamlname-grammar.md) o puede ser un objeto evaluado a través de una extensión de marcado. Vea "Notas de uso de WPF" para obtener un ejemplo de WPF.  
  
 En general, los elementos secundarios de un elemento primario que es una implementación de <xref:System.Collections.IDictionary>, deben incluir un atributo `x:Key` que especifica un valor de clave único dentro de ese diccionario. .NET Framework podría implementar las propiedades clave con alias para sustituir `x:Key` sobre determinados tipos; los tipos que definen tales propiedades deben atribuirse con <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 El equivalente del código cuando se especifica `x:Key` es la clave que se utiliza para el <xref:System.Collections.IDictionary> subyacente. Por ejemplo, una clave `x:Key` aplicada en el marcado de un recurso en WPF equivale al valor del parámetro `key` de <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> cuando se agrega el recurso a un WPF <xref:System.Windows.ResourceDictionary> en el código.  
  
## <a name="wpf-usage-notes"></a>Notas de uso de WPF  
 En general, los objetos secundarios de un objeto primario que es una implementación de <xref:System.Collections.IDictionary>, como <xref:System.Windows.ResourceDictionary> de WPF, deben incluir un atributo `x:Key` y el valor de clave debe ser único dentro de ese diccionario. Existen dos excepciones más importantes:  
  
- Algunos tipos WPF declaran una clave implícita para el uso del diccionario. Por ejemplo, <xref:System.Windows.Style> con <xref:System.Windows.Style.TargetType%2A>, o <xref:System.Windows.DataTemplate> con <xref:System.Windows.DataTemplate.DataType%2A>, se puede colocar en <xref:System.Windows.ResourceDictionary> y utilizar la clave implícita.  
  
- WPF es compatible con un concepto de diccionario de recursos combinados. Las claves se pueden compartir entre diccionarios combinados y se puede tener acceso al comportamiento de la clave compartida mediante <xref:System.Windows.FrameworkContentElement.FindResource%2A>. Para más información, consulte [Merged Resource Dictionaries](../wpf/advanced/merged-resource-dictionaries.md) (Diccionarios de recursos combinados).  
  
 En la implementación de XAML de WPF total y modelo de aplicación, el compilador de marcado XAML no comprueba la unicidad de las claves. En su lugar, los valores de `x:Key` ausentes o que no sean únicos producirán errores en tiempo de carga del analizador XAML. Sin embargo, el control de los diccionarios de WPF en Visual Studio a menudo puede tener en cuenta estos errores en la fase de diseño.  
  
 Observe que en la sintaxis mostrada, el objeto <xref:System.Windows.ResourceDictionary> está implícito en cómo el procesador XAML de WPF genera una colección para rellenar una colección <xref:System.Windows.FrameworkElement.Resources%2A>. <xref:System.Windows.ResourceDictionary> no se suele proporcionar explícitamente como un elemento en el marcado, aunque se puede hacer en algunos casos si se desea para aportar mayor claridad (sería un elemento de objeto de colección entre el elemento de propiedad <xref:System.Windows.FrameworkElement.Resources%2A> y los elementos que contiene incluidos en el diccionario). Para obtener información sobre por qué un objeto de colección casi siempre es un elemento implícito en el marcado, vea la [Sintaxis de XAML en detalle](../wpf/advanced/xaml-syntax-in-detail.md).  
  
 La clase abstracta <xref:System.Windows.ResourceKey> define el control para las claves del diccionario de recursos en la implementación XAML de WPF. Sin embargo, el procesador XAML de WPF genera tipos de extensión subyacentes diferentes para las claves, según su uso. Por ejemplo, la clave de un objeto <xref:System.Windows.DataTemplate> o cualquiera de sus clases derivadas se administra por separado y genera un objeto <xref:System.Windows.DataTemplateKey> diferenciado.  
  
 Claves y nombres usan elementos de directivas y del lenguaje diferentes (`x:Key` contra `x:Name`) en la definición de XAML básica. Las claves y los nombres también se utilizan en situaciones distintas por la definición y aplicación WPF de estos conceptos. Para obtener más información, vea [ámbitos de código XAML de WPF](../wpf/advanced/wpf-xaml-namescopes.md).  
  
 Tal y como se dijo previamente, el valor de una clave se puede proporcionar a través de una extensión de marcado y puede ser cualquier valor excepto un valor de cadena. Un escenario de ejemplo de WPF es que el valor de `x:Key` puede ser [ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md). Algunos controles exponen una clave de estilo de ese tipo para un recurso de estilo personalizado que influye en parte de la apariencia y el comportamiento de ese control sin reemplazar el estilo completamente. Un ejemplo de este tipo de clave es <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.  
  
 La característica de diccionario combinado de WPF presenta algunas consideraciones adicionales con respecto a la singularidad clave y el comportamiento de búsqueda de claves. Para más información, consulte [Merged Resource Dictionaries](../wpf/advanced/merged-resource-dictionaries.md) (Diccionarios de recursos combinados).  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 relaja la restricción de que `x:Key` siempre se proporciona en forma de atributo.  
  
 En WPF, puede usar las características de XAML 2009, pero solo para XAML que no está compilado por marcado. XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.  
  
 En XAML 2009, puede especificar `x:Key` elementos mediante el siguiente uso:  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>Uso de elementos de XAML (XAML 2009 solo)  
  
```xaml  
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
|`keyObject`|Elemento de objeto del objeto que se utiliza como clave de un `object` determinado en un diccionario especializado.|  
  
- El contenedor/elemento primario de este tipo de uso no se muestra aquí. Se espera que `object` sea un elemento secundario de un elemento de objeto que representa una implementación del diccionario especializado. Se espera que `keyObject` sea una instancia de objeto (o un valor de un tipo de valor) adecuada como clave para esa implementación del diccionario especializado particular.  
  
- WPF no implementa diccionarios que requieren este uso. Las claves de objeto son más una característica general del lenguaje XAML, posiblemente útil para ciertos escenarios de diccionario personalizado donde es deseable crear el diccionario en XAML. Para las características de WPF como los estilos implícitos que utilizan las claves no de cadena para los recursos, existen otras técnicas para establecer o especificar las claves, así que no es necesario utilizar una clave de objeto.  
  
- *keyObject* también podría ser un uso de la extensión de marcado en el formulario de elemento de objeto, en lugar de una instancia de objeto directa.  
  
## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight  
 `x:Key` para Silverlight se documenta por separado. Para obtener más información, vea [espacio de nombres XAML (x:) Características del lenguaje (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>Vea también

- [Recursos XAML](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Recursos y código](../wpf/advanced/resources-and-code.md)
- [StaticResource (extensión de marcado)](../wpf/advanced/staticresource-markup-extension.md)
