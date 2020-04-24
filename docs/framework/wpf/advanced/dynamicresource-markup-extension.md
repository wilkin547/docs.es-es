---
title: Extensión de marcado DynamicResource
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: 5ccda8ba8f41a30e0ce1c832a6d3176b7fb8e8c2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646260"
---
# <a name="dynamicresource-markup-extension"></a>Extensión de marcado DynamicResource
Proporciona un valor [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para cualquier atributo de propiedad aplazando ese valor para que sea una referencia a un recurso definido. El comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de ejecución.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>Uso de elementos de propiedad XAML  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`key`|Clave del recurso solicitado. Esta clave se asignó inicialmente mediante la [directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) si `key` se creó un recurso en el marcado o se proporcionó como parámetro al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si el recurso se creó en el código.|  
  
## <a name="remarks"></a>Observaciones  
 A `DynamicResource` creará una expresión temporal durante la compilación inicial y, por lo tanto, aplazará la búsqueda de recursos hasta que el valor de recurso solicitado sea realmente necesario para construir un objeto. Esto puede ser posiblemente después de cargar la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página. El valor del recurso se encontrará en función de la búsqueda de claves en todos los diccionarios de recursos activos a partir del ámbito de página actual y se sustituye por la expresión de marcador de posición de la compilación.  
  
> [!IMPORTANT]
> En términos de prioridad `DynamicResource` de propiedad de dependencia, una expresión es equivalente a la posición donde se aplica la referencia de recurso dinámico. Si establece un valor local para una `DynamicResource` propiedad que anteriormente `DynamicResource` tenía una expresión como valor local, se quita por completo. Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](dependency-property-value-precedence.md).  
  
 Ciertos escenarios de acceso `DynamicResource` a recursos son especialmente adecuados para una extensión de [marcado StaticResource](staticresource-markup-extension.md). Consulta [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) para obtener una explicación sobre `DynamicResource` `StaticResource`los méritos relativos y las implicaciones de rendimiento de y .  
  
 El especificado <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> debe corresponder a un recurso existente determinado por [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) en algún nivel de la página, la aplicación, los temas de control disponibles y los recursos externos, o los recursos del sistema, y la búsqueda de recursos se realizará en ese orden. Para obtener más información acerca de la búsqueda de recursos para recursos estáticos y dinámicos, vea [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 Una clave de recurso puede ser cualquier cadena definida en [la gramática XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md). Una clave de recurso también puede ser <xref:System.Type>otros tipos de objeto, como un archivo . Una <xref:System.Type> clave es fundamental para cómo los temas pueden aplicar estilo a los controles. Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).  
  
 Las API para la búsqueda <xref:System.Windows.FrameworkElement.FindResource%2A>de valores de recursos, como `DynamicResource`, siguen la misma lógica de búsqueda de recursos que usa .  
  
 El medio declarativo alternativo para hacer referencia a un recurso es como una extensión de [marcado StaticResource](staticresource-markup-extension.md).  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `DynamicResource` se asigna como valor de <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.DynamicResourceExtension> subyacente.  
  
 `DynamicResource`se puede utilizar en la sintaxis de elemento de objeto. En este caso, se requiere <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> especificar el valor de la propiedad.  
  
 `DynamicResource` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> como un par de propiedad=valor:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales. Dado que `DynamicResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la implementación del procesador, la <xref:System.Windows.DynamicResourceExtension> clase define el control de esta extensión de marcado.  
  
 `DynamicResource` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Consulte también

- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Recursos y código](resources-and-code.md)
- [x:Key (Directiva)](../../../desktop-wpf/xaml-services/xkey-directive.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [Extensión de marcado StaticResource](staticresource-markup-extension.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
