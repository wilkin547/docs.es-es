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
ms.openlocfilehash: c05f98932ceceeb1530b34a09b1923f2af1378b5
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432759"
---
# <a name="xkey-directive"></a>x:Key (Directiva)
Identifica de forma única los elementos que se crean y a los que se hace referencia en un diccionario definido por XAML. Agregar `x:Key` un valor a un elemento de objeto XAML es la forma más común <xref:System.Windows.ResourceDictionary>de identificar un recurso en un diccionario de recursos, por ejemplo en un WPFWPF .  
  
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
|`stringKeyValue`|Una cadena de texto que se va a usar como clave. La cadena de texto debe ajustarse a [la gramática XamlName](xamlname-grammar.md).|  
|`markupExtensionUsage`|Dentro de los delimitadores {}de extensión de marcado , un uso de extensión de marcado que proporciona un objeto para usarlo como clave. Vea la sección Comentarios.|  
  
## <a name="remarks"></a>Observaciones  
 `x:Key`admite el concepto de diccionario de recursos XAML. XAML como lenguaje no define una implementación de diccionario de recursos, que se deja a marcos de interfaz de usuario específicos. Para obtener más información sobre cómo se implementan los diccionarios de recursos XAML en WPFWPF, vea [Recursos XAML](../fundamentals/xaml-resources-define.md).  
  
 En XAML 2006 `x:Key` y WPFWPF, debe proporcionarse como un atributo. Todavía puede usar claves que no son de cadena, pero esto requiere un uso de extensión de marcado para proporcionar el valor de no cadena en forma de atributo. Si usa XAML 2009, `x:Key` se puede especificar como un elemento, para admitir explícitamente diccionarios con clave de tipos de objeto distintos de cadenas sin necesidad de una extensión de marcado intermedia. Consulte la sección "XAML 2009" de este tema. El resto de la sección Comentarios se aplica específicamente a la implementación de XAML 2006.  
  
 El valor `x:Key` de atributo de puede ser cualquier cadena definida en el [XamlName Grammar](xamlname-grammar.md) o puede ser un objeto evaluado a través de una extensión de marcado. Consulte "Notas de uso de WPF" para obtener un ejemplo de WPFWPF.  
  
 Los elementos secundarios de <xref:System.Collections.IDictionary> un elemento primario `x:Key` que es una implementación normalmente deben incluir un atributo que especifique un valor de clave único dentro de ese diccionario. Los marcos de trabajo pueden implementar `x:Key` propiedades de clave con alias para sustituir los tipos concretos; los tipos que definen estas <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>propiedades deben atribuirse con .  
  
 El equivalente de `x:Key` código de especificar es la <xref:System.Collections.IDictionary>clave que se utiliza para el archivo . Por ejemplo, `x:Key` un que se aplica en el marcado de `key` un <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> recurso en WPFWPF es <xref:System.Windows.ResourceDictionary> equivalente al valor del parámetro de cuando se agrega el recurso a un WPFWPF en el código.  
  
## <a name="wpf-usage-notes"></a>Notas de uso de WPF  
 Objetos secundarios de un <xref:System.Collections.IDictionary> objeto primario que <xref:System.Windows.ResourceDictionary>es una implementación, como WPFWPF , normalmente debe incluir un `x:Key` atributo y el valor de clave debe ser único dentro de ese diccionario. Hay dos excepciones notables:  
  
- Algunos tipos de WPFWPF declaran una clave implícita para el uso del diccionario. Por ejemplo, <xref:System.Windows.Style> un <xref:System.Windows.Style.TargetType%2A>con <xref:System.Windows.DataTemplate> , <xref:System.Windows.DataTemplate.DataType%2A>o un con <xref:System.Windows.ResourceDictionary> un , puede estar en un y usar la clave implícita.  
  
- WPFWPF admite un concepto de diccionario de recursos combinado. Las claves se pueden compartir entre los diccionarios combinados <xref:System.Windows.FrameworkContentElement.FindResource%2A>y se puede acceder al comportamiento de la clave compartida mediante . Para más información, consulte [Merged Resource Dictionaries](../../framework/wpf/advanced/merged-resource-dictionaries.md) (Diccionarios de recursos combinados).  
  
 En el modelo general de aplicación e implementación XAML de WPF, el compilador de marcado XAML no comprueba la unicidad de clave. En su lugar, `x:Key` los valores que faltan o no son únicos provocan errores de analizador XAML en tiempo de carga. Sin embargo, el control de Visual Studio de diccionarios para WPFWPF a menudo puede tener en cuenta estos errores en la fase de diseño.  
  
 Tenga en cuenta que <xref:System.Windows.ResourceDictionary> en la sintaxis que se muestra, el <xref:System.Windows.FrameworkElement.Resources%2A> objeto está implícito en cómo el procesador XAML de WPF genera una colección para rellenar una colección. A <xref:System.Windows.ResourceDictionary> no se proporciona normalmente explícitamente como un elemento en el marcado, aunque puede ser en algunos <xref:System.Windows.FrameworkElement.Resources%2A> casos si se desea claridad (sería un elemento de objeto de colección entre el elemento de propiedad y los elementos dentro de que rellenan el diccionario). Para obtener información sobre por qué un objeto de colección es casi siempre un elemento implícito en el marcado, vea [Sintaxis XAML en detalle](../../framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 En la implementación XAML de WPF, el <xref:System.Windows.ResourceKey> control de las claves de diccionario de recursos se define mediante la clase abstracta. Sin embargo, el procesador XAML de WPF genera diferentes tipos de extensión subyacentes para las claves en función de sus usos. Por ejemplo, la <xref:System.Windows.DataTemplate> clave de una clase derivada o una clase <xref:System.Windows.DataTemplateKey> derivada se controla por separado y genera un objeto distinto.  
  
 Las claves y los nombres usan`x:Key` directivas y elementos de lenguaje diferentes ( frente a `x:Name`) en la definición XAML básica. Las claves y los nombres también se usan en diferentes situaciones mediante la definición de WPFWPF y la aplicación de estos conceptos. Para obtener más información, vea [Visores](../../framework/wpf/advanced/wpf-xaml-namescopes.md)de nombres XAML de WPF .  
  
 Como se indicó anteriormente, el valor de una clave se puede proporcionar a través de una extensión de marcado y puede ser distinto de un valor de cadena. Un escenario WPF de ejemplo `x:Key` es que el valor de puede ser un [ComponentResourceKey](../../framework/wpf/advanced/componentresourcekey-markup-extension.md). Algunos controles exponen una clave de estilo de ese tipo para un recurso de estilo personalizado que influye en parte de la apariencia y el comportamiento de ese control sin reemplazar totalmente el estilo. Un ejemplo de tal <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>clave es .  
  
 La característica de diccionario combinado WPFWPF presenta consideraciones adicionales para la unicidad de clave y el comportamiento de búsqueda de claves. Para más información, consulte [Merged Resource Dictionaries](../../framework/wpf/advanced/merged-resource-dictionaries.md) (Diccionarios de recursos combinados).  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 relaja la `x:Key` restricción que siempre se proporciona en forma de atributo.  
  
 En WPFWPF, puede usar las características de XAML 2009, pero solo para XAML que no está compilado por marcado. XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.  
  
 En XAML 2009, `x:Key` puede especificar elementos mediante el uso siguiente:  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>Uso de elementos XAML (solo XAML 2009)  
  
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
|`keyObject`|Elemento object para el objeto que se `object` utiliza como clave para un diccionario determinado en un diccionario especializado.|  
  
- El contenedor/padre para este tipo de uso no se muestra aquí. `object`se espera que sea un elemento secundario de un elemento de objeto que representa una implementación de diccionario especializada. `keyObject`se espera que sea una instancia de objeto (o un valor de un tipo de valor) que sea adecuada como clave para esa implementación de diccionario especializado en particular.  
  
- WPFWPF no implementa diccionarios que requieren este uso. Las claves de objeto son más una característica general del lenguaje XAML, posiblemente útil para determinados escenarios de diccionario personalizado donde es deseable crear el diccionario en XAML. Para WPFWPF wpfWPF características como estilos implícitos que usan claves que no son de cadena para los recursos, existen otras técnicas para establecer o especificar las claves, por lo que no es necesario usar una clave de objeto.  
  
- `keyObject`también podría ser un uso de extensión de marcado en forma de elemento de objeto, en lugar de una instancia de objeto directo.  
  
## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight  
 `x:Key`para Silverlight se documenta por separado. Para obtener más información, vea [Espacio de nombres XAML (x:) Características del idioma (Silverlight).](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95))  
  
## <a name="see-also"></a>Consulte también

- [Recursos XAML](../fundamentals/xaml-resources-define.md)
- [Recursos y código](../../framework/wpf/advanced/resources-and-code.md)
- [Extensión de marcado StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md)
