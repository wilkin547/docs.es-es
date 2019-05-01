---
title: Estilos y plantillas insertados
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b566e157e2d4a9e9be21a678541bf5d5341a898c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051018"
---
# <a name="inline-styles-and-templates"></a>Estilos y plantillas insertados
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona <xref:System.Windows.Style> objetos y objetos de plantilla (<xref:System.Windows.FrameworkTemplate> subclases) como una forma de definir la apariencia visual de un elemento en los recursos, por lo que puede utilizarse varias veces. Por este motivo, los atributos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que toman los tipos <xref:System.Windows.Style> y <xref:System.Windows.FrameworkTemplate> casi siempre que las referencias de recursos en plantillas y estilos existentes en lugar de definir nuevos en línea.  
  
## <a name="limitations-of-inline-styles-and-templates"></a>Limitaciones de plantillas y estilos en línea  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], técnicamente se pueden establecer propiedades de estilo y plantilla de dos maneras. Puede usar la sintaxis de atributo para hacer referencia a un estilo que se ha definido dentro de un recurso, por ejemplo `<` *objeto*`Style="{StaticResource`*myResourceKey*`}" .../>`. O bien, puede usar la sintaxis de elemento de propiedad para definir un estilo en línea, por ejemplo:  
  
 `<` *object* `>`  
  
 `<` *object* `.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</` *object* `.Style>`  
  
 `</` *object* `>`  
  
 El uso de atributos es mucho más común. Un estilo que se definen en línea y no está definido en los recursos se limita necesariamente a solo el elemento contenedor y no se puede volver a utilizar fácilmente porque no tiene ninguna clave de recurso. En general es más versátil y útil un estilo definido por los recursos y es más en consonancia con el general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] principio del modelo de separar la lógica del programa en el código de diseño en el marcado de programación.  
  
 Normalmente, no hay ninguna razón para establecer un estilo o una plantilla insertada, incluso si solo piensa usar ese estilo o plantilla en esa ubicación. La mayoría de los elementos que pueden tomar un estilo o plantilla también admiten una propiedad de contenido y un modelo de contenido. Si solo usa el árbol lógico cree mediante estilos o plantillas, una vez, es incluso más fácil rellenar esa propiedad de contenido con los elementos secundarios equivalentes en el marcado directo. Los mecanismos de estilo y plantilla Esto podría omitir por completo.  
  
 Otras sintaxis habilitadas por las extensiones de marcado que devuelven un objeto también son posibles para los estilos y plantillas. Dos de estas extensiones que tienen los posibles escenarios incluyen [TemplateBinding](templatebinding-markup-extension.md) y <xref:System.Windows.Data.Binding>.  
  
## <a name="see-also"></a>Vea también

- [Aplicar estilos y plantillas](../controls/styling-and-templating.md)
