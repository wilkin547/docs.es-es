---
title: Enlazar extensión de marcado
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: d0a437e756da16db978d8074c4355fd83d211b67
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453614"
---
# <a name="binding-markup-extension"></a>Enlazar extensión de marcado
Aplaza un valor de propiedad para que sea un valor enlazado a datos, creando un objeto de expresión intermedio e interpretando el contexto de datos que se aplica al elemento y su enlace en tiempo de ejecución.  
  
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
  
## <a name="syntax-notes"></a>Notas sobre la sintaxis  
 En estas sintaxis, las `[]` y `*` no son literales. Forman parte de una notación para indicar que se pueden usar cero o más pares de *valores*`=`*bindProp* , con un separador `,` entre ellos y los pares de *valores* de`=`*bindProp* anteriores.  
  
 Cualquiera de las propiedades enumeradas en la sección "las propiedades de enlace que se pueden establecer con la extensión de enlace" podría establecerse en su lugar utilizando los atributos de un elemento de objeto <xref:System.Windows.Data.Binding>. Sin embargo, eso no es realmente el uso de la extensión de marcado de <xref:System.Windows.Data.Binding>, sino simplemente el procesamiento XAML general de los atributos que establecen las propiedades de la clase <xref:System.Windows.Data.Binding> de CLR. En otras palabras, `<Binding` *bindProp1*`="`*value1*`"[` *bindPropN*`="`*valuen*`"]*/>` es una sintaxis equivalente para los atributos de <xref:System.Windows.Data.Binding> uso de elementos de objeto en lugar de un uso de la expresión `Binding`. Para obtener información sobre el uso de atributos XAML de propiedades específicas de <xref:System.Windows.Data.Binding>, vea la sección sobre el uso de atributos XAML de la propiedad pertinente de <xref:System.Windows.Data.Binding> en la biblioteca de clases .NET Framework.  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Nombre del <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.BindingBase> propiedad que se va a establecer. No todas las propiedades de <xref:System.Windows.Data.Binding> se pueden establecer con la extensión `Binding`, y algunas propiedades se pueden configurar en una expresión `Binding` solo mediante extensiones de marcado anidadas adicionales. Vea la sección "propiedades de enlace que se pueden establecer con la extensión de enlace".|  
|`value1, valueN`|Valor en el que se va a establecer la propiedad. El control del valor del atributo es, en última instancia, específico del tipo y la lógica de la propiedad de <xref:System.Windows.Data.Binding> específica que se establece.|  
|`path`|Cadena de ruta de acceso que establece la propiedad <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> implícita. Vea también [sintaxis XAML de PropertyPath](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>{Binding} sin calificar  
 El uso de `{Binding}` que se muestra en "uso de la expresión de enlace" crea un objeto <xref:System.Windows.Data.Binding> con valores predeterminados, que incluye una <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> inicial de `null`. Esto sigue siendo útil en muchos escenarios, ya que el <xref:System.Windows.Data.Binding> creado podría basarse en propiedades de enlace de datos clave, como <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> y <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> que se establecen en el contexto de datos en tiempo de ejecución. Para obtener más información sobre el concepto de contexto de datos, consulte [enlace de datos](../data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Ruta de acceso implícita  
 La extensión de marcado de `Binding` usa <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> como una "propiedad predeterminada" conceptual, en la que no es necesario que `Path=` aparezca en la expresión. Si especifica una expresión de `Binding` con una ruta de acceso implícita, la ruta de acceso implícita debe aparecer en primer lugar en la expresión, antes de cualquier otro `bindProp`=`value` pares en los que la propiedad <xref:System.Windows.Data.Binding> se especifica por su nombre. Por ejemplo: `{Binding PathString}`, donde `PathString` es una cadena que se evalúa como el valor de <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> en el <xref:System.Windows.Data.Binding> creado por el uso de la extensión de marcado. Puede anexar una ruta de acceso implícita con otras propiedades con nombre después del separador de coma, por ejemplo, `{Binding LastName, Mode=TwoWay}`.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Propiedades de enlace que se pueden establecer con la extensión de enlace  
 La sintaxis que se muestra en este tema utiliza el `bindProp`genérico =`value` aproximación, ya que hay muchas propiedades de lectura y escritura de <xref:System.Windows.Data.BindingBase> o <xref:System.Windows.Data.Binding> que se pueden establecer a través de `Binding` sintaxis de expresión o extensión de marcado. Se pueden establecer en cualquier orden, a excepción de una <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>implícita. (Tiene la opción de especificar explícitamente `Path=`, en cuyo caso se puede establecer en cualquier orden). Básicamente, puede establecer cero o más propiedades en la lista siguiente, mediante `bindProp`=`value` pares separados por comas.  
  
 Algunos de estos valores de propiedad requieren tipos de objeto que no admiten una conversión de tipo nativo de una sintaxis de texto en XAML y, por tanto, requieren extensiones de marcado para establecerse como un valor de atributo. Compruebe la sección uso de atributos XAML de la biblioteca de clases de .NET Framework para cada propiedad para obtener más información; la cadena que se usa para la sintaxis de atributo XAML con o sin más uso de la extensión de marcado es básicamente la misma que el valor que se especifica en una expresión de `Binding`, con la excepción de que no se colocan comillas alrededor de cada `bindProp`=`value` en expresión de `Binding`.  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: una cadena que identifica un posible grupo de enlace. Se trata de un concepto de enlace relativamente avanzado; Vea la página de referencia para obtener <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Boolean, puede ser `true` o `false`. De manera predeterminada, es `false`.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: se puede establecer como una `bindProp`=cadena de `value` en la expresión, pero para ello se requiere una referencia de objeto para el valor, como una [extensión de marcado StaticResource](staticresource-markup-extension.md). En este caso, el valor es una instancia de una clase de convertidor personalizada.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: se pueden establecer en la expresión como un identificador basado en estándares; Vea el tema de referencia para obtener <xref:System.Windows.Data.Binding.ConverterCulture%2A>.  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: se puede establecer como una `bindProp`=cadena de `value` en la expresión, pero esto depende del tipo del parámetro que se pasa. Si se pasa un tipo de referencia para el valor, este uso requiere una referencia de objeto como, por ejemplo, una [extensión de marcado StaticResource](staticresource-markup-extension.md)anidada.  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: mutuamente excluyente frente a <xref:System.Windows.Data.Binding.RelativeSource%2A> y <xref:System.Windows.Data.Binding.Source%2A>; cada una de estas propiedades de enlace representa una metodología de enlace concreta. Vea [información general sobre el enlace de datos](../data/data-binding-overview.md).  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: se puede establecer como una `bindProp`=cadena de `value` en la expresión, pero esto depende del tipo de valor que se pasa. Si se pasa un tipo de referencia, se requiere una referencia de objeto como, por ejemplo, una [extensión de marcado StaticResource](staticresource-markup-extension.md)anidada.  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: Boolean, puede ser `true` o `false`. De manera predeterminada, es `false`.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: el *valor* es un nombre de constante de la enumeración <xref:System.Windows.Data.BindingMode>. Por ejemplo: `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Boolean, puede ser `true` o `false`. De manera predeterminada, es `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Boolean, puede ser `true` o `false`. De manera predeterminada, es `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Boolean, puede ser `true` o `false`. De manera predeterminada, es `false`.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: una cadena que describe una ruta de acceso en un objeto de datos o en un modelo de objetos general. El formato proporciona varias convenciones diferentes para atravesar un modelo de objetos que no se puede describir adecuadamente en este tema. Consulte [sintaxis XAML de PropertyPath](propertypath-xaml-syntax.md).  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: mutuamente excluyente con respecto a <xref:System.Windows.Data.Binding.ElementName%2A> y <xref:System.Windows.Data.Binding.Source%2A>; cada una de estas propiedades de enlace representa una metodología de enlace concreta. Vea [información general sobre el enlace de datos](../data/data-binding-overview.md). Requiere un uso de la [MarkupExtension de RelativeSource](relativesource-markupextension.md) anidado para especificar el valor.  
  
- <xref:System.Windows.Data.Binding.Source%2A>: mutuamente excluyente frente a <xref:System.Windows.Data.Binding.RelativeSource%2A> y <xref:System.Windows.Data.Binding.ElementName%2A>; cada una de estas propiedades de enlace representa una metodología de enlace concreta. Vea [información general sobre el enlace de datos](../data/data-binding-overview.md). Requiere un uso de extensión anidado, normalmente una [extensión de marcado StaticResource](staticresource-markup-extension.md) que hace referencia a un origen de datos de objeto de un diccionario de recursos con clave.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: una cadena que describe una Convención de formato de cadena para los datos enlazados. Se trata de un concepto de enlace relativamente avanzado; Vea la página de referencia para obtener <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: se puede establecer como una `bindProp`=cadena de `value` en la expresión, pero esto depende del tipo del parámetro que se pasa. Si se pasa un tipo de referencia para el valor, se requiere una referencia de objeto como, por ejemplo, una [extensión de marcado StaticResource](staticresource-markup-extension.md)anidada.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: el *valor* es un nombre de constante de la enumeración <xref:System.Windows.Data.UpdateSourceTrigger>. Por ejemplo: `{Binding UpdateSourceTrigger=LostFocus}`. Los controles específicos pueden tener valores predeterminados diferentes para esta propiedad de enlace. Consulte <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Boolean, puede ser `true` o `false`. De manera predeterminada, es `false`. Vea la sección Comentarios.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Boolean, puede ser `true` o `false`. De manera predeterminada, es `false`. Vea la sección Comentarios.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: una cadena que describe una ruta de acceso en el XMLDOM de un origen de datos XML. Vea [enlazar a datos XML mediante XmlDataProvider y consultas XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 A continuación se enumeran las propiedades de <xref:System.Windows.Data.Binding> que no se pueden establecer mediante el formulario de expresión `Binding` extensión de marcado/`{Binding}`.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: esta propiedad espera una referencia a una implementación de devolución de llamada. No se puede hacer referencia a las devoluciones de llamada o métodos distintos de los controladores de eventos en la sintaxis XAML.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: la propiedad toma una colección genérica de objetos <xref:System.Windows.Controls.ValidationRule>. Esto podría expresarse como un elemento de propiedad en un elemento de objeto de <xref:System.Windows.Data.Binding>, pero no tiene una técnica de análisis de atributos de fácil disponibilidad para su uso en una expresión de `Binding`. Consulte el tema de referencia para obtener <xref:System.Windows.Data.Binding.ValidationRules%2A>.  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Comentarios  
  
> [!IMPORTANT]
> En cuanto a la prioridad de las propiedades de dependencia, una expresión de `Binding` es equivalente a un valor establecido localmente. Si establece un valor local para una propiedad que anteriormente tenía una expresión `Binding`, el `Binding` se quita por completo. Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](dependency-property-value-precedence.md).  
  
 En este tema no se describe el enlace de datos en un nivel básico. Vea [información general sobre el enlace de datos](../data/data-binding-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding> y <xref:System.Windows.Data.PriorityBinding> no admiten una sintaxis de extensión de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. En su lugar, usaría elementos de propiedad. Vea los temas de referencia para obtener <xref:System.Windows.Data.MultiBinding> y <xref:System.Windows.Data.PriorityBinding>.  
  
 Los valores booleanos para XAML no distinguen mayúsculas de minúsculas. Por ejemplo, puede especificar `{Binding NotifyOnValidationError=true}` o `{Binding NotifyOnValidationError=True}`.  
  
 Los enlaces que implican la validación de datos normalmente se especifican mediante un elemento `Binding` explícito en lugar de como una expresión `{Binding ...}`, y el establecimiento de <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> o <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> en una expresión no es habitual. Esto se debe a que la propiedad complementaria <xref:System.Windows.Data.Binding.ValidationRules%2A> no se puede establecer fácilmente en el formulario de expresión. Para obtener más información, vea [implementar la validación de enlaces](../data/how-to-implement-binding-validation.md).  
  
 `Binding` es una extensión de marcado. Normalmente, las extensiones de marcado se implementan cuando hay un requisito para que los valores de atributo no sean valores literales o nombres de controlador, y el requisito es más global que los convertidores de tipos con atributos en determinados tipos o propiedades. Todas las extensiones de marcado de XAML usan los caracteres `{` y `}` en su sintaxis de atributo, que es la Convención por la que un procesador XAML reconoce que una extensión de marcado debe procesar el contenido de la cadena. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
 `Binding` es una extensión de marcado atípica en que la clase <xref:System.Windows.Data.Binding> que implementa la funcionalidad de extensión para la implementación XAML de WPF también implementa otros métodos y propiedades que no están relacionados con XAML. Los demás miembros están diseñados para que <xref:System.Windows.Data.Binding> una clase más versátil y independiente que puede abordar muchos escenarios de enlace de datos, además de funcionar como una extensión de marcado XAML.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.Binding>
- [Información general sobre el enlace de datos](../data/data-binding-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
