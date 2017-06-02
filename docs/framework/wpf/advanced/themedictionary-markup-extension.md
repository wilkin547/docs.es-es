---
title: "Extensi&#243;n de marcado ThemeDictionary | Microsoft Docs"
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
  - "ThemeDictionaryExtension"
  - "ThemeDictionary"
helpviewer_keywords: 
  - "ThemeDictionary (extensión de marcado)"
  - "XAML, ThemeDictionary (extensión de marcado)"
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Extensi&#243;n de marcado ThemeDictionary
Proporciona a los autores de controles personalizados o a las aplicaciones que integran controles de otros fabricantes una manera de cargar los diccionarios de recursos específicos del tema para utilizarlos en la aplicación de estilos al control.  
  
## Uso de atributos XAML  
  
```  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## Uso de elementos de objeto XAML  
  
```  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`assemblyUri`|[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] del ensamblado que contiene información del tema.  Normalmente, se trata de un pack URI que hace referencia a un ensamblado en el paquete mayor.  Los recursos de ensamblado y los pack URI simplifican los problemas de implementación.  Para obtener más información, vea [Empaquetar URI en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).|  
  
## Comentarios  
 Extensión está pensada para rellenar un solo valor de propiedad concreto: un valor para <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=fullName>.  
  
 Utilizando esta extensión, puede especificar un único ensamblado sólo de recursos que contenga algunos estilos para utilizarlos solamente cuando se aplique el tema [!INCLUDE[TLA#tla_aero](../../../../includes/tlasharptla-aero-md.md)] al sistema del usuario, otros estilos cuando esté activo el tema Luna, y así sucesivamente.  Utilizando esta extensión, se puede invalidar automáticamente y volver a cargar el contenido de un diccionario de recursos específico del control de modo que sea específico de otro tema cuando se necesite.  
  
 La cadena `assemblyUri` \(valor de propiedad <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>\) constituye la base de una convención de nomenclatura que identifica qué diccionario se aplica para un tema concreto.  La lógica de <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> para `ThemeDictionary` completa la convención generando un [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] que señala a una variante concreta del diccionario del tema, contenida dentro de un ensamblado de recursos precompilado.  En este artículo no se aborda plenamente la descripción de esta convención ni el concepto de las interacciones de los temas con la aplicación general de estilos, a controles o en el nivel de aplicación o página.  El escenario básico para utilizar `ThemeDictionary` es especificar la propiedad <xref:System.Windows.ResourceDictionary.Source%2A> de un objeto `ResourceDictionary` declarado en el nivel de la aplicación.  Cuando se proporciona un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para el ensamblado mediante una extensión de `ThemeDictionary` en lugar de utilizar un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] directo, la lógica de la extensión proporciona la lógica de invalidación que se aplica cada vez que cambia el tema del sistema.  
  
 La sintaxis de atributo es la que se usa más a menudo con esta extensión de marcado.  El token de cadena que se proporciona después de la cadena de identificador `ThemeDictionary` se asigna como valor de <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> de la clase de extensión <xref:System.Windows.ThemeDictionaryExtension> subyacente.  
  
 `ThemeDictionary` también se puede utilizar en la sintaxis de elementos de objeto.  En este caso, es preciso especificar el valor de la propiedad <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>.  
  
 `ThemeDictionary` también se puede utilizar en un uso de atributos detallado que especifica la propiedad <xref:System.Windows.Markup.StaticExtension.Member%2A> como un par propiedad\=valor:  
  
```  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales.  Dado que `ThemeDictionary` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En la implementación del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el control para esta extensión de marcado se define mediante la clase <xref:System.Windows.ThemeDictionaryExtension>.  
  
 `ThemeDictionary` es una extensión de marcado.  Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.  Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado.  Para obtener más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Archivos de recursos, contenido y datos de aplicaciones de WPF](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)