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
ms.openlocfilehash: 25f5fb254ec6f952d7cafa2cb893e35daa0e9029
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573941"
---
# <a name="mcignorable-attribute"></a>Atributo mc:Ignorable
Especifica qué [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefijos de espacios de nombres que se encuentre en un archivo de marcado pueden ser omitidos por un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador. El `mc:Ignorable` atributo admite la compatibilidad de marcado para la asignación de espacio de nombres personalizado tanto para [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] control de versiones.  
  
## <a name="xaml-attribute-usage-single-prefix"></a>Uso de atributos XAML (un solo prefijo)  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>Uso de atributos XAML (dos prefijos)  
  
```  
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
|*ignorablePrefix, ignorablePrefix1, etc.*|Cualquier cadena de prefijo válido, según la especificación XML 1.0.|  
|*ignorableUri*|Cualquier URI válido para designar un espacio de nombres, según la especificación XML 1.0.|  
|*ThisElementCanBeIgnored*|Un elemento que se puede omitir si [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] las implementaciones de procesadores, si no se puede resolver el tipo subyacente.|  
  
## <a name="remarks"></a>Comentarios  
 El `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefijo de espacio de nombres es la convención de prefijo recomendado para usar al asignar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] espacio de nombres de compatibilidad [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].  
  
 Los elementos o atributos donde se identifican la parte del prefijo del nombre del elemento como `mc:Ignorable` no provocará errores cuando se procesa mediante un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador. Si no se pudo resolver en un tipo subyacente o la construcción de programación ese atributo, se omite ese elemento. Sin embargo, tenga en cuenta que los elementos omitidos pueden generar errores de análisis adicionales para los requisitos de elemento adicionales que son los efectos secundarios de ese elemento no se está procesando. Por ejemplo, un modelo de contenido del elemento en particular podría requerir exactamente un elemento secundario, pero si el elemento secundario especificado estaba en un `mc:Ignorable` prefijo y el elemento secundario especificado no se pueden resolver a un tipo, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] podría de procesador se producirá un error.  
  
 `mc:Ignorable` solo se aplica a las asignaciones de espacio de nombres a las cadenas de identificador. `mc:Ignorable` no se aplica a las asignaciones de espacio de nombres en los ensamblados, especifiquen un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] espacio de nombres y un ensamblado (o predeterminada para el ejecutable que el ensamblado actual).  
  
 Si está implementando un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador, la implementación del procesador no debe generar análisis o errores de procesamiento de resolución de tipos para cualquier elemento o atributo que se califica con un prefijo que se identifica como `mc:Ignorable`. Pero la implementación de procesador puede producir excepciones que son el resultado secundario de un elemento no se puede cargar o procesar, como en el ejemplo de un solo elemento secundario proporcionado anteriormente.  
  
 De forma predeterminada, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador pasará por alto el contenido dentro de un elemento omitido. Sin embargo, puede especificar un atributo adicional, [atributo ProcessContent](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), para exigir el procesamiento continuado de contenido dentro de un elemento omitido por el siguiente elemento primario disponible.  
  
 Se pueden especificar varios prefijos en el atributo, con uno o varios caracteres de espacio en blanco como separador, por ejemplo: `mc:Ignorable="ignore1 ignore2"`.  

 El [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] espacio de nombres define otros elementos y atributos que no están documentados en esta área de la [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Para obtener más información, consulte [especificación de compatibilidad de marcado XML](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Markup.XamlReader>
- [PresentationOptions:Freeze (Atributo)](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
- [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
