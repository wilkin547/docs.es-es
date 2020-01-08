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
ms.openlocfilehash: f8b05f314be84e6104f1a9c7fe2edfdf826e51da
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559453"
---
# <a name="dynamicresource-markup-extension"></a>Extensión de marcado DynamicResource
Proporciona un valor para cualquier atributo de propiedad [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] si se difiere ese valor para que sea una referencia a un recurso definido. El comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de ejecución.  
  
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
|`key`|Clave del recurso solicitado. Esta clave se asignó inicialmente mediante la [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) si un recurso se creó en el marcado, o se proporcionó como `key` parámetro al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si el recurso se creó en el código.|  
  
## <a name="remarks"></a>Notas  
 Una `DynamicResource` creará una expresión temporal durante la compilación inicial y, por tanto, aplazará la búsqueda de recursos hasta que el valor de recurso solicitado sea realmente necesario para construir un objeto. Podría ser una vez cargada la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. El valor del recurso se encontrará en función de la búsqueda de clave en todos los diccionarios de recursos activos a partir del ámbito de la página actual y se sustituye por la expresión de marcador de posición de la compilación.  
  
> [!IMPORTANT]
> En cuanto a la prioridad de las propiedades de dependencia, una expresión de `DynamicResource` es equivalente a la posición donde se aplica la referencia de recursos dinámicos. Si establece un valor local para una propiedad que anteriormente tenía una expresión `DynamicResource` como valor local, el `DynamicResource` se quita por completo. Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](dependency-property-value-precedence.md).  
  
 Algunos escenarios de acceso a recursos son especialmente adecuados para `DynamicResource` en lugar de una [extensión de marcado StaticResource](staticresource-markup-extension.md). Vea [recursos XAML](xaml-resources.md) para obtener una explicación sobre las ventajas relativas y las implicaciones de rendimiento de `DynamicResource` y `StaticResource`.  
  
 El <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> especificado debe corresponder a un recurso existente determinado por [la Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) en algún nivel de la página, la aplicación, los temas de control disponibles y los recursos externos, o los recursos del sistema, y la búsqueda de recursos se producirá en ese orden. Para obtener más información sobre la búsqueda de recursos para recursos estáticos y dinámicos, vea [recursos XAML](xaml-resources.md).  
  
 Una clave de recurso puede ser cualquier cadena definida en la [gramática de XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md). Una clave de recurso también puede ser otros tipos de objeto, como un <xref:System.Type>. Una clave <xref:System.Type> es fundamental para el modo en que los temas pueden aplicar estilos a los controles. Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).  
  
 Las API para la búsqueda de valores de recursos, como <xref:System.Windows.FrameworkElement.FindResource%2A>, siguen la misma lógica de búsqueda de recursos que usan `DynamicResource`.  
  
 El medio alternativo declarativo de hacer referencia a un recurso es una [extensión de marcado StaticResource](staticresource-markup-extension.md).  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `DynamicResource` se asigna como valor de <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.DynamicResourceExtension> subyacente.  
  
 `DynamicResource` se puede utilizar en la sintaxis de elementos de objeto. En este caso, es necesario especificar el valor de la propiedad <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>.  
  
 `DynamicResource` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> como un par de propiedad=valor:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales. Dado que `DynamicResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En la implementación del procesador de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], el control de esta extensión de marcado se define mediante la clase <xref:System.Windows.DynamicResourceExtension>.  
  
 `DynamicResource` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también

- [Recursos XAML](xaml-resources.md)
- [Recursos y código](resources-and-code.md)
- [x:Key (Directiva)](../../../desktop-wpf/xaml-services/xkey-directive.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [StaticResource (extensión de marcado)](staticresource-markup-extension.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
