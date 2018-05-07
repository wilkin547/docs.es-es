---
title: Extensión de marcado ComponentResourceKey
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: d11c26add084165eaa9fd0b319a375c4b98c7fb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="componentresourcekey-markup-extension"></a>Extensión de marcado ComponentResourceKey
Define y hace referencia a las claves de recursos que se cargan desde ensamblados externos. Esto permite una búsqueda de recursos especificar un tipo de destino en un ensamblado, en lugar de un diccionario de recursos explícito en un ensamblado o en una clase.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Uso de atributos XAML (clave de configuración, compact)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Uso de atributos XAML (clave de valor, detallado)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Uso de atributos XAML (recurso de solicitud, compact)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Uso de atributos XAML (recurso de solicitud, detallado)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`targetTypeName`|El nombre del público [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] tipo que se define en el ensamblado de recursos.|  
|`targetID`|La clave para el recurso. Cuando se buscan recursos, `targetID` será similar a la [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) del recurso.|  
  
## <a name="remarks"></a>Comentarios  
 Tal como se muestra en los usos de la anteriores, un {`ComponentResourceKey`} uso de la extensión de marcado se encuentra en dos lugares:  
  
-   La definición de una tecla dentro de un diccionario de recursos de tema, proporcionados por el autor de un control.  
  
-   Cuando se obtiene acceso a un recurso de temas desde el ensamblado, el control vuelve a crear plantillas pero desea utilizar los valores de propiedad que proceden de los recursos proporcionados por los temas del control.  
  
 Para hacer referencia a los recursos de componente que proceden de los temas, se recomienda generalmente utilizar `{DynamicResource}` en lugar de `{StaticResource}`. Esto se muestra en los usos. `{DynamicResource}` se recomienda porque el usuario puede cambiar el propio tema. Si desea que el recurso de componente que mejor se ajuste la intención del autor de control para admitir un tema, debe habilitar la referencia de recurso de componente al que también sea dinámica.  
  
 El <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifica un tipo que existe en el ensamblado de destino donde se define realmente el recurso. A `ComponentResourceKey` se puede definir y utilizar independientemente de saber exactamente donde la <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> está definido, pero finalmente debe resolver el tipo en los ensamblados que se hace referencia.  
  
 Un uso común para <xref:System.Windows.ComponentResourceKey> consiste en definir claves que, a continuación, se exponen como miembros de una clase. Para este uso, utilice el <xref:System.Windows.ComponentResourceKey> constructor de clase, no la extensión de marcado. Para obtener más información, consulte <xref:System.Windows.ComponentResourceKey>, o en la sección "Definir y hacer referencia a claves para recursos de tema" del tema [información general de creación de Control](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Para establecer las claves tanto que hacen referencia a recursos con clave, la sintaxis de atributo se utiliza normalmente para el `ComponentResourceKey` extensión de marcado.  
  
 La sintaxis compacta se muestra se basa en el <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> firma del constructor y el uso de parámetro posicional de una extensión de marcado. El orden en que el `targetTypeName` y `targetID` tienen es importante. La sintaxis detallada se basa en el <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> constructor predeterminado y, a continuación, Establece la <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> y <xref:System.Windows.ComponentResourceKey.ResourceId%2A> de forma que es análoga a una verdadera sintaxis de atributo en un elemento de objeto. En la sintaxis detallada, no es importante el orden en el que se establecen las propiedades. La relación y los mecanismos de estas dos alternativas (compacta y detallados) se describe con más detalle en el tema [las extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Técnicamente, el valor de `targetID` puede ser cualquier objeto, no tiene que ser una cadena. Sin embargo, el uso más común en WPF es alinear el `targetID` valor con formularios que son cadenas y donde tales cadenas son válidas en el [XamlName (gramática)](../../../../docs/framework/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey` puede usarse en la sintaxis de elemento de objeto. En este caso, especificar el valor de la <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> y <xref:System.Windows.ComponentResourceKey.ResourceId%2A> propiedades debe inicializar correctamente la extensión.  
  
 En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementación del lector, el control para esta extensión de marcado se define por la <xref:System.Windows.ComponentResourceKey> clase.  
  
 `ComponentResourceKey` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.ComponentResourceKey>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
