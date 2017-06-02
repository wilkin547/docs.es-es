---
title: "Enlazar extensi&#243;n de marcado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Binding"
helpviewer_keywords: 
  - "Binding (extensión de marcado)"
  - "XAML, Binding (extensión de marcado)"
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Enlazar extensi&#243;n de marcado
Aplaza un valor de propiedad para que sea un valor enlazado a datos, y crea un objeto de expresión intermedio e interpreta el contexto de datos que se aplica al elemento y a su enlace en tiempo de ejecución.  
  
## Uso de expresiones de enlace  
  
```  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## Notas de sintaxis  
 En estas sintaxis, `[]` y `*` no son literales.  Son parte de una notación para indicar que se pueden usar cero o más pares *propEnl*`=`*valor*, con un separador `,` entre ellos y los pares *propEnl*`=`*valor* precedentes.  
  
 Cualquiera de las propiedades mostradas en la sección "Propiedades de enlace que se pueden establecer con la extensión de enlace" puede establecerse en su lugar mediante los atributos de un elemento de objeto <xref:System.Windows.Data.Binding>.  Sin embargo, este no es el verdadero uso de la extensión de marcado de <xref:System.Windows.Data.Binding>, simplemente es el procesamiento XAML general de los atributos que establecen las propiedades de la clase <xref:System.Windows.Data.Binding> de CLR.  Es decir, `<Binding` *bindProp1*`="`*value1*`"[` *bindPropN*`="`*valueN*`"]*/>` es una sintaxis casi equivalente para los atributos de uso del elemento de objeto <xref:System.Windows.Data.Binding> en lugar de un uso de la expresión `Binding`.  Para obtener información sobre el uso de atributos XAML de propiedades concretas de <xref:System.Windows.Data.Binding>, vea la sección "Uso de atributos XAML" de la propiedad pertinente de <xref:System.Windows.Data.Binding> en la Biblioteca de clases de .NET Framework.  
  
## Valores XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Nombre de la propiedad <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.BindingBase> que se va a establecer.  No todas las propiedades <xref:System.Windows.Data.Binding> se pueden establecer con la extensión `Binding` y algunas de ellas únicamente se pueden establecer dentro de una expresión `Binding` mediante extensiones de marcado anidadas adicionales.  Consulte la sección "Propiedades de enlace que se pueden establecer con la extensión de enlace".|  
|`value1, valueN`|Valor en que se establecerá la propiedad.  El control del valor de atributo es, en definitiva, específico del tipo y la lógica de la propiedad <xref:System.Windows.Data.Binding> concreta que se establece.|  
|`path`|Cadena de ruta de acceso que establece la propiedad <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> implícita.  Vea también [Sintaxis de PropertyPath de XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## {Binding} incompleto  
 El uso de `{Binding}` mostrado en "Uso de la expresión Binding" crea un objeto <xref:System.Windows.Data.Binding> con valores predeterminados que incluye una propiedad <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> inicial de `null`.  Esto sigue resultando útil en muchos escenarios, porque los objetos <xref:System.Windows.Data.Binding> creados podrían confiar en que las propiedades de enlace de datos clave como <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> y <xref:System.Windows.Data.Binding.Source%2A?displayProperty=fullName> están establecidas en el contexto de datos en tiempo de ejecución.  Para obtener más información sobre el concepto de contexto de datos, vea [Enlace de datos](../../../../docs/framework/wpf/data/data-binding-wpf.md).  
  
## Ruta de acceso implícita  
 La extensión de marcado `Binding` usa <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> como una "propiedad predeterminada" conceptual, donde `Path=` no tiene por qué aparecer en la expresión.  Si especifica una expresión `Binding` con una ruta de acceso implícita, esta debe aparecer primero en la expresión, antes de cualquier otro par `bindProp`\=`value`, la propiedad <xref:System.Windows.Data.Binding> se especifica por nombre.  Por ejemplo: `{Binding PathString}`, donde `PathString` es una cadena que se evalúa como el valor de <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> del objeto <xref:System.Windows.Data.Binding> creada por el uso de la extensión de marcado.  Puede anexar una ruta de acceso implícita con otras propiedades con nombre después del separador de coma, por ejemplo, `{Binding LastName, Mode=TwoWay}`.  
  
## Propiedades de enlace que se pueden establecer con la extensión de enlace  
 En la sintaxis mostrada en este tema se utiliza la aproximación genérica `bindProp`\=`value`, porque hay muchas propiedades de lectura y escritura de <xref:System.Windows.Data.BindingBase> o <xref:System.Windows.Data.Binding> que se pueden establecer mediante la extensión de marcado o la sintaxis de la expresión `Binding`.  Pueden establecerse en cualquier orden, a excepción de una propiedad <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> implícita.  \(Tiene la opción de especificar `Path=` explícitamente, en cuyo caso también puede establecerse en cualquier orden\).  Básicamente, puede establecer cero o más de las propiedades de la lista siguiente, mediante pares `bindProp`\=`value` separados por comas.  
  
 Varios de estos valores de propiedad requieren tipos de objetos que no admiten una conversión de tipo nativo de una sintaxis de texto en XAML y, en consecuencia, requieren extensiones de marcado para poder establecerse como un valor de atributo.  Para obtener más información, vea la sección Uso de atributos XAML en la Biblioteca de clases de .NET Framework para cada propiedad; la cadena que se usa para la sintaxis del atributo XAML con o sin uso adicional de la extensión de marcado es básicamente igual que el valor que se especifica en una expresión `Binding`, con la excepción de que no se colocan las comillas alrededor de `bindProp`\=`value` en la expresión `Binding`.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: una cadena que identifica un posible grupo de enlaces.  Este es un concepto de enlace relativamente avanzado; vea la página de referencia de <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: booleana; puede ser `true` o `false`.  El valor predeterminado es `false`.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>: puede establecerse como una cadena `bindProp`\=`value` en la expresión, pero esto requiere una referencia a objeto para el valor, como [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  El valor en este caso es una instancia de una clase de convertidor personalizada.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>: se puede establecer en la expresión como un identificador basado en normas; vea el tema de referencia correspondiente a <xref:System.Windows.Data.Binding.ConverterCulture%2A>.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>: puede establecerse como una cadena `bindProp`\=`value` en la expresión, pero depende del tipo del parámetro que se va a pasar.  Si se pasa un tipo de referencia para el valor, este uso requiere una referencia a objeto, como una [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) anidada.  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>: mutuamente excluyente frente a <xref:System.Windows.Data.Binding.RelativeSource%2A> y <xref:System.Windows.Data.Binding.Source%2A>; cada una de estas propiedades de enlace representa una metodología de enlace determinada.  Vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: puede establecerse como una cadena `bindProp`\=`value` en la expresión, pero depende del tipo del valor que se va a pasar.  Si se pasa un tipo de referencia, se requiere una referencia a objeto, como una [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) anidada.  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>: booleana; puede ser `true` o `false`.  El valor predeterminado es `false`.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>: *valor* es un nombre constante de la enumeración <xref:System.Windows.Data.BindingMode>.  Por ejemplo, `{Binding Mode=OneWay}`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: booleana; puede ser `true` o `false`.  El valor predeterminado es `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: booleana; puede ser `true` o `false`.  El valor predeterminado es `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: booleana; puede ser `true` o `false`.  El valor predeterminado es `false`.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>: una cadena que describe una ruta de acceso en un objeto de datos o un modelo de objetos general.  El formato proporciona varias convenciones diferentes para atravesar un modelo de objetos que no se puede describir suficientemente en este tema.  Vea [Sintaxis de PropertyPath de XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: mutuamente excluyente frente a <xref:System.Windows.Data.Binding.ElementName%2A> y <xref:System.Windows.Data.Binding.Source%2A>; cada una de estas propiedades de enlace representan una metodología de enlace determinada.  Vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  Exige el uso de una [Extensión de marcado RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) anidada para especificar el valor.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>: mutuamente excluyente frente a <xref:System.Windows.Data.Binding.RelativeSource%2A> y <xref:System.Windows.Data.Binding.ElementName%2A>; cada una de estas propiedades de enlace representa una metodología de enlace determinada.  Vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  Requiere el uso de una extensión anidada, normalmente la [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) que hace referencia a un origen de datos de objeto de un diccionario de recursos clave.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>: una cadena que describe una convención de formato de cadena para los datos enlazados.  Este es un concepto de enlace relativamente avanzado; vea la página de referencia de <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: puede establecerse como una cadena `bindProp`\=`value` en la expresión, pero depende del tipo del parámetro que se va a pasar.  Si se pasa un tipo de referencia para el valor, se requiere una referencia a objeto, como una [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) anidada.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *valor* es un nombre constante de la enumeración <xref:System.Windows.Data.UpdateSourceTrigger>.  Por ejemplo, `{Binding UpdateSourceTrigger=LostFocus}`.  Los controles concretos tienen potencialmente valores predeterminados diferentes para esta propiedad de enlace.  Vea <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: booleana; puede ser `true` o `false`.  El valor predeterminado es `false`.  Vea la sección Comentarios.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: booleana; puede ser `true` o `false`.  El valor predeterminado es `false`.  Vea la sección Comentarios.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>: una cadena que describe una ruta de acceso al XMLDOM de un origen de datos XML.  Vea [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Las siguientes son propiedades de <xref:System.Windows.Data.Binding> que no se pueden establecer mediante la extensión de marcado `Binding`\/forma de expresión `{Binding}`.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: esta propiedad espera una referencia a una implementación de devolución de llamada.  No se puede hacer referencia a las devoluciones de llamada o métodos distintos de los controladores de eventos en sintaxis XAML.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>: esta propiedad toma una colección genérica de objetos <xref:System.Windows.Controls.ValidationRule>.  Esto se puede expresar como un elemento de propiedad en un elemento de objeto <xref:System.Windows.Data.Binding>, pero no tiene ninguna técnica de análisis de atributos disponible para el uso en una expresión `Binding`.  Vea el tema de referencia para <xref:System.Windows.Data.Binding.ValidationRules%2A>.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## Comentarios  
  
> [!IMPORTANT]
>  Por lo que se refiere a la prioridad de las propiedades de dependencia, una expresión `Binding` es equivalente a un valor establecido localmente.  Si establece un valor local para una propiedad que previamente tenía una expresión `Binding`, `Binding` se quita totalmente.  Para obtener información detallada, vea [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 La descripción del enlace de datos en un nivel básico no se incluye en este tema.  Vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding> y <xref:System.Windows.Data.PriorityBinding> no admiten la sintaxis de extensión de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. En su lugar, use los elementos de propiedad.  Vea los temas de referencia para <xref:System.Windows.Data.MultiBinding> y <xref:System.Windows.Data.PriorityBinding>.  
  
 Los valores booleanos para XAML no distinguen entre mayúsculas y minúsculas.  Por ejemplo, puede especificar `{Binding NotifyOnValidationError=true}` o `{Binding NotifyOnValidationError=True}`.  
  
 Los enlaces que implican la validación de datos se especifican normalmente por un elemento `Binding` explícito en lugar de como una expresión `{Binding ...}` y no es frecuente establecer <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> o <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> en una expresión.  Esto es debido a que la propiedad complementaria <xref:System.Windows.Data.Binding.ValidationRules%2A> no se puede establecer directamente en el formulario de expresión.  Para obtener más información, vea [Implementar la validación de enlaces](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md).  
  
 `Binding` es una extensión de marcado.  Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que los convertidores de tipos con atributos en determinados tipos o propiedades.  Todas las extensiones de marcado de código XAML usan caracteres `{` y `}` en su sintaxis de atributo, que es la convención que permite que un procesador XAML reconozca que el contenido de la cadena se debe procesar mediante una extensión de marcado.  Para obtener más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 `Binding` es una extensión de marcado atípica porque la clase <xref:System.Windows.Data.Binding> que implementa la funcionalidad de la extensión para la implementación XAML de WPF también implementa otros muchos métodos y propiedades que no están relacionados con XAML.  Los otros miembros están dirigidos a aumentar la versatilidad y autonomía de la clase <xref:System.Windows.Data.Binding> para que sea pueda resolver numerosos escenarios de enlace de datos además de actuar como extensión de marcado XAML.  
  
## Vea también  
 <xref:System.Windows.Data.Binding>   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)