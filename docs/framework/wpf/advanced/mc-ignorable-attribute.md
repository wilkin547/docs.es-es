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
ms.openlocfilehash: 7b8a2ef6e27bc6b25776157e59bef04b883fcb1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546203"
---
# <a name="mcignorable-attribute"></a>Atributo mc:Ignorable
Especifica qué [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefijos de espacio de nombres que se encuentran en un archivo de marcado pueden omitir un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador. El `mc:Ignorable` atributo admite la compatibilidad de marcado para la asignación de espacio de nombres personalizado y para [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] control de versiones.  
  
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
|*ignorablePrefix, ignorablePrefix1, etcetera.*|Cualquier cadena de prefijo, según la especificación XML 1.0.|  
|*ignorableUri*|Cualquier URI válido para designar un espacio de nombres, según la especificación XML 1.0.|  
|*ThisElementCanBeIgnored*|Un elemento que se puede omitir si [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] las implementaciones del procesador, si no se puede resolver el tipo subyacente.|  
  
## <a name="remarks"></a>Comentarios  
 El `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefijo de espacio de nombres es la convención de prefijo recomendado que se usará al asignar la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] espacio de nombres de compatibilidad [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].  
  
 Elementos o atributos en la parte de prefijo del nombre del elemento se identifican como `mc:Ignorable` no genera errores cuando se procesa mediante un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador. Si ese atributo no se puede resolver a un tipo subyacente o la construcción de programación, se omite ese elemento. Sin embargo, tenga en cuenta que los elementos omitidos pueden generar errores de análisis adicionales para los requisitos de elemento adicionales que son efectos secundarios de ese elemento no se están procesando. Por ejemplo, un modelo de contenido de elemento en particular podría necesitar exactamente un elemento secundario, pero si el elemento secundario especificado estaba en un `mc:Ignorable` prefijo y el elemento secundario especificado no se pueden resolver a un tipo, la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] posible que el procesador se producirá un error.  
  
 `mc:Ignorable` solo se aplica a las asignaciones de espacio de nombres a las cadenas de identificador. `mc:Ignorable` no se aplica a las asignaciones de espacio de nombres en los ensamblados, especifiquen un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] espacio de nombres y un ensamblado (o valor predeterminado para el archivo ejecutable actual que el ensamblado).  
  
 Si está implementando un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador, la implementación de procesador no debe generar análisis ni el procesamiento de errores en la resolución de tipo para cualquier elemento o atributo que se califica con un prefijo que se identifica como `mc:Ignorable`. Pero la implementación de procesador puede producir excepciones que sean el efecto secundario de un elemento de un error de carga o se procesarán, tales como el ejemplo de un solo elemento secundario proporcionado anteriormente.  
  
 De forma predeterminada, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador omitirá el contenido incluido en un elemento omitido. Sin embargo, puede especificar un atributo adicional, [ProcessContent atributo](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), para exigir el procesamiento continuado de contenido dentro de un elemento omitido por el siguiente elemento primario disponible.  
  
 Se pueden especificar varios prefijos en el atributo, con uno o más caracteres de espacio en blanco como separador, por ejemplo: `mc:Ignorable="ignore1 ignore2"`.  
  
 El [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] espacio de nombres define otros elementos y atributos que no están documentados en esta área de la [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Para obtener más información, consulte [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Markup.XamlReader>  
 [PresentationOptions:Freeze (Atributo)](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
