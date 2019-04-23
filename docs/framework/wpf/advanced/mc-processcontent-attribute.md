---
title: mc:ProcessContent (Atributo)
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 865b1a3ccc30ff5efab4b08956bf7ba2bba4769c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110591"
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent (Atributo)
Especifica qué [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementos todavía deben tener contenido procesado por los elementos primarios pertinentes, incluso si el elemento primario inmediato puede ser omitido por un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador debido a la especificación de [mc: Ignorable (atributo)](mc-ignorable-attribute.md) . El `mc:ProcessContent` atributo admite la compatibilidad de marcado para la asignación de espacio de nombres personalizado tanto para [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] control de versiones.  
  
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
|*ignorablePrefix*|Cualquier cadena de prefijo válido, según la especificación XML 1.0.|  
|*ignorableUri*|Cualquier URI válido para designar un espacio de nombres, según la especificación XML 1.0.|  
|*ThisElementCanBeIgnored*|Un elemento que se puede omitir si [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] las implementaciones de procesadores, si no se puede resolver el tipo subyacente.|  
|*[content]*|*ThisElementCanBeIgnored* está marcado como ignorable. Si el procesador omite ese elemento, *[contenido]* procesa *objeto*.|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador pasará por alto el contenido dentro de un elemento omitido. Puede especificar un elemento específico por `mc:ProcessContent`y un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador seguirá procesando el contenido dentro del elemento omitido. Esto normalmente se usaría si el contenido está anidado dentro de varias etiquetas, al menos uno de los cuales se puede pasar por alto y al menos uno de los cuales no es puede pasar por alto.  
  
 Se pueden especificar varios prefijos en el atributo, con un espacio como separador, por ejemplo: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 El [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] espacio de nombres define otros elementos y atributos que no están documentados en esta área de la [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Para obtener más información, consulte [especificación de compatibilidad de marcado XML](https://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Vea también

- [mc:Ignorable (atributo)](mc-ignorable-attribute.md)
- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
