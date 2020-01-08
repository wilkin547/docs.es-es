---
title: Extensión de marcado StaticResource
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: aa7f69e8871295006c3c5a9c7d0a70d0ecbd6d7e
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559825"
---
# <a name="staticresource-markup-extension"></a>Extensión de marcado StaticResource
Proporciona un valor para cualquier atributo de propiedad [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mediante la búsqueda de una referencia a un recurso ya definido. El comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de carga, que buscará los recursos que se cargaron previamente desde el marcado de la página de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] actual, así como otros orígenes de aplicación, y generará ese valor de recurso como valor de propiedad en los objetos en tiempo de ejecución.  
  
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
|`key`|Clave del recurso solicitado. Esta clave se asignó inicialmente mediante la [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) si un recurso se creó en el marcado, o se proporcionó como `key` parámetro al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si el recurso se creó en el código.|  
  
## <a name="remarks"></a>Notas  
  
> [!IMPORTANT]
> Un `StaticResource` no debe intentar realizar una referencia adelantada a un recurso que se define léxicamente en el archivo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. No se admite el intento de hacerlo y, incluso si no se produce un error en una referencia de este tipo, el intento de la referencia adelantada incurrirá en el rendimiento en tiempo de carga cuando se busquen las tablas hash internas que representan una <xref:System.Windows.ResourceDictionary>. Para obtener los mejores resultados, ajuste la composición de los diccionarios de recursos de forma que se puedan evitar las referencias hacia delante. Si no puede evitar una referencia adelantada, utilice en su lugar la [extensión de marcado DynamicResource](dynamicresource-markup-extension.md) .  
  
 El <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> especificado debe corresponder a un recurso existente, identificado con una [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) en algún nivel de la página, aplicación, los temas de control disponibles y los recursos externos, o los recursos del sistema. La búsqueda de recursos se produce en ese orden. Para obtener más información sobre el comportamiento de búsqueda de recursos para recursos estáticos y dinámicos, vea [recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 Una clave de recurso puede ser cualquier cadena definida en la [gramática de XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md). Una clave de recurso también puede ser otros tipos de objeto, como un <xref:System.Type>. Una clave <xref:System.Type> es fundamental para el modo en que los temas pueden aplicar estilos a los controles mediante una clave de estilo implícita. Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).  
  
 El método declarativo alternativo de hacer referencia a un recurso es una [extensión de marcado DynamicResource](dynamicresource-markup-extension.md).  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `StaticResource` se asigna como valor de <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.StaticResourceExtension> subyacente.  
  
 `StaticResource` se puede utilizar en la sintaxis de elementos de objeto. En este caso, es necesario especificar el valor de la propiedad <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>.  
  
 `StaticResource` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> como un par de propiedad=valor:  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales. Dado que `StaticResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En la implementación del procesador de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], el control de esta extensión de marcado se define mediante la clase <xref:System.Windows.StaticResourceExtension>.  
  
 `StaticResource` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también

- [Aplicar estilos y plantillas](../controls/styling-and-templating.md)
- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Recursos y código](resources-and-code.md)
