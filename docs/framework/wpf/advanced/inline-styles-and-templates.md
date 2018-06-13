---
title: Estilos y plantillas insertados
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: 9c06f61bce1e17770fa0a9b9ed7a0e20625a79ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545894"
---
# <a name="inline-styles-and-templates"></a>Estilos y plantillas insertados
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona <xref:System.Windows.Style> objetos y objetos de plantilla (<xref:System.Windows.FrameworkTemplate> subclases) como una manera de definir la apariencia visual de un elemento en recursos, por lo que se pueden usar varias veces. Por esta razón, los atributos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que tenga los tipos <xref:System.Windows.Style> y <xref:System.Windows.FrameworkTemplate> casi siempre realizan referencias de recursos existentes estilos y plantillas, en lugar de definir otros nuevos insertados.  
  
## <a name="limitations-of-inline-styles-and-templates"></a>Limitaciones de plantillas y estilos en línea  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], propiedades de estilo y plantilla técnicamente pueden establecerse en uno de dos maneras. Puede usar la sintaxis de atributo para hacer referencia a un estilo que se ha definido dentro de un recurso, por ejemplo `<` *objeto*`Style="{StaticResource`*myResourceKey*`}" .../>`. O bien, puede usar sintaxis de elemento de propiedad para definir un estilo en línea, por ejemplo:  
  
 `<` *Objeto* `>`  
  
 `<` *Objeto* `.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</` *Objeto* `.Style>`  
  
 `</` *Objeto* `>`  
  
 El uso de atributos es mucho más común. Un estilo que se define en línea y recursos no está definidos en necesariamente ámbito es solo el elemento que lo contiene y no se puede volver a usar fácilmente porque no tiene ninguna clave de recurso. Por lo general un estilo definido por el recurso es más versátil y útil y es más en consonancia con la ficha general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] principio de modelo de separar la lógica del programa en el código de diseño en el marcado de programación.  
  
 Normalmente no hay ninguna razón para establecer un estilo o una plantilla insertados, incluso si solo desea usar ese estilo o una plantilla en esa ubicación. Mayoría de los elementos que puede llevar a cabo un estilo o una plantilla también admite una propiedad de contenido y un modelo de contenido. Si solo usa el árbol lógico cree mediante estilos o plantillas una vez, sea incluso más fácil rellenar esa propiedad de contenido con los elementos secundarios equivalentes en el marcado directo. Los mecanismos de estilo y plantilla Esto podría omitir por completo.  
  
 Otras sintaxis habilitadas por las extensiones de marcado que devuelven un objeto también son posibles para los estilos y plantillas. Dos de estas extensiones que tienen los posibles escenarios incluyen [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) y <xref:System.Windows.Data.Binding>.  
  
## <a name="see-also"></a>Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)
