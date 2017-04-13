---
title: "mc:ProcessContent (Atributo) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "mc:ProcessContent (atributo)"
  - "XAML, mc:ProcessContent (atributo)"
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# mc:ProcessContent (Atributo)
Especifica los elementos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cuyo contenido deben procesar los elementos primarios pertinentes, aunque un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] omita el elemento primario inmediato por tener especificado el [Atributo mc:Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).  El atributo `mc:ProcessContent` admite la compatibilidad de marcado para la asignación de espacios de nombres personalizados y para el control de versiones [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
## Uso de atributos XAML  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|*ignorablePrefix*|Cualquier cadena de prefijo válida, de acuerdo con la especificación de XML 1.0.|  
|*ignorableUri*|Cualquier URI válido para designar un espacio de nombres, de acuerdo con la especificación de XML 1.0.|  
|*ThisElementCanBeIgnored*|Elemento que las implementaciones del procesador [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pueden omitir si no se puede resolver el tipo subyacente.|  
|*\[content\]*|*ThisElementCanBeIgnored* está marcado como omitible.  Si el procesador de impresión omite ese elemento, se procesa *\[content\]* mediante *object*.|  
  
## Comentarios  
 De manera predeterminada, un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] omitirá el contenido incluido en un elemento omitido.  Puede especificar un elemento concreto mediante `mc:ProcessContent`, en cuyo caso un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] continuará procesando el contenido incluido dentro del elemento omitido.  Esto se suele utilizar si el contenido está anidado dentro de varias etiquetas, y al menos una de ellas es omitible y otra de ellas no lo es.  
  
 Se pueden especificar varios prefijos en el atributo, utilizando un separador de espacio; por ejemplo: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 El espacio de nombres [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] define otros elementos y atributos que se documentan en esta sección del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].  Para obtener más información, vea [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## Vea también  
 [Atributo mc:Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)