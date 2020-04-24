---
title: Extensión de marcado ThemeDictionary
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: f6ba0fe45aa11063c79d673b26794072968f4200
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646184"
---
# <a name="themedictionary-markup-extension"></a>Extensión de marcado ThemeDictionary
Proporciona a los autores de controles personalizados o a las aplicaciones que integran controles de otros fabricantes una manera de cargar los diccionarios de recursos específicos del tema para usarlos en la aplicación de estilos al control.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`assemblyUri`|Identificador uniforme de recursos (URI) del ensamblado que contiene información del tema. Normalmente, se trata de un Pack URI que hace referencia a un ensamblado en el paquete mayor. Los recursos de ensamblado y los Pack URI simplifican los problemas de implementación. Para más información, vea [Empaquetar URI en WPF](../app-development/pack-uris-in-wpf.md).|  
  
## <a name="remarks"></a>Observaciones  
 Esta extensión está diseñada para rellenar solo un <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>valor de propiedad específico: un valor para .  
  
 Mediante esta extensión, puede especificar un único ensamblado de solo recursos que contenga algunos estilos para usar solo cuando el tema Aero de Windows se aplica al sistema del usuario, otros estilos solo cuando el tema Luna está activo, etc. Al usar esta extensión, se puede invalidar automáticamente y volver a cargar el contenido de un diccionario de recursos específico del control de modo que sea específico de otro tema cuando se necesite.  
  
 La `assemblyUri` cadena<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> (valor de propiedad) forma la base de una convención de nomenclatura que identifica qué diccionario se aplica a un tema determinado. La <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> lógica `ThemeDictionary` para completar la convención mediante la generación de un identificador uniforme de recursos (URI) que apunta a una variante de diccionario de tema determinado, como se encuentra dentro de un ensamblado de recursos precompilado. En este artículo no se aborda plenamente la descripción de esta convención, ni el concepto de las interacciones de los temas con la aplicación general de estilos a controles o en el nivel de aplicación o de página. El escenario básico `ThemeDictionary` para su <xref:System.Windows.ResourceDictionary.Source%2A> uso `ResourceDictionary` es especificar la propiedad de un declarado en el nivel de aplicación. Cuando se proporciona un URI `ThemeDictionary` para el ensamblado a través de una extensión en lugar de como un URI directo, la lógica de extensión proporcionará lógica de invalidación que se aplica siempre que cambie el tema del sistema.  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `ThemeDictionary` se asigna como valor de <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> de la clase de extensión <xref:System.Windows.ThemeDictionaryExtension> subyacente.  
  
 `ThemeDictionary` también se puede usar en la sintaxis de elementos de objeto. En este caso, se requiere <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> especificar el valor de la propiedad.  
  
 `ThemeDictionary` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.Markup.StaticExtension.Member%2A> como un par de propiedad=valor:  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales. Dado que `ThemeDictionary` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la implementación del procesador, la <xref:System.Windows.ThemeDictionaryExtension> clase define el control de esta extensión de marcado.  
  
 `ThemeDictionary` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Consulte también

- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [Archivos de recursos, contenido y datos de aplicaciones de WPF](../app-development/wpf-application-resource-content-and-data-files.md)
