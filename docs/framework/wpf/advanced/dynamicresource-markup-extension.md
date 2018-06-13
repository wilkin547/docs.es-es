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
ms.openlocfilehash: c09d009a8cc90e050f6cfb1a8d2abd5c61c5b19f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545329"
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
|`key`|Clave del recurso solicitado. Esta clave se asignó inicialmente por el [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) si un recurso se creó en el marcado, o se proporcionó como el `key` parámetro al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si el recurso se creó en el código.|  
  
## <a name="remarks"></a>Comentarios  
 Un `DynamicResource` creará una expresión temporal durante la compilación inicial y, por tanto, aplazar la consulta de recursos hasta que el valor de recurso solicitado se necesite realmente para construir un objeto. Esto puede ser después de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se carga la página. El valor del recurso se encontrará en función de búsqueda de la clave en todos los diccionarios de recursos activos a partir del ámbito de la página actual y se sustituye por la expresión de marcador de posición de la compilación.  
  
> [!IMPORTANT]
>  En términos de prioridad de la propiedad de dependencia, una `DynamicResource` expresión es equivalente a la posición donde se aplica la referencia de recurso dinámico. Si establece un valor local para una propiedad que previamente tenía un `DynamicResource` expresión como el valor local, el `DynamicResource` se ha quitado completamente. Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Son especialmente adecuadas para determinados escenarios de acceso de recurso `DynamicResource` en contraposición a un [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md). Vea [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) para obtener información sobre las ventajas relativas y las implicaciones de rendimiento de `DynamicResource` y `StaticResource`.  
  
 Especificado <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> debe corresponder a un recurso existente determinado por [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) en algún nivel en la página, aplicación, los temas de control disponibles y recursos externos o recursos del sistema y la búsqueda de recursos se realizará en ese orden. Para obtener más información acerca de las búsquedas de recursos para los recursos estáticos y dinámicos, consulte [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Una clave de recurso puede ser cualquier cadena definida en el [XamlName (gramática)](../../../../docs/framework/xaml-services/xamlname-grammar.md). Una clave de recurso también puede ser otros tipos de objeto, como un <xref:System.Type>. Un <xref:System.Type> clave es fundamental para cómo pueden aplicarse estilos a controles por los temas. Para obtener más información, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] para la búsqueda de valores de recursos, como <xref:System.Windows.FrameworkElement.FindResource%2A>, siga la misma lógica de búsqueda de recursos que usa `DynamicResource`.  
  
 Es la manera declarativa alternativa de hacer referencia a un recurso como una [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `DynamicResource` se asigna como valor de <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.DynamicResourceExtension> subyacente.  
  
 `DynamicResource` puede usarse en la sintaxis de elemento de objeto. En este caso, especificando el valor de la <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> propiedad es obligatoria.  
  
 `DynamicResource` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> como un par de propiedad=valor:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales. Dado que `DynamicResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementación del procesador, el control para esta extensión de marcado se define por la <xref:System.Windows.DynamicResourceExtension> clase.  
  
 `DynamicResource` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también  
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Recursos y código](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [x:Key (Directiva)](../../../../docs/framework/xaml-services/x-key-directive.md)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [StaticResource (extensión de marcado)](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
