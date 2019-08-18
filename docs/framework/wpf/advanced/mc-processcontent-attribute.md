---
title: mc:ProcessContent (Atributo)
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: bc406659bec3fd8d5da87b597356a3411c7a2605
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567402"
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent (Atributo)
Especifica los [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementos que deben seguir teniendo el contenido procesado por los elementos primarios pertinentes, incluso si un procesador puede omitir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] el elemento primario inmediato debido a la especificación de un [atributo MC: ignorable](mc-ignorable-attribute.md). El `mc:ProcessContent` atributo admite la compatibilidad de marcado para la asignación de espacio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de nombres personalizada y para el control de versiones.  
  
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
|*ignorablePrefix*|Cualquier cadena de prefijo válida, según la especificación de XML 1,0.|  
|*ignorableUri*|Cualquier URI válido para designar un espacio de nombres, según la especificación de XML 1,0.|  
|*ThisElementCanBeIgnored*|Un elemento que las implementaciones de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] procesador pueden omitir, si no se puede resolver el tipo subyacente.|  
|*[content]*|*ThisElementCanBeIgnored* está marcado como ignorable. Si el procesador omite ese elemento, el *objeto*procesa *[Content]* .|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un procesador pasará por alto el contenido dentro de un elemento omitido. Puede especificar un elemento específico por `mc:ProcessContent`y un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador continuará procesando el contenido dentro del elemento omitido. Esto se suele usar si el contenido está anidado en varias etiquetas, al menos uno de los cuales es ignorable y, al menos, uno de los cuales no se puede omitir.  
  
 Se pueden especificar varios prefijos en el atributo, mediante un separador de espacio, `mc:ProcessContent="ignore:Element1 ignore:Element2"`por ejemplo:.  
  
 El [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] espacio de nombres define otros elementos y atributos que no están documentados en esta área del SDK. Para obtener más información, vea [especificación de compatibilidad de marcado XML](https://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Vea también

- [mc:Ignorable (atributo)](mc-ignorable-attribute.md)
- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
