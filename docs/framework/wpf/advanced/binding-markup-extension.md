---
title: Enlazar extensión de marcado
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: c6a424e085c7499db08d0a7e6b652f45fb2cdd70
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644080"
---
# <a name="binding-markup-extension"></a>Enlazar extensión de marcado
Aplaza un valor de propiedad para que sea un valor enlazado a datos, creando un objeto de expresión intermedia e interpretando el contexto de datos que se aplica al elemento y su enlace en tiempo de ejecución.  
  
## <a name="binding-expression-usage"></a>Uso de expresiones de enlace  
  
```xaml  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## <a name="syntax-notes"></a>Notas de sintaxis  
 En estas sintaxis, el `[]` y `*` no son literales. Forman parte de una notación para indicar que se pueden utilizar `,` cero o más pares de*valores* *bindProp,*`=`con un separador entre ellos y los pares de*valores* *bindProp*`=`anteriores.  
  
 Cualquiera de las propiedades enumeradas en la sección "Propiedades de enlace que se <xref:System.Windows.Data.Binding> pueden establecer con la extensión de enlace" en su lugar se podría establecer mediante atributos de un elemento de objeto. Sin embargo, ese no es <xref:System.Windows.Data.Binding>realmente el uso de la extensión de marcado <xref:System.Windows.Data.Binding> de , es sólo el procesamiento XAML general de atributos que establecen propiedades de la clase CLR. En otras `<Binding` palabras, *bindProp1*`="`*value1* `"[` *bindPropN*`="`*valueN* `"]*/>` es una sintaxis equivalente para los atributos de uso de elementos de <xref:System.Windows.Data.Binding> objeto en lugar de un `Binding` uso de expresión. Para obtener información sobre el uso <xref:System.Windows.Data.Binding>de atributos XAML de propiedades específicas <xref:System.Windows.Data.Binding> de , vea la sección "Uso de atributos XAML" de la propiedad relevante de la biblioteca de clases de .NET Framework.  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|El nombre <xref:System.Windows.Data.Binding> de <xref:System.Windows.Data.BindingBase> la propiedad o que se ha establecido. No <xref:System.Windows.Data.Binding> todas las propiedades `Binding` se pueden establecer con la `Binding` extensión y algunas propiedades se pueden establecer dentro de una expresión solo mediante el uso de más extensiones de marcado anidadas. Consulte la sección "Propiedades de enlace que se pueden establecer con la extensión de enlace".|  
|`value1, valueN`|El valor en el que se establecerá la propiedad. El control del valor del atributo es en última <xref:System.Windows.Data.Binding> instancia específico para el tipo y la lógica de la propiedad específica que se establece.|  
|`path`|Cadena de ruta de <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> acceso que establece la propiedad implicit. Vea también [Sintaxis XAML PropertyPath](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>No calificados ?  
 El `{Binding}` uso que se muestra en <xref:System.Windows.Data.Binding> "Uso de expresiones <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> de `null`enlace" crea un objeto con valores predeterminados, que incluye una inicial de . Esto sigue siendo útil en muchos <xref:System.Windows.Data.Binding> escenarios, porque el creado podría <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> depender de propiedades de enlace de datos clave como y se establece en el contexto de datos en tiempo de ejecución. Para obtener más información sobre el concepto de contexto de datos, vea [Enlace de](../../../desktop-wpf/data/data-binding-overview.md)datos .  
  
## <a name="implicit-path"></a>Ruta implícita  
 La `Binding` extensión <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> de marcado se utiliza como `Path=` una "propiedad predeterminada" conceptual, donde no es necesario aparecer en la expresión. Si especifica `Binding` una expresión con una ruta de acceso implícita, la ruta `bindProp` = `value` de <xref:System.Windows.Data.Binding> acceso implícita debe aparecer primero en la expresión, antes de cualquier otro par donde la propiedad se especifique por nombre. Por `{Binding PathString}`ejemplo: `PathString` , donde se evalúa una cadena <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> que <xref:System.Windows.Data.Binding> se evalúa como el valor de en el creado por el uso de la extensión de marcado. Puede anexar una ruta de acceso implícita con otras `{Binding LastName, Mode=TwoWay}`propiedades con nombre después del separador de comas, por ejemplo, .  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Propiedades de enlace que se pueden establecer con la extensión de enlace  
 La sintaxis que se `bindProp` = `value` muestra en este tema utiliza la aproximación <xref:System.Windows.Data.Binding> genérica, porque `Binding` hay muchas propiedades de lectura y escritura de <xref:System.Windows.Data.BindingBase> o que se pueden establecer a través de la sintaxis de expresión o extensión de marcado. Se pueden establecer en cualquier orden, con <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>la excepción de un archivo . (Tiene la opción de especificar `Path=`explícitamente , en cuyo caso se puede establecer en cualquier orden). Básicamente, puede establecer cero o más de las `bindProp` = `value` propiedades de la lista siguiente, utilizando pares separados por comas.  
  
 Varios de estos valores de propiedad requieren tipos de objeto que no admiten una conversión de tipo nativo de una sintaxis de texto en XAML y, por lo tanto, requieren extensiones de marcado para establecerse como un valor de atributo. Compruebe la sección Uso de atributos XAML en la biblioteca de clases de .NET Framework para cada propiedad para obtener más información; la cadena que se usa para la sintaxis de atributo XAML con o `Binding` sin más uso de extensión de `bindProp` = `value` marcado es básicamente la misma que el valor que especifique en una expresión, con la excepción de que no se colocan comillas alrededor de cada uno en la `Binding` expresión.  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: una cadena que identifica un posible grupo de enlace. Este es un concepto de enlace relativamente avanzado; consulte la <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>página de referencia para .  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: booleano, `true` puede `false`ser cualquiera o . El valor predeterminado es `false`.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: se puede `bindProp` = `value` establecer como una cadena en la expresión, pero para ello se requiere una referencia de objeto para el valor, como una extensión de [marcado StaticResource](staticresource-markup-extension.md). El valor en este caso es una instancia de una clase de convertidor personalizada.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: configurable en la expresión como un identificador basado en estándares; consulte el tema <xref:System.Windows.Data.Binding.ConverterCulture%2A>de referencia de .  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: se puede `bindProp` = `value` establecer como una cadena en la expresión, pero esto depende del tipo del parámetro que se pasa. Si se pasa un tipo de referencia para el valor, este uso requiere una referencia de objeto como una extensión de [marcado StaticResource](staticresource-markup-extension.md)anidada.  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: mutuamente <xref:System.Windows.Data.Binding.RelativeSource%2A> excluyente frente a y <xref:System.Windows.Data.Binding.Source%2A>; cada una de estas propiedades de enlace representa una metodología de enlace determinada. Consulte [Información general sobre el enlace](../../../desktop-wpf/data/data-binding-overview.md)de datos .  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: se puede `bindProp` = `value` establecer como una cadena en la expresión, pero esto depende del tipo del valor que se pasa. Si se pasa un tipo de referencia, se requiere una referencia de objeto como una extensión de [marcado StaticResource](staticresource-markup-extension.md)anidada .  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: booleano, `true` puede `false`ser cualquiera o . El valor predeterminado es `false`.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: *value* es un <xref:System.Windows.Data.BindingMode> nombre constante de la enumeración. Por ejemplo: `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: booleano, `true` puede `false`ser cualquiera o . El valor predeterminado es `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: booleano, `true` puede `false`ser cualquiera o . El valor predeterminado es `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: booleano, `true` puede `false`ser cualquiera o . El valor predeterminado es `false`.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: una cadena que describe una ruta de acceso a un objeto de datos o un modelo de objetos general. El formato proporciona varias convenciones diferentes para recorrer un modelo de objetos que no se pueden describir adecuadamente en este tema. Consulte [Sintaxis XAML PropertyPath](propertypath-xaml-syntax.md).  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: mutuamente excluyente frente a <xref:System.Windows.Data.Binding.ElementName%2A> y <xref:System.Windows.Data.Binding.Source%2A>; cada una de estas propiedades de enlace representa una metodología de enlace determinada. Consulte [Información general sobre el enlace](../../../desktop-wpf/data/data-binding-overview.md)de datos . Requiere un uso anidado de [RelativeSource MarkupExtension](relativesource-markupextension.md) para especificar el valor.  
  
- <xref:System.Windows.Data.Binding.Source%2A>: mutuamente <xref:System.Windows.Data.Binding.RelativeSource%2A> excluyente frente a y <xref:System.Windows.Data.Binding.ElementName%2A>; cada una de estas propiedades de enlace representa una metodología de enlace determinada. Consulte [Información general sobre el enlace](../../../desktop-wpf/data/data-binding-overview.md)de datos . Requiere un uso de extensión anidada, normalmente una extensión de [marcado StaticResource](staticresource-markup-extension.md) que hace referencia a un origen de datos de objeto de un diccionario de recursos con clave.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: una cadena que describe una convención de formato de cadena para los datos enlazados. Este es un concepto de enlace relativamente avanzado; consulte la <xref:System.Windows.Data.BindingBase.StringFormat%2A>página de referencia para .  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: se puede `bindProp` = `value` establecer como una cadena en la expresión, pero esto depende del tipo del parámetro que se pasa. Si se pasa un tipo de referencia para el valor, se requiere una referencia de objeto como una extensión de [marcado StaticResource](staticresource-markup-extension.md)anidada .  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *value* es un <xref:System.Windows.Data.UpdateSourceTrigger> nombre constante de la enumeración. Por ejemplo: `{Binding UpdateSourceTrigger=LostFocus}`. Los controles específicos potencialmente tienen valores predeterminados diferentes para esta propiedad de enlace. Vea <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: booleano, `true` puede `false`ser cualquiera o . El valor predeterminado es `false`. Vea la sección Comentarios.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: booleano, `true` puede `false`ser cualquiera o . El valor predeterminado es `false`. Vea la sección Comentarios.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: una cadena que describe una ruta de acceso al XMLDOM de un origen de datos XML. Consulte [Enlazar a datos XML mediante un XMLDataProvider y consultas XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 A continuación se <xref:System.Windows.Data.Binding> indican las propiedades `Binding` que`{Binding}` no se pueden establecer mediante el formulario de expresión/extensión de marcado.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: esta propiedad espera una referencia a una implementación de devolución de llamada. No se puede hacer referencia a las devoluciones de llamada/métodos que no sean controladores de eventos en la sintaxis XAML.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: la propiedad toma <xref:System.Windows.Controls.ValidationRule> una colección genérica de objetos. Esto podría expresarse como un <xref:System.Windows.Data.Binding> elemento de propiedad en un elemento de objeto, pero `Binding` no tiene técnica de análisis de atributos fácilmente disponible para su uso en una expresión. Consulte el <xref:System.Windows.Data.Binding.ValidationRules%2A>tema de referencia para .  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Observaciones  
  
> [!IMPORTANT]
> En términos de prioridad `Binding` de propiedad de dependencia, una expresión es equivalente a un valor establecido localmente. Si establece un valor local para una `Binding` propiedad `Binding` que anteriormente tenía una expresión, se quita por completo. Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](dependency-property-value-precedence.md).  
  
 La descripción del enlace de datos en un nivel básico no se trata en este tema. Consulte [Información general sobre el enlace](../../../desktop-wpf/data/data-binding-overview.md)de datos .  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding>y <xref:System.Windows.Data.PriorityBinding> no admiten una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintaxis de extensión. En su lugar, usaría elementos de propiedad. Consulte los <xref:System.Windows.Data.MultiBinding> temas <xref:System.Windows.Data.PriorityBinding>de referencia para y .  
  
 Los valores booleanos para XAML no distinguen mayúsculas de minúsculas. Por ejemplo, puede `{Binding NotifyOnValidationError=true}` `{Binding NotifyOnValidationError=True}`especificar uno o .  
  
 Los enlaces que implican la validación `Binding` de datos normalmente se especifican mediante un elemento explícito en lugar de como una `{Binding ...}` expresión, y establecer <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> o <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> en una expresión es poco frecuente. Esto se debe <xref:System.Windows.Data.Binding.ValidationRules%2A> a que la propiedad complementaria no se puede establecer fácilmente en el formulario de expresión. Para obtener más información, vea [Implementar validación](../data/how-to-implement-binding-validation.md)de enlace .  
  
 `Binding` es una extensión de marcado. Las extensiones de marcado se implementan normalmente cuando hay un requisito para que los valores de atributo de escape sean distintos de los valores literales o los nombres de controlador, y el requisito es más global que los convertidores de tipos atribuidos a determinados tipos o propiedades. Todas las extensiones `{` de `}` marcado en XAML usan los caracteres y en su sintaxis de atributo, que es la convención por la que un procesador XAML reconoce que una extensión de marcado debe procesar el contenido de la cadena. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
 `Binding`es una extensión de marcado <xref:System.Windows.Data.Binding> atípica en que la clase que implementa la funcionalidad de extensión para la implementación XAML de WPF también implementa varios otros métodos y propiedades que no están relacionados con XAML. Los demás miembros <xref:System.Windows.Data.Binding> están diseñados para crear una clase más versátil y independiente que puede abordar muchos escenarios de enlace de datos además de funcionar como una extensión de marcado XAML.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Data.Binding>
- [Descripción general del enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
