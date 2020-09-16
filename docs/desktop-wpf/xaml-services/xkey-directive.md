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
ms.openlocfilehash: 7e4e9cbded01297818f9f01df01e95e94d7dc4af
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548278"
---
# <a name="xkey-directive"></a>x:Key (Directiva)
Identifica de forma única los elementos que se crean y a los que se hace referencia en un diccionario definido por XAML. Agregar un `x:Key` valor a un elemento de objeto XAML es la forma más común de identificar un recurso en un diccionario de recursos, por ejemplo en un WPF <xref:System.Windows.ResourceDictionary> .  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>Uso de atributos XAML (específicos de WPF)  
  
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
|`stringKeyValue`|Cadena de texto que se va a usar como clave. La cadena de texto debe ajustarse a la [Gramática XamlName](xamlname-grammar.md).|  
|`markupExtensionUsage`|Dentro de los delimitadores de la extensión de marcado {} , un uso de la extensión de marcado que proporciona un objeto que se va a usar como clave. Vea la sección Comentarios.|  
  
## <a name="remarks"></a>Comentarios  
 `x:Key` admite el concepto de Diccionario de recursos XAML. XAML como lenguaje no define una implementación de Diccionario de recursos, que se deja en marcos de interfaz de usuario específicos. Para obtener más información sobre cómo se implementan los diccionarios de recursos XAML en WPF, vea [recursos XAML](../fundamentals/xaml-resources-define.md).  
  
 En XAML 2006 y WPF, `x:Key` se debe proporcionar como un atributo. Todavía puede usar claves que no sean de cadena, pero esto requiere un uso de la extensión de marcado para proporcionar el valor no de cadena en el formato de atributo. Si usa XAML 2009, `x:Key` se puede especificar como un elemento para admitir explícitamente diccionarios con clave de tipos de objeto que no sean cadenas sin requerir una extensión de marcado intermedia. Vea la sección "XAML 2009" en este tema. El resto de la sección comentarios se aplica específicamente a la implementación de XAML 2006.  
  
 El valor del atributo de `x:Key` puede ser cualquier cadena definida en la [gramática de XamlName](xamlname-grammar.md) o puede ser un objeto evaluado a través de una extensión de marcado. Vea "Notas de uso de WPF" para obtener un ejemplo de WPF.  
  
 Los elementos secundarios de un elemento primario que es una <xref:System.Collections.IDictionary> implementación de deben incluir normalmente un `x:Key` atributo que especifica un valor de clave único dentro de ese diccionario. Los marcos de trabajo pueden implementar propiedades de clave con alias para sustituirlos `x:Key` en determinados tipos; los tipos que definen dichas propiedades deben tener el atributo <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute> .  
  
 El equivalente de código de especificar `x:Key` es la clave que se usa para el subyacente <xref:System.Collections.IDictionary> . Por ejemplo, un `x:Key` que se aplica en el marcado para un recurso en WPF es equivalente al valor del `key` parámetro de <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> cuando se agrega el recurso a WPF <xref:System.Windows.ResourceDictionary> en código.  
  
## <a name="wpf-usage-notes"></a>Notas de uso de WPF  
 Los objetos secundarios de un objeto primario que es una <xref:System.Collections.IDictionary> implementación de, como WPF <xref:System.Windows.ResourceDictionary> , normalmente deben incluir un `x:Key` atributo y el valor de clave debe ser único dentro de ese diccionario. Hay dos excepciones importantes:  
  
- Algunos tipos de WPF declaran una clave implícita para el uso del diccionario. Por ejemplo, <xref:System.Windows.Style> con <xref:System.Windows.Style.TargetType%2A> , o <xref:System.Windows.DataTemplate> con <xref:System.Windows.DataTemplate.DataType%2A> , puede estar en <xref:System.Windows.ResourceDictionary> y usar la clave implícita.  
  
- WPF admite un concepto de Diccionario de recursos combinados. Las claves se pueden compartir entre los diccionarios combinados y se puede tener acceso al comportamiento de la clave compartida mediante <xref:System.Windows.FrameworkContentElement.FindResource%2A> . Para obtener más información, vea [diccionarios de recursos combinados](/dotnet/desktop/wpf/advanced/merged-resource-dictionaries).  
  
 En el modelo de aplicación y la implementación XAML de WPF generales, el compilador de marcado XAML no comprueba la unicidad de la clave. En su lugar, los valores que faltan o no son únicos `x:Key` causan errores del analizador de XAML en tiempo de carga. Sin embargo, el control de los diccionarios de WPF en Visual Studio a menudo puede tener en cuenta estos errores en la fase de diseño.  
  
 Tenga en cuenta que en la sintaxis mostrada, el <xref:System.Windows.ResourceDictionary> objeto está implícito en cómo el procesador XAML de WPF genera una colección para rellenar una <xref:System.Windows.FrameworkElement.Resources%2A> colección. <xref:System.Windows.ResourceDictionary>Normalmente, no se proporciona explícitamente como un elemento en el marcado, aunque puede ser en algunos casos si se desea para mayor claridad (sería un elemento de objeto de colección entre el <xref:System.Windows.FrameworkElement.Resources%2A> elemento de propiedad y los elementos de que rellenan el diccionario). Para obtener información sobre por qué un objeto de colección casi siempre es un elemento implícito en el marcado, vea la [Sintaxis de XAML en detalle](/dotnet/desktop/wpf/advanced/xaml-syntax-in-detail).  
  
 En la implementación XAML de WPF, el control de las claves de Diccionario de recursos se define mediante la <xref:System.Windows.ResourceKey> clase abstracta. Sin embargo, el procesador XAML de WPF genera distintos tipos de extensión subyacentes para las claves en función de sus usos. Por ejemplo, la clave de un <xref:System.Windows.DataTemplate> objeto o cualquier clase derivada se administra por separado y genera un <xref:System.Windows.DataTemplateKey> objeto distinto.  
  
 Las claves y los nombres usan directivas y elementos de lenguaje diferentes ( `x:Key` frente a `x:Name` ) en la definición básica de XAML. La definición y la aplicación de estos conceptos también usan claves y nombres en diferentes situaciones. Para obtener más información, vea [ámbitos de código XAML de WPF](/dotnet/desktop/wpf/advanced/wpf-xaml-namescopes).  
  
 Como se indicó anteriormente, el valor de una clave se puede proporcionar a través de una extensión de marcado y puede ser distinto de un valor de cadena. Un escenario de ejemplo de WPF es que el valor de `x:Key` puede ser un [ComponentResourceKey](/dotnet/desktop/wpf/advanced/componentresourcekey-markup-extension). Ciertos controles exponen una clave de estilo de ese tipo para un recurso de estilo personalizado que influye en parte de la apariencia y el comportamiento de ese control sin reemplazar completamente el estilo. Un ejemplo de este tipo de clave es <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A> .  
  
 La característica de diccionario combinado de WPF presenta consideraciones adicionales para la singularidad clave y el comportamiento de búsqueda de claves. Para obtener más información, vea [diccionarios de recursos combinados](/dotnet/desktop/wpf/advanced/merged-resource-dictionaries).  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 relaja la restricción que `x:Key` siempre se proporciona en forma de atributo.  
  
 En WPF, puede usar las características de XAML 2009, pero solo para XAML que no está compilado por marcado. XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.  
  
 En XAML 2009, puede especificar `x:Key` elementos mediante el siguiente uso:  
  
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
|`keyObject`|Elemento de objeto para el objeto que se utiliza como clave para un determinado `object` en un diccionario especializado.|  
  
- El contenedor/elemento primario para este tipo de uso no se muestra aquí. `object` se espera que sea un elemento secundario de un elemento de objeto que representa una implementación de diccionario especializada. `keyObject` se espera que sea una instancia de objeto (o un valor de un tipo de valor) que sea adecuada como clave para esa implementación concreta de diccionario especializado.  
  
- WPF no implementa diccionarios que requieran este uso. Las claves de objeto son más una característica general del lenguaje XAML, que probablemente resulta útil para ciertos escenarios de diccionario personalizado en los que es deseable crear el Diccionario en XAML. En el caso de las características de WPF, como los estilos implícitos que usan claves que no son de cadena para los recursos, existen otras técnicas de establecimiento o especificación de las claves, por lo que no es necesario usar una clave de objeto.  
  
- `keyObject` también podría ser un uso de la extensión de marcado en el formulario de elemento de objeto, en lugar de una instancia de objeto directa.  
  
## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight  
 `x:Key` para Silverlight se documenta por separado. Para obtener más información, vea [espacio de nombres XAML (x:) Características del lenguaje (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>Vea también

- [Recursos XAML](../fundamentals/xaml-resources-define.md)
- [Recursos y código](/dotnet/desktop/wpf/advanced/resources-and-code)
- [StaticResource (extensión de marcado)](/dotnet/desktop/wpf/advanced/staticresource-markup-extension)
