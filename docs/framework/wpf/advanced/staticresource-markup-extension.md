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
ms.openlocfilehash: 5c0bb247bae525658d89d53f1672e57b87aba7bc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646212"
---
# <a name="staticresource-markup-extension"></a>Extensión de marcado StaticResource
Proporciona un valor [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para cualquier atributo de propiedad buscando una referencia a un recurso ya definido. El comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] carga, que buscará los recursos que se cargaron previamente desde el marcado de la página actual, así como otros orígenes de aplicación, y generará ese valor de recurso como el valor de propiedad en los objetos en tiempo de ejecución.  
  
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
|`key`|Clave del recurso solicitado. Esta clave se asignó inicialmente mediante la [directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) si `key` se creó un recurso en el marcado o se proporcionó como parámetro al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si el recurso se creó en el código.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!IMPORTANT]
> A `StaticResource` no debe intentar hacer una referencia directa a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] recurso que se define léxicamente más dentro del archivo. No se admite el intento de hacerlo, e incluso si una referencia de este tipo no falla, al intentar <xref:System.Windows.ResourceDictionary> la referencia de reenvío se incurrirá en una penalización del rendimiento del tiempo de carga cuando se busquen las tablas hash internas que representan a. Para obtener los mejores resultados, ajuste la composición de los diccionarios de recursos de modo que se puedan evitar las referencias directas. Si no puede evitar una referencia directa, utilice [DynamicResource Markup Extension](dynamicresource-markup-extension.md) en su lugar.  
  
 El especificado <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> debe corresponder a un recurso existente, identificado con una [directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) en algún nivel de la página, la aplicación, los temas de control disponibles y los recursos externos, o los recursos del sistema. La búsqueda de recursos se produce en ese orden. Para obtener más información sobre el comportamiento de búsqueda de recursos para recursos estáticos y dinámicos, vea [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 Una clave de recurso puede ser cualquier cadena definida en [la gramática XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md). Una clave de recurso también puede ser <xref:System.Type>otros tipos de objeto, como un archivo . Una <xref:System.Type> clave es fundamental para cómo los temas pueden aplicar estilo a los controles a través de una clave de estilo implícita. Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).  
  
 El medio declarativo alternativo para hacer referencia a un recurso es como una extensión de [marcado DynamicResource](dynamicresource-markup-extension.md).  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `StaticResource` se asigna como valor de <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.StaticResourceExtension> subyacente.  
  
 `StaticResource`se puede utilizar en la sintaxis de elemento de objeto. En este caso, se requiere <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> especificar el valor de la propiedad.  
  
 `StaticResource` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> como un par de propiedad=valor:  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales. Dado que `StaticResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la implementación del procesador, la <xref:System.Windows.StaticResourceExtension> clase define el control de esta extensión de marcado.  
  
 `StaticResource` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Consulte también

- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Recursos y código](resources-and-code.md)
