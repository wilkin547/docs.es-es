---
title: "Enlazar extensión de marcado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc6a0616c6b462ffe6aca0a9adf27ac2ac7b7828
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="binding-markup-extension"></a>Enlazar extensión de marcado
Pasa un valor de propiedad para que sea un valor enlazado a datos, creación de un objeto de expresión intermedio e interpretar el contexto de datos que se aplica al elemento y su enlace en tiempo de ejecución.  
  
## <a name="binding-expression-usage"></a>Uso de la expresión de enlace  
  
```  
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
 En estas sintaxis, el `[]` y `*` no son literales. Forman parte de una notación para indicar que cero o más *bindProp*`=`*valor* pares se pueden usar, con un `,` separador entre ellos y *bindProp*  `=` *valor* pares.  
  
 En su lugar alguna de las propiedades enumeradas en la sección "Propiedades de enlace que se puede establecer con la extensión de enlace" podría establecer uso de atributos de un <xref:System.Windows.Data.Binding> los elementos de objeto. Sin embargo, que no es realmente el uso de la extensión de marcado de <xref:System.Windows.Data.Binding>, es simplemente el procesamiento de XAML general de atributos que definen propiedades de CLR <xref:System.Windows.Data.Binding> clase. En otras palabras, `<Binding` *bindProp1*`="`*value1* `"[` *bindPropN*`="`*valorN* `"]*/>` es una sintaxis equivalente para los atributos de <xref:System.Windows.Data.Binding> objeto uso de elementos en lugar de un `Binding` uso de la expresión. Para obtener información sobre el uso de atributos XAML de propiedades específicas de <xref:System.Windows.Data.Binding>, vea la sección "Uso de atributos XAML" de la propiedad correspondiente de <xref:System.Windows.Data.Binding> en la biblioteca de clases de .NET Framework.  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|El nombre de la <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.BindingBase> propiedad que se va a establecer. No todos los <xref:System.Windows.Data.Binding> propiedades se pueden establecer con el `Binding` extensión y algunas propiedades son configurables en una `Binding` expresión sólo utilizando más anidar las extensiones de marcado. Vea la sección "Propiedades de enlace que se puede establecer con la extensión de enlace".|  
|`value1, valueN`|Valor que se establecerá la propiedad. El control del valor del atributo es en última instancia específico para el tipo y la lógica específicas de <xref:System.Windows.Data.Binding> propiedad se ha establecido.|  
|`path`|La cadena de ruta de acceso que establece la parte implícita <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> propiedad. Vea también [sintaxis de PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>{Binding} incompleto  
 El `{Binding}` uso se muestra en "Uso de la expresión de enlace" crea una <xref:System.Windows.Data.Binding> objeto con valores predeterminados, que incluye un inicial <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> de `null`. Esto también es útil en muchos escenarios, porque creado <xref:System.Windows.Data.Binding> podrían confiar en las propiedades de enlace de datos de la clave como <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> y <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> que se va a establecer en el contexto de datos de tiempo de ejecución. Para obtener más información sobre el concepto de contexto de datos, vea [enlace de datos](../../../../docs/framework/wpf/data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Ruta de acceso implícita  
 El `Binding` usos de la extensión de marcado <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> como un conceptual "propiedad predeterminada", donde `Path=` no es necesario que aparezcan en la expresión. Si especifica un `Binding` expresión con una ruta de acceso implícita, la ruta de acceso implícita debe aparecer primero en la expresión, antes de cualquier otro `bindProp` = `value` pares dónde el <xref:System.Windows.Data.Binding> propiedad se especifica por nombre. Por ejemplo: `{Binding PathString}`, donde `PathString` es una cadena que se evalúa como el valor de <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> en el <xref:System.Windows.Data.Binding> creado mediante el uso de la extensión de marcado. Puede anexar una ruta de acceso implícita con otras propiedades con nombre después del separador de coma, por ejemplo, `{Binding LastName, Mode=TwoWay}`.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Propiedades de enlace que se pueden establecer con la extensión de enlace  
 La sintaxis se muestra en este tema utiliza la interfaz genérica `bindProp` = `value` aproximación, porque hay muchas propiedades de lectura/escritura de <xref:System.Windows.Data.BindingBase> o <xref:System.Windows.Data.Binding> que se pueden establecer a través de la `Binding` extensión de marcado / sintaxis de expresiones. Se pueden establecer en cualquier orden, a excepción de un modo implícito <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. (Es necesario especificar explícitamente la opción `Path=`, en cuyo caso se puede establecer en cualquier orden). Básicamente, puede establecer cero o más de las propiedades en la lista siguiente, con `bindProp` = `value` pares separados por comas.  
  
 Algunos de estos valores de propiedad requieren tipos de objetos que no admita una conversión de tipo nativo de una sintaxis de texto en XAML y, por tanto, se requieren las extensiones de marcado para poder establecerse como un valor de atributo. Compruebe el uso de atributos XAML en la sección en la biblioteca de clases de .NET Framework para cada propiedad para obtener más información; la cadena que se usa para la sintaxis de atributo XAML con o sin la extensión de marcado más uso es básicamente el mismo que el valor especificado en un `Binding` expresión, con la excepción que no se colocan las comillas alrededor de cada una `bindProp` = `value` en el `Binding` expresión.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: una cadena que identifica un grupo de enlace posibles. Este es un concepto de enlace relativamente avanzado; Consulte la página de referencia para <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Valor booleano, puede ser `true` o `false`. De manera predeterminada, es `false`.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>: se puede establecer como un `bindProp` = `value` cadena en la expresión, pero para ello requiere una referencia de objeto para el valor, como un [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md). En este caso, el valor es una instancia de una clase de convertidor personalizado.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>: se puede establecer en la expresión como un identificador basado en estándares; vea el tema de referencia para <xref:System.Windows.Data.Binding.ConverterCulture%2A>.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>: se puede establecer como un `bindProp` = `value` cadena en la expresión, pero esto no es depende del tipo del parámetro que se pasa. Si pasa un tipo de referencia para el valor, este uso requiere una referencia de objeto como un anidada [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>: mutuamente excluyente frente a <xref:System.Windows.Data.Binding.RelativeSource%2A> y <xref:System.Windows.Data.Binding.Source%2A>; cada de estas propiedades de enlace representa una metodología de enlace concreto. Vea [información general de enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: se puede establecer como un `bindProp` = `value` cadena en la expresión, pero esto no es depende del tipo del valor que se pasa. Si pasa un tipo de referencia requiere una referencia de objeto como un anidada [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>: Valor booleano, puede ser `true` o `false`. De manera predeterminada, es `false`.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>: *valor* es un nombre de la constante del <xref:System.Windows.Data.BindingMode> enumeración. Por ejemplo: `{Binding Mode=OneWay}`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Valor booleano, puede ser `true` o `false`. De manera predeterminada, es `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Valor booleano, puede ser `true` o `false`. De manera predeterminada, es `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Valor booleano, puede ser `true` o `false`. De manera predeterminada, es `false`.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>: una cadena que describe una ruta de acceso en un objeto de datos o un modelo de objetos generales. El formato proporciona varias convenciones para atravesar un modelo de objetos que no se puede describir adecuadamente en este tema. Vea [sintaxis de PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: mutuamente excluyente frente a <xref:System.Windows.Data.Binding.ElementName%2A> y <xref:System.Windows.Data.Binding.Source%2A>; cada de estas propiedades de enlace representa una metodología de enlace concreto. Vea [información general de enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md). Requiere un anidada [RelativeSource MarkupExtension](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) uso para especificar el valor.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>: mutuamente excluyente frente a <xref:System.Windows.Data.Binding.RelativeSource%2A> y <xref:System.Windows.Data.Binding.ElementName%2A>; cada de estas propiedades de enlace representa una metodología de enlace concreto. Vea [información general de enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md). Requiere el uso de una extensión anidada, normalmente un [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) que hace referencia a un origen de datos de objeto de un diccionario de recursos con clave.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>: una cadena que describe una convención de formato de cadena para los datos enlazados. Este es un concepto de enlace relativamente avanzado; Consulte la página de referencia para <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: se puede establecer como un `bindProp` = `value` cadena en la expresión, pero esto no es depende del tipo del parámetro que se pasa. Si pasa un tipo de referencia para el valor, requiere una referencia de objeto como un anidada [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *valor* es un nombre de la constante del <xref:System.Windows.Data.UpdateSourceTrigger> enumeración. Por ejemplo: `{Binding UpdateSourceTrigger=LostFocus}`. Controles específicos potencialmente tienen valores predeterminados diferentes para esta propiedad de enlace. Vea <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Valor booleano, puede ser `true` o `false`. De manera predeterminada, es `false`. Vea la sección Comentarios.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Valor booleano, puede ser `true` o `false`. De manera predeterminada, es `false`. Vea la sección Comentarios.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>: una cadena que describe una ruta de acceso al XMLDOM de un origen de datos XML. Vea [enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Los siguientes son propiedades de <xref:System.Windows.Data.Binding> que no se puede establecer utilizando la `Binding` extensión de marcado /`{Binding}` forma de expresión.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: esta propiedad espera una referencia a una implementación de devolución de llamada. No se puede hacer referencia a las devoluciones de llamada o métodos distintos de los controladores de eventos en sintaxis XAML.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>: la propiedad toma una colección genérica de <xref:System.Windows.Controls.ValidationRule> objetos. Esto se puede expresar como un elemento de propiedad en un <xref:System.Windows.Data.Binding> elemento de objeto, pero no tiene ninguna técnica de análisis de atributos disponible para su uso en un `Binding` expresión. Vea el tema de referencia para <xref:System.Windows.Data.Binding.ValidationRules%2A>.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Comentarios  
  
> [!IMPORTANT]
>  En términos de prioridad de la propiedad de dependencia, una `Binding` expresión es equivalente a establecida localmente un valor. Si establece un valor local para una propiedad que previamente tenía un `Binding` expresión, el `Binding` se ha quitado completamente. Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Descripción del enlace de datos en un nivel básico no se incluye en este tema. Vea [información general de enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding>y <xref:System.Windows.Data.PriorityBinding> no admiten un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintaxis de extensión. En su lugar, use los elementos de propiedad. Consulte los temas de referencia para <xref:System.Windows.Data.MultiBinding> y <xref:System.Windows.Data.PriorityBinding>.  
  
 Valores booleanos para XAML distinguen mayúsculas de minúsculas. Por ejemplo, puede especificar `{Binding NotifyOnValidationError=true}` o `{Binding NotifyOnValidationError=True}`.  
  
 Enlaces que implican la validación de datos se suelen especificar por explícito `Binding` elemento en lugar de como un `{Binding ...}` expresión y configuración <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> o <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> en una expresión es poco habitual. Esto es porque la propiedad complementaria <xref:System.Windows.Data.Binding.ValidationRules%2A> no se puede establecer con facilidad en forma de expresión. Para obtener más información, consulte [Implement Binding Validation](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md).  
  
 `Binding` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando hay un requisito que los valores de atributo sean valores literales o controlador de nombres de escape y el requisito es de índole más global que los convertidores de tipos con atributos en determinados tipos o propiedades. Todas las extensiones de marcado de XAML utilizan la `{` y `}` caracteres en su sintaxis de atributo, que es la convención que permite que un procesador XAML reconozca que una extensión de marcado debe procesar el contenido de la cadena. Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 `Binding`es una extensión de marcado típicos en los que la <xref:System.Windows.Data.Binding> clase que implementa la funcionalidad de extensión para la implementación de XAML de WPF también implementa otros muchos métodos y propiedades que no están relacionadas con XAML. Se pretenden hacer que los demás miembros <xref:System.Windows.Data.Binding> una clase más versátil e independiente que puede tener muchos escenarios de enlace de datos además de actuar como una extensión de marcado XAML.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Data.Binding>  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
