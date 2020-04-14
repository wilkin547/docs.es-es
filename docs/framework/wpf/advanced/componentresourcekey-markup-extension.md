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
ms.openlocfilehash: 4cdba2a61be4e9686cd2120fd90a213534c222c8
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243367"
---
# <a name="componentresourcekey-markup-extension"></a>Extensión de marcado ComponentResourceKey
Define y hace referencia a claves para los recursos que se cargan desde ensamblados externos. Esto permite que una búsqueda de recursos especifique un tipo de destino en un ensamblado, en lugar de un diccionario de recursos explícito en un ensamblado o en una clase.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Uso de atributos XAML (clave de configuración, compacta)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Uso de atributos XAML (clave de configuración, detallado)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Uso de atributos XAML (recurso solicitante, compacto)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Uso de atributos XAML (recurso solicitante, detallado)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`targetTypeName`|El nombre del tipo de Common Language Runtime (CLR) público que se define en el ensamblado de recursos.|  
|`targetID`|La clave del recurso. Cuando se buscan `targetID` recursos, será análogo a la [directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) del recurso.|  
  
## <a name="remarks"></a>Observaciones  
 Como se ve en los usos anteriores, un`ComponentResourceKey`uso de la extensión de marcado de la marca se encuentra en dos lugares:  
  
- La definición de una clave dentro de un diccionario de recursos de tema, tal como lo proporciona un autor de control.  
  
- Tener acceso a un recurso de tema desde el ensamblado, cuando se vuelve a realizar la plantillas del control, pero desea utilizar valores de propiedad que proceden de los recursos proporcionados por los temas del control.  
  
 Para hacer referencia a los recursos de componentes que `{DynamicResource}` proceden `{StaticResource}`de temas, generalmente se recomienda usar en lugar de . Esto se muestra en los usos. `{DynamicResource}`se recomienda porque el propio tema puede ser cambiado por el usuario. Si desea que el recurso de componente que coincida más estrechamente con la intención del autor del control para admitir un tema, debe habilitar la referencia de recurso de componente para que también sea dinámico.  
  
 El <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifica un tipo que existe en el ensamblado de destino donde el recurso está realmente definido. A `ComponentResourceKey` se puede definir y usar independientemente de saber exactamente dónde se define, <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> pero finalmente debe resolver el tipo a través de ensamblados a los que se hace referencia.  
  
 Un uso <xref:System.Windows.ComponentResourceKey> común para es definir las claves que, a continuación, se exponen como miembros de una clase. Para este uso, <xref:System.Windows.ComponentResourceKey> se usa el constructor de clase, no la extensión de marcado. Para obtener más <xref:System.Windows.ComponentResourceKey>información, vea , o la sección "Definición y referencia de claves para recursos temáticos" del tema [Información general](../controls/control-authoring-overview.md)sobre la creación de controles .  
  
 Tanto para establecer claves como para hacer referencia a recursos `ComponentResourceKey` con clave, la sintaxis de atributo se utiliza normalmente para la extensión de marcado.  
  
 La sintaxis compacta que <xref:System.Windows.ComponentResourceKey.%23ctor%2A> se muestra se basa en la firma del constructor y el uso de parámetros posicionales de una extensión de marcado. El orden en `targetTypeName` `targetID` que se dan y se dan es importante. La sintaxis detallada se <xref:System.Windows.ComponentResourceKey.%23ctor%2A> basa en el constructor <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> <xref:System.Windows.ComponentResourceKey.ResourceId%2A> sin parámetros y, a continuación, establece el y de una manera que es análoga a una sintaxis de atributo true en un elemento de objeto. En la sintaxis detallada, el orden en que se establecen las propiedades no es importante. La relación y los mecanismos de estas dos alternativas (compactas y detalladas) se describen con más detalle en el tema [Extensiones](markup-extensions-and-wpf-xaml.md)de marcado y XAML de WPF .  
  
 Técnicamente, el `targetID` valor para puede ser cualquier objeto, no tiene que ser una cadena. Sin embargo, el uso más `targetID` común en WPFWPF es alinear el valor con formularios que son cadenas y donde estas cadenas son válidas en la [gramática XamlName](../../../desktop-wpf/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey`se puede utilizar en la sintaxis de elemento de objeto. En este caso, es necesario <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> especificar <xref:System.Windows.ComponentResourceKey.ResourceId%2A> el valor de las propiedades y para inicializar correctamente la extensión.  
  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la implementación del lector, la <xref:System.Windows.ComponentResourceKey> clase define el control de esta extensión de marcado.  
  
 `ComponentResourceKey` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Información general sobre la creación de controles](../controls/control-authoring-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
