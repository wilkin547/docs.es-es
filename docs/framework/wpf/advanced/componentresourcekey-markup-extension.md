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
ms.openlocfilehash: 5f72d6c3273cfda4276383cfe72f90196e5d4340
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037757"
---
# <a name="componentresourcekey-markup-extension"></a>Extensión de marcado ComponentResourceKey
Define y hace referencia a las claves de recursos que se cargan desde ensamblados externos. Esto permite una búsqueda de recursos especificar un tipo de destino en un ensamblado, en lugar de un diccionario de recursos explícita en un ensamblado o en una clase.  
  
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
|`targetID`|La clave para el recurso. Cuando se buscan recursos `targetID` será similar a la [Directiva x: Key](../../xaml-services/x-key-directive.md) del recurso.|  
  
## <a name="remarks"></a>Comentarios  
 Tal como se muestra en los usos anteriores, un {`ComponentResourceKey`} uso de la extensión de marcado se encuentra en dos lugares:  
  
- La definición de una clave dentro de un diccionario de recursos de tema, según lo proporcionado por el autor de un control.  
  
- Obtener acceso a un recurso de temas desde el ensamblado, cuando el control vuelve a crear plantillas, pero desea utilizar los valores de propiedad que proceden de los recursos proporcionados por los temas del control.  
  
 Para hacer referencia a los recursos del componente que proceden de los temas, se recomienda por lo general utilice `{DynamicResource}` lugar `{StaticResource}`. Esto se muestra en los usos. `{DynamicResource}` se recomienda porque el propio tema puede cambiarse por el usuario. Si desea que el recurso de componente que mejor coincida con intención del autor de control para admitir un tema, debe habilitar la referencia de recurso de componente que también sean dinámicos.  
  
 El <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifica un tipo que existe en el ensamblado de destino que el recurso está definido realmente. Un `ComponentResourceKey` puede definirse y utilizarse independientemente de saber exactamente donde el <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> está definido, pero finalmente debe resolver el tipo de los ensamblados que se hace referencia.  
  
 Un uso común para <xref:System.Windows.ComponentResourceKey> consiste en definir las claves que, a continuación, se exponen como miembros de una clase. Para este uso, usa el <xref:System.Windows.ComponentResourceKey> constructor de clase, no la extensión de marcado. Para obtener más información, consulte <xref:System.Windows.ComponentResourceKey>, o en la sección "Definir y hacer referencia a claves de recursos de tema" del tema [Control Authoring Overview](../controls/control-authoring-overview.md).  
  
 Para establecer las claves tanto que hacen referencia a recursos con clave, normalmente se utiliza la sintaxis de atributo para el `ComponentResourceKey` extensión de marcado.  
  
 La sintaxis compacta se muestra se basa en el <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> firma del constructor y el uso de parámetro posicional de una extensión de marcado. El orden en que el `targetTypeName` y `targetID` reciben es importante. La sintaxis detallada se basa en el <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> constructor predeterminado y, a continuación, Establece el <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> y <xref:System.Windows.ComponentResourceKey.ResourceId%2A> de manera que es análoga a una sintaxis de atributo es true en un elemento de objeto. En la sintaxis detallada, no es importante el orden en el que se establecen las propiedades. La relación y los mecanismos de estas dos alternativas (compacta y detallados) se describe con más detalle en el tema [extensiones de marcado y WPF XAML](markup-extensions-and-wpf-xaml.md).  
  
 Técnicamente, el valor de `targetID` puede ser cualquier objeto, no tiene que ser una cadena. Sin embargo, el uso más común en WPF es alinear los `targetID` valor con los formularios que son cadenas, y donde las cadenas de este tipo son válidas en el [gramática de XamlName](../../xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey` se puede usar en la sintaxis de elemento de objeto. En este caso, especificando el valor de ambos el <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> y <xref:System.Windows.ComponentResourceKey.ResourceId%2A> propiedades es necesario para inicializar correctamente la extensión.  
  
 En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementación de lector, el control para esta extensión de marcado se define por la <xref:System.Windows.ComponentResourceKey> clase.  
  
 `ComponentResourceKey` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Información general sobre la creación de controles](../controls/control-authoring-overview.md)
- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
