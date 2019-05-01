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
ms.openlocfilehash: d07816718ebee2507f1888cffb70e6f8037bb996
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010402"
---
# <a name="dynamicresource-markup-extension"></a>Extensión de marcado DynamicResource
Proporciona un valor para cualquier [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributo de propiedad aplazando ese valor para que sea una referencia a un recurso definido. Comportamiento de búsqueda de ese recurso es análogo a la búsqueda de tiempo de ejecución.  
  
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
|`key`|Clave del recurso solicitado. Esta clave se asignó inicialmente por el [Directiva x: Key](../../xaml-services/x-key-directive.md) si un recurso se creó en el marcado, o se proporcionó como el `key` parámetro al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si el recurso se creó en el código.|  
  
## <a name="remarks"></a>Comentarios  
 Un `DynamicResource` creará una expresión temporal durante la compilación inicial y, por tanto, aplazar la consulta de recursos hasta que el valor del recurso solicitado sea realmente necesario para construir un objeto. Esto puede ser potencialmente después el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se carga la página. El valor del recurso se encuentra en función de búsqueda de clave en todos los diccionarios de recursos activos a partir del ámbito de la página actual y se sustituye por la expresión de marcador de posición de la compilación.  
  
> [!IMPORTANT]
>  En términos de prioridad de la propiedad de dependencia, una `DynamicResource` expresión es equivalente a la posición donde se aplica la referencia de recurso dinámico. Si establece un valor local para una propiedad que previamente tenía una `DynamicResource` expresión como el valor local, el `DynamicResource` se ha quitado completamente. Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](dependency-property-value-precedence.md).  
  
 Son especialmente adecuadas para determinados escenarios de acceso de recurso `DynamicResource` en contraposición a un [StaticResource Markup Extension](staticresource-markup-extension.md). Consulte [recursos XAML](xaml-resources.md) para obtener información sobre las ventajas relativas y las implicaciones de rendimiento de `DynamicResource` y `StaticResource`.  
  
 Especificado <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> debe corresponder a un recurso existente determinado por [Directiva x: Key](../../xaml-services/x-key-directive.md) en algún nivel en la página, aplicación, temas de control disponibles y los recursos externos o recursos del sistema y la búsqueda de recursos se realizará en ese orden. Para obtener más información acerca de la búsqueda de recursos para recursos estáticos y dinámicos, consulte [recursos XAML](xaml-resources.md).  
  
 Una clave de recurso puede ser cualquier cadena definida en el [gramática de XamlName](../../xaml-services/xamlname-grammar.md). Una clave de recurso también puede ser otros tipos de objeto, como un <xref:System.Type>. Un <xref:System.Type> es fundamental en cómo puede cambiar el estilo por temas clave. Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] para la búsqueda de valores de recursos, tales como <xref:System.Windows.FrameworkElement.FindResource%2A>, siguen la misma lógica de búsqueda de recursos que usa el `DynamicResource`.  
  
 Es la manera declarativa alternativa de hacer referencia a un recurso como un [StaticResource Markup Extension](staticresource-markup-extension.md).  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `DynamicResource` se asigna como valor de <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.DynamicResourceExtension> subyacente.  
  
 `DynamicResource` se puede usar en la sintaxis de elemento de objeto. En este caso, especificando el valor de la <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> propiedad es obligatoria.  
  
 `DynamicResource` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> como un par de propiedad=valor:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales. Dado que `DynamicResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementación del procesador, el control para esta extensión de marcado se define por la <xref:System.Windows.DynamicResourceExtension> clase.  
  
 `DynamicResource` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también

- [Recursos XAML](xaml-resources.md)
- [Recursos y código](resources-and-code.md)
- [x:Key (Directiva)](../../xaml-services/x-key-directive.md)
- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [StaticResource (extensión de marcado)](staticresource-markup-extension.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
