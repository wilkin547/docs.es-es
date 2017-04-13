---
title: "Extensi&#243;n de marcado StaticResource | Microsoft Docs"
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
  - "StaticResource"
  - "StaticResourceExtension"
helpviewer_keywords: 
  - "StaticResource (extensión de marcado)"
  - "XAML, StaticResource (extensión de marcado)"
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Extensi&#243;n de marcado StaticResource
Proporciona un valor para cualquier atributo de propiedad [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] buscando una referencia a un recurso ya definido.  El comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de carga, que busca recursos que se cargaron previamente desde el marcado de la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] actual, así como desde otros orígenes de la aplicación, y genera ese valor de recurso como el valor de propiedad de los objetos en tiempo de ejecución.  
  
## Uso de atributos XAML  
  
```  
<object property="{StaticResource key}" .../>  
```  
  
## Uso de elementos de objeto XAML  
  
```  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`key`|Clave del recurso solicitado.  Esta clave la asigna [x:Key \(Directiva\)](../../../../docs/framework/xaml-services/x-key-directive.md) inicialmente si se ha creado un recurso en el marcado, o bien se proporciona como parámetro `key` al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=fullName> si el recurso se ha creado mediante código.|  
  
## Comentarios  
  
> [!IMPORTANT]
>  `StaticResource` no debe intentar realizar una referencia adelantada a un recurso que se define léxicamente en un punto posterior del archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Esto no se admite, e incluso si una referencia de este tipo no da lugar a ningún error, el intento de hacerla provocará una reducción del rendimiento en tiempo de carga cuando se busque en las tablas hash internas que representan un objeto <xref:System.Windows.ResourceDictionary>.  Para obtener los mejores resultados, ajuste la composición de los diccionarios de recursos de modo que se eviten las referencias adelantadas.  Si no puede evitar una referencia adelantada, utilice la [Extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) en su lugar.  
  
 La propiedad <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> especificada debe corresponder a un recurso existente, identificado con un [x:Key \(Directiva\)](../../../../docs/framework/xaml-services/x-key-directive.md) en algún nivel de la página, la aplicación, los temas de control disponibles y los recursos externos o del sistema.  La búsqueda de recursos se produce en ese orden.  Para obtener más información sobre el comportamiento de la búsqueda de recursos estáticos y dinámicos, vea [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Una clave de recurso puede ser cualquier cadena definida en [Gramática de XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md).  Una clave de recurso también puede ser otros tipos de objeto, como un <xref:System.Type>.  Una clave <xref:System.Type> es fundamental para determinar cómo se pueden aplicar los estilos a los controles mediante temas, a través de una clave de estilo implícita.  Para obtener más información, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 La manera declarativa alternativa de hacer referencia a un recurso es hacerlo como [Extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
 La sintaxis de atributo es la que se usa más a menudo con esta extensión de marcado.  El token de cadena que se proporciona después de la cadena de identificador `StaticResource` se asigna como valor de <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.StaticResourceExtension> subyacente.  
  
 `StaticResource` se puede utilizar en la sintaxis de elementos de objeto.  En este caso, es preciso especificar el valor de la propiedad <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>.  
  
 `StaticResource` también se puede utilizar en un uso de atributos detallado que especifica la propiedad <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> como un par propiedad\=valor:  
  
```  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales.  Dado que `StaticResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En la implementación del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el control para esta extensión de marcado se define mediante la clase <xref:System.Windows.StaticResourceExtension>.  
  
 `StaticResource` es una extensión de marcado.  Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.  Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado.  Para obtener más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Recursos y código](../../../../docs/framework/wpf/advanced/resources-and-code.md)