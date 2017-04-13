---
title: "Extensi&#243;n de marcado ComponentResourceKey | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ComponentResourceKey"
  - "ComponentResourceKeyExtension"
helpviewer_keywords: 
  - "ComponentResourceKey (extensión de marcado)"
  - "XAML, ComponentResourceKey (extensión de marcado)"
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Extensi&#243;n de marcado ComponentResourceKey
Define claves para recursos que se cargan desde ensamblados externos, y hace referencia a ellas.  Esto permite especificar en una búsqueda de recursos un tipo de destino de un ensamblado, en lugar de un diccionario de recursos explícito del ensamblado o de una clase.  
  
## Uso de atributos XAML \(clave de valor, sintaxis compacta\)  
  
```  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## Uso de atributos XAML \(clave de valor, sintaxis detallada\)  
  
```  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## Uso de atributos XAML \(recurso de solicitud, sintaxis compacta\)  
  
```  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## Uso de atributos XAML \(recurso de solicitud, sintaxis detallada\)  
  
```  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`targetTypeName`|Nombre del tipo [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] público definido en el ensamblado de recursos.|  
|`targetID`|Clave del recurso.  Al buscar los recursos, `targetID` será análogo al [x:Key \(Directiva\)](../../../../docs/framework/xaml-services/x-key-directive.md) del recurso.|  
  
## Comentarios  
 Tal y como se ve en las utilizaciones anteriores, un uso de la extensión de marcado `ComponentResourceKey`} se encuentra en dos lugares:  
  
-   La definición de una clave dentro de un diccionario de recurso de tema, tal como la proporciona un autor de control.  
  
-   Tener acceso a un recurso de temas desde el ensamblado, cuando vuelve a crear plantillas en el control pero desea utilizar los valores de propiedades que proceden de los recursos proporcionados por los temas del control.  
  
 Para hacer referencia a los recursos de componente que proceden de los temas, generalmente se recomienda utilizar `{DynamicResource}` en lugar de `{StaticResource}`.  Esto se muestra en los usos.  Se recomienda `{DynamicResource}` porque el usuario puede cambiar el propio tema.  Si desea que el recurso de componente se aproxime más a la intención del autor de control para apoyar un tema, debería habilitar su referencia de recurso de componente para que también sea dinámica.  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifica un tipo que existe en el ensamblado de destino donde el recurso está definido en realidad.  `ComponentResourceKey` se puede definir y utilizar independientemente de si se sabe con exactitud dónde está definida la propiedad <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>, pero en su caso deberá resolverse el tipo a través de los ensamblados a los que se hace referencia.  
  
 Un uso común de <xref:System.Windows.ComponentResourceKey> consiste en definir claves que luego se exponen como miembros de una clase.  Para este uso, se utiliza el constructor de clase <xref:System.Windows.ComponentResourceKey>, no la extensión de marcado.  Para obtener más información, vea <xref:System.Windows.ComponentResourceKey> o la sección "Definir y hacer referencia a claves para los recursos de tema" del tema [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Tanto para establecer claves como para hacer referencia a recursos con clave, la sintaxis de atributo se utiliza normalmente para la extensión de marcado `ComponentResourceKey`.  
  
 La sintaxis compacta mostrada se basa en la firma del constructor <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=fullName> y en la utilización del parámetro posicional de una extensión de marcado.  El orden en que se proporcionan `targetTypeName` y `targetID` es importante.  La sintaxis detallada se basa en el constructor predeterminado <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=fullName> y, a continuación, establece <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> y <xref:System.Windows.ComponentResourceKey.ResourceId%2A> de manera análoga a una verdadera sintaxis de atributo en un elemento de objeto.  En la sintaxis detallada, el orden en que se establecen las propiedades carece de importancia.  La relación y los mecanismos de estas dos alternativas \(compacta y detallada\) se describen con más detalle en el tema [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Técnicamente, el valor para `targetID` puede ser cualquier objeto, no tiene que ser una cadena.  Sin embargo, el uso más común en WPF es alinear el valor `targetID` con formularios que son cadenas y donde tales cadenas son válidas en [Gramática de XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey` se puede utilizar en sintaxis de elementos de objeto.  En este caso, es necesario especificar el valor de las propiedades <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> y <xref:System.Windows.ComponentResourceKey.ResourceId%2A> para inicializar correctamente la extensión.  
  
 La clase <xref:System.Windows.ComponentResourceKey> define el control para esta extensión de marcado en la implementación del lector [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 `ComponentResourceKey` es una extensión de marcado.  Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.  Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado.  Para obtener más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Vea también  
 <xref:System.Windows.ComponentResourceKey>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)