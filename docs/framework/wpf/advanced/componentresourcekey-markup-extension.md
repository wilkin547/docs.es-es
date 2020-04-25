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
ms.openlocfilehash: f86b7000b97bbc1287347947a9244c24a7de74c2
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141136"
---
# <a name="componentresourcekey-markup-extension"></a>Extensión de marcado ComponentResourceKey
Define y hace referencia a las claves de los recursos que se cargan desde ensamblados externos. Esto permite que una búsqueda de recursos especifique un tipo de destino en un ensamblado, en lugar de un diccionario de recursos explícito en un ensamblado o en una clase.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Uso de atributos XAML (clave de configuración, Compact)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Uso de atributos XAML (configuración de clave, detallado)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Uso de atributos XAML (recurso de solicitud, Compact)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Uso de atributos XAML (recurso de solicitud, detallado)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" ... />  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`targetTypeName`|Nombre del tipo de Common Language Runtime público (CLR) que se define en el ensamblado de recursos.|  
|`targetID`|La clave para el recurso. Cuando se buscan los recursos, `targetID` será análogo a la [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) del recurso.|  
  
## <a name="remarks"></a>Observaciones  
 Tal como se ha mostrado en los usos anteriores,`ComponentResourceKey`un uso de la extensión de marcado {} se encuentra en dos lugares:  
  
- La definición de una clave dentro de un diccionario de recursos de tema, tal y como la proporciona el autor de un control.  
  
- Obtener acceso a un recurso de tema desde el ensamblado, cuando se replantilla el control, pero se desea usar valores de propiedad que proceden de los recursos proporcionados por los temas del control.  
  
 Para hacer referencia a los recursos de componentes que proceden de los temas, se `{DynamicResource}` recomienda usar `{StaticResource}`en lugar de. Esto se muestra en los usos. `{DynamicResource}`se recomienda porque el usuario puede cambiar el propio tema. Si desea que el recurso del componente coincida mejor con la intención del autor del control para admitir un tema, debe permitir que la referencia de recurso del componente también sea dinámica.  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> Identifica un tipo que existe en el ensamblado de destino en el que se define realmente el recurso. Se `ComponentResourceKey` puede definir y usar independientemente de que sepa exactamente dónde <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> se define, pero finalmente debe resolver el tipo a través de los ensamblados a los que se hace referencia.  
  
 Un uso común de <xref:System.Windows.ComponentResourceKey> es definir las claves que se exponen como miembros de una clase. Para este uso, se usa el <xref:System.Windows.ComponentResourceKey> constructor de clase, no la extensión de marcado. Para obtener más información, <xref:System.Windows.ComponentResourceKey>vea o la sección "definir y hacer referencia a las claves para los recursos del tema" del tema [información general sobre la creación de controles](../controls/control-authoring-overview.md).  
  
 Para establecer claves y hacer referencia a recursos con clave, la sintaxis de atributo se `ComponentResourceKey` usa normalmente para la extensión de marcado.  
  
 La sintaxis compacta que se muestra se basa <xref:System.Windows.ComponentResourceKey.%23ctor%2A> en la firma del constructor y el uso de parámetros posicionales de una extensión de marcado. El orden en el que `targetTypeName` se `targetID` proporcionan y es importante. La sintaxis detallada se basa en el <xref:System.Windows.ComponentResourceKey.%23ctor%2A> constructor sin parámetros y, a continuación, establece <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> y <xref:System.Windows.ComponentResourceKey.ResourceId%2A> de forma análoga a una sintaxis de atributo verdadera en un elemento de objeto. En la sintaxis detallada, el orden en el que se establecen las propiedades no es importante. La relación y los mecanismos de estas dos alternativas (compacta y detallada) se describen con más detalle en el tema [extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
 Técnicamente, el valor de `targetID` puede ser cualquier objeto, no tiene que ser una cadena. Sin embargo, el uso más común en WPF es alinear `targetID` el valor con formularios que son cadenas, y donde dichas cadenas son válidas en la [gramática de XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey`se puede usar en la sintaxis de elemento de objeto. En este caso, es necesario especificar el valor de las <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> propiedades <xref:System.Windows.ComponentResourceKey.ResourceId%2A> y para inicializar correctamente la extensión.  
  
 En la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementación del lector, la <xref:System.Windows.ComponentResourceKey> clase define el control para esta extensión de marcado.  
  
 `ComponentResourceKey` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Información general sobre la creación de controles](../controls/control-authoring-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
