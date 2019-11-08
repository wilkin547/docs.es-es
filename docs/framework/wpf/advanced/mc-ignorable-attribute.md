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
ms.openlocfilehash: e14ab0ebc7d44e2792307b16c7c0581ff7a71bc6
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740828"
---
# <a name="mcignorable-attribute"></a>Atributo mc:Ignorable
Especifica los prefijos de espacios de nombres XML que se encuentran en un archivo de marcado que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] puede omitir. El atributo `mc:Ignorable` admite la compatibilidad de marcado para la asignación de espacios de nombres personalizados y para el control de versiones de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
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
|*ThisElementCanBeIgnored*|Un elemento que puede ser omitido por implementaciones de procesador [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], si no se puede resolver el tipo subyacente.|  
  
## <a name="remarks"></a>Comentarios  
 El prefijo de espacio de nombres XML `mc` es la Convención de prefijo recomendada que se debe usar al asignar el espacio de nombres `http://schemas.openxmlformats.org/markup-compatibility/2006`[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Compatibility.  
  
 Los elementos o atributos en los que la parte del prefijo del nombre del elemento se identifican como `mc:Ignorable` no producirán errores cuando los procese un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Si ese atributo no se pudo resolver en un tipo o una construcción de programación subyacentes, se omite ese elemento. Tenga en cuenta, sin embargo, que los elementos omitidos todavía pueden generar errores de análisis adicionales para requisitos de elementos adicionales que son efectos secundarios de ese elemento que no se están procesando. Por ejemplo, un modelo de contenido de elemento determinado podría requerir exactamente un elemento secundario, pero si el elemento secundario especificado estuviera en un prefijo de `mc:Ignorable`, y el elemento secundario especificado no se pudo resolver en un tipo, el procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] podría producir un error.  
  
 `mc:Ignorable` solo se aplica a las asignaciones de espacio de nombres a cadenas de identificador. `mc:Ignorable` no se aplica a las asignaciones de espacio de nombres a los ensamblados, que especifican un espacio de nombres CLR y un ensamblado (o el valor predeterminado para el ejecutable actual como ensamblado).  
  
 Si va a implementar un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], la implementación del procesador no debe generar errores de análisis o procesamiento en la resolución de tipos para cualquier elemento o atributo calificado con un prefijo identificado como `mc:Ignorable`. Pero la implementación del procesador todavía puede producir excepciones que son un resultado secundario de un elemento que no se carga o se procesa, como el ejemplo de elemento One-Child proporcionado anteriormente.  
  
 De forma predeterminada, un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] omitirá el contenido dentro de un elemento omitido. Sin embargo, puede especificar un atributo adicional, [MC: ProcessContent](mc-processcontent-attribute.md), para requerir el procesamiento continuado de contenido dentro de un elemento omitido por el siguiente elemento primario disponible.  
  
 Se pueden especificar varios prefijos en el atributo, utilizando uno o más caracteres de espacio en blanco como separador, por ejemplo: `mc:Ignorable="ignore1 ignore2"`.  

 El espacio de nombres `http://schemas.openxmlformats.org/markup-compatibility/2006` define otros elementos y atributos que no están documentados en esta área del SDK. Para obtener más información, vea [especificación de compatibilidad de marcado XML](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Markup.XamlReader>
- [PresentationOptions:Freeze (Atributo)](presentationoptions-freeze-attribute.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Documentos en WPF](documents-in-wpf.md)
