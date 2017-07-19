---
title: "Extensi&#243;n de marcado DynamicResource | Microsoft Docs"
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
  - "DynamicResource"
  - "DynamicResourceExtension"
helpviewer_keywords: 
  - "DynamicResource (extensión de marcado)"
  - "XAML, DynamicResource (extensión de marcado)"
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Extensi&#243;n de marcado DynamicResource
Proporciona un valor para cualquier atributo de propiedad [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] difiriendo ese valor de modo que sea una referencia a un recurso definido.  El comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de ejecución.  
  
## Uso de atributos XAML  
  
```  
<object property="{DynamicResource key}" .../>  
```  
  
## Uso de elementos de propiedad XAML  
  
```  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`key`|Clave del recurso solicitado.  Esta clave la asigna [x:Key \(Directiva\)](../../../../docs/framework/xaml-services/x-key-directive.md) inicialmente si se ha creado un recurso en el marcado, o bien se proporciona como parámetro `key` al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=fullName> si el recurso se ha creado mediante código.|  
  
## Comentarios  
 Un `DynamicResource` creará una expresión temporal durante la compilación inicial y, de este modo, diferirá la consulta de recursos hasta que el valor de recurso solicitado se necesite realmente para construir un objeto.  Potencialmente, esto puede suceder una vez cargada la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  El valor de recurso se buscará mediante la búsqueda de clave en todos los diccionarios de recursos activos empezando por el ámbito de la página actual, y reemplazará la expresión utilizada como marcador de posición en la compilación.  
  
> [!IMPORTANT]
>  Por lo que se refiere a la prioridad de las propiedades de dependencia, una expresión `DynamicResource` es equivalente a la posición donde se aplica la referencia dinámica al recurso.  Si establece un valor local para una propiedad que previamente tenía una expresión `DynamicResource` como su valor local, `DynamicResource` se quita totalmente.  Para obtener información detallada, vea [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Algunos escenarios de acceso a recursos son particularmente adecuados para `DynamicResource` al contrario que una [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  Vea [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) para obtener una explicación sobre las ventajas relativas y las implicaciones de rendimiento de `DynamicResource` y `StaticResource`.  
  
 La propiedad <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> especificada debe corresponder a un recurso existente determinado por [x:Key \(Directiva\)](../../../../docs/framework/xaml-services/x-key-directive.md) en algún nivel de la página, la aplicación, los temas de control disponibles y los recursos externos o recursos del sistema, y la búsqueda de recursos se realizará en ese orden.  Para obtener más información sobre la búsqueda de recursos estáticos y dinámicos, vea [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Una clave de recurso puede ser cualquier cadena definida en [Gramática de XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md).  Una clave de recurso también puede ser otros tipos de objeto, como un <xref:System.Type>.  Una clave <xref:System.Type> es fundamental para el modo de aplicar estilos a los controles mediante temas.  Para obtener más información, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] para la búsqueda de valores de recursos, como <xref:System.Windows.FrameworkElement.FindResource%2A>, siguen la misma lógica de búsqueda de recursos que `DynamicResource`.  
  
 La manera declarativa alternativa de hacer referencia a un recurso es hacerlo como [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
 La sintaxis de atributo es la que se usa más a menudo con esta extensión de marcado.  El token de cadena que se proporciona después de la cadena de identificador `DynamicResource` se asigna como valor de <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.DynamicResourceExtension> subyacente.  
  
 `DynamicResource` se puede utilizar en sintaxis de elementos de objeto.  En este caso, es preciso especificar el valor de la propiedad <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>.  
  
 `DynamicResource` también se puede utilizar en un uso de atributos detallado que especifica la propiedad <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> como un par propiedad\=valor:  
  
```  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales.  Dado que `DynamicResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En la implementación del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el control para esta extensión de marcado se define mediante la clase <xref:System.Windows.DynamicResourceExtension>.  
  
 `DynamicResource` es una extensión de marcado.  Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.  Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado.  Para obtener más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Vea también  
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Recursos y código](../../../../docs/framework/wpf/advanced/resources-and-code.md)   
 [x:Key \(Directiva\)](../../../../docs/framework/xaml-services/x-key-directive.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)   
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)