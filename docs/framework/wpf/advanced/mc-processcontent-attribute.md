---
title: mc:ProcessContent (Atributo)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fe43e2450c35d976db7a188f854f7864f298afc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent (Atributo)
Especifica qué [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementos todavía deben tener contenido procesado por los elementos primarios pertinentes, aunque se puede omitir el elemento primario inmediato por un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador debido a la especificación de [mc: Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) . El `mc:ProcessContent` atributo admite la compatibilidad de marcado para la asignación de espacio de nombres personalizado y para [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] control de versiones.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
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
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|*ignorablePrefix*|Cualquier cadena de prefijo, según la especificación XML 1.0.|  
|*ignorableUri*|Cualquier URI válido para designar un espacio de nombres, según la especificación XML 1.0.|  
|*ThisElementCanBeIgnored*|Un elemento que se puede omitir si [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] las implementaciones del procesador, si no se puede resolver el tipo subyacente.|  
|*[contenido]*|*ThisElementCanBeIgnored* se marca puede pasar por alto. Si el procesador de impresión omite ese elemento, *[contenido]* procesa *objeto*.|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador omitirá el contenido incluido en un elemento omitido. Puede especificar un elemento específico por `mc:ProcessContent`y un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador continuará procesando el contenido dentro del elemento omitido. Esto lo que normalmente se utiliza si el contenido está anidado dentro de varias etiquetas, al menos uno de los cuales se pueden pasar por alto y al menos uno de los cuales no pueden pasar por alto.  
  
 Se pueden especificar varios prefijos en el atributo, con un espacio como separador, por ejemplo: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 El [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] espacio de nombres define otros elementos y atributos que no están documentados en esta área de la [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Para obtener más información, consulte [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Vea también  
 [mc:Ignorable (atributo)](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
