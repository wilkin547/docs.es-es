---
title: "Extensión de marcado StaticResource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 821cd152ccb7a02dda5338d6a3ec44d6625c0097
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="staticresource-markup-extension"></a>Extensión de marcado StaticResource
Proporciona un valor para cualquier [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributo de propiedad buscando una referencia a un recurso ya definido. Comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de carga, que tendrá un aspecto de los recursos que se cargaron previamente desde el marcado del elemento actual [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página, así como otros orígenes de la aplicación y generará ese valor de recurso como la valor de propiedad en los objetos de tiempo de ejecución.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`key`|La clave para el recurso solicitado. Esta clave se asignó inicialmente por el [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) si un recurso se creó en el marcado, o se proporcionó como el `key` parámetro al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si el recurso se creó en el código.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!IMPORTANT]
>  A `StaticResource` no debe intentar realizar una referencia adelantada a un recurso que se define léxicamente adicional dentro de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo. No se admite el intento de hacerlo, y aunque no producirá un error en dicha referencia, intentando la referencia adelantada incurrirá en una penalización de rendimiento de tiempo de carga cuando las tablas hash interna que representa un <xref:System.Windows.ResourceDictionary> se buscan. Para obtener mejores resultados, ajuste la composición de los diccionarios de recursos, que se pueden evitar las referencias adelantadas. Si no se puede evitar una referencia adelantada, utilice [extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) en su lugar.  
  
 Especificado <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> debe corresponder a un recurso existente, identificado con un [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) en algún nivel en la página, aplicación, los temas de control disponibles y recursos externos o recursos del sistema. La búsqueda de recursos se produce en ese orden. Para obtener más información acerca del comportamiento de búsqueda de recursos para recursos estáticos y dinámicos, consulte [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Una clave de recurso puede ser cualquier cadena definida en el [XamlName (gramática)](../../../../docs/framework/xaml-services/xamlname-grammar.md). Una clave de recurso también puede ser otros tipos de objeto, como un <xref:System.Type>. Un <xref:System.Type> clave es fundamental para cómo pueden aplicarse estilos a controles por temas, a través de una clave de estilo implícita. Para obtener más información, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Es la manera declarativa alternativa de hacer referencia a un recurso como una [extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `StaticResource` se asigna como valor de <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.StaticResourceExtension> subyacente.  
  
 `StaticResource`puede usarse en la sintaxis de elemento de objeto. En este caso, especificando el valor de la <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> propiedad es obligatoria.  
  
 `StaticResource` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> como un par de propiedad=valor:  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales. Dado que `StaticResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementación del procesador, el control para esta extensión de marcado se define por la <xref:System.Windows.StaticResourceExtension> clase.  
  
 `StaticResource` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Recursos y código](../../../../docs/framework/wpf/advanced/resources-and-code.md)
