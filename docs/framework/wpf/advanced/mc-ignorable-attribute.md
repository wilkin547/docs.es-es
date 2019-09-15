---
title: Atributo mc:Ignorable
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: a72b2886c63a80a4887aa16fc6a952fa837a800f
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991443"
---
# <a name="mcignorable-attribute"></a>Atributo mc:Ignorable
Especifica qué [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefijos de espacio de nombres que se encuentran en un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de marcado puede ser omitido por un procesador. El `mc:Ignorable` atributo admite la compatibilidad de marcado para la asignación de espacio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de nombres personalizada y para el control de versiones.  
  
## <a name="xaml-attribute-usage-single-prefix"></a>Uso de atributos XAML (prefijo único)  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>Uso de atributos XAML (dos prefijos)  
  
```xaml  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|*ignorablePrefix, ignorablePrefix1, etc.*|Cualquier cadena de prefijo válida, según la especificación de XML 1,0.|  
|*ignorableUri*|Cualquier URI válido para designar un espacio de nombres, según la especificación de XML 1,0.|  
|*ThisElementCanBeIgnored*|Un elemento que las implementaciones de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] procesador pueden omitir, si no se puede resolver el tipo subyacente.|  
  
## <a name="remarks"></a>Comentarios  
 El `mc` [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] `http://schemas.openxmlformats.org/markup-compatibility/2006`prefijo de espacio de nombres es la Convención de prefijo recomendada que se va a usar al asignar el espacio de nombres de compatibilidad. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]  
  
 Los elementos o atributos en los que la parte del prefijo del nombre `mc:Ignorable` del elemento se identifican como no producirán errores cuando los procese un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador. Si ese atributo no se pudo resolver en un tipo o una construcción de programación subyacentes, se omite ese elemento. Tenga en cuenta, sin embargo, que los elementos omitidos todavía pueden generar errores de análisis adicionales para requisitos de elementos adicionales que son efectos secundarios de ese elemento que no se están procesando. Por ejemplo, un modelo de contenido de elemento determinado podría requerir exactamente un elemento secundario, pero si el elemento secundario especificado estaba `mc:Ignorable` en un prefijo, y el elemento secundario especificado no se pudo resolver en un tipo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , entonces el procesador podría producir un error.  
  
 `mc:Ignorable`solo se aplica a las asignaciones de espacio de nombres a cadenas de identificador. `mc:Ignorable`no se aplica a las asignaciones de espacio de nombres a los ensamblados, que especifican un espacio de nombres CLR y un ensamblado (o el valor predeterminado para el ejecutable actual como el ensamblado).  
  
 Si está implementando un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador, la implementación del procesador no debe generar errores de análisis o procesamiento en la resolución de tipos para cualquier elemento o atributo calificado con un prefijo identificado `mc:Ignorable`como. Pero la implementación del procesador todavía puede producir excepciones que son un resultado secundario de un elemento que no se carga o se procesa, como el ejemplo de elemento One-Child proporcionado anteriormente.  
  
 De forma predeterminada, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un procesador pasará por alto el contenido dentro de un elemento omitido. Sin embargo, puede especificar un atributo adicional, [MC: ProcessContent](mc-processcontent-attribute.md), para requerir el procesamiento continuado de contenido dentro de un elemento omitido por el siguiente elemento primario disponible.  
  
 Se pueden especificar varios prefijos en el atributo, utilizando uno o más caracteres de espacio en blanco como separador, por `mc:Ignorable="ignore1 ignore2"`ejemplo:.  

 El `http://schemas.openxmlformats.org/markup-compatibility/2006` espacio de nombres define otros elementos y atributos que no están documentados en esta área del SDK. Para obtener más información, vea [especificación de compatibilidad de marcado XML](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Markup.XamlReader>
- [PresentationOptions:Freeze (Atributo)](presentationoptions-freeze-attribute.md)
- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [Documentos en WPF](documents-in-wpf.md)
