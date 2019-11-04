---
title: Estilos y plantillas insertados
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b88ef444283f4e1e85009c59b39f3cc41965d300
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460008"
---
# <a name="inline-styles-and-templates"></a>Estilos y plantillas insertados
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona <xref:System.Windows.Style> objetos y objetos de plantilla (subclases<xref:System.Windows.FrameworkTemplate>) como una manera de definir la apariencia visual de un elemento en los recursos, de modo que se puedan usar varias veces. Por esta razón, los atributos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que toman los tipos <xref:System.Windows.Style> y <xref:System.Windows.FrameworkTemplate> casi siempre hacen referencias de recursos a estilos y plantillas existentes en lugar de definir nuevas en línea.  
  
## <a name="limitations-of-inline-styles-and-templates"></a>Limitaciones de las plantillas y los estilos en línea  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], las propiedades de estilo y de plantilla se pueden establecer técnicamente de una de estas dos maneras. Puede usar la sintaxis de atributo para hacer referencia a un estilo definido en un recurso, por ejemplo `<`*objeto*`Style="{StaticResource`*myResourceKey*`}" .../>`. O bien, puede usar la sintaxis de elementos de propiedad para definir un estilo insertado, por ejemplo:  
  
 `<` *objeto* `>`  
  
 `<` *objeto* `.Style>`  
  
 `<` `Style``.../>`  
  
 `</` *objeto* `.Style>`  
  
 `</` *objeto* `>`  
  
 El uso de atributos es mucho más común. Un estilo que se define en línea y no se define en los recursos tiene que tener el ámbito del elemento contenedor únicamente y no se puede volver a usar tan fácilmente porque no tiene ninguna clave de recurso. En general, un estilo definido por recursos es más versátil y útil, y se mantiene más en consonancia con el principio del modelo de programación de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] general de separar la lógica del programa en el código del diseño en el marcado.  
  
 Por lo general, no hay ninguna razón para establecer un estilo o una plantilla en línea, incluso si solo tiene previsto usar ese estilo o plantilla en esa ubicación. La mayoría de los elementos que pueden tomar un estilo o una plantilla también admiten una propiedad de contenido y un modelo de contenido. Si solo usa el árbol lógico que crea a través de estilos o plantillas una vez, es incluso más fácil rellenar esa propiedad de contenido con los elementos secundarios equivalentes en el marcado directo. Esto omitiría por completo los mecanismos de estilo y de plantilla.  
  
 Otras sintaxis habilitadas por las extensiones de marcado que devuelven un objeto también son posibles para los estilos y las plantillas. Dos de estas extensiones que tienen posibles escenarios son [TemplateBinding](templatebinding-markup-extension.md) y <xref:System.Windows.Data.Binding>.  
  
## <a name="see-also"></a>Vea también

- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
