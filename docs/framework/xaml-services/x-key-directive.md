---
title: x:Key (Directiva)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
caps.latest.revision: 25
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f28ed1e4077a48016ddd8d9b5eeb45d6ba25d8e5
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="xkey-directive"></a>x:Key (Directiva)
Identifica de forma única los elementos que se crean y se hace referencia en un diccionario definido por el XAML. Agregar un `x:Key` valor a un elemento de objeto XAML es la manera más común para identificar un recurso en un diccionario de recursos, por ejemplo, en un WPF <xref:System.Windows.ResourceDictionary>.  
  
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
|`stringKeyValue`|Una cadena de texto que se usará como una clave. La cadena de texto debe ajustarse a la [XamlName (gramática)](../../../docs/framework/xaml-services/xamlname-grammar.md).|  
|`markupExtensionUsage`|Dentro de los delimitadores de extensión de marcado {}, uso de una extensión de marcado que proporciona un objeto que se usará como una clave. Vea la sección Comentarios.|  
  
## <a name="remarks"></a>Comentarios  
 `x:Key` admite el concepto de diccionario de recursos XAML. XAML como un lenguaje no define una implementación de diccionario de recursos, que es de izquierda a marcos de interfaz de usuario específicos. Para obtener más información acerca de cómo se implementan los diccionarios de recursos XAML en WPF, vea [recursos XAML](../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 En XAML 2006 y WPF, `x:Key` se debe proporcionar como un atributo. Todavía puede usar las claves que no son cadenas, pero esto requiere el uso de una extensión de marcado con el fin de proporcionar el valor que no son cadenas en forma de atributo. Si utiliza XAML 2009, `x:Key` puede especificarse como un elemento admitir explícitamente diccionarios ordenados por tipos de objeto distinto de cadenas sin necesidad de una extensión de marcado intermedia. Vea la sección "XAML 2009" de este tema. El resto de la sección de comentarios se aplica específicamente a la implementación de XAML 2006.  
  
 El valor del atributo `x:Key` puede ser cualquier cadena definida en el [XamlName (gramática)](../../../docs/framework/xaml-services/xamlname-grammar.md) o puede ser un objeto que se evalúan a través de una extensión de marcado. Vea "Notas de uso de WPF" para obtener un ejemplo de WPF.  
  
 Los elementos secundarios de un elemento primario que es una <xref:System.Collections.IDictionary> implementación normalmente debe incluir un `x:Key` atributo que especifica un valor de clave única dentro de ese diccionario. .NET Framework podría implementar propiedades de clave de un alias para sustituir `x:Key` en determinados tipos; tipos que definen tales propiedades se deben atribuir con <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 El equivalente en código de especificar `x:Key` es la clave que se usa para subyacente <xref:System.Collections.IDictionary>. Por ejemplo, un `x:Key` que se aplica en el marcado para un recurso en WPF es equivalente al valor de la `key` parámetro de <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> al agregar el recurso a un WPF <xref:System.Windows.ResourceDictionary> en el código.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 Los objetos secundarios de un elemento primario del objeto que es un <xref:System.Collections.IDictionary> implementación, como WPF <xref:System.Windows.ResourceDictionary>, normalmente debe incluir un `x:Key` atributo y el valor de clave deben ser únicos dentro de ese diccionario. Existen dos excepciones notables:  
  
-   Algunos tipos WPF declaran una clave implícita para el uso de diccionario. Por ejemplo, un <xref:System.Windows.Style> con un <xref:System.Windows.Style.TargetType%2A>, o un <xref:System.Windows.DataTemplate> con un <xref:System.Windows.DataTemplate.DataType%2A>, puede estar en un <xref:System.Windows.ResourceDictionary> y use la clave implícita.  
  
-   WPF admite un concepto de diccionario de recursos combinado. Las claves se pueden compartir entre los diccionarios combinados y el comportamiento de la clave compartido se puede acceder mediante <xref:System.Windows.FrameworkContentElement.FindResource%2A>. Para más información, consulte [Merged Resource Dictionaries](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md) (Diccionarios de recursos combinados).  
  
 XAML de WPF a la aplicación modelo general, la unicidad de las claves no se comprueba por el compilador de marcado XAML. En su lugar, falta o no único `x:Key` valores provocarán errores en tiempo de carga XAML analizador. Sin embargo, control de Visual Studio de diccionarios de WPF a menudo puede anotar estos errores en la fase de diseño.  
  
 Tenga en cuenta que en la sintaxis mostrada, el <xref:System.Windows.ResourceDictionary> objeto está implícito en el modo en que el procesador XAML de WPF genera una colección para rellenar un <xref:System.Windows.FrameworkElement.Resources%2A> colección. A <xref:System.Windows.ResourceDictionary> no se proporciona normalmente explícitamente como un elemento de marcado, aunque puede ser en algunos casos, si deseara por motivos de claridad (sería un elemento de objeto de colección entre el <xref:System.Windows.FrameworkElement.Resources%2A> rellenan el elemento de propiedad y los elementos que el diccionario). Para obtener información sobre por qué un objeto de colección casi siempre es un elemento implícito en el marcado, vea [XAML Syntax In Detail](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 En la implementación XAML de WPF, se define el control para las claves del diccionario de recursos mediante la <xref:System.Windows.ResourceKey> clase abstracta. Sin embargo, el procesador XAML de WPF genera diferentes tipos de extensión subyacentes para claves basadas en sus usos. Por ejemplo, la clave para un <xref:System.Windows.DataTemplate> o cualquier clase derivada se trata por separado y genera un distintos <xref:System.Windows.DataTemplateKey> objeto.  
  
 Claves y nombres usan diferentes directivas y elementos del lenguaje (`x:Key` frente a `x:Name`) en la definición de XAML básica. Las claves y los nombres también se utilizan en situaciones diferentes mediante la definición y aplicación WPF de estos conceptos. Para obtener más información, consulte [ámbitos de nombres de XAML de WPF](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 Como se mencionó anteriormente, el valor de una clave puede proporcionarse a través de una extensión de marcado y puede ser distinto de un valor de cadena. Un escenario de WPF de ejemplo es que el valor de `x:Key` puede ser un[ComponentResourceKey](../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md). Algunos controles exponen una clave de estilo de ese tipo para un recurso de estilo personalizado que influye en parte de la apariencia y el comportamiento de ese control sin reemplazar el estilo completamente. Un ejemplo de este tipo de clave es <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.  
  
 La característica de diccionario combinado de WPF presenta algunas consideraciones adicionales para la unicidad de las claves y el comportamiento de búsqueda de claves. Para más información, consulte [Merged Resource Dictionaries](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md) (Diccionarios de recursos combinados).  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 relaja la restricción que `x:Key` siempre se proporciona en forma de atributo.  
  
 En WPF, puede usar características de XAML 2009, pero solo para XAML que no está compilado por marcado. XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.  
  
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
  
-   Contenedor/elemento primario de este tipo de uso no se muestra aquí. `object` debe ser un elemento secundario de un elemento de objeto que representa una implementación del diccionario especializado. `keyObject` se espera que sea una instancia de objeto (o un valor de un tipo de valor) que es adecuado como clave para esa implementación del diccionario especializado particular.  
  
-   WPF no implementa diccionarios que requieren este uso. Claves de objeto es más una característica general del lenguaje XAML, posiblemente útil para ciertos escenarios de diccionario personalizado donde es deseable crear el diccionario en XAML. Para las características de WPF como los estilos implícitos que utilizan las claves no son de cadena para los recursos, existen otras técnicas para establecer o especificar las claves, por lo que no es necesario utilizar una clave de objeto.  
  
-   *keyObject* también podría ser el uso de una extensión de marcado en el formulario de elemento de objeto, en lugar de una instancia de objeto directo.  
  
## <a name="silverlight-usage-notes"></a>Notas de uso de Silverlight  
 `x:Key` para Silverlight se documenta por separado. Para obtener más información, vea [XAML Namespace (x:) Características del lenguaje (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vea también  
 [Recursos XAML](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Recursos y código](../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [StaticResource (extensión de marcado)](../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)
