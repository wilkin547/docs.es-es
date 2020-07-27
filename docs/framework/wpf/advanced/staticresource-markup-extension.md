---
title: Extensión de marcado StaticResource
description: Proporciona un valor para cualquier atributo de propiedad XAML mediante la búsqueda de una referencia a un recurso ya definido.
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: 77396c1867dcbe279d7ba158ed9e6f5f833f17b5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164678"
---
# <a name="staticresource-markup-extension"></a>Extensión de marcado StaticResource
Proporciona un valor para cualquier [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributo de propiedad buscando una referencia a un recurso ya definido. El comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de carga, que buscará los recursos que se cargaron previamente desde el marcado de la página actual, así [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como otros orígenes de aplicación, y generará ese valor de recurso como valor de propiedad en los objetos en tiempo de ejecución.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xml  
<object property="{StaticResource key}" ... />  
```  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" ... />  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`key`|Clave del recurso solicitado. Esta clave se asignó inicialmente mediante la [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) si un recurso se creó en el marcado, o se proporcionó como `key` parámetro al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si el recurso se creó en el código.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!IMPORTANT]
> `StaticResource`No debe intentar realizar una referencia adelantada a un recurso que se define léxicamente en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo. No se admite el intento de hacerlo y, incluso si no se produce un error en una referencia de este tipo, si se intenta la referencia adelantada, se producirá una reducción del rendimiento de tiempo de carga cuando se busquen en las tablas hash internas que representan a <xref:System.Windows.ResourceDictionary> . Para obtener los mejores resultados, ajuste la composición de los diccionarios de recursos de forma que se puedan evitar las referencias hacia delante. Si no puede evitar una referencia adelantada, utilice en su lugar la [extensión de marcado DynamicResource](dynamicresource-markup-extension.md) .  
  
 El especificado <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> debe corresponder a un recurso existente, identificado con una [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) en algún nivel de la página, en la aplicación, en los temas de control disponibles y en los recursos externos, o en los recursos del sistema. La búsqueda de recursos se produce en ese orden. Para obtener más información sobre el comportamiento de búsqueda de recursos para recursos estáticos y dinámicos, vea [recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 Una clave de recurso puede ser cualquier cadena definida en la [gramática de XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md). Una clave de recurso también puede ser otros tipos de objeto, como <xref:System.Type> . Una <xref:System.Type> clave es fundamental para el modo en que los temas pueden aplicar estilos a los controles mediante una clave de estilo implícita. Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).  
  
 El método declarativo alternativo de hacer referencia a un recurso es una [extensión de marcado DynamicResource](dynamicresource-markup-extension.md).  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `StaticResource` se asigna como valor de <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.StaticResourceExtension> subyacente.  
  
 `StaticResource`se puede usar en la sintaxis de elemento de objeto. En este caso, es necesario especificar el valor de la <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> propiedad.  
  
 `StaticResource` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> como un par de propiedad=valor:  
  
```xml  
<object property="{StaticResource ResourceKey=key}" ... />  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales. Dado que `StaticResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementación del procesador, la clase define el control para esta extensión de marcado <xref:System.Windows.StaticResourceExtension> .  
  
 `StaticResource` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también

- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Recursos y código](resources-and-code.md)
